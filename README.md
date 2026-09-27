# Data for OpenCHJ

[国立国語研究所](https://www.ninjal.ac.jp/)の[コーパス検索アプリケーション「中納言」](https://chunagon.ninjal.ac.jp/)で公開しているコーパス[「オープンCHJ」](https://chunagon.ninjal.ac.jp/open-chj/)のもととなっているデータのうち[@togiso](https://github.com/togiso)が関与したものの一部をここで公開しています。

- [源氏物語（渋谷栄一版）](https://github.com/togiso/OpenCHJ-Genji)
- [青空文庫（国語教科書所収作品など19作品）](https://github.com/togiso/OpenCHJ-Aozora)
- [速記叢書講談演説集](https://github.com/togiso/OpenCHJ-Sokkikoudan)
- [国定理科教科書](https://github.com/togiso/OpenCHJ-KokuteiRikaTextbooks)

オープンCHJについては[OpenCHJ Project](https://openchj.github.io/)のページをご覧ください。

## データ一覧

| リポジトリ | 内容 | 規模 | データ形式 | 解析辞書 | 形態論情報ライセンス | 公開・更新 |
|---|---|---|---|---|---|---|
| [OpenCHJ-Genji](https://github.com/togiso/OpenCHJ-Genji) | 源氏物語 全54帖 | 230ファイル／約54万語 | 形態論情報（TSV） | [中古和文UniDic](https://clrd.ninjal.ac.jp/unidic/download_all.html#unidic_wabun) | CC BY 4.0 | 2025/03 公開 |
| [OpenCHJ-Aozora](https://github.com/togiso/OpenCHJ-Aozora) | 青空文庫所収の近現代小説・詩 19作品 | 約8万語 | 形態論情報（TSV）、OpenCHJ XML（XHTML） | [UniDic](https://clrd.ninjal.ac.jp/unidic/) | CC BY 4.0 | 2025/03 公開、2026/05 13作品追加 |
| [OpenCHJ-Sokkikoudan](https://github.com/togiso/OpenCHJ-Sokkikoudan) | 『速記叢書講談演説集』 明治期の演説・講談 27編 | 約10万語 | 形態論情報（TSV） | [UniDic](https://clrd.ninjal.ac.jp/unidic/) | CC BY 4.0 | 2025/03 公開 |
| [OpenCHJ-KokuteiRikaTextbooks](https://github.com/togiso/OpenCHJ-KokuteiRikaTextbooks) | 『尋常小学理科書』（1910年 第5学年、1918年 第5・6学年）3冊 | 3ファイル | OpenCHJ XML（TEI） | ― | 未記載 | 2026/07 公開 |

語数は形態論情報ファイルの行数にもとづく概数です。

### 源氏物語（渋谷栄一版）
- 本文は渋谷栄一氏「[源氏物語の世界](http://www.sainet.or.jp/~eshibuya/index.html)」と、宮脇文経氏による再編集版（[XML版](https://www.genji-monogatari.net/)）にもとづきます。
- 「桐壺」巻以外は修正が十分ではありませんが、語彙素認定のレベルで概ね98～99％以上の精度です。
- 本文自体のライセンスは上記のオリジナルサイトを参照してください。

### 青空文庫
- `20250303/`：6作品（走れメロス、羅生門、高瀬舟、注文の多い料理店、山月記、トロッコ）。総合研究大学院大学の2024年度の授業「言語資源学演習1」で作成したものです。
- `20260531/`：13作品（名人伝、夢十夜、どんぐりと山猫、やまなし、よだかの星、〔雨ニモマケズ〕、ごん狐、手袋を買いに、檸檬、最後の一句、芋粥、鼻、夏の葬列）。国立国語研究所共同研究プロジェクト「開かれた共同開発環境による通時コーパスの拡張」の成果です。
- `XHTML_OCXmini/`：青空文庫のXHTMLに[OpenCHJ XML](https://openchj.github.io/ocx.html)（OCX mini）のタグを付けたファイルが5作品分あります。
- テキストのライセンスは[青空文庫の収録ファイルの取り扱い規準](https://www.aozora.gr.jp/guide/kijyunn.html)に従ってください。

### 速記叢書講談演説集
- 原テキストは国語研究所言語処理データ集『[速記叢書講談演説集](https://mmsrv.ninjal.ac.jp/lanpro/spokenlanguage2/)』です。

### 国定理科教科書
- [TEI](https://tei-c.org/)準拠のXMLに、OpenCHJ XMLに合わせた修正（ルビタグの変更、文境界 `ocx:eos` と文書ルート `ocx:doc` の付与など）を加えたものです。
- `ocx:doc` の範囲だけがOpenCHJの本文として形態論情報を付与され、「中納言」で検索できるようになります。
- 形態論情報のデータとライセンス表記は、まだリポジトリにありません。

## 形態論情報ファイルの共通形式

源氏物語・青空文庫・速記叢書講談演説集の形態論情報ファイルは、共通して次の形式です。

- UTF-8（BOMなし）、LF改行、タブ区切り
- フィールド（左から）
  1. ファイル名
  2. サブコーパス名
  3. 開始文字位置（ファイル先頭からのオフセット値×10）
  4. 終了文字位置（同上）
  5. 文境界（B=文頭）
  6. 書字形出現形（表層形）
  7. 語彙素
  8. 語彙素読み
  9. 品詞
  10. 活用型
  11. 活用形
  12. 発音形
  13. 語種
