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
4 branchに書き込んでみた

```
C:\Users\ra123\github\gittest>git add gitについて.md

C:\Users\ra123\github\gittest>git commit -m "mdを追加"
[testbranch e0cb867] mdを追加
 1 file changed, 69 insertions(+)
 create mode 100644 "git\343\201\253\343\201\244\343\201\204\343\201\246.md"

C:\Users\ra123\github\gittest>git push origin testbranch
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1002 bytes | 1002.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'testbranch' on GitHub by visiting:
remote:      https://github.com/Smasui0302/FiistGit/pull/new/testbranch
remote:
To https://github.com/Smasui0302/FiistGit.git
 * [new branch]      testbranch -> testbranch
 ```

 5 mergeする
 ```
 C:\Users\ra123\github\gittest>git checkout master
Switched to branch 'master'

C:\Users\ra123\github\gittest>git merge testbranch
Updating 6ccc97f..e0cb867
Fast-forward
 ...201\253\343\201\244\343\201\204\343\201\246.md" | 69 ++++++++++++++++++++++
 1 file changed, 69 insertions(+)
 create mode 100644 "git\343\201\253\343\201\244\343\201\204\343\201\246.md"

C:\Users\ra123\github\gittest>git push origin master
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/Smasui0302/FiistGit.git
   6ccc97f..e0cb867  master -> master
```

まとめると

1）新しいブランチを作る
$ git branch ブランチ名

2）今あるブランチを確認する
$ git branch

3）ブランチを移動する
$ git checkout ブランチ名

4）ブランチを結合（マージ）する
※$ git checkoutで，結合したいブランチに移動して…
$ git merge 取り込むブランチ名
