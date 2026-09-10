---
title: ランディングページの作成と公開
description: 個人向けジャーニーのランディングページを作成、デザイン、公開します。Marketo Optimizerでは、ゼロから作成、HTMLをインポートし、フォームを追加、コンテンツをパーソナライズし、メールからリンクできます。
feature: Landing Pages, Content Design Tools
role: User
TQID: 'https://experienceleague.adobe.com/XIXt4QcgK7VALQqpPHf6GqhCwEsV3mlyV1ZrgrIXi0s'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
  - id: 8881ff95-1653-5fea-82af-ce1549c0d99d
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1550
ht-degree: 19%

---

# ランディングページの作成と公開

マーケターは、ジャーニーに組み込むページを定義して公開できます。 新しいランディングページを追加する場合、プライマリページとサブページを設定し、コンテンツをデザインしてテストし、公開します。

![&#x200B; ランディングページワークフロー図](assets/landing-page-work-flow-diagram-no-subpages.svg)

>[!BEGINSHADEBOX]

## ランディングページの前提条件 {#landing-page-prerequisites}

マーケターがジャーニーをサポートするランディングページを作成する前に、次の設定とアセットを実施する必要があります。

* [&#x200B; ランディングページサブドメイン &#x200B;](../admin/configuration-presets-landing-pages.md#lp-subdomains) - ランディングページのホスティング専用のサブドメインを設定します。
* [&#x200B; ランディングページプリセット &#x200B;](../admin/configuration-presets-landing-pages.md#lp-presets) - プリセットは、ランディングページに適用されるサブドメインおよびその他の設定を定義します。
* [Form](./forms.md) （データキャプチャのユースケースの場合） – ランディングページにフォームを埋め込み、Experience Platformにデータを送信する場合に必要です。

>[!ENDSHADEBOX]

## ランディングページの作成 {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_create"
>title="ランディングページの定義と設定"
>abstract="ランディングページを作成するには、プリセットを選択し、プライマリページとサブページを設定してから、公開する前にページをテストする必要があります。"

ジャーニーオーディエンスのメンバーが特定のリンクをクリックしたときに、定義されたweb ページに誘導するには、[!DNL Marketo Optimizer]にランディングページを作成します。

>[!IMPORTANT]
>
>最初のランディングページを作成する前に、ランディングページの設定を完了します。 これには、ランディングページをホストするサブドメインを設定したり、サブドメインやその他のチャネル設定を指定する 1 つ以上のプリセットを定義したりすることが含まれます。 ランディングページの作成時にプリセットを選択します。 管理者の設定については、[&#x200B; ランディングページ設定](../admin/configuration-presets-landing-pages.md)を参照してください。
>
>データキャプチャのユースケースの場合は、ランディングページに埋め込む前に[&#x200B; フォーム &#x200B;](./forms.md)を作成します。

_ランディングページを作成するには&#x200B;:_

1. 左側のナビゲーションに移動し、**[!UICONTROL コンテンツ管理]**/**[!UICONTROL ランディングページ]**&#x200B;を選択します。

1. ランディングページのリストから、「**[!UICONTROL ランディングページの作成]**」をクリックします。

1. **[!UICONTROL タイトル]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

   タイトルと説明基準：

   * **タイトル** – 最大100文字。 一意である必要があります（大文字と小文字を区別しません）。
   * **説明** – 最大300文字。
   * Alpha、数値、特殊文字は使用できます。
   * 予約済みの文字は&#x200B;**_許可されていません_**: `\ / : * ? " < > |`

   ![&#x200B; ランディングページの作成](assets/landing-page-create.png){width="600"}

1. **[!UICONTROL プリセット]**&#x200B;を選択します。

   管理者[は、ランディングページに使用するサブドメインやその他の設定を定義するために、ランディングページプリセット &#x200B;](../admin/configuration-presets-landing-pages.md#lp-presets)を作成します。 プリセットを選択し、**[!UICONTROL プリセットを表示]**&#x200B;をクリックして設定を確認し、ランディングページの要件に一致することを確認します。

1. 「**[!UICONTROL 作成]**」をクリックします。

   プライマリページとそのプロパティが表示されます。 プライマリページ設定を[設定する方法について説明します](#configure-primary-page)。

   ![新しいランディングページ – プライマリページのプロパティ &#x200B;](assets/landing-page-primary-new-properties.png){width="700" zoomable="yes"}

1. サブページ（例えば、感謝ページやエラーページ）を追加するには、**+** アイコンをクリックします。

   ランディングページごとに最大2つのサブページを追加できます。

プライマリページとサブページを設定およびデザインしたら、ランディングページを公開する前に[&#x200B; テスト &#x200B;](#test-landing-page)します。

>[!CAUTION]
>
>ランディングページが公開されている場合でも、定義されたURLをweb ブラウザーにコピー&amp;ペーストして、ランディングページにアクセスすることはできません。 [&#x200B; ランディングページのテスト &#x200B;](#test-landing-page)の説明に従って、プレビュー関数を使用してページをテストします。

## プライマリページの設定 {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_primary_page"
>title="プライマリページ設定の定義"
>abstract="メールや web サイトなどで、受信者がランディングページのリンクをクリックした際にすぐに表示されるプライマリページを定義します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_access_settings"
>title="ランディングページ URL の定義"
>abstract="このセクションでは、一意のランディングページ URL を定義します。 URL の最初の部分では、選択したプリセットの一部としてランディングページのサブドメインを事前に設定する必要があります。"

プライマリページとは、電子メールやweb サイトなどのランディングページのリンクを受信者がクリックすると、すぐに表示されるページのことです。

_プライマリページ設定を定義するには&#x200B;:_

1. ニーズに応じて&#x200B;**[!UICONTROL ページ名]**&#x200B;を変更します。デフォルトでは&#x200B;_プライマリページ_&#x200B;です。

1. ページ URLの終了部分を定義します。

   選択したプリセットによって、URLの最初の部分が決まります。 管理者は、プリセットの一部として[&#x200B; ランディングページサブドメイン &#x200B;](../admin/configuration-presets-landing-pages.md#lp-subdomains)を設定します。

   >[!CAUTION]
   >
   >ランディングページの URL は一意にする必要があります。
   >
   >ランディングページが公開されている場合でも、このURLをweb ブラウザーにコピー&amp;ペーストしてランディングページにアクセスすることはできません。 [&#x200B; ランディングページのテスト &#x200B;](#test-landing-page)の説明に従って、プレビュー関数を使用してテストします。

1. 匿名のランディングページが必要な場合は、**[!UICONTROL 特定のユーザーを要求]** オプションを無効にします。

1. _カレンダー_ （![&#x200B; カレンダーアイコン &#x200B;](../assets/do-not-localize/icon-calendar.svg)）アイコンをクリックして、**[!UICONTROL ページの有効期限]**&#x200B;を設定します。

   有効期限を選択したら、ページの有効期限に応じてアクションを選択します。

   * **[!UICONTROL リダイレクト URL]** - リダイレクトとして使用するページのURLを入力します。

     ![&#x200B; ランディングページの有効期限 – リダイレクト URL](assets/landing-page-expiry-redirect-url.png){width="400"}

   * **[!UICONTROL ブラウザーエラー]** - ページの代わりに表示するエラーテキストを入力します。

     ![&#x200B; ランディングページの有効期限 – ブラウザーエラー](assets/landing-page-expiry-browser-error.png){width="400"}

## コンテンツデザインの種類を選択 {#choose-design-type}

ページの&#x200B;_[!UICONTROL Content]_&#x200B;を追加するには、**[!UICONTROL Designerを開く]**&#x200B;をクリックします。 設計プロセスは、どのように開始するかを選択することから始まります。

* [ゼロからデザイン](#design-from-scratch)
* [HTML の読み込み](#import-html)

![&#x200B; ランディングページデザインの開始方法を選択](assets/landing-page-create-design.png){width="800" zoomable="yes"}

ランディングページのデザインを開始するための好みの方法を選択したら、ビジュアルデザインツールを使用して[&#x200B; ページコンテンツを完成させます](./landing-page-design.md)。

### ゼロからデザイン {#design-from-scratch}

ビジュアルコンテンツデザイン機能を使用して、ランディングページの構造とコンテンツを定義します。 シンプルなドラッグ&amp;ドロップ操作で構造コンポーネントを追加、移動することで、ページコンテンツのレイアウトや整理を数秒でデザインできます。

1. デザインホームページから、「**[!UICONTROL ゼロからデザイン]**」オプションを選択します。

1. [構造とコンテンツ &#x200B;](./landing-page-design.md#structure-content-landing-page)をページに追加します。

1. [&#x200B; リンクされたURL トラッキングの確認と編集](./landing-page-design.md#linked-url-tracking)。

1. [&#x200B; ランディングページをテストする](#test-landing-page)。

コンテンツに問題がなければ、**[!UICONTROL 保存]**&#x200B;をクリックします。

### HTML の読み込み {#import-html}

<!-- originally  from   /help/_includes/content-design-import.md but copied and revised to omit the part about Marketo Engage assets and AEM assets -->

読み込むコンテンツは次のとおりです。

* スタイルシートが組み込まれたHTML ファイル
* HTML ファイル、スタイルシート（.css）および画像を含む.zip ファイル

  >[!NOTE]
  >
  >.zip ファイル構造に制約はありません。&#x200B; ただし、.zip フォルダーのツリー構造に合わせて、相対参照を指定する必要があります。 画像は常に[&#x200B; アセットリポジトリ &#x200B;](./digital-asset-management.md)にアップロードされます。

_HTML コンテンツを含むファイルを読み込むには&#x200B;:_

1. デザインホームページから、「**[!UICONTROL HTMLを読み込み]**」オプションを選択します。

1. HTML コンテンツを含んだ HTML または .zip ファイルをドラッグ＆ドロップし、「**[!UICONTROL 読み込み]**」をクリックします。

![zip ファイルにHTML コンテンツを読み込む](assets/templates-import-zip-file.png){width="500"}

>[!NOTE]
>
>`<table>` タグを HTML ファイルの最初のレイヤーとして使用すると、上部レイヤータグの背景や幅の設定などのスタイルが失われる可能性があります。

ビジュアルデザインツールを使用して、インポートしたコンテンツを必要に応じてパーソナライズできます。

## アラートの確認 {#check-alerts}

ランディングページのコンテンツをデザインする際に、重要な設定が欠落している場合に右上にアラートが表示されます。

![&#x200B; ページコンテンツの問題に関するアラート &#x200B;](assets/alerts-button.png){width="250"}

このボタンが表示されない場合、検出された問題はありません。

アラートには、次の2種類があります。

* 推奨事項とベストプラクティスに関する&#x200B;**_警告_**&#x200B;は、次のとおりです。

  * `Placeholder links are present in the landing page body`: プレースホルダーを有効なリンクに置き換えることを忘れないでください。

  * `Text version of HTML is empty`: HTML コンテンツを表示できない場合に使用する、ページ本文のテキスト版を定義することを忘れないでください。

  * `Empty link is present in page body`: ページ内のすべてのリンクが正しいことを確認してください。

* 解決されない限り、ジャーニーのテストやアクティブ化を妨げる&#x200B;**_エラー_**&#x200B;が発生します。例えば、次のようになります。

  * `The landing page content is empty`: ページコンテンツは必須です。

## ランディングページのテスト {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_preview_lp_profiles"
>title="ランディングページのプレビューとテスト"
>abstract="ランディングページの設定とコンテンツを定義したら、テストプロファイルを使用してページをプレビューします。"

ランディングページの設定とコンテンツが定義されている場合は、テストプロファイルを使用してページをプレビューできます。 [&#x200B; パーソナライズされたコンテンツ &#x200B;](./landing-page-design.md#personalize-content)を挿入した場合、テストプロファイルデータを使用して、このコンテンツがランディングページにどのように表示されるかを確認できます。

>[!PREREQUISITES]
>
>ランディングページをプレビューしてテストするには、**[!UICONTROL メッセージを公開]**&#x200B;権限と、テストプロファイルを含む定義済みデータセットが必要です。

1. 「**[!UICONTROL プレビューとテスト]**」をクリックして、テストプロファイルの選択を開きます。

   >[!NOTE]
   >
   >ビジュアルデザイン空間にいる場合は、**[!UICONTROL コンテンツをシミュレート]**&#x200B;することもできます。

1. _[!UICONTROL Simulate]_&#x200B;画面から、テストプロファイルを選択します。

   ![選択したプロファイルのランディングページコンテンツをシミュレート &#x200B;](assets/landing-page-simulate.png){width="700" zoomable="yes"}

   必要なプロファイルがリストにない場合は、**[!UICONTROL テストプロファイルの管理]**&#x200B;をクリックして、既知のテストプロファイルのメールアドレスを使用し、リストに追加します。

   +++テストプロファイルの追加

   **[!UICONTROL ID名前空間]**&#x200B;の場合、_選択_ アイコン （![選択アイコン &#x200B;](../assets/do-not-localize/icon-select-data.svg)）をクリックし、プロファイルのテストに使用する`Email`名前空間を選択します。

   ![&#x200B; テストプロファイルを管理してメール ID名前空間を設定](assets/manage-test-profiles.png){width="700" zoomable="yes"}

   「**[!UICONTROL ID値]**」フィールドに、テストプロファイルを識別する電子メールアドレスを入力し、**[!UICONTROL プロファイルを追加]**&#x200B;をクリックします。 これを繰り返して複数のプロファイルを追加できます。

   ![&#x200B; テストプロファイルの管理プロファイルの追加](assets/manage-test-profiles-add.png){width="700" zoomable="yes"}

   左上の後向き矢印をクリックして、_[!UICONTROL シミュレーション]_ ページに戻ります。

   +++

1. 「**[!UICONTROL プレビューを開く]**」を選択してランディングページをテストします。

   ランディングページのプレビューが新しいタブで開きます。 選択したテストプロファイルデータは、パーソナライズされた要素に置き換わります。

   ![&#x200B; プロファイルデータを使用したランディングページのプレビュー](assets/landing-page-preview.png){width="600"}

1. ランディングページの各バリエーションに対してレンダリングをプレビューするには、別のテストプロファイルを選択します。

## ページを公開 {#publish-landing-page}

>[!PREREQUISITES]
>
>ランディングページを公開するには、**[!UICONTROL メッセージを公開]**&#x200B;権限が必要です。 公開前に、[すべてのアラートを確認して解決](#check-alerts)。

ドラフトページが条件を満たし、ジャーニーメッセージでリンクできるようにするには、右上の「**[!UICONTROL 公開]**」をクリックします。 確認ダイアログで、**[!UICONTROL 公開]**&#x200B;をもう一度クリックして確認します。

![&#x200B; パブリッシュの確認ダイアログ &#x200B;](assets/landing-page-publish-confirm.png){width="250"}

ランディングページが公開されると、ランディングページリストに&#x200B;**_[!UICONTROL 公開済み]_** ステータスで表示されます。 つまり、ライブ状態であり、ジャーニーを通じて送信される電子メールまたはSMS メッセージで使用する準備ができていることを意味します。

URLをweb ブラウザーにコピー&amp;ペーストして、公開されたランディングページにアクセスすることはできません。 [&#x200B; プレビュー関数](#test-landing-page)を使用して、いつでもテストできます。
