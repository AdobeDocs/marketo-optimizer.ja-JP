---
title: レポート
description: レポートセクション、書き出しとスケジュールのオプション、日付範囲の変更方法など、Adobe Marketo Optimizerの「レポート」タブについて説明します。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 56f39b3c77bd13984cf72761621ac3b228f13abd
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 2%
---

# レポート

「[!UICONTROL &#x200B; レポート &#x200B;]」タブには、ジャーニーエンゲージメント、メールパフォーマンス、web アクティビティなど、[!DNL Adobe Marketo Optimizer]全体のパフォーマンスインサイトが表示されます。 左側のナビゲーションで「**[!UICONTROL レポート]**」を選択して開きます。

各レポートは[!DNL Adobe Customer Journey Analytics]に基づいて作成され、[!DNL Marketo Optimizer]に直接埋め込まれます。 _リスト_ アイコン （![&#x200B; リストアイコン &#x200B;](../assets/do-not-localize/icon-table-of-contents.svg)）をクリックすると、左側の&#x200B;**[!UICONTROL 目次]** パネルを使用して、セクション間を移動できます。

![人物ジャーニーの概要、エンゲージメント、電子メールエンゲージメント、およびWeb エンゲージメントのセクションを一覧表示するレポートページ &#x200B;](./assets/reports-table-of-contents.png){width="800" zoomable="yes"}

## レポートセクション {#report-sections}

「[!UICONTROL &#x200B; レポート &#x200B;]」タブでは、事前定義済みのレポートを4つのセクションに整理します。 各セクションには、1つ以上のダウンロード可能なアイテムと、その指標とビジュアライゼーションに関する詳細を含む独自のドキュメントページがあります。

| セクション | ダウンロード可能なアイテム | レポートページ |
| --- | --- | --- |
| [!UICONTROL 人物ジャーニーの概要] | アクティブなジャーニーの数 | [人物ジャーニーの概要レポート &#x200B;](./person-journey-overview-report.md) |
| [!UICONTROL エンゲージメント] | 人物によるエンゲージメント、人物のエンゲージメントの推移 | [エンゲージメントレポート](./engagement-report.md) |
| [!UICONTROL &#x200B; メールエンゲージメント &#x200B;] | メールエンゲージメント | [電子メールエンゲージメントレポート &#x200B;](./email-engagement-report.md) |
| [!UICONTROL Web エンゲージメント &#x200B;] | 上位ページビュー数 | [Web エンゲージメントレポート &#x200B;](./web-engagement-report.md) |

## 個人レコードレポート {#individual-record-reports}

一部のレポートは、セクション全体のビューではなく、単一のレコードに焦点を当て、アプリケーションの別の領域からアクセスされます。

* メール送信時間の最適化パフォーマンスについては、[!UICONTROL 同僚]のチャットインターフェイスからレポートを開きます。 手順については、[&#x200B; メール送信時間の最適化](../marketing/email-send-time-optimization.md#reporting)を参照してください。
* 単一のジャーニーを通じた個人の進捗状況について、そのジャーニー内からレポートを開きます。

## レポートの書き出し {#export-a-report}

レポートページの上部にある「**[!UICONTROL 共有]**」を選択して、そのデータの書き出しまたは配信スケジュールを設定します。

![CSVのダウンロード、PDFのダウンロード、スケジュールの書き出し、スケジュールの管理オプションを含むメニューを共有](./assets/reports-share-menu.png){width="500"}

* **[!UICONTROL CSVをダウンロード]** - レポートデータをプレーンテキスト値として書き出します。

* **[!UICONTROL PDFをダウンロード]** - レポート内のすべての表示可能なテーブルとビジュアライゼーションをPDF ファイルとして書き出します。

* **[!UICONTROL スケジュール書き出し]** - レポートの定期的な書き出しを設定し、CSV ファイルまたはPDF ファイルとして毎週または毎月配信します。

* **[!UICONTROL スケジュールの管理]** – 既存のスケジュール済み書き出しを確認して管理します。 このオプションは、組織の制限に対して使用されるスケジュールの`3/10`などの実行中の数を表示します。

>[!NOTE]
>
>週単位または月単位で、すべてのレポートに対して最大10個のスケジュールされた書き出しを設定できます。 管理者でない場合は、自分のスケジュール済み書き出しのみを管理できます。 管理者は、組織内のすべてのスケジュール済み書き出しを表示および管理できます。

## CJAでのレポートの分析 {#analyze-a-report-in-cja}

>[!AVAILABILITY]
>
>この関数は、組織が[!DNL Adobe Customer Journey Analytics]のライセンスを取得しており、製品プロファイルが割り当てられている場合に使用できます。

任意のレポートセクションで「**[!UICONTROL CJAで分析]**」を選択して、[!DNL Adobe Customer Journey Analytics] Workspaceで開きます。このセクションでは、埋め込みレポートで使用可能な内容に加えて、カスタムビジュアライゼーションを作成できます。

## 日付範囲の変更 {#change-the-date-range}

各レポートセクションには、特定の日付範囲のデータが表示され、セクションの右上隅に表示されます。 日付範囲フィールドをクリックして、日付選択ツールを表示し、日付範囲を選択します。 別のプリセットを選択するか、カスタム範囲を定義できます。

![2か月のカレンダー、開始日と終了日のフィールド、プリセットオプションを含む日付範囲ピッカー](./assets/reports-date-range.png){width="600"}
