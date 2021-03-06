# Github pull requestまでの流れ

#＃ 対象プロジェクトを fork する
対象のプロジェクトを Github のサイトで fork する。  

方法は、  
対象のプロジェクトの画面右上の _Fork_ ボタンをクリックする。
自分のプロジェクトとして、まぁコピーが作成される。

#＃ ローカルにクローンする

```shell
$ cd ~/github/
$ git clone https://github.com/yourAccount/angular-ja.git
```

## ブランチ(branch)を作成しブランチを切り替える

```shell
$ git checkout -b guide/dynamic-component-loader
```

### ファイルを編集する
翻訳を行う。  
一センテンス単位で、[Google翻訳](https://translate.google.co.jp/?hl=ja&authuser=0) で翻訳する。  
 自動翻訳を修正する。  

### コミット(commit)する

```shell
$ git commit -m "docs: translate to Japanese from English."
```

### プッシュ(push)する

```shell
$ git push origin guide/dynamic-component-loader
```

### upstream(Forkの元)の設定
通常Fork元の名称には *upstream* を付ける。

```shell
$ git remote add upstream https://github.com/angular/angular-ja.git
```

## pull request(PR, プルリク)

### master を更新

1. masterに変更
```shell
$ git checkout master
```

2. upstream　から pull して最新を取得
```shell
$ git pull upstream master
```

3. local の master を origin に push
```shell
$ git push origin master
```

4. branch を作業中のブランチに変更
```shell
$ git checkout guide/dynamic-component-loader
```

5. branch を rebase
```shell
$ git rebase master
```

6. branch を origin に push
```shell
$ git push -f origin guide/dynamic-component-loader
```

### Pull request の作成
Github で Fork した自分のリポジトリに行き、ブランチを切り換える。
右上の Pull Requestボタンを押す。
