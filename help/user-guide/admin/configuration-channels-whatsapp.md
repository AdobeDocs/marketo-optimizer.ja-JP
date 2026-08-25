---
title: WhatsApp チャネル設定
description: Meta Cloud APIを介してWhatsApp Business アカウントを接続し、Marketo Optimizerの個人ジャーニーでWhatsApp メッセージを有効にします。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 19%

---

# WhatsApp チャネル設定

Marketo Optimizerは、Meta APIを介してWhatsApp メッセージを送信します。 マーケターが個人のジャーニー用にWhatsApp メッセージを作成する前に、製品管理者がWhatsApp チャネルを設定する必要があります。

Marketo Optimizerの![WhatsApp タスク フロー](assets/whatsapp-flow-diagram.png)

## 前提条件 {#prerequisites}

WhatsApp チャネルを設定する前に、次のことを確認してください。

* [Meta Business Manager アカウント](https://business.facebook.com/)
* [確認済みの送信者名と電話番号を持つWhatsApp ビジネスアカウント](https://developers.facebook.com/docs/whatsapp/overview/business-accounts/)
* [適切な権限を持つMeta ユーザー認証トークン](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
* [WhatsApp ビジネスアカウントの承認済みメッセージテンプレート](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/)

>[!IMPORTANT]
>
>WhatsApp メッセージングサービスの使用には、Metaの利用条件が適用されます。 Marketo Optimizerを通じてWhatsApp メッセージにアクセスすることにより、お客様は[Meta WhatsApp ビジネス ポリシー](https://www.whatsapp.com/legal/business-policy/)を確認し、遵守することに同意したことになります。

## 制限事項 {#limitations}

次の制限が WhatsApp チャネルに適用されます。

* Adobe Marketo Optimizerは&#x200B;**HIPAAに準拠しておらず、HIPAA対応ではありません**。 さらに、サードパーティベンダーは、AdobeのBAAの対象ではありません。 顧客は、独自のコンプライアンスとベンダー検証に責任を負います。

* 自動応答メッセージまたは事前定義された応答メッセージは、まだサポートされていません。

* 2025年4月より、Metaは、米国の電話番号（+1のダイヤル コードと米国のエリアコードで構成される番号）を持つWhatsApp ユーザーに対するすべてのマーケティングテンプレートメッセージの配信を一時的に停止しました。 [詳しくは、Meta ドキュメント ](https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/marketing-templates/per-user-limits/)を参照してください。

* ネイティブ統合機能では、サードパーティのビジネスサービスプロバイダー（BSP）との統合は許可されていません。

## チャネル設定の完了 {#complete-channel-configuration}

WhatsApp メッセージを送信する前に、Marketo Optimizer環境を設定し、WhatsApp アカウントに接続する必要があります。

次のタスクを実行します。

1. [WhatsApp API資格情報の作成](#create-whatsapp-api-credentials)
1. [WhatsApp Webhook を追加](#configure-webhooks)
1. [WhatsApp チャネル設定の作成](#create-channel-configuration)

### WhatsApp API 資格情報の作成 {#create-whatsapp-api-credentials}

>[!NOTE]
>
>説明された設定は、管理者権限を持つユーザーのみがアクセスできます。

1. 左側のナビゲーションで、**[!UICONTROL 管理]** セクションを展開し、**[!UICONTROL チャネル]**&#x200B;をクリックします。

1. パネルで、**[!UICONTROL WhatsApp Settings]**&#x200B;を展開し、**[!UICONTROL API Credentials]**&#x200B;を選択します。

   ![管理 / WhatsApp設定が拡張されたチャネル ](./assets/config-whatsapp-channels.png){width="800" zoomable="yes"}

1. 右上の「**[!UICONTROL 新しいAPI資格情報を作成]**」をクリックします。

1. 以下で説明するように、API 資格情報を設定します。

   * **[!UICONTROL 名前]** – 資格情報の一意の名前を入力します
   * **[!UICONTROL API トークン]** - API トークンを入力します。 詳しくは、[Meta ドキュメント ](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)を参照してください。
   * **[!UICONTROL ビジネス アカウント ID]** - ビジネス ポートフォリオに関連する一意の番号を入力します。 詳しくは、[Meta ドキュメント ](https://www.facebook.com/business/help/1181250022022158?id=180505742745347)を参照してください。

   ![WhatsApp設定API資格情報](assets/config-whatsapp-channels-api-credentials.png){width="500" zoomable="yes"}

1. 「**[!UICONTROL 続行]**」をクリックします。

1. WhatsApp API資格情報に接続する&#x200B;**[!UICONTROL WhatsApp Business Account]**&#x200B;を選択します。

   ![WhatsApp設定API資格情報は、ビジネスアカウントを選択します](assets/config-whatsapp-channels-api-credentials-details.png){width="500" zoomable="yes"}

1. WhatsApp メッセージの送信に使用する&#x200B;**[!UICONTROL 送信者名]**&#x200B;を選択します。

   電話番号の設定は自動的に入力されます。

   * **品質評価** – 過去24時間以内に送信されたメッセージに対する顧客からのフィードバックを反映します。
     * 緑色：高品質
     * 黄色：中品質
     * 赤色：低品質

     詳しくは、Meta ドキュメントの&#x200B;[_品質評価_](https://www.facebook.com/business/help/766346674749731#)を参照してください。

   * **スループット** – 電話番号がメッセージを送信できる割合を示します。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

_[!UICONTROL 送信]_&#x200B;をクリックすると、資格情報はすぐに検証および保存され、_[!UICONTROL API資格情報]_&#x200B;の一覧ページにリダイレクトされます。

送信された資格情報が無効な場合は、HTTP 500 エラーメッセージが表示されます。 この場合、設定をキャンセルするか、更新して再送信するかを選択できます。

+++HTTP 500 エラーのトラブルシューティング

WhatsApp API 資格情報の設定時に HTTP 500 エラーが発生した場合は、次のトラブルシューティング手順に従います。

1. Adobeの使用権限を確認する – 組織に&#x200B;_cjm_ whatsapp_の使用権限がプロビジョニングされていることを確認します。 この使用権限がないと、WhatsApp チャネルを設定できません。

1. ビジネスアカウントフィールドの検証 – すべての必須フィールドが正しいことを確認します。

   * API トークン – 適切な権限](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)を持つ有効な[Meta アクセストークンである必要があります。
   * Business Account ID - [Meta Business Account ID](https://www.facebook.com/business/help/1181250022022158?id=180505742745347)と正確に一致する必要があります。

1. 資格情報を外部でテストする – Meta APIを使用して資格情報を直接検証し、問題が資格情報に関するものであるか、Marketo Optimizerの資格情報処理に関するものであるかを確認します。

1. Adobeへのお問い合わせ – 環境と使用権限が有効であることが確認されたものの、HTTP 500 エラーが解決しない場合は、Adobe担当者にお問い合わせください。

+++

### WhatsApp Webhook を追加 {#configure-webhooks}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin-whatsapp-webhook-inbound-keyword-category"
>title="インバウンドキーワードカテゴリ"
>abstract="<b>オプトイン</b>：ユーザーが登録すると、定義済みの自動応答が送信されます。 <br/><b>オプトアウト</b>：ユーザーが登録解除すると、定義済みの自動応答が送信されます。 <br/><b>ヘルプ</b>：ユーザーがヘルプまたはサポートをリクエストした際に、定義済みの自動応答が送信されます。 <br/><b>デフォルト</b>：一致するキーワードがない場合に、フォールバック自動応答が送信されます。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_whatsapp-webhook-inbound-keyword"
>title="キーワードの入力"
>abstract="ユーザーがテキスト入力した内容に基づいて特定の自動応答をトリガーするキーワードを定義できます。 キーワードでは、大文字と小文字は区別されません（stop と STOP は同じように処理されます）。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin-whatsapp-webhook-webhook-url"
>title="コールバック URL"
>abstract="このオブジェクトの検証リクエストと Webhook 通知は、指定した URL に送信されます。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin-whatsapp-webhook-verify-token"
>title="トークンの検証"
>abstract="検証プロセス中にコールバック URL を確認および検証するのに Meta がエコーバックするトークン。"

Webhookを使用すると、Marketo Optimizerは、WhatsApp Business アカウントからインバウンドメッセージ、同意応答、配信通知を受け取ることができます。 Webhookを設定して、適切な同意管理とメッセージ追跡を確保します。

>[!NOTE]
>
>オプトインまたはオプトアウトのキーワードが指定されていない場合、標準の同意メッセージは有効になりません。

WhatsApp API資格情報が正常に作成されたら、webhookを設定できます。

1. ナビゲーションパネルで、**[!UICONTROL WhatsApp Webhook]**&#x200B;を選択します。

1. 「**[!UICONTROL Webhookを作成]**」をクリックします。

1. Webhook設定の&#x200B;**[!UICONTROL Name]**&#x200B;を入力します。

1. **[!UICONTROL 設定]**&#x200B;で、Webhookに関連付けるAPI資格情報（前のタスクで作成）を選択します。

1. **[!UICONTROL インバウンドキーワードカテゴリ]**&#x200B;で、キーワードと返信メッセージを定義するカテゴリを選択します。

   * **[!UICONTROL オプトイン]** - WhatsApp メッセージを受信するには、ユーザーが積極的に同意する必要があります。多くの場合、Web サイトまたはアプリのフォームを通じて管理されます。
   * **[!UICONTROL オプトアウト]** - `Stop`や`No Message`などのフレーズをリッスンするようにWebhookを設定して、ユーザーをオプトアウトとして自動的にマークします。
   * **[!UICONTROL ヘルプ]** - ユーザーが`HELP` （または`Unknown`などの類似キーワード）を送信するタイミングを自動システムで検出し、サービスの指示などの特定の情報を含む自動的に返信できるようにします。
   * **[!UICONTROL Default]** – 特定のキーワードに一致しない受信メッセージを処理します。 これは、Adobe Experience Platform データセットでトラッキングイベント（開封数や配信レポートなど）を有効にするフォールバックカテゴリとして機能します。

   キーワードカテゴリを選択すると、デフォルトのキーワードが入力されます。

1. **[!UICONTROL キーワードを入力]**&#x200B;するには、カスタムキーワードを入力し、_追加_ （**+**）をクリックします。

   カテゴリごとに複数のキーワードを追加できます。

   >[!NOTE]
   >
   >キーワードでは大文字と小文字が区別されません（`stop`と`STOP`は同じように扱われます）。

1. 受信したメッセージがこのカテゴリのキーワードと一致したときに自動的に送信するには、**[!UICONTROL 返信メッセージ]**&#x200B;を入力します。

   オプトインキーワードと返信メッセージを含む![WhatsApp設定のWebhook](assets/config-whatsapp-channels-webhooks.png){width="500" zoomable="yes"}

1. 設定する追加のキーワードカテゴリごとに、右上隅にある&#x200B;_追加_ （**+**）をクリックし、手順5 ～ 7を繰り返します。

1. **[!UICONTROL 送信]**&#x200B;をクリックして、Webhook設定を保存します。

### トークンとURLをコピーし {#copy-token-and-url}

Webhookが送信されたら、トークンとURL値を取得し、Metaに登録できます。

1. **[!UICONTROL WhatsApp Webhook]** リストで、作成したWebhookの名前をクリックします。

1. **[!UICONTROL Verify Token]**&#x200B;と&#x200B;**[!UICONTROL Webhook URL]**&#x200B;の値をコピーします。

   ![WhatsApp設定Webhook設定でURLをコピーし、トークンを検証する](assets/config-whatsapp-channels-webhooks-copy-token-url.png){width="500" zoomable="yes"}

1. [Meta for Developers ポータル ](https://developers.facebook.com/)で、WhatsApp アプリケーション設定に移動し、コピーした値を使用してWebhookを設定します。

### チャネル設定の作成 {#create-channel-configuration}

チャネル設定では、ジャーニーアクションノードからWhatsApp メッセージを送信する際に使用される配信設定を定義します。

1. ナビゲーションパネルの&#x200B;_[!UICONTROL 一般設定]_&#x200B;で、**[!UICONTROL チャネル設定]**&#x200B;を選択します。

   ![ チャネル設定リスト ](./assets/config-whatsapp-channels-general.png){width="600" zoomable="yes"}

1. 右上の「**[!UICONTROL チャネル設定を作成]**」をクリックします。

1. 設定に「**[!UICONTROL 名前]**」と「**[!UICONTROL 説明]**」（オプション）を入力します。

   >[!NOTE]
   >
   >名前は文字（A ～ Z）で始まる必要があり、英数字、アンダースコア （`_`）、ドット （`.`）、ハイフン （`-`）のみを含めることができます。

1. **[!UICONTROL チャネルを選択]**&#x200B;するには、`WhatsApp`を選択します。

   顧客のプリファレンスを尊重するため、選択したマーケティングアクションに関連するあらゆる同意ポリシーが自動的に活用されます。 例えば、ジャーニーでその設定を使用しているWhatsApp メッセージは、WhatsApp メッセージの受信に同意したプロファイルにのみ送信されます。 これらのコミュニケーションの受信に同意しないプロファイルは除外されます。

1. _[!UICONTROL WhatsApp Settings]_&#x200B;で、前のタスクで作成した&#x200B;**[!UICONTROL WhatsApp設定]** （API資格情報）を選択します。

1. メッセージ配信に使用する&#x200B;**[!UICONTROL 送信者の電話番号]**&#x200B;を入力します。

   ![WhatsApp チャネル設定の詳細](assets/config-whatsapp-channels-general-create.png){width="500" zoomable="yes"}

1. （現在Marketo Optimizerには適用されません） **[!UICONTROL WhatsApp Execution フィールド]**&#x200B;で、受信者に複数の電話番号が使用可能な場合に優先電話番号として使用するプロファイル属性を選択します。

1. **[!UICONTROL 送信]**&#x200B;をクリックして保存するか、**[!UICONTROL ドラフトとして保存]**&#x200B;をクリックして、後で設定を完了して送信します。

検証チェックの実行時に、設定は最初に&#x200B;_処理中_ ステータスで表示されます。 すべてのチェックが合格すると、ステータスは&#x200B;**_アクティブ_**&#x200B;に変更され、マーケターがジャーニーアクションでWhatsApp メッセージを作成するときに設定を選択できる状態になります。