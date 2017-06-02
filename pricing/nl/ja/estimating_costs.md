---



copyright:

  years: 2015, 2017
lastupdated: "2017-04-12"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# コストの見積もり
{: #cost}

{{site.data.keyword.Bluemix_notm}} を使用してアプリを作成およびホストするのに必要な金額を確認するには、さまざまなメソッドを使うことができます。

* {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.pricing_sheet}} にあるコスト見積もりツールは、アプリのサイズに基づくコストのおおまかな見積もりを提供します。
* {{site.data.keyword.Bluemix_notm}} の「料金」ページにあるコスト計算器は、ユーザーが入力したランタイムとサービスの使用量に基づくアプリの正確な価格を提供します。
* コストは手動で計算することもできます。

## コスト計算器の使用
{: #calculator}

{{site.data.keyword.Bluemix_notm}} で提供されるコスト計算器を使用すると、アプリの価格を素早く設定できます。

1. {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.pricing_sheet}} にアクセスします。
2. いずれかのインフラストラクチャー・ウィジェットを使用するか、**「料金カリキュレーター」**をクリックします。

計算器を使用するには、インスタンス数やプッシュ通知数など、リストされたリソースの予想される月々の使用量を入力します。**「月々の使用量」**フィールドの内側をクリックすると、フィールドでの使用が見込まれる単位に関するヒントが表示されます。計算器は、入力に対する価格を即時に表示します。計算器は、月々のコストではなく、年間のコストを表示するように調整することもできます。

