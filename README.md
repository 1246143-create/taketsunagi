# 竹つなぎ

放置竹林の課題を解決するため、竹を切ってほしい竹林の所有者と、竹を切りたい・竹を活用したい人をつなぐWebアプリのプロトタイプです。

学校の発表用のモックアップで、画面遷移と操作を体験できます。表示されるデータはすべてサンプルで、実際の決済機能や位置情報（GPS）は使っていません。

## 画面

- トップ：「竹林を探す」「竹林を登録する」を切り替え
- 竹林を探す：地図と一覧、作業内容（伐採・整備・運搬）で絞り込み、近い順などで並べ替え
- 竹林の詳細：場所、必要な作業、人数、日時、作業時間の目安、ポイント、応募
- 竹林を登録する：場所、写真、広さ、作業、日時、人数、報酬
- マイページ：応募した作業、登録した竹林、獲得ポイント、活動履歴、ポイント交換

## 使い方

`index.html` をブラウザで開くか、GitHub Pages で公開したURLを開いてください。

## バージョン

- `index.html`：最初のバージョン（トップ画面で「探す」「登録する」を切り替え）
- `v2/index.html`：ログイン画面つきのバージョン。新規登録で「竹林の所有者」か「竹を切りたい人」をえらび、アカウントの種類によって画面が変わります。発表用のデモアカウントでもログインできます（入力内容はどこにも送信・保存されません）。
- `v3/index.html`：竹林整備と竹の利活用を促進するバージョン。
  - 人の「やりたい目的」と竹林の「してほしいこと・報酬」の相性を計算して、おすすめの竹林を表示
  - 応募 → 所有者が承認 → マッチング成立 → アプリ内チャットで日時・集合場所・持ち物などを調整
  - 竹林整備・運搬・調査・記録・広報・加工の活動ごとに「竹林活動実績」ポイントとランクを表示
  - 整備した竹の状態（年数・太さ・状態・形）を記録すると、食品・竹炭・竹チップ・工芸品・建材・バイオマスなどの活用先を提案し、竹を必要とする事業者につなぐ
  - 地図は国土地理院の地理院タイルと Leaflet を使用。データはブラウザの localStorage に保存（本番では Firebase・Supabase などのデータベースに置きかえる想定）
- `v4/index.html`：「自分では整備できない所有者」が必要な作業を依頼し、複数の担い手が継続的に関われる仕組みとして作り直したバージョン。
  - 新規登録で「竹林所有者・農家」「参加者」を選び、それぞれ専用の登録画面とホーム画面に切りかわる
  - 竹林の登録と「整備依頼」の登録を分け、作業ごとに参加条件（経験者限定・立ち会い・安全講習・資格）を設定。伐採など危険な作業は条件なしでは登録できず、条件を満たさない参加者は応募できない
  - 地図は募集状況（募集中・整備中・継続管理中・募集終了）で色分け。正確な位置はマッチング成立後にだけ共有
  - 活動完了時に「できたこと・残っている課題・次に必要な作業」を記録し、整備状況（%）を更新。次の作業で続けて募集でき、「前回の続きに参加する」ことができる
  - 竹林活動実績は、伐採も調査・記録・清掃・広報・活用もほぼ同じ配点。初挑戦・継続参加にボーナス

## 写真について

v4 の写真は、Wikimedia Commons で **CC0（パブリックドメイン）** として公開されている写真を使っています。CC0 は著作権を放棄した作品なので、クレジット表記なしで自由に利用・加工できます（礼儀として下に出典を記載しています）。
見能林町の竹林の写真（`v4/img/g1.jpg`）は、作者が撮影した放置竹林の写真です。

