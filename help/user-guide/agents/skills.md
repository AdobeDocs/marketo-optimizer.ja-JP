---
title: 共同作業スキル
description: Marketo Optimizerの大規模な共同作業者のスキル（プログラム、ジャーニー、オーディエンス、スコアリング、コンテンツ、送信時間の最適化用にパッケージ化されたワークフロー）を確認できます。
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 581
ht-degree: 11%

---

# 共同作業者のスキル

_スキル_&#x200B;は、共同作業者が実行方法を認識しているパッケージ化されたワークフローです。`/` メニューと自然言語リクエストの両方の背後にある構成要素です。 各スキルには、ステップバイステップの指示と、1つのジョブに必要な特定のツール（例えば、「ジャーニーの公開」、「2人のリストの比較」、「スコアリングモデルの構築」）がバンドルされています。

>[!NOTE]
>
>各スキルは、スキルが[!DNL Marketo Optimizer]または[!DNL Marketo Engage]状態（**Write**）、クエリ/分析/生成（**Read**）のみか、同等クエリ+変異関数（**Read+Write**）のどちらに基づいて分類されます。

## プログラムとプランニング {#programs-planning}

| スキル | 機能 | アクセス | 製品サーフェス | 影響/データフロー |
|---|---|---|---|---|
| `falco-program-creation` | エンドツーエンドの[!DNL Marketo Optimizer] プログラム作成 – プログラム、サブフォルダー、トークン、リスト、ジャーニー。 <p>_[概要からプログラムを作成](./program-from-brief.md)_&#x200B;を参照してください。 | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer]。 |
| `adapt-program` | [!DNL Marketo Optimizer]適応のために[!DNL Marketo Engage] プログラムから移行ストーリーを生成します。 | 読み取り | [!DNL Marketo Optimizer] | [!DNL Marketo Engage]を読み取り、[!DNL Marketo Optimizer]を書き込みます |
| `folder-creation` | アセットツリーに組織フォルダーを作成します。 | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `program-creation` *（ビルド プログラム）* | キャンペーン概要からMarketoプログラムを作成します。 | 書き込み | [!DNL Marketo Engage] | 読み取り+書き込み[!DNL Marketo Engage] |
| `program-planning` *（プラン キャンペーン）* | ブリーフを設定/実装ドキュメントに変換。 | 読み取り | [!DNL Marketo Engage] | [!DNL Marketo Engage]を読み取ります |
| `program-qa` *（プログラムの検証）* | プログラムの検証/監査（ルールのみ、テスト計画、概要）。 | 読み取り | [!DNL Marketo Engage] | [!DNL Marketo Engage]を読み取ります |

## ジャーニー {#journeys}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `journey-creation` | 自然言語からカスタマージャーニーを作成、編集。 | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `journey-edit-dates` | 公開せずにジャーニーの開始日/終了日を変更します。 | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `journey-publish` | ユーザージャーニーの公開/立ち上げ/スケジュール： | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `journey-stop` | ジャーニーを中断、閉じる、停止、停止、または終了します。 | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `journey-reentry` | 再エントリを設定：許可/禁止、クールダウン、最大エントリ。 | 書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | プロファイルのルーティングを示すトラフィック制御シミュレーションを実行します。 | 読み取り | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] （シミュレーション）を読み取ります |
| `journey-observability` | デバッグ/監視の進行状況 – パス、タイミング、分割、ストール、ドウェル。 <p>_[ジャーニーの進行状況のデバッグと監視](./journey-observability.md)_&#x200B;を参照してください。 | 読み取り | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] + [!DNL Marketo Engage]を読み取ります（静的リスト チェック） |

