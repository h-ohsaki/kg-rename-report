# NAME

kg-rename-report - LUNA で一括ダウンロードしたレポートのファイル名を正規化する

# DESCRIPTION

**kg-rename-report** は LUNA で一括ダウンロードしたレポートファイル
(assigmentDL-\*.zip ファイルに含まれるファイル) を採点しやすい名前に変更する
Python スクリプトです。

LUNA で一括ダウンロードしたレポートは、「学籍番号.txt」に学生の情報が、「学籍
番号-\*」というファイルに提出されたレポートの本体が格納されています。このプロ
グラムは、レポートファイルを一括して「report-学籍番号-ID-氏名.拡張子」という名
前に変更します※。

※ 本来は名前を変更 (リネーム) すべきですが、現在は安全のため元のファイルを残
したまま複製 (コピー) しています。不要な場合は元のファイルを手動で削除してくだ
さい。

例えば、一括ダウンロードしたレポートファイルが

- 20174567-実習課題ファイル(2).pdf
- 20174567-実習課題ファイル.pdf
- 20174567.txt
- 20179876-レポート課題3.jpg
- 20179876.txt

のようになっている場合に、**kg-rename-report** ですべてのファイルを選択すれば、
レポートファイルが

- report-20174567-xyz78901-関学 太郎-2.pdf
- report-20174567-xyz78901-関学 太郎-note.pdf
- report-20174567-xyz78901-関学 太郎.pdf
- report-20179876-abc12345-関学 花子.jpg

のような正規化されたファイル名でコピーされます。\*.txt ファイル中にコメントが
記録されている場合は、\*.txt ファイルもあわせてコピーされます。

# REQUIREMENTS

- Python 3
- perlcompat (https://pypi.org/project/perlcompat/)

## 実行ファイルを使用する場合

Linux (x64) または Windows 10 (x64) 向けの実行ファイルを使用する場合は Python
の実行環境等は不要です。

# INSTALLATION

```sh
pip3 install perlcompat
./kg-rename-report
```
## Linux (x64) または Windows 10 (x64) で実行ファイルを使用する場合

Linux (x64) および Windows 10 (x64) 用の実行ファイルを用意してあります。
PyInstaller で単一の実行ファイルに変換したものです。以下の実行ファイルをダウン
ロードして、そのまま (エクスプローラでダブルクリックする等して) 実行してくださ
い。

https://github.com/h-ohsaki/kg-rename-report/raw/master/linux-x64/kg-rename-report-1.4

https://github.com/h-ohsaki/kg-rename-report/raw/master/win10-x64/kg-rename-report-1.4.exe

# USAGE

実行すると変更するファイル名の先頭に付与する文字列を聞かれます。何も入力せずに
OK を選択すると「report」が使用されます。

続いてファイル選択ダイアログが開きますので、LUNA からダウンロードしたレポート
ファイル (JPEG ファイルや PDF ファイル等)を選択してください。複数のファイルを
選択することが可能です。余計なファイルは無視しますので、すべてのファイルを一括
して選択して構いません。

作業完了を知らせるダイアログ等は何も表示されませんが、レポートファイルと同じディ
レクトリに、「report-学籍番号-ID-氏名.拡張子」のような名前でレポートファイルが
コピーされています。

# AVAILABILITY

最新版の **kg-rename-report** は https://github.com/h-ohsaki/kg-rename-report
から入手できます。

# AUTHOR

Hiroyuki Ohsaki (ohsaki[atmark]lsnl.jp)