## 手動でのコスト計算
{: #manual}

{{site.data.keyword.Bluemix_notm}} コストをご自身で見積もると、{{site.data.keyword.Bluemix_notm}} コストがどのように計算されるかを詳しく理解することができます。ランタイムの価格および使用されるサービスの価格を考慮することにより、{{site.data.keyword.Bluemix_notm}} を使用してアプリケーションを構築しホストする場合の総額を計算することができます。ランタイムとサービスの価格は時折変動するため、総額を計算する際には、{{site.data.keyword.Bluemix_notm}} 価格設定シートで最新情報を参照する必要があります。

## 例: サンプル・アプリの価格設定
{: #sample}

スケーラビリティー機能を持つ Node.js Web アプリを使用しており、そのアプリは {{site.data.keyword.Bluemix_notm}} が提供する
複数のサービスを使用していると仮定します。この例で、ご使用のアプリの実際のコストがどのように計算されるかを学習することができます。この Web アプリは、以下の {{site.data.keyword.Bluemix_notm}}
サービスとアイテムを使用します。

* 4 個の 256 MB Node.js ランタイム・インスタンス
* 2 個の {{site.data.keyword.autoscaling}} ポリシー、およびプロセッサーとメモリー
* 1 月あたり 2 GB の {{site.data.keyword.datacshort}}
* 1 月あたり 150 GB の NoSQL データベース、100,000 回の高負荷 API 呼び出し、および 500,000 回の軽負荷 API 呼び出し
* 20 GB のインバウンドまたはアウトバウンドのネットワーク・トラフィック

## Bluemix リソースの価格
{: #sample_resources}

例を単純にするため、以下の表の価格が月などの時間フレーム内または時間フレーム間で変動しないと仮定します。この例の価格設定はすべてアメリカ合衆国の通貨です。

|サービス |	フィーチャー |	価格 |
|--------|-----------|--------|
|SDK for Node.js |	1 月あたり 375 GB 時間無料 (すべてのランタイム間で共有) |	$0.07 (米ドル)/GB 時間|
|Auto-Scaling |	Auto-Scaling サービスの無料サービス・プラン |	無料|
|Data Cache - Starter |	1 GB のキャッシュ・スペースおよびレプリカ |	$55.00 (米ドル)/インスタンス |
|Data Cache - Standard |	5 GB のキャッシュ・スペースおよびレプリカ |	$155.00 (米ドル)/インスタンス |
|Data Cache - Premium |	25 GB のキャッシュ・スペースおよびレプリカ |	$505.00 (米ドル)/インスタンス|
|IBM Cloudant® NoSQL DB for {{site.data.keyword.Bluemix_notm}} |	2 GB の無料データ・ストレージ
<br/>1 月あたり 50,000 回の無料軽負荷 API 呼び出し
<br/>1 月あたり 10,000 回の無料高負荷 API 呼び出し | $1.00 (米ドル)/GB
<br/>$0.03 (米ドル)/軽負荷 API 呼び出し 1000 回
<br/>$0.15 (米ドル)/高負荷 API 呼び出し 1000 回 |
{:caption="表 1. 価格設定シート" caption-side="top"}

## アプリ価格の計算

アプリの価格は、次の方法で計算することができます。

<dl>
<dt>4 個の 256 MB Node.js ランタイム・インスタンス</dt>
<dd>Bluemix は、GB 時間ごとにランタイムに課金します。1 月あたりに使用される GB 数は、<code>4 x 256 = 1024 MB つまり 1 GB /月</code>です。<code>1 カ月を 24 x 30 = 720 時間</code> と仮定すると、アプリケーションは <code>1 x 720 = 720 GB 時間</code>に対して課金されます。
<p>
{{site.data.keyword.Bluemix_notm}} ランタイムを通して共有される 1 月あたりの無料枠に、375 GB 時間が含まれます。そのため、ランタイムの総額は、<code>$0.07 x (720-375) = $24.15</code> となります。</p></dd>

<dt>2 個の Auto-Scaling ポリシー (プロセッサーとメモリー)</dt>
<dd>Auto-Scaling ポリシーは無料です。</dd>

<dt>1 月あたり 2 GB の Data Cache</dt>
<dd>Data Cache サービスが提供する 50 MB プランは無料です。ただし、無料のプランでは、1 カ月当たり 2 GB と予測される使用量をカバーできません。Data Cache の 3 つの有料プランでは、実際に使用したスペースの量にかかわらず、特定のスペース量に対する一定の料金がかかります。そのため、予測される使用量を満たす最小限のプランである 5 GB の標準プランを選択することにします。総額は 1 月あたり $155 になります。</dd>

<dt>1 月あたり 150 GB の NoSQL データベース</dt>
<dd>IBM Cloudant NoSQL DB for {{site.data.keyword.Bluemix_notm}} のサービス料金は、データ・ストレージおよび各 API メソッドでそのデータにアクセスする機能に基づきます。<strong>PUT</strong> コマンドおよび
<strong>POST</strong> コマンドは高負荷 API 呼び出しとみなされますが、
<strong>GET</strong> コマンドは軽負荷 API 呼び出しとみなされます。
<p>
GB 数を合計して、2 GB の無料枠を減算します。1 月あたり 148 GB が課金されます。軽負荷 API 呼び出し 50,000 回の無料枠と、高負荷 API 呼び出し 10,000 回の無料枠を減算します。ストレージの総額には、次のものが含まれています。</p>
<pre class="codeblock">
<codeblock>
    148 x 1 = $148
    (450,000 / 1000) x 0.03 = $13.5
    (90,000 / 1000) x 0.15 = $13.5
</codeblock>
</pre>
<p>
総額は、148 + 13.5 + 13.5 = $175 です。</p></dd>

<dt>20 GB のインバウンドまたはアウトバウンドのネットワーク・トラフィック</dt>
<dd>インバウンドおよびアウトバウンドのネットワーク・トラフィックは無料です。</dd>

</dl>

すべてのアイテムが加算される場合、アプリケーションの総額は $354.15 となります。

## サポートされている通貨

価格設定サンプルでは米国ドル (USD) が使用されていますが、{{site.data.keyword.Bluemix_notm}} では他の通貨もサポートされています。次の表に、サポートされているさまざまな通貨を示します。

|ISO 4217 コード| 通貨|
|-------------|---------|
|AUD |	  オーストラリア・ドル|
|BRL |	  ブラジル・リアル|
|CAD |	  カナダ・ドル|
|CHF |	  スイス・フラン|
|DKK |	  デンマーク・クローネ|
|EUR |	  ユーロ|
|GBP |	  スターリング・ポンド|
|INR |	  インド・ルピー|
|JPY |	  日本円|
|KRW |	  韓国ウォン|
|NOK |	  ノルウェー・クローネ|
|NZD |	  ニュージーランド・ドル|
|SEK |	  スウェーデン・クローネ|
|USD |    米国ドル|
|ZAR |	  南アフリカ共和国ランド|
{:caption="表 2. サポートされている通貨" caption-side="top"}

**注:** {{site.data.keyword.Bluemix_notm}} と SoftLayer のアカウントをリンクした場合、受け取る単一の請求書は、米国ドル (USD) 単位のもののみになります。