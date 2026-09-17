---
title: イベントノードをリッスン
description: Marketo Optimizerでイベントノードのリッスンを設定 – イベントトリガーを設定し、オプションのフィルターを適用して、アクティビティやデータの変更が発生したときにユーザーを促します。
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: bc370a501d3f8ff80ad846576b62504aca77f530
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 3%
---
# イベントノードをリッスンします

イベントが発生したときにオーディエンスをジャーニーの次のステップに進めるには、「_イベントをリッスン_」ノードを追加します。

## イベントトリガー {#event-triggers}

ジャーニーノードを起動し、オーディエンスメンバーを前進させるイベント基準を定義します。

| トリガー | 説明 |
| -------- | ----------- |
| Brand Concierge | [!DNL Brand Concierge]とエンゲージするリードのアクティビティ。 |
| メール | リードのメールアクティビティ（送信、配信、エンゲージメントなど）。 |
| イベント | 登録、出席、インタラクションなど、リード向けのインタラクティブなウェビナーアクティビティ。 |
| 商談 | リードまたはアカウントに関連付けられた商談レコードに関連するアクティビティ。 |
| セールスアプリ | [!DNL Sales Qualifier]または[!DNL Marketo Sales Insights]に関連するリード アクティビティ。 |
| その他 | 定義済みのカテゴリに該当しないアクティビティは、カスタム イベントまたはその他のイベント トリガーに柔軟に対応します。 |

>[!BEGINSHADEBOX]

**トリガーでサポートされているMarketo Engage アクティビティ**

イベントをトリガーする場合、[!DNL Marketo Optimizer]は、データソースとして接続されている[!DNL Marketo Engage] インスタンスのアクティビティをサポートします。

>[!NOTE]
>
>データソースとして使用できる[!DNL Marketo Engage] インスタンスは1つだけで、[!DNL Marketo Optimizer] インスタンスのプロビジョニング時に事前に設定されています。

次の[!DNL Marketo Engage] アクティビティを中心にイベントトリガーを作成できます。

* **[!UICONTROL Marketo Engage フォームに入力]** - リードが指定した[!DNL Marketo Engage] フォームを送信するとアクティベートされます。
* **[!UICONTROL Marketo Engage web ページにアクセス]** - Munchkin トラッキング Cookieを持つリードが指定されたweb ページにアクセスするとアクティベートされます。
* **[!UICONTROL Marketo Engage web ページ上のリンクをクリック]** - [!DNL Marketo Engage] Munchkin トラッキングコードがインストールされているweb ページ上で、リードがトラッキングされたハイパーリンクをクリックするとアクティベートされます。
* **[!UICONTROL Marketo Engage電子メールが配信されます]** - リードのメールサーバー（MX）が、[!DNL Marketo Engage]送信サーバーに成功応答（250 OK メッセージ）を返したときに起動します。
* **[!UICONTROL Marketo Engage電子メールバウンス]** - ターゲットメールサーバーが、送信された[!DNL Marketo Engage]電子メールメッセージを、無効なユーザーや不明なドメインなどの永続的なエラーとして拒否するとアクティベートされます。
* **[!UICONTROL Marketo Engage電子メールのバウンスがソフト]** - ターゲットメールサーバーが、送信された[!DNL Marketo Engage]電子メールメッセージを一時的な問題（サーバービジーまたはメールボックスがいっぱいなど）として拒否したときに発生します。 [!DNL Marketo Engage]は、問題をフラグ付けする前に、MX サーバーを通じてソフトバウンスを最大3回自動的に再試行します。
* **[!UICONTROL Marketo Engage メールの購読解除]** - リードが非運用マーケティングメールをオプトアウトするとアクティベートされます。 トリガーされると、[!DNL Marketo Engage]はリードの`Unsubscribed` フィールド値を自動的に`true`に更新し、今後の標準メール送信からそれらを除外します。
* **[!UICONTROL Marketo Engage電子メールを開く]** - リードがトラッキングされた[!DNL Marketo Engage]電子メールを開いたときに起動します。
* **[!UICONTROL Marketo Engage電子メール内のリンクをクリック]** - リードが[!DNL Marketo Engage]電子メール内の任意のリンク（または特定の制約付きリンク）をクリックするとアクティベートされます。

