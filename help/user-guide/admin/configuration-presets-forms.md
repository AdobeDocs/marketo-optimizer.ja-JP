---
title: Formsの設定
description: プレースホルダー
TQID: 'https://experienceleague.adobe.com/7X5-67hfrjRjWbGjq9duLu7mVjgfCs7tpAQLV8u6YKE'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: f65df8d5e83eca29ffaaabf51e7c80ed223d175a
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 27%
---
# Forms設定

マーケターがランディングページで使用するフォームを作成して公開するには、事前に1つ以上の専用プリセットを作成する必要があります。 各プリセットは、フォーム送信データの送信に使用される接続エンドポイントと、キャプチャしたデータの保存に使用されるデータセットを定義します。

データがストリーミングエンドポイントに到達すると、データセット情報にリンクされます。 生成されたソース／ターゲット接続とソースフローを使用すると、データがデータセットにプッシュされます。

>[!BEGINSHADEBOX]

## 前提条件

Web フォームを使用するには、Adobe Experience Platformで1つ以上の&#x200B;_&#x200B;**HTTP API ストリーミング接続**&#x200B;_&#x200B;を定義する必要があります。 使用する各接続が次の要件を満たしていることを確認します。

* データ型はXDMに設定する必要があります（Raw データではありません）
* 認証は無効にする必要があります（認証されていない接続）

ストリーミングソース接続の作成について詳しくは、[_Experience Platform ドキュメント_](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/streaming/http)を参照してください。

[!DNL Marketo Optimizer]のForms チャネル設定には、次の[権限](../start/permissions-reference.md)が必要です。

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL B2B Forms プリセットを表示]_ - フォームプリセット設定を表示するには必須です。
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL B2B Forms プリセットの管理]_ - フォームプリセット設定の作成、編集、削除に必要です。
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL B2B Forms プリセットを公開]_ - フォームプリセット設定を公開するために必要です。

>[!ENDSHADEBOX]

## フォームプリセット設定のガイドライン

プリセットの作成時：

* データセットとストリーミング接続の異なる組み合わせを使用して、複数のプリセットを設定できます。

* 複数のプリセットで同じデータセットまたはストリーミング接続を再利用できます。

* 各ストリーミング接続は、次のようなリソースを自動的に生成します。

  * _ソース接続_ - データの発生元。
  * _ターゲット接続_ - データが保存または使用される場所。
  * _Source フロー_ - ソース接続からExperience Platformにデータを移動するパイプライン。 マッピング、変換、検証を処理します。

## フォームプリセットを作成 {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="使用するエンドポイントを選択"
>abstract="フォーム送信時にデータが送信されるストリーミングエンドポイントを定義します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="HTTP API ストリーミング接続を作成"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="データセットを選択"
>abstract="フォームの応答を保存および反映するデータセットを定義します。 テキストを入力して特定のデータセットを検索するか、リストから選択できます。"

1. 左側のナビゲーションで、**[!UICONTROL 管理]** > **[!UICONTROL チャネル]**&#x200B;に移動します。

1. ナビゲーションパネルの&#x200B;_[!UICONTROL フォーム設定]_&#x200B;で、**[!UICONTROL フォームプリセット]**&#x200B;を選択します。

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. 「**[!UICONTROL フォームプリセットを作成]**」をクリックします。

1. 設定に一意の&#x200B;**[!UICONTROL 名前]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

   >[!NOTE]
   >
   >名前は文字（A ～ Z）で始める必要があり、英数字のみを含めることができます。 アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. **[!UICONTROL ストリーミング接続]**&#x200B;を選択します。

   この接続は、web ビューアがフォームを送信するときにデータを送信するために使用されるストリーミングエンドポイントです。 必要なストリーミング接続がリストに表示されない場合は、要件が満たされていることを確認します。

1. _データセットを選択_ （![&#x200B; データセットを選択アイコン &#x200B;](../assets/do-not-localize/icon-select-data.svg)）アイコンをクリックして、データセットをフォームにリンクします。

   データセットは、フォームの応答が保存され、反映される場所です。 特定のデータセットを検索するためのテキスト文字列を入力するか、リストから選択できます。

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >現在、選択できるのは、プロファイルが有効な[Adobe Experience Platform データセット &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)とプロファイルが無効なデータセットのみです。 一度に1つのデータセットを選択できます。 フォームデータの保存にシステムデータセットは使用できません。

   データセットのチェックボックスを選択し、**[!UICONTROL 選択]**&#x200B;をクリックします。

1. 「**[!UICONTROL ドラフトとして保存]**」をクリックします。

## フォームプリセットの公開

1. フォームプリセット名をクリックして、設定ページを開きます。

   必要に応じて、ドラフトを調整できます。

1. 「**[!UICONTROL 公開]**」をクリックします。

   フォームプリセットが&#x200B;_公開済み_ ステータスで一覧表示されている場合、フォーム作成に使用できます。
