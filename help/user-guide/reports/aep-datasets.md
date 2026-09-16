---
title: Experience Platform データセット
description: Marketo OptimizerがAdobe Experience Platformに書き込むデータセットについて説明します。Customer Journey Analyticsのレポートとアドホッククエリを強化します。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 1ebb0036699252c50f33ba6c0f4a56e8e670aacd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 4%
---

# Experience Platform データセット

[!DNL Adobe Marketo Optimizer]は、リード、ジャーニー、およびアクティビティのデータを[!DNL Adobe Experience Platform]個のデータセットにレプリケートします。 これらのデータセットは、[!UICONTROL Reports] ページと組み込み[!DNL Adobe Customer Journey Analytics] レポートエクスペリエンスに役立ちます。 アドホック分析のために[!DNL Query Service]を使用して直接クエリすることもできます。

データセットはシステム管理です。 [!DNL Customer Journey Analytics]の接続は、[!DNL Marketo Optimizer]のレポートが使用するデータビューにそれらをリンクするので、この接続を自分で構築する必要はありません。 この接続は、レポートセクションで「**[!UICONTROL CJAで分析]**」を選択した場合に到達するのと同じ接続です。 [Customer Journey Analyticsでのレポートの分析](./reports-overview.md#analyze-a-report-in-cja)を参照してください。

## 使用可能なデータセット {#available-datasets}

次のデータセットは、[!DNL Marketo Optimizer] インスタンスごとに入力されます。

>[!NOTE]
>
>各データセット名は、接頭辞`AJOB2B`を使用します。これは、[!DNL Marketo Optimizer] データのシステム名を示します。 この動作は想定されており、これらの名前を使用して、[!DNL Experience Platform] サンドボックス内のデータセットを検索できます。

| データセット | スキーマ | 説明 |
| --- | --- | --- |
| `AJOB2B - Person` | 顧客 | 標準リード属性： |
| `AJOB2B - PersonActivity` | 人物アクティビティ | 個人に関連付けられたアクティビティイベント。 |
| `AJOB2B - PersonActivityType` | 人物アクティビティタイプ | 個人に関連付けられたアクティビティタイプ。 |
| `AJOB2B - PersonActivityTypeEngagementMapping` | 人物アクティビティタイプのエンゲージメントマッピング | アクティビティタイプを、エンゲージメント分類、チャネルイベント、方向性にマッピングします。 |
| `AJOB2B - Journey` | ジャーニー | ジャーニーとそのライフサイクルメタデータのリスト。 |
| `AJOB2B - JourneyNode` | ジャーニーノード | ジャーニー内のノードと関連するメタデータのリスト。 |
| `AJOB2B - EngagementAsset` | エンゲージメントアセット | エンゲージメントアセットのタイプをまたいで、エンゲージメントアセット IDと表示名の統合ルックアップ。 |

## Adobe Experience Platform Query Serviceのクエリ機能 {#query-service}

[!DNL Customer Journey Analytics]個のレポート以外で分析が必要な場合は、[!DNL Query Service]を使用して、これらのデータセットに対してアドホック SQL クエリを実行します。 クエリ アクセスには、サンドボックスに適切な[!DNL Experience Platform]権限が必要です。 一般的なクエリの構文と設定については、[&#x200B; クエリサービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home){target="_blank"}を参照してください。

![ajob2b_journey データセットに対するSELECT クエリと、結果のジャーニーレコードのテーブルを表示するクエリサービスエディター。](./assets/aep-query-service.png){width="800" zoomable="yes"}

>[!NOTE]
>
>これらのデータセットは読み取り専用です。 データ [!DNL Marketo Optimizer]がキャプチャするデータを変更するには、データセットを直接編集する代わりに、[!DNL Marketo Optimizer]または[!DNL Marketo Engage]のソースデータを更新します。
