# 模範解答・確認用

このファイルは、第1回課題の確認用リファレンスです。

> 実際の絶対パスやGitHubのブランチ名は、受講生の環境によって異なります。

## 1. CSVファイルを探して整理する

プロジェクト直下にいることを確認します。

```bash
pwd
ls -la
```

対象ファイルを検索します。

```bash
find . -name "sales_2026.csv"
```

想定結果：

```text
./data/current/sales_2026.csv
```

分析用ディレクトリを作成し、CSVをコピーします。

```bash
mkdir analysis
cp data/current/sales_2026.csv analysis/
ls -l analysis
```

CSVの先頭を確認します。

```bash
head analysis/sales_2026.csv
```

`Keyboard` を含む行を検索します。

```bash
grep "Keyboard" analysis/sales_2026.csv
```

### `.` と `..`

- `.`：現在のディレクトリ
- `..`：1つ上の親ディレクトリ

### 相対パス

プロジェクト直下から見た場合：

```text
analysis/sales_2026.csv
```

### 絶対パス

環境によって異なります。`pwd` の結果とファイル名を組み合わせて確認します。

例：

```text
/Users/username/work/linux-git-practice/analysis/sales_2026.csv
```

---

## 2. 権限を確認する

```bash
ls -l analysis/sales_2026.csv
chmod 644 analysis/sales_2026.csv
ls -l analysis/sales_2026.csv
```

`644` の意味：

- owner：読み取り・書き込み（6 = 4 + 2）
- group：読み取り（4）
- others：読み取り（4）

つまり、一般的には次の表示になります。

```text
-rw-r--r--
```

`r / w / x` は以下を意味します。

- `r`：read（読み取り）
- `w`：write（書き込み）
- `x`：execute（実行）

---

## 3. Linux環境について

### sudo

一時的に管理者権限でコマンドを実行するために使います。
必要のない操作まで `sudo` で実行すると、誤操作時の影響範囲が大きくなるため注意が必要です。

### apt

Debian / Ubuntu系Linuxでパッケージを管理するためのコマンドです。

```text
apt update
```

利用可能なパッケージ情報を更新します。

```text
apt install <パッケージ名>
```

指定したパッケージをインストールします。

### PATH

コマンドを実行するときに、OSが実行ファイルを探すディレクトリの一覧です。

確認例：

```bash
echo $PATH
```

---

## 4. Git / GitHub

作業ブランチを作成します。

```bash
git switch -c student/<name>
```

変更内容を確認します。

```bash
git status
```

追加・コミットします。

```bash
git add README.md analysis/sales_2026.csv
git commit -m "Linux/CUI課題の作業結果を追加"
```

GitHubへpushします。

```bash
git push -u origin student/<name>
```

その後、GitHub上で作業ブランチから `main` 向けのPull Requestを作成します。

---

## 最終的な確認ポイント

受講生の作業後は、少なくとも以下が追加・更新されていればOKです。

```text
linux-git-practice/
├── README.md            # 作業結果を追記
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
├── logs/
│   └── application.log
└── answer/
    └── README.md
```
