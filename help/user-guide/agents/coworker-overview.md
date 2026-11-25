---
title: Adobe Marketo OptimizerにおけるCX Enterprise Coworkerの概要
description: CX Enterprise CoworkerがMarketo Optimizerのスキルを活用して、プログラムの構築と適応、AIによる意思決定の準備状況の確認、MCP ツールの呼び出しをどのように行うのかをご確認ください。
autotag-review: '2026-11-24T22:43:00.917Z'
TQID: https://experienceleague.adobe.com/V4Kww-NcdfbFxXqWrs7mPq7UYu8AREqDgyfvlMnlURM
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 418b81a0a39eca0ca7b537c76da972df7eefd09f
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 2%
---

# [!DNL Adobe Marketo Optimizer] における [!DNL CX Enterprise Coworker] {#coworker-overview}

[!DNL CX Enterprise Coworker] チャットは、[!DNL Adobe Marketo Optimizer]のタスクを完了するための会話型インターフェイスです。 目標を平易な言葉で説明し、[!DNL Coworker]さんがタスクを計画し、[!DNL Marketo Optimizer]でそれらを実行し、結果を検証し、完成した作業を承認のために提供します。

[!DNL Coworker]は、[!DNL Marketo Optimizer]用に構築されたスキルを使用して、新しいプログラムの作成、既存の[!DNL Marketo Engage] プログラムの適応、AIによる意思決定に向けたデータの準備が整っているかどうかの確認など、一般的なマーケティング業務タスクをガイドします。

[!DNL Coworker]は、組織の既存の[[!DNL Marketo Optimizer] 権限](../start/permissions-reference.md)を尊重します。 既に実行が許可されているアクションのみを実行でき、書き込みアクセス権を持つ場合は管理者が制御できます。 [!DNL Coworker]はAdobe エコシステムの一部であり、[!DNL Marketo Optimizer]に限定されません。

詳しくは、次を参照してください。