| ファイル | 使用場所 | 元の写真 | 撮影者 | ライセンス |
|---|---|---|---|---|
| `v4/img/hero.jpg` | ホーム画面のバナー | [Arashiyama Bamboo Forest, Kyoto, Japan (Unsplash).jpg](https://commons.wikimedia.org/wiki/File:Arashiyama_Bamboo_Forest,_Kyoto,_Japan_(Unsplash).jpg) | Ståle Grut stalebg | CC0 |
| `v4/img/auth.jpg` | ログイン画面 | [Japan The Bamboo Forest (13914447656).jpg](https://commons.wikimedia.org/wiki/File:Japan_The_Bamboo_Forest_(13914447656).jpg) | Yiannis Theologos Michellis | CC0 |
| `v4/img/use.jpg` | 竹の活用画面 | [Bamboo grove - Eishō-ji - Kamakura, Kanagawa, Japan - DSC08150.JPG](https://commons.wikimedia.org/wiki/File:Bamboo_grove_-_Eish%C5%8D-ji_-_Kamakura,_Kanagawa,_Japan_-_DSC08150.JPG) | Daderot | CC0 |
| `v4/img/g2.jpg` | 竹林 2 の写真 | [Arashiyama Bamboo Grove (Unsplash).jpg](https://commons.wikimedia.org/wiki/File:Arashiyama_Bamboo_Grove_(Unsplash).jpg) | Erol Ahmed erol | CC0 |
| `v4/img/g3.jpg` | 竹林 3 の写真 | [Bamboo grove - Eishō-ji - Kamakura, Kanagawa, Japan - DSC08161.JPG](https://commons.wikimedia.org/wiki/File:Bamboo_grove_-_Eish%C5%8D-ji_-_Kamakura,_Kanagawa,_Japan_-_DSC08161.JPG) | Daderot | CC0 |
| `v4/img/g4.jpg` | 竹林 4 の写真 | [Bamboo invading forest in Kamakura, Japan.jpg](https://commons.wikimedia.org/wiki/File:Bamboo_invading_forest_in_Kamakura,_Japan.jpg) | Chirua | CC0 |
| `v4/img/g5.jpg` | 竹林 5 の写真 | [Bamboo grove - Eishō-ji - Kamakura, Kanagawa, Japan - DSC08147.JPG](https://commons.wikimedia.org/wiki/File:Bamboo_grove_-_Eish%C5%8D-ji_-_Kamakura,_Kanagawa,_Japan_-_DSC08147.JPG) | Daderot | CC0 |
| `v4/img/g6.jpg` | 竹林 6 の写真 | [Moso Bamboo 568570739.jpg](https://commons.wikimedia.org/wiki/File:Moso_Bamboo_568570739.jpg) | no rights reserved | CC0 |
| `v4/img/g7.jpg` | 竹林 7 の写真 | [Bamboo grove - Eishō-ji - Kamakura, Kanagawa, Japan - DSC08158.JPG](https://commons.wikimedia.org/wiki/File:Bamboo_grove_-_Eish%C5%8D-ji_-_Kamakura,_Kanagawa,_Japan_-_DSC08158.JPG) | Daderot | CC0 |
| `v4/img/g8.jpg` | 竹林 8 の写真 | [Phyllostachys edulis - Hakusan-jinja - Chusonji, Hiraizumi, Iwate - DSC04949.jpg](https://commons.wikimedia.org/wiki/File:Phyllostachys_edulis_-_Hakusan-jinja_-_Chusonji,_Hiraizumi,_Iwate_-_DSC04949.jpg) | Daderot | CC0 |
| `v4/img/g9.jpg` | 竹林 9 の写真 | [Bamboo grove - Eishō-ji - Kamakura, Kanagawa, Japan - DSC08145.JPG](https://commons.wikimedia.org/wiki/File:Bamboo_grove_-_Eish%C5%8D-ji_-_Kamakura,_Kanagawa,_Japan_-_DSC08145.JPG) | Daderot | CC0 |
| `v4/img/gdef.jpg` | 写真のない竹林（標準の写真） | [Bamboo grove - Eishō-ji - Kamakura, Kanagawa, Japan - DSC08169.JPG](https://commons.wikimedia.org/wiki/File:Bamboo_grove_-_Eish%C5%8D-ji_-_Kamakura,_Kanagawa,_Japan_-_DSC08169.JPG) | Daderot | CC0 |
