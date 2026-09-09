---
title: Personalizationのカスタムトークン
description: マーケティングアーティファクトを動的にパーソナライズするためのカスタムのマイトークンを作成および管理する – Marketo Optimizerでプログラムのテキスト変数と数変数を定義します。
TQID: 'https://experienceleague.adobe.com/utVM69g7aQSuF-V3XQIdVBqvBXyiDz1ZWr0WtE67UCg'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 629
ht-degree: 3%

---

# パーソナライゼーション用のカスタムトークン

コンテンツパーソナライゼーションでは、コンテンツアーティファクトが生成されたときに入力されるプレースホルダーまたは変数としてトークンを使用します。 標準のパーソナライズトークンは、メール、ランディングページ、フラグメント、テンプレートで利用できます。 プログラムまたはフォルダーに固有の値を持つカスタムトークンのセットを定義することもできます。 この一連のカスタムトークンは&#x200B;_マイトークン_&#x200B;と呼ばれ、これらのカスタムトークンはすべてパーソナライゼーション用です。

カスタムトークンをメールに追加すると、メールは`{{my.TokenName}}`と表示されます。 例えば、今後のウェビナーに関連するメールコンテンツを管理するために、`{{my.EventDate}}`または`{{my.WebinarSpeaker}}`個のトークンを作成できます。

プログラムまたはフォルダーに固有の&#x200B;_マイトークン_&#x200B;に加えて、任意の標準（組み込み）トークンをパーソナライゼーションに使用できます。

>[!NOTE]
>
>_マイトークン_&#x200B;は、現在、このBeta リリースのPersonalization エディターで有効になっていません。

## アクセストークン

1. 左側のナビゲーションで、**[!UICONTROL マーケティング管理]**&#x200B;を展開します。

1. **[!UICONTROL マーケティング]**&#x200B;のリソース リストの右側で、**[!UICONTROL プログラム]**&#x200B;を選択します。

1. ツリー構造を選択し、プログラムまたはフォルダーを選択して、センターワークスペースで詳細を開きます。

1. 「**[!UICONTROL トークン]**」タブをクリックします。

   選択したプログラムの「![ トークン」タブ ](./assets/program-tokens-tab.png){width="800" zoomable="yes"}

   このタブには、フォルダーまたはプログラム内で定義されているすべてのカスタムトークンと、親フォルダーまたはプログラムに定義されているすべてのカスタムトークンが表示されます。

### トークンのタイプ {#my-tokens}

_マイトークン_&#x200B;は、プログラムまたはフォルダー用に作成または変更するカスタム変数です。 このカスタムトークンセットは、次のトークンタイプをサポートしています。

| トークンタイプ | 説明 |
| ---------- | ----------- |
| テキスト | このタイプは、標準のテキスト文字列を保持します。 テキストトークンのサイズ制限は524,288文字（UTF-8）または2 MBです。 |
| 日付 | この型は日付値を保持します。 日付は、月日 – 年（09-23-2026など）として表示されます。 |
| 日時 | このタイプは、日付と時刻の値を保持します。 |
| 数字 | この型は標準的な整数値を保持します。 |
| メール | この種類には有効な電子メールアドレスが含まれています。 |
| スコア | このトークンは、ジャーニーアクションノードのスコアの変更に使用します。 |
| ブール | このタイプは、trueまたはfalseの標準ブール値を保持します。 |
| リッチテキスト | このタイプは、書式設定されたテキストを保持します。 |

### トークンネスティング

プログラムまたはフォルダーでトークンを作成すると、他の子オブジェクトで参照できるようになります。

* ローカルトークン – トークンは、同じプログラムまたはフォルダーで定義されます。
* 継承されたトークン – トークンは、親プログラムまたはフォルダー（現在のプログラムまたはフォルダーより1つ以上のレベル）で定義されます。
* オーバーライドされたトークン – トークンは親プログラムまたはフォルダーで定義されますが、現在のプログラムまたはフォルダーでは別の値が定義されます。 トークンのステータスが&#x200B;_上書き_&#x200B;に変更され、子フォルダー、プログラム、マーケティングアーティファクトが新しい値を継承します。

![ トークンタイプと継承](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### トークンの作成

1. 「_[!UICONTROL トークン]_」タブで、**[!UICONTROL 作成]**&#x200B;をクリックします。

1. ダイアログで、トークンの&#x200B;**[!UICONTROL Name]**&#x200B;を入力します。

   ![ テキストトークンの名前と値を入力](./assets/token-create-dialog.png){width="400"}

   トークン名にはスペースや特殊文字を使用できません。 `EventType`などの&#x200B;_キャメルケース_&#x200B;を使用して、簡単に識別できるマルチワード名を使用できます。

1. トークンの&#x200B;**[!UICONTROL Type]**&#x200B;を選択します。

1. トークンの&#x200B;**[!UICONTROL 値]**&#x200B;を設定します。

1. 「**[!UICONTROL 作成]**」をクリックします。

### トークンの編集

定義されたマイトークンの値を編集できます。 これを行うと、継承されたトークンの値が上書きされます。

<!-- (How does this affect live person journeys? ) -->

1. _[!UICONTROL トークン]_&#x200B;で、トークン名の横にある&#x200B;_編集_ アイコンをクリックします。

1. フィールドで、必要に応じて値を変更します。

   ![ トークンの名前と値を変更](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. _保存_ アイコンをクリックします。

### トークンの削除

カスタムトークンがジャーニーメールコンテンツで現在使用されていない場合は、リストから削除できます。

1. _[!UICONTROL トークン]_&#x200B;で、トークン名の横にある&#x200B;_削除_ アイコンをクリックします。

1. 確認ダイアログで、「**[!UICONTROL 削除]**」をクリックします。

<!--

## Use custom tokens in your content

When you are authoring email content for your programs, you can use any of the tokens from the _My Tokens_ list when you use the personalization tools in the visual design space.

1. Select the text component and click the _Add personalization_ ( ![Add personalization icon](../assets/do-not-localize/icon-personalization-field.svg) ) icon in the toolbar.

   ![Click the Add personalization icon](assets/email-personalize-text.png){width="600"}

   This action opens the _Edit Personalization_ dialog. The dialog includes a _[!UICONTROL My tokens]_ folder in the _[!UICONTROL Personalization Tokens]_ library if there are custom tokens defined for the account journey.

1. To add one of your custom tokens to the blank space, expand the **[!UICONTROL My tokens]** folder, then click **+** or **...**.

   You can add any additional static text as needed.

   ![Construct personalized text using My tokens](assets/personalization-edit-dialog-my-tokens.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->
