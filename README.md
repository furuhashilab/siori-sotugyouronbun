## 帰宅困難者を対象とした避難所位置情報オープン化の実践−目黒区を例として−
## 第1章
### 1.本研究について

世界で起こる大地震の20％は日本で起こっており、日本と災害は切り離せない存在となっている。甚大な被害を引き起こした2011年の東日本大震災時においては避難場所と避難所が区別されず混乱を招いた為、内閣府は平成25年に災害対策基本法（昭和36年法律第223号）を改正し、指定緊急避難場所と指定避難所を区別しなければならないこととした。又、指定緊急避難場所においては災害の種類ごとの指定をするように呼びかけており、各避難所の情報は住民に知らされなければならないとされている。
<b>現状では、避難所情報は地方自治体の公式サイト又は地理院地図 指定緊急避難場所情報、東京都防災マップ等から確認でできる。しかしそれぞれのウェブサイトによって地図表現が異なり、避難所マップ自体も行政区全域を表現する反面、各避難所への細かな道路が判読しづらく、ナビゲーション目的には適していない。そこで、本研究では誰もがアクセスが可能であり、更に足りない部分は自ら編集作業も行える草の根のオープンデータ地図プラットフォームOpenStreetMapにこれらの避難所情報を確認できるようにすべきだと考えた。対象地域については、東日本大震災時において帰宅困難者の受け入れについて問題が起きたとされる、東京都渋谷区及び隣接する目黒区とした。対象施設は主に帰宅困難者向けの建物が付随する避難所に限定し、本研究は目黒区を対象地域とした。

#### 災害避難所の定義
* 避難所：災害によって自宅で生活できない場合に生活をする場所
* 一時:災害が起きた時に次の行動を決めるためにまず集まる場所。
* 避難場所：一時集合場所も危険と判断された時、更に避難する場所。

### 2.

具体的なデータ作成手法として、政府標準利用規約に則り公開されている国土地理院の地理院地図 指定緊急避難場所の地図情報より避難所情報をリストアップし、既存のOpenStreetMap登録データと比較を行った結果の現状で避難所タグが入力されていないのを確認した。その後OpenStreetMapで避難所タグの種類を調査し、現時点ではemergency＝assembly_point タグが適当であると判断して避難場所と広域避難場所として該当するエリア及び建物にその情報を付加した。

```markdown


# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### results

結果として、まず避難所と避難場所に使用する emergency=assembly_pointのタグの解説を拡充するために日本語訳ページを作成し、目黒区内において未だOSMに入力されていない避難所情報を新規に57箇所入力した。隣接する渋谷区と目黒区との比較調査を通して、避難所や避難場所の定義は同じだが区ごとで分類方法が異なることも明らかになった。又OpenStreetMapにおける帰宅困難者支援施設に該当するタグのみが存在しなかった為、帰宅困難者支援施設のタグを考察しOpenStreetMap Wikiに新たなタグとして提案した。

## discussion
### 提案：帰宅困難者支援施設タグ

帰宅困難者支援施設の重要性は、2011年の東日本大震災において渋谷区民以外の大勢の人が帰宅困難者になった問題で明らかになった。この帰宅困難者が多くいて動けない状況を日本において重大な災害とみなし、避難所のタグであるemergency:assembly_pointにunable_to_move=yesを反映した。
帰宅困難者支援施設のタグemergency=assembly_point:unable_to_move=yesは今の状態では仮のタグとなっているので、正式なタグとするためOpenStreetMap Wikiの議論に載せた。検討が進んだ後に投票でタグが決定した後に正式な定義となるので、議論を進めて帰宅困難者支援施設を入力していくことがこれからの課題の一つである。

### 課題
のタグの公式地物としての認定に関する議論はこれから始まり、最終的には投票で正式に決定するので、そのためのタグ提案のプロセスを経ることが今後の課題である。避難所タグを災害ごとに分けること、避難所以外の災害支援施設の入力が未着手である。避難所と避難場所は日本では区別すべきとされているが、OpenStreetMapでは同じタグとして区別されていたのでどのように表現すべきか検討すべきである。本また研究によってOpenStreetMapの目黒地区における避難所と広域避難所の情報の入力が完了し、日本において重要性の高い帰宅困難者支援施設のタグを新たに提案することができた。

第1章の１に述べてあるように日本では指定緊急避難所と指定緊急避難場所の区別分けを推奨しているが、OpenStreetMapでは現状ではどちらもemergency=assembly_pointタグでまとめられている。ここで避難所と避難場所の定義の違いについて述べると、避難場所は

