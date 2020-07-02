# NAME

kg-merge - Microsoft Forms の回答ファイルに学生の学籍番号を記入する

# DESCRIPTION

**kg-merge** は、XLSX 形式で保存された Microsoft Forms の回答ファイルに、回答
者の学籍番号を記入する Python スクリプトです。

Microsoft Forms では回答者の ID を記録することは可能なのですが、回答者の学籍番
号がわからないため採点等の時に不便です。**kg-merge** は回答者の学籍番号を記入
するためだけのプログラムです。

Microsoft Forms からダウンロードした XLSX 形式の「回答ファイル」の D 列に記録
されている回答者の ID (Microsoft 365 の ID) を学生名簿 (名簿ファイル) から探索
し、学生名簿に ID が存在すれば C 列に学籍番号を記入します。C 列 (もともとは回
答完了時刻が記録されています) を書き換えることに注意してください。書き換えられ
た回答ファイルは「\*-merged.xlsx」という別のファイルに保存されます (元の回答ファ
イルは変更されません)。名簿ファイルは LUNA (関西学院向けにカスタマイズされた
Blackboard)の「名簿ダウンロード」からダウンロードされた、タブ区切りのテキスト
ファイル (ただし拡張子は .XLS) を前提としています。

Microsoft Forms が書き出す回答ファイルの形式や LUNA が書き出す学生名簿の形式に
依存したプログラムになっています。ファイルの形式が変更になった場合は適宜プログ
ラムを書き換えてご利用ください。

# REQUIREMENTS

- Python 3
- openpyxl (https://pypi.org/project/openpyxl/)

## 実行ファイルを使用する場合

Linux (x64) または Windows 10 (x64) 向けの実行ファイルを使用する場合は Python
の実行環境等は不要です。

# INSTALLATION

```sh
pip3 install openpyxl
./kg-merge
```
## Linux (x64) または Windows 10 (x64) で実行ファイルを使用する場合

Linux (x64) および Windows 10 (x64) 用の実行ファイルを用意してあります。
PyInstaller で単一の実行ファイルに変換したものです。以下の実行ファイルをダウン
ロードして、そのまま (エクスプローラでダブルクリックする等して) 実行してくださ
い。

https://github.com/h-ohsaki/kg-merge/raw/master/linux-x64/kg-merge

https://github.com/h-ohsaki/kg-merge/raw/master/win10-x64/kg-merge.exe

# USAGE

実行するとファイル選択ダイアログが開きます。

1. LUNA からダウンロードした名簿ファイル (meibo-\*.xls) を選択してください。

2. 再度ファイル選択ダイアログが開きますので、Microsoft Forms からダウンロード
   した回答ファイル (\*.xlsx) を選択してください。

回答ファイルと同じディレクトリに \*-merged.xlsx という名前のファイルが作成され
ます。

# AVAILABILITY

最新版の **kg-merge** は https://github.com/h-ohsaki/kg-merge から入手できます。

# AUTHOR

Hiroyuki Ohsaki (ohsaki[atmark]lsnl.jp)
