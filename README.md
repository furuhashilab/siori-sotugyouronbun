## 帰宅困難者を対象とした避難所位置情報オープン化の実践−目黒区を例として−
### 1.本研究について

世界で起こる大地震の20％は日本で起こっており、日本と災害は切り離せない存在となっている。甚大な被害を引き起こした2011年の東日本大震災時においては避難場所と避難所が区別されず混乱を招いた為、内閣府は平成25年に災害対策基本法（昭和36年法律第223号）を改正し、指定緊急避難場所と指定避難所を区別しなければならないこととした。又、災害の種類ごとの指定をするように呼びかけており、各避難所の情報は住民に知らされなければならないとされている。
<br>現状では、避難所情報は地方自治体の公式サイト又は地理院地図 指定緊急避難場所情報、東京都防災マップ等から確認でできる。しかしそれぞれのウェブサイトによって地図表現が異なり、避難所マップ自体も行政区全域を表現する反面、各避難所への細かな道路が判読しづらく、ナビゲーション目的には適していない。そこで、本研究では誰もがアクセスが可能であり、更に足りない部分は自ら編集作業も行える草の根のオープンデータ地図プラットフォーム[OpenStreetMap](https://openstreetmap.jp/map#zoom=6&lat=40.86368&lon=135.67017&layers=FB00F)にこれらの避難所情報を確認できるようにすべきだと考えた。対象地域については、東日本大震災時において帰宅困難者の受け入れについて問題が起きたとされる、東京都渋谷区及び隣接する目黒区とした。対象施設は主に帰宅困難者向けの建物が付随する避難所に限定し、本研究は目黒区を対象地域として目黒区役所に確認をとった後入力をした。

#### 共通の災害避難施設の定義
* 避難所：災害によって自宅で生活できない場合に生活をする場所
* 一時集合場所:災害が起きた時に次の行動を決めるためにまず集まる場所。
* 避難場所：一時集合場所も危険と判断された時、更に避難する場所。
#### 目黒区の避難所の分類
* 地域避難所:自宅に滞在が困難になった場合に避難する場所。
* 広域避難所:東京都が指定する大規模公園などのオープンスペースで、区内には8か所の広域避難場所があります。地域避難所に危険が迫りさらに避難が必要となった場合に広域避難場所に集団で避難をする。
* 補完避難所:住区センター、社会教育館等が指定されている。避難者が増加して地域避難所では受け入れきれない場合や生活が困難になった避難者を受け入れる場合に利用する。
* 福祉避難所:地域避難所での生活が困難な要介護高齢者や障害をもつ方のための、特別養護老人ホーム、福祉工房、高齢者センター等が含まれる。
今回地域避難所と広域避難所に限定した理由について帰宅困難者が発生した場合に重要となる点は、1)災害が起きた直後にまず避難する場所 2)更に帰宅が困難になった際に生活ができるかどうかの二つであると考えたので、二次避難に含まれる避難施設は含まなかった。

### 2.研究手法

