--- 
title: Markdown でブログ記事を執筆する方法
date: 2020-06-12 12:00:00 
tags: 
  - Markdown
  - ブログ
  - Other
---

Azure Networking サポートチームの山口です。
この記事は、Markdown でブログを執筆するためのテンプレートです。ぜひご活用ください。

<!-- more -->

## はじめに

Markdown とは html を軽量に記述するためのマークアップ 言語です。
テキストファイルのように記述できて、文章を簡単に構造化できることから、エンジニアにとても重宝されています。

Markdown はこのような場面で利用されています。

- docstring: ソースコード内に埋め込まれたドキュメンテーション
- github: GitHub の Issue は markdown に対応しています
- qiita: Qiita や Hatenablog を始めとする、エンジニア向けのブログ サービスは、基本的に markdown で記事を執筆できます

インターネットにたくさん解説記事があるので、参考にしてみてください。

## どのようにして書くのか

### 書き出し

基本は、以下のような構文で記事の書き出しが始まります。

```md
--- 
title: ここにタイトルを記述します 
date: 2020-05-11 12:30:00 
tags: 
  - My Awesome Tag
  - Godly Tag
---

Azure Networking サポートチームの山口です。この記事は、Markdown でブログを執筆するためのテンプレートです。ぜひご活用ください。

<!-- more-- >
```

ポイントは以下の通り:

* `title` や `date` は適宜修正
* `tag` を考える前に、一旦ブログを調べてなるべく表記揺れをなくす (既存のタグと表記を合わせる)
* 冒頭で挨拶をしましょう
  * 名前は名乗る
  * 記事でなにを説明するかを書く
* `<!-- more -->` とある部分で [続きを見る] みたいなボタンが現れます。

### 本文

実際の本文は次の通りです。

```md
## はじめに

## Chapter2

### Section 2.1

### Section 2.2

## Chapter3

## Chapter4

## まとめ
```

`#` が `<h1>`、`##` が `<h2>` を表すように、`#` はその数の文だけのセクションのレベルを表します。文章の構造化に一番寄与する部分なので気をつけましょう。

### その他 Tips

リスト `<ul> <li>` を挿入する場合

```
*  証明書の CN (Common Name) と URL で指定した FQDN があってない
*  証明書の有効期限が切れている
*  自己証明書を使用しており、ルート証明書とのチェーンの検証で失敗している
*  リスナーに登録した証明書に中間証明書が含まれていない
```

順番付きリスト `<ol> <li>` を挿入する場合

```
1. 最初のステップです
1. 次のステップです
1. 最後のステップです
```

画像を挿入する場合

```
![image-title](./article-title-with-lower-camel-case/image.png) 
```

Pre (ソースコード) を挿入する場合

```bash
curl https://xxxxx.com
curl: (60) SSL certificate problem: unable to get local issuer certificate
More details here: https://curl.haxx.se/docs/sslcerts.html

curl failed to verify the legitimacy of the server and therefore could not
establish a secure connection to it. To learn more about this situation and
how to fix it, please visit the web page mentioned above.
```

赤色の文字を挿入する場合

```
<span style="color: red">とても大事なメッセージです</span>
```

## まとめ

とはいっても一回でわかるものではないので、どしどしかいて言ってください。


## 参考文献

* [jpaztech/blog: 日本マイクロソフト Azure IaaS サポート チームのブログです。](https://github.com/jpaztech/blog)
* [Hexo](https://hexo.io/)