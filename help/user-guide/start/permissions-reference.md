---
title: 製品の権限
description: Marketo Optimizer機能へのアクセスを制御するExperience Platform権限のリストと、管理者、オールアクセス、および読み取り専用ユーザーに対する説明と推奨権限のリストを参照します。
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: a33f749c32631dcd77ecf2892bdc3b1a5e06cd66
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 6%
---
# 製品の権限

次の権限は、[!DNL Adobe Marketo Optimizer]の機能へのアクセスを制御します。 [!DNL Adobe Experience Platform]の&#x200B;_[!UICONTROL 権限]_&#x200B;領域の役割に追加します。 役割の作成とユーザーへの割り当てについて詳しくは、[_ユーザーのアクセスと権限_](./user-management.md)&#x200B;を参照してください。

最後の3つの列には、[推奨ユーザータイプ ](#suggested-user-types)のそれぞれに対して推奨される権限（管理者、すべてのアクセスユーザー、読み取り専用アクセスユーザー）が表示されます。 チェックマーク （✔）は、そのユーザータイプに対して権限が推奨されていることを意味し、ダッシュ （ – ）は、そうでないことを意味します。 組織に合わせてレコメンデーションを調整する：

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] アクセスするには、次の命名規則を使用してプロビジョニングされた特定のサンドボックスを有効にする必要があります：`Mktoaep` + [!DNL Marketo Engage] サブスクリプション プレフィックス。 例えば、リンクされた[!DNL Marketo Engage] サブスクリプションのプレフィックスが&#x200B;_AcmeAssoc_&#x200B;の場合、[!DNL Marketo Optimizer] アクセスに必要なサンドボックスは&#x200B;_MktoaepAcmeAssoc_&#x200B;です。 このサンドボックスをすべての役割に追加します。

>[!NOTE]
>
>Experience Platformで&#x200B;_[!UICONTROL 権限]_ タイルを表示するには、システム管理者である必要があります。

一部の権限は、製品でまだ使用できない機能に適用されます。 管理者はこれらの権限を追加できるようになりました。これにより、ユーザーは機能が利用可能になったときに該当するアクセス権を持つことができます。

## 推奨されるユーザータイプ {#suggested-user-types}

このページの表の権限の推奨事項を、作成する役割の出発点として使用します。 ユーザーのタイプごとに推奨されます。 組織に合わせて調整しましょう。

| 属性 | 管理 | すべてのアクセスユーザー | 読み取り専用アクセス ユーザー |
| --- | ----- | --------------- | --------------------- |
| **対象** | チームの[!DNL Marketo Optimizer]を設定および管理するユーザー。 | 毎日[!DNL Marketo Optimizer]で作業するマーケターとオペレーター。 | [!DNL Marketo Optimizer]を参照する必要がありますが、経営陣、アナリスト、監査人など、何も変更しないユーザー。 |
| **実行できること** | セットアップと管理設定を含むあらゆるものです。 | ジャーニー、プログラム、コンテンツ、リスト、レポート、アシスタントなど、あらゆる機能を利用する。 | ジャーニー、プログラム、コンテンツ、リスト、レポートを表示し、アシスタントに質問できます。 |
| **割り当てる権限** | このページのすべての権限（役割エディターで&#x200B;**[!UICONTROL すべてを追加]**&#x200B;を選択）。 | このページのテーブルの&#x200B;_すべてのアクセス_&#x200B;列に✔を持つ権限。 | このページのテーブルの&#x200B;_読み取り専用_&#x200B;列の✔を持つ権限。 |
| **含まれていません** | - | <li>管理者設定<li>チャネル設定（メール設定、フォームプリセット、ランディングページ設定、WhatsApp プリセットおよび設定を含む）<li>プログラムの種類（表示と管理） | <li>作成、編集、削除、公開、または書き出し（チャットアクセスを除くすべての&#x200B;_管理_&#x200B;および&#x200B;_公開_&#x200B;権限）<li>配信先でのオーディエンスのアクティブ化<li>メール設定やフォームプリセットの表示などの管理者設定とチャネル設定<li>プログラムタイプの表示 |
| **推奨ユーザーグループ** | Marketo Optimizer Administrators Group | Marketo Optimizer Users Group | Marketo Optimizer読み取り専用ユーザーグループ |
| **提案された役割** | Marketo Optimizer Administrator | Marketo Optimizer All Access User | Marketo Optimizer読み取り専用アクセス ユーザー |