* [[!DNL Adobe CX Enterprise Coworker] チャットの概要](https://experienceleague.adobe.com/ja/docs/coworker/content/chat/overview)
* [&#x200B; [!DNL Marketo Optimizer]のチャット インターフェイス](./chat-interface.md)
* [&#x200B; [!DNL Marketo Optimizer]の[!DNL Coworker] スキル](./skills.md)

## [!DNL CX Enterprise Coworker]の[!DNL Marketo Optimizer] スキル {#skills}

次の製品固有のスキルを使用して、プログラムを作成および適応させ、データ準備状況を評価します。

| スキル | お客様のビジネスにどのように役立つのか | リクエストの例 |
| --- | --- | --- |
| `program-creation-marketo-optimizer` | [!DNL Marketo Optimizer] マーケティングプログラムをエンドツーエンドで作成します。 [!DNL Coworker]は、目標から構築されたプログラムに導きます。 | キャンペーン概要をアップロードし、次の質問を行います。_添付された概要を使用してプログラムを作成します。_ |
| `adapt-program-marketo-optimizer` | 既存の[!DNL Marketo Engage] プログラムを[!DNL Marketo Optimizer] プログラムに適応、移行、または変換します。 | _第3四半期のエンタープライズウェビナーナーナーチャリングプログラムを[!DNL Marketo Engage]から[!DNL Marketo Optimizer]に調整します。_ |
| `ai-decisioning-health-marketo-optimizer` | テナントのデータがAIによる意思決定に適しているかどうかをレポートし、ストーリーのカバー範囲、特性の豊富さ、ペルソナのカバー範囲を明らかにします。 | _AIによる意思決定に使用されるデータは何ですか？_ |

### プログラム作成プロンプトの例 {#program-creation-prompt}

概要をアップロードするか、プログラムを直接説明します。 [!DNL Coworker]が使用するオーディエンス、ジャーニー、コンテンツ、設定を含めます。

次の図は、次の例のプロンプトの節をまとめたものです。 ストーリーを進める順序ではなく、リクエストを整理する方法を示します。

![&#x200B; プログラム作成プロンプトの8つのセクション：プログラム目標、オーディエンス、インテントベースの招待を伴うジャーニー、メールコンテンツ、LinkedIn アクティベーション、登録処理、イベント後のフォローアップ、設定](./assets/coworker-program-creation-prompts.svg){width="800" zoomable="yes"}

各セクションを展開して、サンプルプロンプトを表示します。

+++プログラムの目標

_電子メールとLinkedInを使用して、8月3日から12月3日まで開催されるExperience Cloud Leadership Forum - AIを活用したExperience Summitという名前のB2B マーケティングプログラムを作成します。 Bay Area Innovation Centerにて9:00 AMに開催。 ジャーニーをすぐに開始します。_

+++

+++オーディエンス

_Experience Cloudに対する製品の意図とエンゲージメントスコアが1を超えるユーザーをターゲットにします。 購読解除およびマーケティング中のプロファイルを除外します。_

+++

+++ジャーニー

_Next Best Pathを使用して、Adobe Experience Cloudの高、Medium、低の意図でオーディエンスを分割します。 それぞれの意図レベルに合わせて、パーソナライズされた電子メールの招待状を送信。 パスをマージして2日間待ちます。 メールの開封数、クリック数、コンテンツのエンゲージメント、登録数を確認します。 エンゲージメントしている会員にアジェンダのプレビューを送信する。エンゲージメントしていない会員はLinkedInでアクティベートし、2日間待つ。 関心の高いパスを統合し、イベントの10日前に最終的な登録リマインダーを送信します。 すべての電子メールの送信時間の最適化を有効にします。_

+++

+++メールコンテンツ

_エグゼクティブ招待状（イベントの6週間前）、アジェンダプレビュー（イベントの6週間前）、最終登録リマインダー（イベントの10日前）の3通のメールを作成します。 人物ストーリー、ペルソナ分類、業界、ソリューションへの興味、最近のエンゲージメント、Experience Cloudのインテントを使用して、関連する件名、プリヘッダー、行動喚起（自分の席を予約する、アジェンダを表示する、完全な登録）、AIを活用してパーソナライズされたコンテンツを含めます。 招待に会場画像を含めますが、議題のプレビューにバナーを含めません。_

+++

+++LinkedIn

_顧客体験の変革とAIによるパーソナライゼーションを促進するスポンサードコンテンツで、エンゲージメントしていないメンバーをターゲットにします。_

+++

+++登録

_登録メンバーを招待ジャーニーからすぐに終了し、AIが生成したディスカッショントピック、パーソナライズされたアジェンダ、会場の詳細、推奨セッション、カレンダーリンクを含むエグゼクティブ準備メールを送信します。_

+++

+++イベント後

_参加者をExperience Cloud リーダーシップフォローアッププログラムに振り分け、振り返り、録画、リソース、販売資格のレビューを行います。 不参加者向けSummitのハイライト、オンデマンドコンテンツ、今後のイベント招待状を送信します。_

+++

+++設定

_my.replyToEmailを`events@example.com`に、my.senderNameをExperience Cloud Eventsに設定します。 市、会場、基調講演のトピック、業界の焦点のみが変更される再利用可能なテンプレートを使用します。_

+++

概要の準備について詳しくは、[概要からプログラムを作成](./program-from-brief.md)を参照してください。

## ユースケースの例 {#use-cases}

### データ準備状況を確認した後にプログラムを作成する {#check-readiness-create-program}

マーケティングオペレーション部門の責任者は、新しいアカウントベースのプログラムを構築する前に、テナントがAIによる意思決定を行う準備ができていることを把握したいと考えています。

1. ストーリーのカバー範囲、特性の豊富さ、ペルソナのカバー範囲を確認するには、[AIによる意思決定のヘルスチェック &#x200B;](./ai-decisioning-health.md)を実行します。 例えば、_AIの意思決定に利用されたMarketo データを表示します。_
1. レポートで特定されたギャップに対処します。
1. キャンペーン概要をアップロードして、次の質問を行います。_添付された概要を使用してプログラムを作成します。_
1. [!DNL Coworker]さんが結果を提示したときに、プログラムをレビューして承認します。

この結果は、欠陥を特定する準備状況レポートであり、その後、AIによる意思決定をサポートできるデータにもとづいて構築されたプログラムが続きます。

### 既存の[!DNL Marketo Engage] プログラムを[!DNL Marketo Optimizer]に移動 {#adapt-program}

需要創出チームは、手動で再構築することなく、[!DNL Marketo Optimizer]で実行される実績のあるプログラムを必要としています。

1. 調整する[!DNL Marketo Engage] プログラムに名前を付けます。 例：_第3四半期のエンタープライズウェビナーナーナーチャリングプログラムを[!DNL Marketo Engage]から[!DNL Marketo Optimizer]に調整します。_
1. [!DNL Coworker]はプログラムを[!DNL Marketo Optimizer]のコンストラクトにマッピングし、コンバージョンしないものをフラグ付けします。
1. 結果を確認して承認します。

結果は、レビュー用に変換されたプログラムと、手動で決定する必要があるアイテムのリストです。

## [!DNL Marketo Optimizer]個のMCP ツール {#mcp-tools}

[!DNL Coworker] スキルは、[!DNL Marketo Optimizer] モデル コンテキスト プロトコル （MCP） サーバー上の次の37 ツールを呼び出します。 各ツール名には、接頭辞`marketo-optimizer__`が付きます。

このリファレンスでは、ワークフロー中に使用されるサポートスキルなど、登録されたスキルによって文書化されたツールについて説明します。 デプロイメントのステータスや使用頻度は示されません。 この表のスキル名はツール参照に従い、上記の製品固有のスキル名とは異なる場合があります。

| ツール | スキル | 目的 |
| --- | --- | --- |
| `marketo-optimizer__get_workspace_root_tree` | `program-creation-marketo-optimizer` | 新しいプログラムのワークスペースゾーンまたは名前付きサブフォルダーを見つけます。 |
| `marketo-optimizer__create_program` | `program-creation-marketo-optimizer` | 確認されたゾーンまたはフォルダーにプログラムを作成します。 |
| `marketo-optimizer__list_programs` | `program-creation-marketo-optimizer`, `landing-page-authoring` | プログラムを参照するか、ランディングページの保存場所を見つけます。 |
| `marketo-optimizer__get_program` | `program-creation-marketo-optimizer` | IDでプログラムを読み取ります。 |
| `marketo-optimizer__update_program` | `program-creation-marketo-optimizer` | プログラム名などのプログラムメタデータを更新します。 |
| `marketo-optimizer__create_program_token` | `program-creation-marketo-optimizer` | 承認済みプログラムトークンを作成または修正します。 |
| `marketo-optimizer__list_program_tokens` | `program-creation-marketo-optimizer` | プログラムの解決済みトークンを読み取ります。 |
| `marketo-optimizer__create_dynamic_people_list_with_rules` | `program-creation-marketo-optimizer` | プログラムにリンクした人物リストを作成し、説明からオーディエンスルールを生成します。 |
| `marketo-optimizer__list_people_journeys` | `adapt-program`; チャネルプラグインの共有参照 | 宛先ジャーニー名の競合を確認したり、不明確な結果の後に既存のジャーニーを見つけたり、チャネル作業のジャーニーを参照したりします。 |
| `marketo-optimizer__create_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`, `channel-content-authoring` | プログラムにリンクしたジャーニーを作成したり、アダプティブジャーニーを開始したり、メールチャネルに欠けているジャーニーを作成したりできます。 |
| `marketo-optimizer__get_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`; チャネルプラグイン共有参照 | ジャーニーやキャンバスの読み取り、ステージングされた編集の検証、チャネル作業のジャーニーの検索などをおこなうことができます。 |
| `marketo-optimizer__update_person_journey` | `adapt-program` | 承認済みのビルドステップを宛先ジャーニーに一度に1つ追加します。 |
| `marketo-optimizer__run_person_journey_simulation` | `program-creation-marketo-optimizer` | 公開せずにジャーニーフローを検証。 |
| `marketo-optimizer__run_program_qa` | `program-creation-marketo-optimizer` | プログラムとそのジャーニーに対して、読み取り専用の準備状況チェックを実行します。 |
| `marketo-optimizer__create_channel` | `channel-content-authoring`、`program-creation-marketo-optimizer`および`image-to-html`をハンドオフで使用 | チャネルの作成とリンク： メールの場合、最初の呼び出しはテンプレートをリストし、2番目の呼び出しは選択したテンプレートを使用してメールを作成し、リンクします。 |
| `marketo-optimizer__get_channel` | `channel-content-authoring` | 電子メールの件名とHTMLを含むチャネルを読む（オプション）。 |
| `marketo-optimizer__list_channels` | `channel-content-authoring` | タイプ別にチャネルを参照し、オプションで名前でフィルタリングします。 |
| `marketo-optimizer__update_channel_content` | `channel-content-authoring`; `image-to-html` ～ ハンドオフ | 変換されたHTMLの適用を含め、メールの件名またはHTMLを更新します。 |
| `marketo-optimizer__image_to_html` | `image-to-html` | 非同期メールデザインの変換を開始し、編集可能なHTMLを取得します。 |
| `marketo-optimizer__list_asset_library_images` | `landing-page-authoring` | ランディングページのスロットの交換画像を検索します。 |
| `marketo-optimizer__add_asset_to_program_or_folder` | `landing-page-authoring` | 選択したOptimizer プログラムまたはフォルダーに新しいランディングページを登録します。 |
| `marketo-optimizer__get_person_story` | `personalization-engine-health` | 数値IDで1人のパーソナライゼーションストーリーを読む。 |
| `marketo-optimizer__get_persona_story` | `personalization-engine-health` | ペルソナ名の例を正確に把握する。 |
| `marketo-optimizer__run_arbitration` | `personalization-engine-health` | 明示的な確認の後、対象となるユーザーのジャーニーを再スコアリングして再選択します。 |
| `marketo-optimizer__get_arbitration_summary` | `personalization-engine-health` | 最新の仲裁実行の概要の統計を読み取ります。 |
| `marketo-optimizer__get_arbitration_decisions` | `personalization-engine-health` | 最新の仲裁ランから1人あたりの決定を読み取ります。 |
| `marketo-optimizer__get_ai_decisioning_health_summary` | `ai-decisioning-health` | テナント対応状況全体レポートを取得します。 |
| `marketo-optimizer__get_persona_distribution` | `ai-decisioning-health` | ペルソナの数と割合を報告する： |
| `marketo-optimizer__get_people_without_personas` | `ai-decisioning-health` | ペルソナを持たない人々の数と割合を報告する： |
| `marketo-optimizer__get_person_story_attribute_coverage` | `ai-decisioning-health` | 特性カテゴリのカバレッジを測定し、入力フィールドを特定します。 |
| `marketo-optimizer__get_person_story_data_completeness` | `ai-decisioning-health` | ペルソナ別のストーリーの豊かさ、完全性、バリエーションをレポートできます。 |
| `marketo-optimizer__get_person_story_coverage` | `ai-decisioning-health` | レポート記事のカバー範囲、トレンド、保留中の生成。 |
| `marketo-optimizer__get_personalization_story_pipeline_status` | `ai-decisioning-health` | パイプラインのステータス、実行履歴、レポート期間の読み取り。 |
| `marketo-optimizer__get_person_story_refresh_backlog` | `ai-decisioning-health` | ソースデータが変更されたため、更新待ちのストーリーをカウントします。 |
| `marketo-optimizer__get_person_intent_signal_coverage` | `ai-decisioning-health` | 製品の意図、キーワードの意図、アクティビティカバレッジを測定。 |
| `marketo-optimizer__get_person_story_activity_coverage` | `ai-decisioning-health` | キャプチャしたエンゲージメントフィールドとアクティビティの傾向をレポートします。 |
| `marketo-optimizer__get_person_audience_membership_distribution` | `ai-decisioning-health` | 1人あたりのオーディエンスメンバーシップの平均と分布を報告します。 |
