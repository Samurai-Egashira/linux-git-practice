# 第22222222222回課題：Linux/CUI操作とGitHubでの課題提出

## 課題の目的

この課題では、LinuxのCUI環境でファイルやディレクトリを操作し、必要なデータを探して作業用ディレクトリへ整理します。

また、作業内容をGitで管理し、GitHubへPull Requestとして提出します。

---

## 課題の設定

社内サーバー上に保存されている売上データを使って、今後データ分析を行うことになりました。

プロジェクト内から対象となるCSVファイルを探し、分析用ディレクトリへ整理してください。

対象ファイルは以下です。

```text
sales_2026.csv
```

---

## 1. CSVファイルを探して分析用に整理する

Linuxコマンドを使って、プロジェクト内から`sales_2026.csv`を探してください。

見つけたファイルは、プロジェクト直下に作成した`analysis`ディレクトリへコピーします。

あわせて、以下も確認してください。

* 現在いるディレクトリ
* ファイル・ディレクトリの一覧
* `.` と `..` の意味
* 絶対パスと相対パス
* CSVファイルの中身
* CSV内の特定の文字列

必要に応じて、以下のコマンドを使用してください。

```text
pwd
ls
cd
find
mkdir
cp
cat
head
grep
```

---

## 2. ファイルの権限を確認する

コピーした`sales_2026.csv`のファイル権限を確認し、`644`へ変更してください。

そのうえで、以下について確認してください。

* owner / group / others とは何か
* `r` / `w` / `x` は何を表すか
* `644`はどのような権限なのか

必要に応じて以下を使用してください。

```text
ls -l
chmod
```

---

## 3. Linux環境について調べる

以下について、それぞれ1〜2行程度でREADME.mdに説明を書いてください。

* `sudo`とは何か
* `apt`とは何か
* `apt update`と`apt install`の違い
* `PATH`とは何か

PATHは次のコマンドでも確認できます。

```bash
echo $PATH
```

今回は`sudo`や`apt`を実際に使用する必要はありません。

---

## 4. GitHubで課題を提出する

作業が完了したら、Gitで変更内容を確認し、作業ブランチからGitHubへ提出してください。

以下の流れで行います。

```text
作業ブランチを作成
↓
変更内容を確認
↓
git add
↓
git commit
↓
git push
↓
GitHubでPull Requestを作成
```

使用する主なコマンドは以下です。

```text
git status
git switch -c
git add
git commit
git push
```

mainへ直接commit・pushせず、必ず作業ブランチを使用してください。

---

## README.mdに記載する内容

以下を簡潔に記載してください。

```text
## 作業結果

- sales_2026.csvを見つけた場所
- sales_2026.csvの絶対パス
- sales_2026.csvの相対パス
- chmod 644の意味
- sudoとは
- aptとは
- PATHとは
```

---

## 完成イメージ

```text
linux-git-practice/
├── README.md
├── analysis/
│   └── sales_2026.csv
├── data/
│   ├── backup/
│   │   └── sales_2025.csv
│   ├── old/
│   │   └── customer_old.csv
│   └── current/
│       ├── customers.csv
│       └── sales_2026.csv
├── docs/
│   └── memo.txt
└── logs/
    └── application.log
```

---

## この課題で確認すること

**必要なファイルを探す → 整理する → 状態を確認する → GitHubへ提出する**
という一連の操作についての確認問題します。

コマンドを暗記しているかの確認ではないので、
分からないコマンドはWeb検索や生成AIで調べても構いませんが、何をするコマンドなのか確認してから実行してください。