## オーディエンスと人 {#audiences-people}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `audience-creation` | [!DNL Marketo Engage] スマートリストの適応、ユーザーリストの作成、ルールの追加/更新。 <p>「_[プログラムのオーディエンスを作成](./audience-creation.md)_」を参照してください。 | 書き込み | [!DNL Marketo Optimizer] | [!DNL Marketo Engage]を読み取り、[!DNL Marketo Optimizer]を読み取り/書き込みます。 |
| `people-list-comparison` | 2つの人物リストを比較し、重複するメンバーを表示します。 | 読み取り | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer]を読み取ります |
| `import-leads` | CSV データ品質を検査し、[!DNL Marketo Engage]へのインポートをコミットします。 | 読み取り/書き込み | 両方 | 読み取り+書き込み[!DNL Marketo Engage] |
| `lead-investigation` *（リードの調査）* | リードのアクティビティ、スコアリング、クオリフィケーション、ライフサイクルを調査し、 | 読み取り | [!DNL Marketo Engage] | [!DNL Marketo Engage]を読み取ります |

## コンテンツとチャネル {#content-channels}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `content-personalization` | テンプレートの参照/プレビュー、コンテンツの編集/バリエーションの生成。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer]。 _[ペルソナ別のメールコンテンツのパーソナライズ](./personalize-content.md)_&#x200B;を参照してください。 |
| `asset-tokens` | プログラム/フォルダー/ジャーニーでの完全なトークン CRUD。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `fcs-channels` | チャネル検索とCRUD + パブリッシュ/停止/削除。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |

## スコアリングとシグナル {#scoring-signals}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `scoring-studio` | スコアリングモデルのリスト作成/取得、構築/公開。 <p>_[カスタムスコアリングモデルの作成](./lead-scoring-model.md)_&#x200B;を参照してください。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] （スコアリングサービス）; [!DNL Marketo Engage]個のリードフィールド/アクティビティタイプを読み取ります。 |
| `engagementconfiguration` | エンゲージメント設定とウェイトの編集/更新を表示します。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `intentconfiguration` | インテント設定とウェイトの設定/更新を表示します。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `intent-query` | 人物/セグメント/リスト別のインテントスコアのクエリと説明。 | 読み取り | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer]を読み取ります |

## 送信時間の最適化 {#sto}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `send-time-optimization` | メールノードでSTO ステータスを確認し、有効/無効にします。 | 読み取り/書き込み | [!DNL Marketo Optimizer] | 読み取り+書き込み[!DNL Marketo Optimizer] |
| `send-time-report` | STO パフォーマンスレポートを取得/表示します。 | 読み取り | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer]を読み取ります |

## 知識 {#knowledge}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `product-knowledge` | Experience Leagueに関する[!DNL Marketo Optimizer] ドキュメントのハウツー/コンセプトに関する質問に答えます。 | 読み取り | 両方 | 外部ドキュメントを読み取り – 製品データなし |

## クロスバックエンド {#cross-backend}

これらのスキルは、複数のバックエンドにまたがっています。

- **`adapt-program`** — `gather_program_assets`は[!DNL Marketo Engage] （`get_program`、`get_smart_campaign`、`list_emails`）を読み取り、次に`falcomcp_create_journey`経由で書き込みます。従来のクロスバックエンドです。
- **`audience-creation`** — [!DNL Marketo Engage] スマートリスト （`get_smart_list` / `get_smart_campaign`）を読み取り、[!DNL Marketo Optimizer]人のユーザーリストを書き込みます。
- **`journey-observability`** — [!DNL Marketo Optimizer]件の読み取りに加えて`check_lead_in_marketo_static_list` [!DNL Marketo Engage]件の読み取り。
- **`scoring-studio`** — [!DNL Marketo Optimizer]個のスコアリングサービスと共に[!DNL Marketo Engage]個のリードフィールド/アクティビティタイプを読み取ります。

すべての`falco-mcp_*`およびジャーニー/トークン/スコアリング/STO/FCS ツールが[!DNL Marketo Optimizer] サービスにヒットし、CSV/プログラム/リードツールが[!DNL Marketo Engage]にヒットしました。
