---
title: WhatsApp オーサリング
description: Marketo Optimizerで承認済みのMetaテンプレート、パーソナライゼーショントークン、配信設定を使用して、カスタマージャーニー向けのWhatsApp メッセージを作成できます。
TQID: 'https://experienceleague.adobe.com/BSXYq8UkffBwDDc4wVl4b2MPjNh83-8nrQx-YS57-9U'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: d4203578-d294-5145-b397-f26f4488a904
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 801
ht-degree: 20%

---

# WhatsApp オーサリング

[!DNL Adobe Marketo Optimizer]を使用して、モバイルデバイス上のユーザーにWhatsApp メッセージを送信します。 WhatsApp エディターで承認済みのMetaメッセージテンプレートを使用して、メッセージを作成、パーソナライズ、プレビューできます。

個人向けジャーニー用のWhatsApp メッセージを作成する前に、_[!UICONTROL 管理者]_&#x200B;設定で[WhatsApp チャネルが設定されていることを確認してください](../admin/configuration-channels-whatsapp.md)。

>[!NOTE]
>
>[!DNL Marketo Optimizer]では、_アウトバウンド_ WhatsApp メッセージ要素のみがサポートされています。

+++ サポートされているメッセージ要素とcall-to-action オプション

このセクションの表を、承認済みのMeta テンプレートに含めることができるアウトバウンド WhatsApp コンテンツと、メッセージに追加できるインタラクティブボタンのリファレンスとして使用します。

次の表は、サポートされているメッセージ要素とその要件をまとめたものです。

| メッセージ要素 | 説明 |
| - | - |
| ヘッダー | メッセージの本文の上に表示されるオプションのテキスト。 |
| テキスト | パラメーターを通じて動的コンテンツをサポートします。 |
| 画像（JPEG、PNG） | 8 ビット RGB または RGBA 形式で、サイズが 5 MB 未満である必要があります。 |
| ビデオ | 3GPPまたはMP4で、16 MB未満で、URLでホストされている必要があります。 |
| オーディオ | 応答メッセージにのみ使用できます。 AAC、AMR、MP3、MP4 オーディオまたは OGG 形式で、URL でホストされ、16 MB 未満である必要があります。 |
| ドキュメント | 100 MB未満で、URLにホストされ、次のいずれかの形式である必要があります：`.txt`、`.xls`/`.xlsx`、`.doc`/`.docx`、`.ppt`/`.pptx`、または`.pdf`。 |
| 本文 | パラメーターを通じて動的コンテンツをサポートします。 |
| フッターテキスト | パラメーターを通じて動的コンテンツをサポートします。 |

次の表に、call-to-action ボタンの種類とメッセージ内での動作を示します。

| Call to action | 説明 |
| - | - |
| Web サイトに訪問 | 変数パラメーターを含むボタンは、1 つのみ許可されます。 |
| WhatsApp で通話 | メッセージから直接、指定された電話番号との WhatsApp チャットを開くボタンを提供します。 |
| 電話番号に通話 | ユーザーがタップすると、指定された番号への通話を開始するボタンを提供します。 |

+++

## ユーザージャーニーにWhatsApp アクションを追加する {#add-whatsapp-journey-action}

>[!IMPORTANT]
>
>**WhatsApp同意管理**: Metaのポリシーと適用可能な規制に従って、すべてのWhatsApp マーケティングメッセージは、メッセージの受信をオプトインした受信者にのみ送信する必要があります。 WhatsAppの受信者は、オプトアウトキーワードを使用して返信することで、いつでもオプトアウトできます。 オプトアウトした応答は自動的に尊重され、対応するプロファイルは今後のマーケティングメッセージのオーディエンスから削除されます。

