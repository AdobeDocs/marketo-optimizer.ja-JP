---
title: 人物オーディエンスジャーニーノード
description: Journey Optimizer B2Bの人物オーディエンスノードを設定して、動的な人物リストまたはイベントベースのオーディエンスを使用して、ジャーニーに参加するプロファイルを指定します。
TQID: 'https://experienceleague.adobe.com/WqM-yLPadt6lBFtqJOGUxDtk0fm6n6S29wQTRSWB8fY'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 0%

---

# 人物オーディエンスノード

_人物オーディエンス_ ノードは、ジャーニーにエントリする人物プロファイルを指定します。 ユーザーのジャーニー[を作成する場合、ジャーニーは常に、入力を定義するユーザーのオーディエンスノードから始まります。 ](./person-journeys.md)人物オーディエンスノードには、動的な人物リストまたはイベントトリガーの2つのオーディエンス入力タイプのいずれかを使用できます。

ユーザージャーニーに必要な動的ユーザーリストが既に存在しない場合は、[ ユーザーリストを作成](../audiences/people-lists.md#create-a-people-list)してから、ユーザーオーディエンスノードを設定します。

_ジャーニーオーディエンスを設定するには&#x200B;:_

1. 「**[!UICONTROL 人物オーディエンス]**」ノードをクリックします。

   このアクションは、右側にノードプロパティを表示します。

   ![人物オーディエンスジャーニーノード ](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. 人物オーディエンスに対して、次のいずれかのオーディエンス設定オプションを使用します。

   * **[!UICONTROL 動的リスト]** – 動的なルールベースの人物リストを使用します。 リストルールは、ジャーニー実行時に評価され、ジャーニーのメンバーが選定されます。 後で動的リストの資格を失ったユーザーは、ジャーニーから削除されません。 _[動的リスト](../audiences/people-lists.md#dynamic-lists)_&#x200B;を参照してください。

   * **[!UICONTROL イベントオーディエンス]** - イベントオーディエンスを使用すると、条件を満たすイベントに基づいてジャーニーオーディエンスを定義できます。 イベント条件による人物プロファイルフィルタリングとトリガージャーニー入力を使用して、オーディエンスメンバーを定義します。 _[イベントベースのオーディエンス](../audiences/event-based-audiences.md)_&#x200B;を参照してください。