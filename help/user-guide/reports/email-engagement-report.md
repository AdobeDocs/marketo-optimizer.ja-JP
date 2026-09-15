---
title: メールエンゲージメントレポート
description: Adobe Marketo Optimizerの「電子メールエンゲージメントレポート」では、電子メールとジャーニーごとに電子メールの配信品質とエンゲージメント指標を確認できます。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 8c47a9c69c32ba0a37ba2efadb6ad4c1b796c21d
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 3%
---

# メールエンゲージメントレポート

<!-- SPHR-39569: content drafted, but hide: true and hide-from-toc stay until eng confirms this shipped to production. Filter by Program, Filter by Audience, and the program data point from SPHR-32511 are not documented here pending delivery-state confirmation. -->

[!UICONTROL 電子メールエンゲージメント ] レポートを使用して、電子メールとジャーニーごとに、インスタンス全体の電子メールの配信品質とエンゲージメントのパフォーマンスを確認します。

レポートを表示するには（_T） :_

1. 左側のナビゲーションで、**[!UICONTROL レポート]**&#x200B;を選択します。
1. _リスト_ アイコン （![ リストアイコン ](../assets/do-not-localize/icon-table-of-contents.svg)）をクリックし、_[!UICONTROL 目次]_ パネルで&#x200B;**[!UICONTROL 電子メールエンゲージメント]**&#x200B;を選択します。

ジャーニー名とペルソナのフィルター、過去30日間の日付範囲、メールアクティビティ指標のテーブルを含む![ メールエンゲージメントレポート。](./assets/reports-email-engagement.png){width="700" zoomable="yes"}

他のレポートセクションで使用可能な同じ日付範囲ピッカーを使用して、[日付範囲](./reports-overview.md#change-the-date-range)を変更できます。

レポートの上部にある「**[!UICONTROL 共有]**」を選択して、すべてのレポートデータの書き出しをダウンロードまたはスケジュールします。 レポートの概要の「[_レポートの書き出し_](./reports-overview.md#export-a-report)」を参照してください。

## レポートテーブル {#report-table}

[!UICONTROL 電子メールエンゲージメント ] レポートには、電子メールごとに1行が表示され、次の行のディメンションが表示されます。

* **[!UICONTROL Email Name]** - メールの名前。
* **[!UICONTROL ジャーニー名]** – 電子メールを送信したジャーニーの名前。

指標の列は、**[!UICONTROL メールアクティビティ]**&#x200B;の下にグループ化されます。

| 列 | 説明 |
| --- | --- |
| [!UICONTROL 送信済み] | 送信されたメールの数。 |
| [!UICONTROL 配信済み] | 配信されたメール数： |
| [!UICONTROL %配信済み] | 送信されたメールの割合。 |
| [!UICONTROL ハードバウンス済み] | 永続的に配信できなかったメールの数。 |
| [!UICONTROL ソフトバウンス済み] | 一時的に配信に失敗したメールの数。 |
| [!UICONTROL 開封済み] | 受信者がメールを開いた回数。 |
| [!UICONTROL %開封] | 配信されたメールのうち、開封された割合。 |
| [!UICONTROL クリック済み] | 受信者がメール内のリンクをクリックした回数。 |
| [!UICONTROL % クリックしました] | クリックを受け取った電子メールの割合。 |
| [!UICONTROL  クリックして比率を開く] | クリックを受け取った、開封された電子メールの割合。 |
| [!UICONTROL 登録解除済み] | メールの購読を解除した受信者の数。 |
| [!UICONTROL %登録解除] | 配信されたメールのうち、配信停止に至った割合。 |

<!--

## Filters {#filters}

Use filters to narrow the report to a specific journey, persona, or date range. Select **[!UICONTROL Reset all]** to clear every filter and return to the default view.

* **[!UICONTROL Journey Name (Event)]** - Filter by the journey that sent the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Persona (Event)]** - Filter by the persona associated with the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Date range]** - Filter by a specific date span, shown as explicit start and end dates. Default is [!UICONTROL Last 30 days].
-->