これらのグループと役割を作成する手順については、[提案されたユーザータイプのユーザーグループと役割の作成](./user-management.md#create-suggested-roles)を参照してください。

## コンテンツとアセット {#content-assets}

| カテゴリ | 権限 | 説明 | 管理 | すべてのアクセス | 読み取り専用 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Assets | B2B Assetsの管理 | アセットファイルを作成、編集、削除します。 | ✔ | ✔ | - |
| | B2B メールの管理 | メールメッセージの作成、編集、削除。 | ✔ | ✔ | - |
| | B2B Formsの管理 | フォームの作成、編集、削除。 | ✔ | ✔ | - |
| | B2B フラグメントの管理 | コンテンツフラグメントを作成、編集、削除します。 | ✔ | ✔ | - |
| | B2B ランディングページの管理 | ランディングページの作成、編集、削除。 | ✔ | ✔ | - |
| | B2B メッセージ書き出しの管理 | 「_電子メール_」セクションでメッセージレポートをエクスポートします。 | ✔ | ✔ | - |
| | B2B テンプレートの管理 | コンテンツテンプレートを作成、編集、削除します。 | ✔ | ✔ | - |
| | B2B ウェビナーの管理 | インタラクティブなウェビナーを作成、編集、削除。 | ✔ | ✔ | - |
| | B2B Formsの公開 | ランディングページで使用するフォームを公開します。 | ✔ | ✔ | - |
| | B2B フラグメントの公開 | テンプレート、メール、ランディングページで使用するコンテンツフラグメントを公開します。 | ✔ | ✔ | - |
| | B2B ランディングページの公開 | ランディングページの公開： | ✔ | ✔ | - |
| | B2B Assetsを見る | Assets ライブラリとアセットファイルの詳細を表示します。 | ✔ | ✔ | ✔ |
| | B2B メールの表示 | 電子メールメッセージの表示。 | ✔ | ✔ | ✔ |
| | B2B Formsを見る | フォームの表示： | ✔ | ✔ | ✔ |
| | B2B フラグメントの表示 | コンテンツフラグメントのリストと詳細を表示します。 | ✔ | ✔ | ✔ |
| | B2B ランディングページを見る | ランディングページを見る。 | ✔ | ✔ | ✔ |
| | B2B テンプレートの表示 | コンテンツテンプレートのリストと詳細を表示します。 | ✔ | ✔ | ✔ |
| | B2B ウェビナーを見る | インタラクティブなウェビナーを見る。 | ✔ | ✔ | ✔ |

## チャネルの設定と管理 {#channels-admin}

| カテゴリ | 権限 | 説明 | 管理 | すべてのアクセス | 読み取り専用 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B 管理設定 | B2B 管理設定の管理 | デジタルアセット管理の接続、アセットリポジトリ、イベントなどの管理設定を行います。 | ✔ | - | - |
| B2B チャネル設定 | B2B チャネル設定の管理 | 左側のナビゲーションおよびすべてのチャネル設定操作の&#x200B;_チャネル_ メニュー項目にアクセスします。 | ✔ | - | - |
| | B2B メール設定の管理 | メール設定を行います。 これらの設定は、ユーザーがメールを送信する前に必要です。 | ✔ | - | - |
| | B2B Forms プリセットの管理 | フォームプリセットの作成、編集、削除。 | ✔ | - | - |
| | B2B ランディングページ設定の管理 | サブドメインなどのランディングページ設定を行います。 | ✔ | - | - |
| | B2B WhatsApp プリセットの管理 | WhatsApp メッセージプリセットと関連するSMS設定を作成、表示、削除します。 | ✔ | - | - |
| | B2B WhatsApp設定の管理 | WhatsApp チャネル設定を設定します。 | ✔ | - | - |
| | B2B Forms プリセットの公開 | フォームプリセットの公開： | ✔ | - | - |
| | B2B メール設定の表示 | メール設定（サブドメイン、PTR レコード、IP プール、抑制リスト、シードリスト、IP ウォームアッププラン）を表示します。 | ✔ | - | - |
| | B2B Formsプリセットの表示 | フォームプリセットの表示。 | ✔ | - | - |

## ジャーニー、プログラム、フォルダー {#journeys-programs}

| カテゴリ | 権限 | 説明 | 管理 | すべてのアクセス | 読み取り専用 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B フォルダートークン | B2B フォルダートークンの管理 | フォルダー上のトークンを作成、編集、削除します。 フォルダー内のすべての項目に変更が適用されるので、_B2B フォルダーの管理_&#x200B;から個別に割り当てます。 | ✔ | ✔ | - |
| | B2B フォルダートークンの表示 | フォルダーで定義されたトークンを表示します。 | ✔ | ✔ | ✔ |
| B2B フォルダー | B2B フォルダーの管理 | フォルダーを作成、編集、削除します。 | ✔ | ✔ | - |
| | B2B フォルダーの表示 | フォルダーを表示します。 | ✔ | ✔ | ✔ |
| B2B ジャーニー | B2Bジャーニーのトラフィック制御の管理 | 効果のシミュレーションを含む、ジャーニーのトラフィック制御を設定します。 | ✔ | ✔ | - |
| | B2B人物ジャーニーの管理 | _人物ジャーニー_ リストとすべての人物ジャーニー操作にアクセスします。 | ✔ | ✔ | - |
| | B2B人物ジャーニーの公開 | 個人ジャーニーを公開します。 | ✔ | ✔ | - |
| | B2Bジャーニーのトラフィック制御の表示 | ジャーニーのトラフィック制御の設定を表示します。 | ✔ | ✔ | ✔ |
| | B2B人物ジャーニーレポートの表示 | _個人ジャーニー_ レポートを含む個人ジャーニーレポートを表示します。 | ✔ | ✔ | ✔ |
| | B2B人物のジャーニーの表示 | _人物ジャーニー_ リストおよびジャーニーの詳細への読み取り専用アクセス。 | ✔ | ✔ | ✔ |
| B2B プログラムトークン | B2B プログラムトークンの管理 | プログラムおよびプログラムタイプのトークンを作成、編集および削除します。 | ✔ | ✔ | - |
| | B2B プログラムトークンの表示 | プログラムおよびプログラムタイプで定義されたトークンを表示します。 | ✔ | ✔ | ✔ |
| B2B プログラムの種類 | B2B プログラムの種類の管理 | マーケティングプログラムタイプを作成、編集、削除します。 | ✔ | - | - |
| | B2B プログラムの種類の表示 | マーケティングプログラムの種類を表示します。 | ✔ | - | - |
| B2B プログラム | B2B プログラムの管理 | マーケティングプログラムの作成、編集、削除。 | ✔ | ✔ | - |
| | B2B プログラムの表示 | マーケティングプログラムの表示。 | ✔ | ✔ | ✔ |

## オーディエンス、意図、配信先 {#audiences-intent}

| カテゴリ | 権限 | 説明 | 管理 | すべてのアクセス | 読み取り専用 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B配信先 | B2B配信先のアクティベーション | B2B向け配信先でオーディエンスを活用。 | ✔ | ✔ | - |
| | B2B配信先の管理 | B2B宛先の作成、編集、削除。 | ✔ | ✔ | - |
| | B2B配信先の表示 | B2B宛先への表示専用アクセス。 | ✔ | ✔ | ✔ |
| B2B インテント設定 | B2B インテント設定の管理 | インテント設定を作成、編集、削除します。 | ✔ | ✔ | - |
| | B2B インテント設定の表示 | インテント設定（インテントの重み付けモデル）を表示します。 | ✔ | ✔ | ✔ |
| B2B組織のルール | B2B組織ルールの管理 | 組織ルールを作成、編集、削除します。 | ✔ | ✔ | - |
| | B2B組織ルールの表示 | 組織ルールの表示。 | ✔ | ✔ | ✔ |
| B2B人物リスト | B2B人物リストの管理 | 個人リストの作成、編集、削除、リストメンバーシップの管理。 | ✔ | ✔ | - |
| | B2B人物リストの表示 | 静的リストと動的リスト。 | ✔ | ✔ | ✔ |

## レポート、ラボ、チャット {#reports-labs-chat}

| カテゴリ | 権限 | 説明 | 管理 | すべてのアクセス | 読み取り専用 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2Bの会話体験 | B2B会話体験の管理 | チャットパネルとアシスタントへのアクセス： パネル内のアクションには、一致する機能の権限も必要です。 例えば、ジャーニーを作成するには、_B2B人物ジャーニーの管理_&#x200B;が必要です。 [ チャット権限](#chat-permissions)を参照してください。 | ✔ | ✔ | ✔ |
| B2B Labs | B2B Labsの管理 | ラボ機能を有効にして設定します。 | ✔ | ✔ | - |
| | B2B Labsの事例を見る | 利用可能で有効なラボ機能を表示します。 | ✔ | ✔ | ✔ |
| B2B レポート | B2B埋め込みレポートを表示 | 「_レポート_」タブでレポートを表示します。 | ✔ | ✔ | ✔ |
| | B2B インテントレポートの表示 | インテントレポートの表示。 | ✔ | ✔ | ✔ |

## チャット権限 {#chat-permissions}

チャットの権限は、機能レベルの権限に従います。 [!DNL Coworker for Marketo Optimizer]は、チャット内のすべてのスキルまたはアクションを、チャット以外の機能に必要な権限と同じ権限に照らし合わせてチェックします。作成、編集、公開する&#x200B;_管理_&#x200B;権限と、読み取り専用スキルの&#x200B;_表示_&#x200B;権限です。 ユーザーに機能の権限がない場合、[!DNL Coworker]はそのアクションを実行できません。 例えば、ジャーニーを作成するには&#x200B;_B2B人物ジャーニーを管理_&#x200B;する必要があり、フォームをリストするには&#x200B;_B2B Formsを表示_&#x200B;する必要があります。

<!--
_Manage B2B Conversational Experience_ gives access to the [!DNL CX Coworker] chat panel, but it does not grant access to any feature functions.

Per wiki: 
Update 10/02: We are no longer mapping b2b-conversational-experience read or write to any tools. It was decided that chat will be available for all users without permissions, but what they can do within the chat (i.e. tools they can use) will be defined by other permissions.
-->

## 外部宛先権限 {#external-destinations-permissions}

[!DNL Marketo Optimizer]のユーザーに外部宛先へのアクセスを提供するには、次の権限が必要です。 列は、[推奨ユーザータイプ ](#suggested-user-types)で説明されている各ユーザータイプに対して同じ推奨事項に従います。

| カテゴリ | 権限 | 説明 | 管理 | すべてのアクセス | 読み取り専用 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| ダッシュボード | 標準ダッシュボードの管理 | データウェアハウスにないカスタム属性の追加。 | ✔ | ✔ | - |
| | 標準ダッシュボードを表示 | _プロファイル_、_宛先_、_セグメント_ ダッシュボードへの表示専用アクセス。 左側のナビゲーションの&#x200B;_ダッシュボード_&#x200B;へのアクセスも有効にします。 | ✔ | ✔ | ✔ |
| 宛先 | 宛先のアクティブ化 | アクティブな配信先へのデータのアクティベーション。 _宛先の表示_&#x200B;または&#x200B;_宛先の管理_&#x200B;も必要です。 | ✔ | ✔ | - |
| | マッピングなしでセグメントをアクティブ化 | マッピング手順を使用せずに、既存の配信先でオーディエンスを活用できます。 ユーザーは、アクティベーションワークフローでオーディエンスを追加および削除できますが、マッピングされた属性や ID を追加または削除することはできません。 _宛先の表示_&#x200B;も必要です。 | ✔ | ✔ | - |
| | 宛先オーサリング | Experience Platform Destination SDKを使用して宛先を作成します。 | ✔ | ✔ | - |
| | データセット宛先の管理とアクティブ化 | データセット書き出しフローを表示、作成、編集および無効化し、データセットへのデータをアクティベートします。 _宛先の表示_&#x200B;も必要です。 | ✔ | ✔ | - |
| | 宛先の管理 | 宛先の接続と宛先アカウントを表示、作成、削除します。 | ✔ | ✔ | - |
| | 宛先の表示 | _カタログ_ タブで利用可能な宛先を表示し、_参照_ タブで認証済みの宛先を表示します。 | ✔ | ✔ | ✔ |
| データガバナンス | B2B削除使用ラベルの管理 | データセットとスキーマに適用されたデータ使用ラベル（DULE）を表示、作成、削除します。 | ✔ | ✔ | - |
| | データ使用ポリシーの管理 | データ使用ポリシーの表示、作成、編集、削除。 | ✔ | ✔ | - |
| | データ使用ポリシーの表示 | 組織に属するデータ使用ポリシーの表示専用アクセス。 | ✔ | ✔ | ✔ |
| データ取り込み | ソースの管理 | ソースの表示、作成、編集、および無効化。 | ✔ | ✔ | - |
| | ソースの表示 | _カタログ_ タブで利用可能なソースを表示し、_参照_ タブで認証されたソースを表示します。 | ✔ | ✔ | ✔ |
| プロファイル管理 | プロファイル設定の管理 | すべてのプロファイル設定を表示および編集します。 | ✔ | ✔ | - |
| | プロファイル設定の表示 | すべてのプロファイル設定への表示専用アクセス。 | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
