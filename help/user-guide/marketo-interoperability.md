---
title: Marketo Engageとの相互運用性
description: データ、アクティビティ、オーディエンスなど、Marketo OptimizerがMarketo Engageと共有する内容と、ジャーニーのどちらの商品からもメールを送信する方法について説明します。
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# Marketo Engageとの相互運用性

[!DNL Adobe Marketo Optimizer]と[!DNL Adobe Marketo Engage]は、データ、一部のアクティビティ、およびオーディエンスを共有しています。 アセットを分離します。 各製品が何を共有しているかを把握し、マーケティングをどこで構築して配信するかを決定できます。

## 製品間で共有 {#shared}

* [!DNL Marketo Engage]件のリードとアクティビティが[!DNL Marketo Optimizer]に自動的にフローされます。
* ジャーニーは[!DNL Marketo Engage]件のアクティビティをリッスンできます。
* イベントベースのオーディエンスには、[!DNL Marketo Engage]件のアクティビティを実行するユーザーを含めることができます。
* ジャーニー操作は[!DNL Marketo Engage]とやり取りできます。 ユーザーを[!DNL Marketo Engage] リストに追加またはリストから削除し、[!DNL Marketo Engage] キャンペーンをリクエストできます。
* [!UICONTROL &#x200B; スコアリングスタジオ &#x200B;]は、[!DNL Marketo Engage]および[!DNL Marketo Optimizer]のアクティビティに対してユーザーをスコアリングします。 [!DNL Marketo Engage]のスコアを使用できます。
* どちらの製品もIP アドレスとサブドメインを共有します。
* 統合された会話型レポートは両方の製品をカバーしています。

## 個別に保持 {#separate}

* **Assets:**&#x200B;電子メール、テンプレート、プログラム、および画像は、別々のリポジトリにあります。
* **アクティビティ：** [!DNL Marketo Optimizer]件のアクティビティが[!DNL Marketo Engage]に共有されません。
* **フィールドと制限：**&#x200B;個のペルソナ フィールドは、[!DNL Marketo Optimizer]さんが取得するもので、[!DNL Marketo Engage]では使用できません。 通信制限は、各製品で個別に設定されます。

同期の詳細については、[&#x200B; エンティティの同期](./data-architecture.md#entity-sync)を参照してください。

## Marketo Engageからメールを送信 {#send-from-marketo}

このアプローチを使用すると、[!DNL Marketo Engage]さんがメールを1通ずつ送信しながら、[!DNL Marketo Optimizer]でジャーニー、待機手順、AIによる意思決定を実行できます。

1. [!DNL Marketo Optimizer]で、待機ステップとAIによる意思決定を含むジャーニーを構築します。
1. 各送信ステップについて、**[!UICONTROL Marketo Engage キャンペーンをリクエスト]** アクションを追加し、一致する[!DNL Marketo Engage] キャンペーンを選択します。
1. オプション：ジャーニー全体の成功レポートを集計するために、[!DNL Marketo Engage]にデフォルトの包括的なプログラムを追加します。

アクションの詳細については、[&#x200B; アクションノードの実行](./marketing/action-nodes.md)を参照してください。

[!DNL Marketo Engage]は、既存のチャネル設定を通じてメールを送信します。 [!DNL Marketo Engage]は電子メールを送信するので、[!DNL Marketo Optimizer]ではチャネルまたは電子メールを設定しません。 さらに：

* 送信、開封、クリックは[!DNL Marketo Engage]に記録されます。
* 購読解除の管理とメール ガバナンスが[!DNL Marketo Engage]に適用されます。
* メールアクティビティは、既存の[!DNL Marketo Engage] スコアリングキャンペーンにフィードします。
* アクティビティによってトリガーされたSalesforceの同期キャンペーンが期待どおりに実行されます。
* 各マップは[!DNL Marketo Engage] キャンペーンに送信されるので、メールキャンペーンごとにプログラムのメンバーシップを追跡し、使い慣れたプログラムでレポートを作成できます。

## Marketo Optimizerからメールを送信 {#send-from-optimizer}

このアプローチを使用して、ジャーニーを構築し、完全に[!DNL Marketo Optimizer]でメールを送信します。 [!DNL Marketo Engage]は引き続き、顧客関係管理（CRM）システムへの引き渡しの記録システムです。

1. メールチャネルの設定。 メールテンプレートの作成、IP アドレスとサブドメイン、登録解除リンク、ランディングページの設定。 [&#x200B; メール配信品質](./start/email-deliverability.md)を参照してください。
1. [!DNL Marketo Optimizer]で通信制限を設定します。 共有された通信制限は利用できません。
1. オーディエンス、AIによる意思決定、次善のパスを通じて、ジャーニーを構築。
1. [!DNL Marketo Optimizer]からメールを送信します。 [!DNL Marketo Optimizer]はアクティビティを記録します。
1. [!UICONTROL &#x200B; スコアリングスタジオ &#x200B;]のユーザーをスコア付けして、[!DNL Marketo Engage]と[!DNL Marketo Optimizer]のアクティビティ全体で1つのモデルを作成します。 [&#x200B; スコアリングスタジオ &#x200B;](./labs/scoring-studio.md)を参照してください。

購読解除は、共有フィールドを通じて自動的に[!DNL Marketo Engage]に同期されます。 [!DNL Marketo Optimizer]件のメールアクティビティは[!DNL Marketo Engage]に送信されませんが、[!UICONTROL Scoring Studio]は引き続きそれを使用します。

### リードを営業部門に引き渡す {#hand-off}

[!DNL Marketo Optimizer]には直接CRM統合がありません。 次のいずれかの方法で[!DNL Marketo Engage]を通じてリードをルーティングします。

* **スコアベース：** スコアフィールドが[!DNL Marketo Engage]に表示され、スマートキャンペーンがリードをCRMに同期します。
* **アクティビティベース：** [!DNL Marketo Optimizer]のジャーニーがアクティビティをリッスンし、リードを[!DNL Marketo Engage] スマートキャンペーンに追加します。
* **プログラム メンバーシップ：** ジャーニーは[!DNL Marketo Optimizer] プログラムに属しているので、開始から終了までのステータスを追跡できます。
