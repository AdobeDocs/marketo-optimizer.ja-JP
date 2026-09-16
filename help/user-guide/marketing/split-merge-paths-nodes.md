---
title: パスの分割と結合ノード
description: 対面ジャーニーで分割および結合パスノードを使用して、定義された条件に基づいて個別のパスにユーザーをセグメント化し、ダウンストリームの共通ポイントでユーザーを再結合する方法を説明します。
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: bc370a501d3f8ff80ad846576b62504aca77f530
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%
---
# パスノードの分割と結合

個人ジャーニーで「パスを分割」ノードと「パスを結合」ノードを使用して、定義した条件に基づいて個人を個別のパスにセグメント化し、それらのパスを結合してジャーニーを続行できるようにします。 分割パスを使用すると、特定のオーディエンスセグメントに合わせてアクションやイベントをカスタマイズできます。また、結合パスを使用すると、共通ポイントでそれらのセグメントを組み合わせることができます。

## パス ノードの分割

分割ノードを使用して、定義した条件に従ってユーザーをセグメント化します。 条件に従ってオーディエンスリストのパスを作成し、セグメントのアクションノードとイベントノードで各パスを定義し、パスを組み合わせてジャーニーを続行します。

「パスを分割」ノードは、人物フィルターに基づいて、1つ以上のセグメント化されたパスを定義します。

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**スプリットパスノード関数**_&#x200B;の仕組み

* 各パスの評価は上から下まで行われます。 人が1番目と2番目のパスに一致した場合、最初のパスに沿ってのみ進みます。
* ノードは、_その他のユーザー_ パスの定義をサポートしています。このパスでは、定義されたセグメントまたはパスのいずれかに一致しないユーザーのアクションまたはイベントを追加できます。

### 一致する人物フィルター

ノードに定義するパスごとに、次のフィルタータイプを使用して、1つ以上の条件に従ってユーザーを一致させます。

| フィルター | 説明 |
| ------- | ----------- |
| アクティビティ履歴 | 選択した1つ以上の項目を使用して評価される条件に基づくアクティビティ |
| Brand Concierge | [!DNL Brand Concierge]とエンゲージするリードのアクティビティ。 |
| 会社属性 | 会社/アカウントプロファイルの属性（以下を含む）: <li>[!UICONTROL 年間売上高] <li>[!UICONTROL 会社名] <li>[!UICONTROL 請求先の国] <li>[!UICONTROL 業界] <li>[!UICONTROL 従業員数] <li>[!UICONTROL SIC コード ] <li>[!UICONTROL 都道府県] |
| インテントデータ | 人物プロファイルに関連付けられたインテントデータにもとづく属性。 |
| 商談 | 個人プロファイルに関連する機会に基づくステータスと属性（次を含む）: <li>[!UICONTROL 商談]あり <li>[!UICONTROL 商談件数] <li>[!UICONTROL 商談の合計金額] <li>[!UICONTROL が商談]に追加されました <li>[!UICONTROL が商談]から削除されました |
| 顧客属性 | B2B人物プロファイルの属性（以下を含む）: <li>[!UICONTROL 都市] <li>[!UICONTROL 国] <li>[!UICONTROL 生年月日] <li>[!UICONTROL 電子メールアドレス ] <li>[!UICONTROL 電子メールが無効です] <li>[!UICONTROL 電子メールが停止されました] <li>[!UICONTROL 名] <li>[!UICONTROL 推測状態領域] <li>[!UICONTROL 役職] <li>[!UICONTROL 姓] <li>[!UICONTROL 携帯電話番号] <li>[!UICONTROL ユーザーエンゲージメントスコア] <li>[!UICONTROL 電話番号] <li>[!UICONTROL 郵便番号] <li>[!UICONTROL 都道府県] <li>[!UICONTROL 登録解除済み] <li>[!UICONTROL 登録解除の理由] |
| セールスアプリ | [!DNL Sales Qualifier]または[!DNL Marketo Sales Insights]に関連するリード アクティビティ。 |
| 特殊なフィルター | 定義済みのカテゴリに該当しない属性をフィルタリングして、カスタムまたは様々なフィルター条件に柔軟に対応できます。 |

>[!BEGINSHADEBOX]

**条件フィルター**&#x200B;の[!DNL Marketo Optimizer] アクティビティをサポートしました

パス条件の場合、[!DNL Marketo Optimizer]は、データソースとして接続されている[!DNL Marketo Engage] インスタンスのアクティビティをサポートします。

>[!NOTE]
>
>データソースとして使用できる[!DNL Marketo Engage] インスタンスは1つだけで、[!DNL Marketo Optimizer] インスタンスのプロビジョニング時に事前に設定されています。

次の[!DNL Marketo Engage] アクティビティに関する条件を作成できます。