1)データ収集
具体的なデータ作成手法として、政府標準利用規約に則り公開されている国土地理院の地理院地図 指定緊急避難場所の地図情報より避難所情報をリストアップし、既存のOpenStreetMap登録データと比較を行った結果の現状で避難所タグが入力されていないのを確認した。
![避難所情報が入力されていない状態。](https://github.com/furuhashilab/siori-sotugyouronbun/blob/image/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202019-01-09%2021.17.20.png)

2）OpenStreetMapタグの定義
現時点でのOpenStreetMapでの避難所として定義できるのは、避難小屋のタグ[amenity=shelter](https://wiki.openstreetmap.org/wiki/JA:Tag:amenity%3Dshelter),一時集合場所のタグ[social_facility=shelter](https://wiki.openstreetmap.org/wiki/JA:Tag:social_facility%3Dshelter),未翻訳だった[emergency=assembly_point](https://wiki.openstreetmap.org/wiki/Tag:emergency%3Dassembly_point)の三つであった。避難小屋は悪天候の際に避難ができる小さい小屋であるので、現時点ではemergency＝assembly_pointタグが指定緊急避難場所及び指定緊急避難所のタグとして適当であると判断し、避難所と広域避難所として該当するエリア及び建物にその情報を付加した。情報を付加する際にまずOpenStreetMap　Wikiのemergency=assembly_pointの[日本語翻訳ページ](https://wiki.openstreetmap.org/wiki/JA:Tag:emergency%3Dassembly_point)の作成に着手した。

### 3.成果

結果として、目黒区における避難所情報を新規に57箇所入力することができた。また隣接する渋谷区と目黒区との比較調査を通して、避難所や避難場所の定義は同じであっても区ごとで分類方法が異なることも明らかになった。例えば目黒区では避難所という区別しかなかったが、渋谷区は加えて避難場所、一時集合場所、帰宅困難者支援施設等とより細かく分類されている。更にOpenStreetMapにおける帰宅困難者支援施設に該当するタグのみが存在しなかった為、帰宅困難者支援施設のタグを考察しOpenStreetMap Wikiに新たなタグとして提案することができた。
![避難所情報入力後](https://github.com/furuhashilab/siori-sotugyouronbun/blob/master/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202019-01-08%2020.08.38.png)


### 4.課題
#### 提案：帰宅困難者支援施設タグ

帰宅困難者支援施設の重要性は、2011年の東日本大震災において渋谷区民以外の大勢の人が帰宅困難者になった問題で明らかになった。この帰宅困難者が多くいて動けない状況を日本において重大な災害とみなし、避難所のタグであるemergency:assembly_pointにunable_to_move=yesを反映した。
帰宅困難者支援施設のタグemergency=assembly_point:unable_to_move=yesは今の状態では仮のタグとなっているので、公式地物としての認定に関する議論はこれから始まり、最終的には投票で正式に決定するので、そのためのタグ提案のプロセスを経ることが今後の課題である。

#### 提案：emergency=assembly_pointの分類
1)避難所・避難場所の区別について
避難所・避難場所のタグを災害ごとに分けること、避難所以外の災害支援施設の入力が未着手である。避難所と避難場所は日本では区別すべきとされているが、OpenStreetMapでは同じタグとして区別されていたのでどのように表現すべきかが検討すべき課題である。各避難施設の定義をふまえて帰宅困難者の視点から考えると、一時集合場所と避難場所は一時的な利用を目的とされていることから帰宅困難者も利用ができると考えられるが避難所は区民以外は利用できない場合があるので、特に帰宅困難者が多いと想定される地域ではどの施設が利用できるのかを記載しておく必要がある。

2)災害ごとの区別について
現在のこのタグで分類できるのは、

* emergency=assembly_point:earthquake 
* emergency=assembly_point:fire
* emergency=assembly_point:flood
* emergency=assembly_point:landslide
* emergency=assembly_point:tornade
* emergency=assembly_point:tsunamiの６種類であった。

内閣府は指定緊急避難場所・指定緊急避難所の指定を促しているのと同時に日本工業規格（JIS)の災害種別の図記号（JIS　Z8210)を使った[災害種別避難誘導標識システム](http://www.bousai.go.jp/kyoiku/zukigo/pdf/symbol_02.pdf) （JIS　Z9098、H28.3.22）により災害ごとの避難場所の表示を促しており、それによる災害分類の中で上記の６つに該当指定ない高潮、内水氾濫、崖崩れ、土石流、火山等の分類も区別するべきかを議論すべきだと考える。

### 5.結論
本研究によってOpenStreetMapの目黒地区における避難所と広域避難所の情報の入力が完了し、避難所のwikiページの作成、及び日本において重要性の高い帰宅困難者支援施設のタグを新たに提案することができた。提案した議論に加えて更に細かい災害対策に関する情報をインドアマッピングで入力することで、より速やかな災害支援や避難をオープンソースで利用できるようになると考える。

### 6.参考文献
* [OpenStreetMap Wiki](https://wiki.openstreetmap.org/wiki/JA:Main_Page)
* [地理院地図指定緊急避難場所](https://maps.gsi.go.jp/#14/35.665021/139.695725/&base=std&ls=std%2C0.29%7Cskhb04&disp=11&lcd=skhb04&vs=c1j0h0k0l0u0t0z0r0s0f0&d=vl)
* [渋谷区防災地図](https://www.city.shibuya.tokyo.jp/assets/detail/files/anzen_bosai_hasai_pdf_bosaimap2017.pdf)
* [いざという時に/防災・防犯](http://www.city.meguro.tokyo.jp/iza/bohan_bosai.html)
* [目黒区防災マップ](http://www.city.meguro.tokyo.jp/kurashi/anzen/bosai/map/bousaimap.files/2018japanmap.pdf)
* [osm/wiki/tag:emergency=assembly_point](https://wiki.openstreetmap.org/wiki/JA:Tag:emergency%3Dassembly_point)
* [osm/wiki/key:emergency](https://en.wikipedia.org/wiki/Meeting_point)
* [osm/wiki/WikiProject Emergency Cleanup](https://wiki.openstreetmap.org/wiki/JA:WikiProject_Emergency_Cleanup)
* [osm/wiki/Talk:WikiProject Emergency Cleanup](https://wiki.openstreetmap.org/wiki/JA:Talk:WikiProject_Emergency_Cleanup)
* [osm/wiki/JA:Tag:amenity=shelter](https://wiki.openstreetmap.org/wiki/JA:Tag:amenity%3Dshelter)
* [公共施設の入力例 osm/wiki/amenity=social_centre](https://wiki.openstreetmap.org/wiki/JA:Tag:amenity%3Dsocial_centre)
* [平成30年　防災白書](http://www.bousai.go.jp/kaigirep/hakusho/h30/honbun/index.html)
* [避難場所等の図記号の標準化の取り組み](http://www.bousai.go.jp/kyoiku/zukigo/index.html)
* [防災標識ガイドブック](http://www.bousai.go.jp/kyoiku/zukigo/pdf/symbol_02.pdf)
* [都立一時滞在施設情報](http://www.bousai.metro.tokyo.jp/smart/kitaku_portal/1005196/1005247.html)
* [都立一時滞在施設情報一覧](http://www.bousai.metro.tokyo.jp/smart/_res/projects/default_project/_page_/001/005/247/20180401.pdf)
* [東京都防災マップ](http://map.bousai.metro.tokyo.jp/search_facility_list.html?p1=&p2=51&p3=)