[ アクションを実行&#x200B;]_ノード ](../marketing/action-nodes.md)を追加し、アクションリストから&#x200B;**[!UICONTROL WhatsAppを送信]**を選択すると、WhatsApp メッセージ配信を個人ジャーニーで設定できます。_[!UICONTROL 

## WhatsApp メッセージの作成 {#create-whatsapp-message}

1. _[!UICONTROL アクションを実行]_ パネルの下部にある「**[!UICONTROL WhatsAppを作成]**」をクリックします。

1. ダイアログで、WhatsApp メッセージに一意の&#x200B;**[!UICONTROL 名前]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

   ![新しいWhatsApp メッセージの作成ダイアログ ](assets/whatsapp-create-dialog.png){width="400"}

1. 「**[!UICONTROL 作成]**」をクリックします。

   _WhatsApp デザインスペース_&#x200B;が開き、WhatsApp アクションを定義し、メッセージを送信するためのコンテンツを作成できます。

### アクション設定を選択します {#select-actions-configuration}

1. _WhatsApp デザインスペース_&#x200B;で、「**[!UICONTROL アクション]**」タブを選択します。

1. **[!UICONTROL WhatsApp設定]**&#x200B;で、ニーズに合わせてマーケティングアクションとメッセージ配信設定をサポートする設定を選択します。

   ![WhatsAppの作成 – アクション タブ ](assets/whatsapp-create-actions-tab.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL コンテンツを編集]**」をクリックして、メッセージパラメーターとテキストに進みます。

### メッセージテンプレートの選択 {#select-message-template}

WhatsApp メッセージは、Meta WhatsApp Business アカウントの事前承認済みメッセージテンプレートを使用して送信されます。 **テンプレートを[!DNL Marketo Optimizer]で使用するには、Meta**&#x200B;によるレビューと承認が必要です。 テンプレートを管理して承認のために送信するには、[!DNL Meta Business Manager] アカウント管理者と協力してください。

1. **[!UICONTROL テンプレート カテゴリを選択]**&#x200B;するには、次のいずれかを選択します。

   * マーケティング
   * ユーティリティ
   * 認証

1. **[!UICONTROL WhatsApp テンプレートを選択]**&#x200B;するには、設定した法人アカウントの承認済みテンプレートを選択します。

   テンプレートコンテンツがメッセージエディターに読み込まれ、テンプレート構造とパーソナライゼーションに使用できる変数フィールドが表示されます。

   ![ プレビューウィンドウにメッセージが読み込まれたWhatsApp メッセージテンプレートを選択](assets/whatsapp-create-select-template.png){width="700" zoomable="yes"}

   このシステムは、カテゴリ （_マーケティング_、_ユーティリティ_、_認証_）およびステータス別にテンプレートを整理します。 選択可能なテンプレートは、**_承認済み_**&#x200B;件のみです。 WhatsApp テンプレートの作成について詳しくは、Meta ドキュメントの「[_WhatsApp Business アカウントのメッセージテンプレートを作成_](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343)」を参照してください。

### 画像URL {#image-urls}

テンプレートに画像が含まれている場合は、**[!UICONTROL 画像URL]** フィールドを使用してメディア URLを追加し、テンプレート内のプレースホルダーを置き換えます。 Meta のテンプレートメディアは、プレースホルダーのみです。 画像、オーディオ、ビデオを正しく表示するには、Adobe Experience Manager またはその他のソースからの外部 URL を使用する必要があります。

### メッセージコンテンツのパーソナライズ {#personalize-message-content}

承認済みのWhatsApp テンプレートには、プロファイルデータまたは動的な値を使用して定義した変数プレースホルダーを含めることができます。

テンプレートに表示されている各変数フィールドについて、フィールドの横にある&#x200B;_パーソナライズ_ アイコン （![ パーソナライズ アイコン ](../assets/do-not-localize/icon-personalize.svg)）をクリックします。

![WhatsApp テンプレート内の変数](assets/whatsapp-create-variables.png){width="700" zoomable="yes"}

このダイアログでは、個人トークンとシステムトークンにアクセスできます。 標準トークンとカスタムトークンの両方が含まれています。 _検索_ バーを使用して必要なトークンを検索するか、フォルダーツリー内を移動してトークンのいずれかを検索して選択できます。

パーソナライゼーショントークンが定義されたら、**[!UICONTROL 保存]**&#x200B;をクリックして変更を保存し、メインのWhatsApp メッセージワークスペースに戻ります。
