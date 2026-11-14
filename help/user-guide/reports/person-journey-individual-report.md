---
title: 人物ジャーニー詳細レポート
description: Adobe Marketo Optimizerの人物ジャーニー詳細レポートについて説明します。このレポートには、選択したジャーニーの完了率、エンゲージメントおよびメール指標が表示されます。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 84abcbf4ddf114898768766d6e91ec855e3f979f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%
---

# 人物ジャーニー詳細レポート

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

ライブまたは完成した人物ジャーニーの&#x200B;**[!UICONTROL レポートを表示]**&#x200B;をクリックして、そのパフォーマンス指標とアクティビティフローを確認します。 レポートを開いた後、レポートに含める複数のジャーニーを選択できます。

>[!PREREQUISITES]
>
>このレポートを表示するには、**[!UICONTROL B2B人物ジャーニーレポートを表示]** [権限](../start/permissions-reference.md)が必要です。

レポートを表示するには（_T） :_

1. _[!UICONTROL 人のジャーニー]_ リストから&#x200B;**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL 完了した]**&#x200B;人のユーザージャーニーを開きます。
1. ジャーニーヘッダーで、「**[!UICONTROL レポートを表示]**」を選択します。

   ![&#x200B; ジャーニーヘッダーで「レポートを表示」ボタンがハイライト表示された人物ジャーニーキャンバス。](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

レポートの日付範囲[&#128279;](./reports-overview.md#change-the-date-range)を変更できます。

レポートの上部にある「**[!UICONTROL 共有]**」を選択して、データの書き出しをダウンロードまたはスケジュールします。 レポートの概要の「[_レポートの書き出し_](./reports-overview.md#export-a-report)」を参照してください。

![&#x200B; ジャーニーのステータス、完了傾向、エンゲージメントタイルの上に、ジャーニー名（イベント）とペルソナ（イベント）フィルターを含む人物ジャーニー個人レポート。](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## フィルター {#filters}

このレポートには、最初に開いたジャーニーが表示されます。 レポートの上部にあるフィルターを使用して、含めるジャーニーとペルソナを変更します。

* **[!UICONTROL ジャーニー名（イベント）]** - レポートを開いたジャーニーに事前設定します。 フィルターリストを開き、含めるジャーニーを選択します。 複数のジャーニーを選択できます。
* **[!UICONTROL ペルソナ （イベント）]** – 特定の[派生ペルソナ &#x200B;](../audiences/personas.md#filter-by-derived-persona)に一致するユーザーにレポートをフィルタリングします。 デフォルトは[!UICONTROL &#x200B; フィルターなし]。

![ジャーニー名（イベント）フィルターリストが開き、3つのジャーニーが選択された人物ジャーニーレポートが、ペルソナ（イベント）フィルターと共に表示されます。](./assets/reports-person-journey-details-filters.png){width="700" zoomable="yes"}

ペルソナでフィルタリングするには、レポートの上部にある&#x200B;**[!UICONTROL ペルソナ（イベント）]** フィルターリストを開き、含める値を選択します。

「**[!UICONTROL すべてをリセット]**」を選択して、レポートフィルターをリセットします。

## 人物のステータスとエンゲージメント {#person-status-and-engagement}

このセクションには、次の4つのタイルが表示されます。

* **[!UICONTROL ジャーニー内の人物のステータス]** - ジャーニー内の人物を&#x200B;_[!UICONTROL 完了]_&#x200B;および&#x200B;_[!UICONTROL 進行中]_&#x200B;のカテゴリに分割し、対応する割合を指定します。
* **[!UICONTROL 完了済みユーザー数]** – 選択した日付範囲でジャーニーを完了したユーザー数を追跡する折れ線グラフ。
* **[!UICONTROL エンゲージメント済みのユーザーとエンゲージメントしていないユーザー]** - ジャーニーに参加しているユーザーを&#x200B;_[!UICONTROL エンゲージメント済みのユーザー]_&#x200B;と&#x200B;_[!UICONTROL エンゲージメントしていないユーザー]_&#x200B;に分割し、対応する割合を指定します。
* **[!UICONTROL エンゲージメント済みユーザー]** - ジャーニーにエンゲージ済みとして認定されたユーザーの合計数。

## メールパフォーマンス {#email-performance}

[!UICONTROL 電子メールパフォーマンス &#x200B;] テーブルには、ジャーニーで送信された各電子メールの配信とエンゲージメントの指標が表示されます。 すべてのジャーニーで同じメール指標については、[&#x200B; メールエンゲージメントレポート &#x200B;](./email-engagement-report.md)を参照してください。

![3通のメールの送信、配信、開封、クリックの指標を示すメールパフォーマンステーブル。](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

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

[!UICONTROL ジャーニーアクティビティのフロー]のビジュアライゼーションは、_[!UICONTROL ユーザーをジャーニーに追加]_ アクティビティから開始して、ユーザーがジャーニーを通過するパスを示します。 各ノードには、そのアクティビティのビュー数が表示されます。

![電子メールと電子メールのバウンスの送信アクティビティを通じて、「人物を追加」から「ジャーニー」へのパス ビューを表示するジャーニーアクティビティのフローのビジュアライゼーション。](./assets/reports-individual-journey-activity-flow.png){width="500" zoomable="yes"}
