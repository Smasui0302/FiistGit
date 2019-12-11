# gitについて勉強してみた

## 基本的な操作

1）ローカルリポジトリを作成する
$ git init

2）ローカルリポジトリにファイルの変更点を追加（インデックスに追加）
$ git add ファイル名

3）ローカルリポジトリにインデックスに追加したファイルを登録
$ git commit -m "変更点などのコメント"

4）追加したインデックス（ファイルの変更点など）をGitHubに作成
$ git remote add origin リポジトリのURI

5）ローカルリポジトリのファイルをGitHubのリポジトリに送信
$ git push origin master

## ファイルを更新する際

1）変更をインデックスに追加
$ git add test.txt

2）ファイルを登録（コミット）
$ git commit -m "変更してみたよ"

3）データの送信
$ git push origin master

## ブランチとマージ

-ブランチ  文字通り枝のこと

  バージョンなどを上げるときに失敗してもコピー

-マージ  結合するという意味

  複数に分岐したものをつなげる

### 実際にやる

1 branchをつくる

$ git branch branch名

2 今あるbranchを確認する

$git branch

```
C:\Users\ra123\github\gittest>git branch
* master
  
  testbranch
```

*がついているところにpushすると書き込まれる.

3 書き込む場所を変更する

```
C:\Users\ra123\github\gittest>git checkout testbranch
Switched to branch 'testbranch'

C:\Users\ra123\github\gittest>git branch
  master
* testbranch
```
