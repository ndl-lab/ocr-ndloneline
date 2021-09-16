# ocr-ndloneline
パブリックドメイン資料から作成した1行単位の文字切り出し画像と対応テキストデータのデータセットです。


## 1.概要
国立国会図書館デジタルコレクション（以下「デジコレ」といいます。）<https://dl.ndl.go.jp>
からインターネット公開している著作権保護期間の満了したデジタル資料のうち、
活字資料について目次のコマの画像と目次情報を、1行毎に対応付けが取れるように加工してOCR等の学習用データセットとして整備したものです。
技術検討目的で館内で作成したデータセットとなります。

### 例
<table ~~~ style="table-layout:fixed;width:100%;">
<tbody>
<tr>
<td align="center" ~~~ style="word-wrap:break-word;">ファイル名</td><td align="center" ~~~ style="word-wrap:break-word;">画像</td><td align="center" ~~~ style="word-wrap:break-word;">正解テキストデータ</td>
</tr>
<tr>
<td align="center" ~~~ style="word-wrap:break-word;">1904210_0008_jzRAqe3gqxN.jpg</td><td align="center" ~~~ style="word-wrap:break-word;"><img alt="(四)「アスフアルトブロツク」鋪道上に「アスフアルト」層を造ること" src="https://www.dl.ndl.go.jp/api/iiif/1904210/R0000008/pct:23.0,20.0,1.1,40.2/,256/0/default.jpg" /></td><td align="center" ~~~ style="word-wrap:break-word;">(四)「アスフアルトブロツク」鋪道上に「アスフアルト」層を造ること</td>
</tr>
<tr>
<td align="center" ~~~ style="word-wrap:break-word;">770210_0020_z8onZXpKBn1.jpg</td><td align="center" ~~~ style="word-wrap:break-word;"><img alt="大岡越前守と石川近江守の抜擢" src="https://www.dl.ndl.go.jp/api/iiif/770210/R0000020/pct:59.6,22.0,1.4,19.3/,256/0/default.jpg" /></td><td align="center" ~~~ style="word-wrap:break-word;">大岡越前守と石川近江守の抜擢</td>
</tr>
</tbody>
</table>

## 2.データについて
画像についてはzipで圧縮されており、次のURLから取得可能です。

https://lab.ndl.go.jp/dataset/ocronelinedataset/ocronelinedataset_pdm.zip

2021年9月16日現在、2,339行分の正解データが含まれています。今後追加を行う予定です。

正解テキストデータは本リポジトリのlabeldata_pdm.tsvを参照してください。

## 正解データの形式について
各行タブ区切りに、左から「ファイル名」「正解テキストデータ」「文字列の向き(tateまたはyoko)」「切り出し画像のURL(フルサイズのIIIF Image API)」の情報が記載されています。

|ファイル名| 正解テキストデータ|文字列の向き |切り出し画像のURL|
----|----|----|---- 
1904210_0008_jzRAqe3gqxN.jpg | (四)「アスフアルトブロツク」鋪道上に「アスフアルト」層を造ること | tate | https://www.dl.ndl.go.jp/api/iiif/1904210/R0000008/pct:23.0,20.0,1.1,40.2/full/0/default.jpg

## 3.画像ファイルのディレクトリ構成について
縦書きの1行画像はoneline_tateディレクトリ、横書きの1行画像はoneline_yokoディレクトリに分かれて配置されています。
必要な解像度と異なる場合には、正解データのIIIF Image APIの仕様(https://iiif.io/api/image/2.1/#region
)に従って適宜サイズを調整して取得してください。


## 4.作成元資料の参照方法について


画像の命名規則は、デジコレの永続的識別子(PID)の数字部分を用いて、

(PID)_(コマ番号)_(ランダムなハッシュ値) .jpg

という形式で記述しています。 例えば1904210_0008_jzRAqe3gqxN.jpg は、
http://dl.ndl.go.jp/info:ndljp/pid/1904210 
のコマ番号3を意味します。

PIDと資料名の対応については、以下から提供している書誌データを参考にしてください。

https://www.ndl.go.jp/jp/dlib/standards/opendataset/index.html


## 本件に関する問い合わせ先
lab@ndl.go.jp

何かお気づきの点がありましたら、お気軽にお問い合わせください。

## その他
パブリックドメイン資料以外から作成した同様のデータセットが公開しているものに加えて7000行程度存在します。
調査研究用途等ご関心のある方はご相談ください。
