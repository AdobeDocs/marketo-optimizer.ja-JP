---
title: Analytics レポートの生成
description: Workfront チャットのSurface Analytics スキルを使用して、自然言語プロンプトからアクティビティ、メール、リード、セグメント、ジャーニーレポートを生成する方法を説明します。
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# 分析レポートの生成

[!DNL Adobe Marketo Optimizer]の&#x200B;[_Surface Analytics_ スキル ](./skills.md#analytics-reporting)は、データに関する自然言語の質問に回答します。 [同僚のチャットインターフェイス ](./chat-interface.md)で使用すると、アクティビティの傾向、メールのパフォーマンス、リードとアカウントのデータ、セグメントとリストのメンバーシップ、ジャーニー指標を確認できます。 結果はグラフや表として返されるため、クエリやダッシュボードを手動で作成する必要はありません。

* **スキル** - `surface-analytics`
* **呼び出し** – 自然言語で質問するか、スラッシュコマンドを使用してSurface Analytics スキルを実行します。 例：_「過去30日間の毎日のアクティビティ数を表示する」_
* **分析データ**&#x200B;から[!DNL Marketo Optimizer]を読み取り、両方の製品にまたがる質問については[!DNL Marketo Engage]分析データを読み取ります

>[!NOTE]
>
>レポートデータは2時間ごとに更新されます。 過去2時間のアクティビティが結果に反映されない場合があります。

## アクティビティの傾向を表示 {#activity-trends}

日次または週次のアクティビティ数を確認し、アクティビティのタイプや商品エリアごとに結果を分類できます。

* _「過去30日間の毎日のアクティビティ数を表示します。」_
* _「今週の上位のアクティビティの種類は何ですか？」_
* _&quot;先月のアクティビティをアプリ領域ごとに分類します。&quot;_

## メールのパフォーマンスを確認 {#email-performance}

メールの配信数、開封率、クリック率、バウンス数、配信停止数を確認します。

* _「ジャーニー別のメール開封率は？」_
* _「過去90日間のクリック率を表示する」_
* _「先週の配信停止はいくつですか？」_

## リードとアカウントのデータを分析 {#lead-account-data}

リードスコアの分布、ペルソナの内訳、地域または企業特性のロールアップについて質問します。

* _&quot;リード間のスコア分布を表示します。&quot;_
* _「各アカウントの人数は？」_
* _「ペルソナ別にリードを分類する」_

## セグメントとリストメンバーシップの確認 {#segment-list-membership}

特定のリストやセグメントに属しているユーザーを確認できます。

* _「Q1 ナーチャリングリストの人数は？」_
* _「最もメンバーが多いセグメントはどれですか？」_

## ジャーニー指標の詳細 {#journey-metrics}

ジャーニーのメンバーシップ、完了率、ノードトラバーサル、funnel分析について質問します。

* _「デモ フォローアップ ジャーニーの完了率を教えてください」_
* _「LeadNurtureJourneyの各ノードの人数は？」_

## 製品間で質問する {#cross-product}

Surface Analyticsは、[!DNL Marketo Engage]と[!DNL Marketo Optimizer]の両方のデータにまたがる質問に1つのプロンプトで回答できます。

* _「LumaSecureとLumaStorageで最もパフォーマンスの高いメールは何ですか？」_

## 制限事項 {#limitations}

| 制限事項 | 詳細 |
|---|---|
| レコードの編集または作成 | サポートされていません。 Surface Analyticsは、既存のデータの読み取りとレポートのみを行います。 |
| 結果に人間が読み取れる名前 | 必ずしも利用可能ではありません。 一部のレポートでは、名前の代わりにジャーニーIDや電子メール IDなどの内部IDが表示されます。 |
| レポートカードの重複 | 1つの質問で、同じ結果に対して複数のレポートカードが返されることがあります。 |
