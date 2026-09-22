---
title: 個人ジャーニーレポート
description: Adobe Marketo Optimizerの個人ジャーニーレポートについて説明します。このレポートでは、1つのジャーニーの完了率、エンゲージメント、メール指標を示します。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 531dce4ffe6000efa0296f0e2393423f54124ea7
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%
---

# 個人ジャーニーレポート

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

ライブまたは完成した人物ジャーニーの&#x200B;**[!UICONTROL レポートを表示]**&#x200B;をクリックして、ステータス、エンゲージメント、メール指標、アクティビティフローなど、そのパフォーマンスを確認します。

レポートを表示するには（_T） :_

1. _[!UICONTROL 人のジャーニー]_ リストから&#x200B;**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL 完了した]**&#x200B;人のユーザージャーニーを開きます。
1. ジャーニーヘッダーで、「**[!UICONTROL レポートを表示]**」を選択します。

   ![&#x200B; ジャーニーヘッダーで「レポートを表示」ボタンがハイライト表示された人物ジャーニーキャンバス。](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

レポートの日付範囲[&#128279;](./reports-overview.md#change-the-date-range)を変更できます。

レポートの上部にある「**[!UICONTROL 共有]**」を選択して、データの書き出しをダウンロードまたはスケジュールします。 レポートの概要の「[_レポートの書き出し_](./reports-overview.md#export-a-report)」を参照してください。

ジャーニーのステータス、完了傾向、エンゲージメントタイルを表示する![人物ジャーニー個人レポート。](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## フィルター {#filters}

レポートフィルターは、現在のジャーニーに対してスコープが設定されます。

* **[!UICONTROL ジャーニー名（イベント）]** - レポートを開いたジャーニーに事前設定します。
* **[!UICONTROL ペルソナ （イベント）]** - （_まだサポートされていません_）特定の[派生ペルソナ &#x200B;](../audiences/personas.md#filter-by-derived-persona)に一致するユーザーにレポートをフィルタリングします。 デフォルトは[!UICONTROL &#x200B; フィルターなし]。

**[!UICONTROL すべてをリセット]**&#x200B;を選択して&#x200B;_[!UICONTROL ペルソナ （イベント）]_ フィルターをクリアし、デフォルトのビューに戻ります。

## 人物のステータスとエンゲージメント {#person-status-and-engagement}

このセクションには、次の4つのタイルが表示されます。

* **[!UICONTROL ジャーニー内の人物のステータス]** - ジャーニー内の人物を&#x200B;_[!UICONTROL 完了]_&#x200B;および&#x200B;_[!UICONTROL 進行中]_&#x200B;のカテゴリに分割し、対応する割合を指定します。
* **[!UICONTROL 完了済みユーザー数]** – 選択した日付範囲でジャーニーを完了したユーザー数を追跡する折れ線グラフ。
* **[!UICONTROL エンゲージメント済みユーザーとエンゲージメントなしユーザー]** – ジャーニー内のユーザーを&#x200B;_[!UICONTROL エンゲージメント済み]_&#x200B;と&#x200B;_[!UICONTROL エンゲージメントなし]_&#x200B;のカテゴリーに分割し、対応する割合を指定します。
* **[!UICONTROL エンゲージメント済みユーザー]** - ジャーニーにエンゲージ済みとして認定されたユーザーの合計数。

## メールパフォーマンス {#email-performance}

[!UICONTROL 電子メールパフォーマンス &#x200B;] テーブルには、ジャーニーで送信された各電子メールの配信とエンゲージメントの指標が表示されます。 すべてのジャーニーで同じメール指標については、[&#x200B; メールエンゲージメントレポート &#x200B;](./email-engagement-report.md)を参照してください。

![1つの電子メールの送信、配信、開封、クリックの指標を示す電子メールパフォーマンステーブル。](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

[!UICONTROL 電子メールパフォーマンス &#x200B;]のテーブル列：

* [!UICONTROL Email Name] - メールの名前。
* [!UICONTROL 送信済み] – 送信されたメール数。
* [!UICONTROL 配信済み] – 配信済みメールの数。
* [!UICONTROL %配信済み] – 配信済みメールの数を送信済みメール数で割った数。
* [!UICONTROL 開封済み] – 受信者が電子メールを開封した回数。
* [!UICONTROL %開封済み] – 開封された電子メールの数を、配信数で割った数。
* [!UICONTROL &#x200B; クリック数] – 受信者がメール内のリンクをクリックした回数。
* [!UICONTROL % クリック済み] - クリック済み電子メールの数を、配信数で割った数。

## ジャーニーアクティビティフロー {#journey-activity-flow}

[!UICONTROL ジャーニーアクティビティのフロー]のビジュアライゼーションは、_[!UICONTROL ユーザーをジャーニーに追加]_ アクティビティから開始して、ユーザーがジャーニーを通過するパスを示します。 各ノードには、そのアクティビティのパスビュー数が表示されます。

![ジャーニーのアクティビティ フローのビジュアライゼーション。電子メール配信を通じて、「人物を追加」から「ジャーニー」へのパス ビューを表示します。](./assets/reports-individual-journey-activity-flow.png){width="700" zoomable="yes"}