>[!ENDSHADEBOX]

## イベントフィルター {#event-filters}

フィルタリングを含めて、様々な条件に基づいて一致するイベントトリガーを制限できます。

| フィルター | 説明 |
| ------- | ----------- |
| アクティビティ履歴 | 選択した1つ以上の項目を使用して評価される条件に基づくアクティビティ |
| Brand Concierge | [!DNL Brand Concierge]とエンゲージするリードのアクティビティ。 |
| 会社属性 | 会社/アカウントプロファイルの属性（以下を含む）: <li>[!UICONTROL 年間売上高] <li>[!UICONTROL 会社名] <li>[!UICONTROL 請求先の国] <li>[!UICONTROL 業界] <li>[!UICONTROL 従業員数] <li>[!UICONTROL SIC コード &#x200B;] <li>[!UICONTROL 都道府県] |
| インテントデータ | 人物プロファイルに関連付けられたインテントデータにもとづく属性。 |
| 商談 | 個人プロファイルに関連する機会に基づくステータスと属性（次を含む）: <li>[!UICONTROL 商談]あり <li>[!UICONTROL 商談件数] <li>[!UICONTROL 商談の合計金額] <li>[!UICONTROL が商談]に追加されました <li>[!UICONTROL が商談]から削除されました |
| 顧客属性 | B2B人物プロファイルの属性（以下を含む）: <li>[!UICONTROL 都市] <li>[!UICONTROL 国] <li>[!UICONTROL 生年月日] <li>[!UICONTROL 電子メールアドレス &#x200B;] <li>[!UICONTROL 電子メールが無効です] <li>[!UICONTROL 電子メールが停止されました] <li>[!UICONTROL 名] <li>[!UICONTROL 推測状態領域] <li>[!UICONTROL 役職] <li>[!UICONTROL 姓] <li>[!UICONTROL 携帯電話番号] <li>[!UICONTROL ユーザーエンゲージメントスコア] <li>[!UICONTROL 電話番号] <li>[!UICONTROL 郵便番号] <li>[!UICONTROL 都道府県] <li>[!UICONTROL 登録解除済み] <li>[!UICONTROL 登録解除の理由] |
| セールスアプリ | [!DNL Sales Qualifier]または[!DNL Marketo Sales Insights]に関連するリード アクティビティ。 |
| 特殊なフィルター | 定義済みのカテゴリに該当しない属性をフィルタリングして、カスタムまたは様々なフィルター条件に柔軟に対応できます。 |

>[!BEGINSHADEBOX]

**フィルターでサポートされているMarketo Engage アクティビティ**

トリガーされたイベントをフィルタリングする場合、[!DNL Marketo Optimizer]は、データソースとして接続されている[!DNL Marketo Engage] インスタンスからのアクティビティをサポートします。

>[!NOTE]
>
>データソースとして使用できる[!DNL Marketo Engage] インスタンスは1つだけで、[!DNL Marketo Optimizer] インスタンスのプロビジョニング時に事前に設定されています。

次の[!DNL Marketo Engage] アクティビティを中心にイベントフィルターを作成できます。

* **[!UICONTROL Marketo Engage フォームに入力]** – 特定の[!DNL Marketo Engage] フォームを完了したリードと、非エイジアウトのアクティビティログの任意の時点で一致します。
* **[!UICONTROL 訪問したMarketo Engageのweb ページ]** - web サイトまたは[!DNL Marketo Engage]のランディングページで特定のURLを閲覧したリードと一致します。 サイトにインストールされているMunchkinトラッキングコードに直接依存します。
* **[!UICONTROL Marketo Engage web ページでリンクをクリック]** – 追跡されたページで特定のリンクまたはアセットをクリックしたリードと一致します。
* **[!UICONTROL 様がMarketo Engageの電子メールを送信しました]** - [!DNL Marketo Engage]様が特定の電子メールを送信しようとしたリードと一致し、ハードバウンスまたはサーバーの承認に先立つデプロイメントアクションを考慮します。
* **[!UICONTROL 様がMarketo Engageの電子メールを配信しました]** - メールサーバー（MX）が[!DNL Marketo Engage]の送信サーバーに成功応答（250 OK メッセージ）を返したリードと一致します。
* **[!UICONTROL Marketo Engage電子メールがバウンスしました]** – 特定の電子メール送信で、または期間内にハードバウンス（永続的な配信エラー）が発生したリードと一致します。
* **[!UICONTROL Marketo Engage電子メールのバウンス率がソフト]** – 電子メールのハードバウンスが永続的ではなく、一時的な配信エラー（受信トレイがいっぱいになっている、オフラインのサーバーなど）が発生したリードと一致します。
* **[!UICONTROL Marketo Engage メールの購読解除]** – 非運用マーケティングメールをオプトアウトしたリードと一致します。 これが発生すると、[!DNL Marketo Engage]はリードの`Unsubscribed` フィールド値を自動的に`true`に更新し、今後の標準メール送信からそれらを除外します。
* **[!UICONTROL Marketo Engage電子メールを開封]** – 追跡された[!DNL Marketo Engage]電子メールを開封したリードと一致します。
* **[!UICONTROL Marketo Engage電子メール内のリンクをクリック]** - [!DNL Marketo Engage]電子メール内の任意のリンク（または特定のリンク）をクリックしたリードと一致します。

>[!ENDSHADEBOX]

## イベントノードの追加 {#add-event-node}

1. ジャーニーキャンバスに移動します。

1. パスのプラス（**+**）アイコンをクリックし、**[!UICONTROL イベントをリッスン]**&#x200B;を選択します。

   ![&#x200B; ジャーニーパスの追加アイコンをクリック &#x200B;](./assets/person-journey-canvas-add-node.png){width="200"}

1. 右側のノードプロパティで、**[!UICONTROL イベント条件を追加]**&#x200B;をクリックします。

1. _[!UICONTROL イベントを編集]_ ダイアログで、イベントを追加し、トリガーに一致させる制約を設定します。

   イベントトリガーをビルダースペースにドラッグ&amp;ドロップして、定義を設定します。 イベントの一致を絞り込むために使用する各制約について、**[!UICONTROL 制約を追加]**&#x200B;をクリックします。

   ![&#x200B; イベントを編集 – イベントトリガー](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   一致するように複数のイベントを追加できます。 最初の適格イベントは、ジャーニー内で人物プロファイルを前進させます。

1. （オプション）「**[!UICONTROL フィルター]**」タブを選択し、トリガーのフィルタリング条件を追加します。

   フィルターをビルダースペースにドラッグ&amp;ドロップし、定義を設定します。 フィルターの一致を絞り込むために使用する各制約の&#x200B;**[!UICONTROL 制約を追加]**&#x200B;をクリックします。

   ![&#x200B; イベントを編集 – イベントフィルタリング &#x200B;](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

   任意の時点で、**[!UICONTROL イベントを編集]**&#x200B;をクリックして、ノードのイベント条件を変更できます。

1. 必要に応じて、**[!UICONTROL タイムアウト]** オプションを設定して、イベントをリッスンする期間を制限します。

   >[!NOTE]
   >
   >タイムアウトパスを定義しない限り、ジャーニーはタイムアウト後に終了します。このパスでは、他のノードを追加できます。

   「**[!UICONTROL タイムアウト]**」オプションを有効にし、ジャーニーがタイムアウトする前にイベントが発生するのを待機する期間を選択します。

   ![&#x200B; イベントジャーニーノードの「リッスン」に対してタイムアウトオプションが有効になっています](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}

   ここでパスを終了するか、別のパスを設定して別のアクションを実行するかを選択できます。 イベントが発生しない場合にプロファイルに適用できるアクションとイベントを追加できるジャーニーに新しいパスを作成するには、「**[!UICONTROL タイムアウトパスを設定]**」チェックボックスをオンにします。