* **[!UICONTROL Marketo Engage フォームに入力]** – 特定の[!DNL Marketo Engage] フォームを完了したリードと、非エイジアウトのアクティビティログの任意の時点で一致します。
* **[!UICONTROL 訪問したMarketo Engageのweb ページ]** - web サイトまたは[!DNL Marketo Engage]のランディングページで特定のURLを閲覧したリードと一致します。 サイトにインストールされているMunchkinトラッキングコードを使用して直接機能します。
* **[!UICONTROL Marketo Engage web ページでリンクをクリック]** – 追跡されたページで特定のリンクまたはアセットをクリックしたリードと一致します。
* **[!UICONTROL 様がMarketo Engageの電子メールを送信しました]** - [!DNL Marketo Engage]様が特定の電子メールを送信しようとしたリードと一致し、ハードバウンスまたはサーバーの承認に先立つデプロイメントアクションを考慮します。
* **[!UICONTROL 様がMarketo Engage電子メールを配信されました]** - メールサーバー（MX）が[!DNL Marketo Engage]送信元サーバーに成功応答（250 OK メッセージ）を返したリードと一致します。
* **[!UICONTROL Marketo Engage電子メールのバウンス]** – 特定の電子メール送信で、または特定の期間内にハードバウンス（永続的な配信エラー）が発生したリードと一致します。
* **[!UICONTROL Marketo Engage電子メールのバウンス率がソフト]** – 電子メールのハードバウンスが永続的ではなく、一時的な配信エラー（受信トレイがいっぱいになっている、オフラインのサーバーなど）が発生したリードと一致します。
* **[!UICONTROL Marketo Engage メールの購読解除]** – 非運用マーケティングメールをオプトアウトしたリードと一致します。 これが発生すると、[!DNL Marketo Engage]はリードの`Unsubscribed` フィールド値を自動的に`true`に更新し、今後の標準メール送信からそれらを除外します。
* **[!UICONTROL Marketo Engage電子メールを開封]** – 追跡された[!DNL Marketo Engage]電子メールを開封したリードと一致します。
* **[!UICONTROL Marketo Engage電子メール内のリンクをクリック]** - [!DNL Marketo Engage]電子メール内の任意のリンク（または特定のリンク）をクリックしたリードと一致します。

>[!ENDSHADEBOX]

### 分割パスノードの追加

1. ジャーニーキャンバスに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL パスを分割]**」を選択します。

   ![ ジャーニーパスの追加アイコンをクリック ](./assets/person-journey-canvas-add-node.png){width="200"}

1. _[!UICONTROL パス 1]_&#x200B;に適用できる条件を定義するには、「**[!UICONTROL 条件を適用]**」をクリックします。

1. 分割パスを定義するには、条件エディターで1つ以上のフィルターを追加します。

   * 左側のナビゲーションから人物フィルターのいずれかをドラッグ&amp;ドロップして、一致定義を完了します。

   * フィルターの一致を絞り込むために使用する各制約の&#x200B;**[!UICONTROL 制約を追加]**&#x200B;をクリックします。

     ![ パスを分割ノード – パス条件に一致する人物フィルター](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * 上部の&#x200B;**[!UICONTROL フィルターロジック]**&#x200B;を適用して、条件を絞り込みます。 すべての条件または1つの条件を一致させます。

   * 「**[!UICONTROL 完了]**」をクリックします。

1. パスをさらに追加するには、**[!UICONTROL パスを追加]**&#x200B;をクリックし、前の手順を繰り返して、パスに適用できる条件を追加します。

   これらの条件に基づいて各パスにラベルを付けることも、デフォルトのラベルを使用することもできます。

1. 必要に応じて、分割する優先度に従ってパスを並べ替えます。

   パスのフィルタリングは、トップダウンの順序で評価されます。 各人は一致する最初のパスに沿って進みます。

   各パスカードの右上にある上下の矢印をクリックして、パスのリストで上下に移動します。

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. 定義されたパスと一致しないユーザーのデフォルトパスを追加するには、**[!UICONTROL その他のユーザー]** オプションを有効にします。

   このオプションが有効になっていない場合、定義されたセグメント/パスに一致しないユーザーは分割を超えて、ジャーニーの次のステップに進みます。

各パスに条件を定義している場合は、パス上のユーザーに適用するアクションノードまたはイベントノードを追加できます。

## パス ノードを結合

1. ジャーニーキャンバスに移動し、2つ以上のパスを持つ分割パスノードを見つけます。

   各パスには、アクションノードとイベントノードの組み合わせが必要です。

1. これらのパスの最後にあるプラス（**+**）アイコンをクリックし、表示されたオプションから「**[!UICONTROL パスを結合]**」を選択します。

1. 右側のノードプロパティで、結合するパスを選択します。

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   この時点で、パスが結合され、選択したパスのユーザーが単一のパスに結合され、ジャーニーを進み続けることができます。

1. 必要に応じて、結合パスのノードプロパティに戻り、削除するパスのチェックボックスをオフにすることで、パスを結合できます。