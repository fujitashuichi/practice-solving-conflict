<h1>Practice Solving Conflict</h1>

## 概要
リモートでファイル編集した際のコンフリクト解消の手順

---

## 目次
- [コンフリクト解消手順](#コンフリクト解消手順)
  - [コンフリクトの発生](#コンフリクトの発生)
  - [ローカルとリモートを統合する](#ローカルとリモートを統合する)
- [gitコマンド](#gitコマンド)
  - [git clone](#git-clone)
  - [3つの基本操作](#3つの基本操作)
  - [git add](#git-add)
  - [git commit](#git-commit)
  - [git push](#git-push)

---

# <a id="コンフリクト解消手順" style="color: #000; border:">コンフリクト解消手順</a>

## コンフリクトの発生
* **リモートでファイルを編集**
  * ブラウザ上のgithubで README を編集した。
  * 次に、ローカルでファイルを編集し、プッシュしようとした。[プッシュの手順](#3つの基本操作)
  * エラー発生！
    ```
    ! [rejected]        main -> main (fetch first)
    error: failed to push some refs to 'https://github.com/fujitashuichi/practice-solving-conflict.git'
    hint: Updates were rejected because the remote contains work that you do
    hint: not have locally. This is usually caused by another   repository pushing
    hint: to the same ref. You may want to first integrate the     remote changes
    hint: (e.g., 'git pull ...') before pushing again.
    hint: See the 'Note about fast-forwards' in 'git push --help'   for details.
    ```

## ローカルとリモートを統合する
* リモートから変更の履歴をとってくる。
  * ```git fetch ```
* リモートの変更をローカルにマージする。
  * ```git merge```
  *


---

# <a id="gitコマンド" style="color: #000;">gitコマンド</a>

## <a id="git-clone">git clone</a>
```git clone <url> ```
* **リモート**（ネット上）のリポジトリを **ローカル**（自分のパソコン上）にコピーする操作。
* 単にコピーするだけでなく接続の設定なども自動で行われる。

## 3つの基本操作
以下の3つのコマンドは、gitの基本操作である。
プッシュするときはこの3つのコマンドをセットで使う。

## <a id="git-add">git add</a>
```git add <files>```
* 例: ```git add *```, ```git add index.html```
* ファイルをgitの **インデックス** に追加する操作。（ステージング）
* **インデックス**: "コミット" したいファイルだけを一時保存する部屋。
* これをしないと、変更の保存ができない。

## <a id="git-commit">git commit</a>
```git commit -m "<message>"```
* 例: ```git commit -m "Fix: ページリンクのずれを修正"```
* "git add" されたファイルのみ、変更を**ローカルに**保存する。
* これをしないと、変更をリモートに保存しようとしても、ローカルにすら保存されていないことになってしまう。また、履歴の管理に影響を及ぼしたりする。


## <a id="git-push">git push</a>
```git push <リモートのブランチ>　<ローカルのブランチ>```
* 例: ```git push origin main``` ```git push origin/html main```<br> ※origin: デフォルトのリモートブランチ
* "git commit" されたファイルのみ、変更を**リモートに**保存する。
