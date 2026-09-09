---
title: プライバシー管理
description: Marketo OptimizerでGDPRやCCPAなどのプライバシー規制に準拠し、Adobe Privacy Serviceを使用してリクエストを送信する方法をご紹介します。
feature: Setup
role: Admin
TQID: 'https://experienceleague.adobe.com/VgnMCjm6l4pWG2-gqMuOmZUqU7E2Wrc-eVxn4kL5rKc'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 18a33a66-85a1-58e4-8e50-418b832ade8bid: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 2%

---


# プライバシーの管理 {#privacy-management}

[Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/home){target="_blank"}には、お客様のデータリクエストの管理に役立つRESTful APIとユーザーインターフェイスが用意されています。 [!DNL Adobe Privacy Service]を使用すると、Adobe CX Enterprise アプリケーションから個人のお客様データにアクセスして削除するリクエストを送信でき、法的および組織のプライバシー規制への自動コンプライアンスが容易になります。

[!DNL Adobe Marketo Optimizer]には、グローバルなデータ保護要件を満たすことができるように、これらのプライバシーツールが用意されています。 [!DNL Privacy Service]を使用して、[!DNL Marketo Optimizer]が収集および保存するデータのアクセス要求と削除要求を送信および管理します。

[!DNL Adobe Marketo Optimizer]から消費者データにアクセスして削除する個々のリクエストを送信するには、次の2つの方法があります。

* [!DNL Privacy Service] UI
* [!DNL Privacy Service] API

## サポートされるプライバシー規制 {#regulations}

[!DNL Marketo Optimizer]個のプライバシーツールを使用すると、[!DNL Privacy Service]を通じて規制に準拠できます。 各規制は、関連する地域に居住している人々のデータを保持する場合に適用されます。

サポートされている規制の最新の一覧については、Privacy Service ドキュメントの&#x200B;[_プライバシー規制の概要_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/regulations/overview){target="_blank"}を参照してください。

## リクエストタイプ {#access-and-delete-requests}

[!DNL Marketo Optimizer]は、次の2つのプライバシーリクエストタイプをサポートしています。

* **データアクセス** – 個人データが処理されていることを確認し、そのデータの無料の電子コピーを受け取ることができます。
* **データの削除** - _忘れられる権利_&#x200B;とも呼ばれ、個人データの消去と処理の中止を要求できます。

## プライバシーリクエストの表示と管理 {#view-manage-requests}

>[!BEGINSHADEBOX]

![AEP権限アイコン ](../assets/do-not-localize/icon_permissions-outline.svg)これらの手順を実行するには、[!DNL Privacy Service]製品プロファイルと、Experience Platform](../start/user-management.md#permissions)で割り当てられたユーザーロールに対する次の[権限が必要です。

* **[!UICONTROL Privacy Service権限]** - `Privacy Read Permission`および`Privacy Write Permission`
* **[!UICONTROL データガバナンス]** - `View Privacy Console`

詳しくは、[!DNL Privacy Service] ガイドの&#x200B;[_Privacy Service_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/permissions){target="_blank"}の権限の管理を参照してください。

>[!ENDSHADEBOX]

[!DNL Marketo Optimizer]でプライバシーリクエストジョブを表示するには、**[!UICONTROL プライバシー]**&#x200B;を展開し、**[!UICONTROL リクエスト]**&#x200B;を選択します。

右上の「**[!UICONTROL 規制タイプ]**」オプションを使用して、ジョブを管理またはリクエストを送信する規制の表示ページを変更します。

![ プライバシー要求ジョブ、規制タイプを選択](./assets/privacy-requests.png){width="800" zoomable="yes"}

### リクエストを送信 {#submit-a-request}

1. 「**[!UICONTROL リクエストを作成]**」をクリックします。

1. **[!UICONTROL ジョブタイプ]**&#x200B;で、リクエストタイプを選択します。

   * **[!UICONTROL アクセス]**

     [!DNL Marketo Optimizer]を含む&#x200B;**_アクセス_**&#x200B;要求を送信すると、[!DNL Privacy Service]が返します。

     * リードに関連付けられた[!DNL Marketo Engage] アクティビティ。
     * 個人またはアカウントに関連付けられている[!DNL Marketo Optimizer] アクティビティ。

   * **[!UICONTROL 削除]**

     [!DNL Marketo Engage]および[!DNL Marketo Optimizer]に対して&#x200B;**delete** リクエストを送信すると、次のレコードが削除されます。

     * [!DNL Marketo Engage]に関連付けられているリード。
     * [!DNL Marketo Optimizer]に作成された個人レコードとアカウントレコード。
     * 個人の個人情報を参照する同僚の会話履歴。

1. **[!UICONTROL 製品]**&#x200B;の場合、**[!UICONTROL Marketo]**&#x200B;を選択します。

   ![Marketo EngageおよびMarketo Optimizerに対するGDPR アクセスのプライバシーリクエストを作成](./assets/privacy-request-create-gdpr.png){width="450" zoomable="yes"}

   この選択には、[!DNL Marketo Optimizer]と[!DNL Marketo Engage] インスタンスの両方のデータが含まれます。

1. ダイアログの一番下までスクロールし、データにアクセスまたは削除するユーザーの電子メールアドレスを入力します。

1. リクエストを送信するには、**[!UICONTROL 作成]**&#x200B;をクリックします。

   [!DNL Privacy Service]は、リクエスト IDを返します。このIDを使用して、リクエストのステータスを確認できます。

### API リクエスト {#api-requests}

[!DNL Privacy Service] APIを使用してプライバシーリクエストを送信することもできます。 一般的なAPIの参照については、[Privacy Service API ドキュメント ](https://developer.adobe.com/experience-platform-apis/references/privacy-service){target="_blank"}を参照してください。

>[!PREREQUISITES]
>
>リクエストを送信する前に、次の情報を収集します。
>
>* 組織のIMS組織ID （`@AdobeOrg`で終わる24文字の英数字の文字列）。 IMS組織IDがわからない場合は、`gdprsupport@adobe.com`のAdobe サポートにお問い合わせください。
>* データにアクセスまたは削除するユーザーの電子メールアドレス。

リクエストで次のフィールド値を使用します。

| フィールド | 値 |
|---|---|
| `companyContexts.namespace` | `imsOrgID` |
| `companyContexts.value` | あなたのIMS組織ID |
| `users.action` | `access` または `delete` |
| `users.userIDs.namespace` | `Email` |
| `include` | `marketo`を使用して[!DNL Marketo Optimizer]と[!DNL Marketo Engage] データの両方を含める |
| `regulation` | 例：`ccpa` <br/>一部のレギュレーション値に状態の略語が含まれるように変更されています（例：`ucpa_ut_usa`）。 古い値は、移行期間でも有効です。 これらの値に対する統合を構築する前に、現在のリストについては、[ プライバシー規制の概要](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/regulations/overview){target="_blank"}を参照してください。 |

次の例では、[!DNL Marketo Optimizer] データを含むGDPR削除要求を送信します。

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": ["delete"],
      "userIDs": [
        {
          "namespace": "Email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": ["marketo"],
  "regulation": "gdpr"
}
```

[!DNL Privacy Service]は、次のような応答を返します。

```json
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": ["delete"],
          "userIDs": [
            {
              "namespace": "Email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
