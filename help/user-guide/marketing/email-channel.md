---
title: メールの作成とジャーニーへの追加
description: プログラムやフォルダー内で電子メールをスタンドアロンアセットとして作成したり、Marketo Optimizerでターゲットを絞ったコミュニケーションのために電子メールアクションノードを個人ジャーニーに追加したりできます。
feature: Email Authoring, Person Journeys
role: User
TQID: 'https://experienceleague.adobe.com/tCJStmR66eVoB8cvzcQWc5UO-klwTjnNfK-4K5Nz-S0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 6311ce00a5c7666c07fb1a523c954637d2e86e46
workflow-type: tm+mt
source-wordcount: '2734'
ht-degree: 7%
---
# メールを作成し、ジャーニーに追加する

[!DNL Adobe Marketo Optimizer]では、最新のエンタープライズ向けメール作成および配信エクスペリエンスをB2B マーケターに提供しています。これにより、プログラムやジャーニーからメールを作成、公開、送信できます。

メールは独立したアセットなので、ジャーニーを作成する必要はありません。 プログラムまたはそのフォルダーの1つの中に[ メール ](#create-email-from-programs)を作成し、準備ができたら[ メールを公開](#publish-email)し、そのプログラムの任意のジャーニーから[ メールを送信します](#add-email-from-journey)。

## メールのライフサイクル {#lifecycle}

電子メールは、常に次のいずれかの状態になります。

| 状態 | 説明 |
| ----- | ----------- |
| **ドラフト** | 新しい電子メールはすべてドラフトとして開始され、プログラムツリーに赤いエンベロープアイコンが表示されます。 プロパティ、アクション、コンテンツを編集し、パーソナライズ、分析、名前の変更、削除を行うことができます。 |
| **パブリッシュ済み** | 公開された電子メールはロックされ、送信準備が整い、緑色の封筒アイコンが表示されます。 編集または非公開にすることはできず、ジャーニーでメールを選択するとリストに表示されます。 |
| **ジャーニーの場合** | _電子メールを送信_ アクションで公開された電子メールを選択すると、ジャーニーに属する公開されたコピーが作成されます。 コピーは読み取り専用で、後で元のコピーが複製および修正された場合も変更されません。 |

電子メールを公開すると、電子メールがドラフトから公開に移動します。 _メール送信_ アクションノードに対して選択すると、コピーがジャーニーに存在します。 公開した電子メールを変更するには、[複製します](#duplicate-email)。 複製は、同じコンテンツと設定を持つドラフトとして作成されます。

![ メールのライフサイクル：下書きを公開するか、公開済みのメールを選択して読み取り専用のジャーニーコピーを作成するか、公開済みのメールを複製して新しい下書きを作成します。](./assets/email-lifecycle-diagram.svg){width="800" zoomable="yes"}

メールの状態によって、アクションの可用性が決まります。

| アクション | 下書き | 公開日 | ジャーニー内 |
| ------ | ----- | --------- | ------------ |
| プロパティ、アクション、コンテンツの編集 | はい | × | いいえ |
| Personalise email | はい | × | いいえ |
| メールを分析 | はい | × | いいえ |
| 公開 | はい、ブロッキングアラートが解決されると | 公開済み | 自動的に公開 |
| 複製 | はい | ○ | いいえ |
| 名前変更 | はい | いいえ | いいえ。 コピーに名前を付けます。 |
| 削除 | はい | いいえ | いいえ。 代わりに、_メール送信_ ノードを削除してください。 |
| ジャーニーで選択 | いいえ | はい | 該当なし |

## 前提条件 {#before-you-begin}

実行するタスクに対して、次の[製品権限](../start/permissions-reference.md)がユーザーロールに含まれていることを確認してください。

* **[!UICONTROL B2B プログラムを表示]**&#x200B;および&#x200B;**[!UICONTROL B2B フォルダーを表示]** – 電子メールが格納されているプログラムとフォルダーを表示します。
* **[!UICONTROL B2B メールを表示]** - メール メッセージを表示します。
* **[!UICONTROL B2B メールの管理]** – 電子メールの作成、編集、複製、名前変更、削除、公開。
* **[!UICONTROL B2B人物ジャーニーの管理]** – 人物ジャーニーのメール アクションを追加または置換します。 ジャーニーへの読み取り専用アクセスには、**[!UICONTROL B2B人物ジャーニーの表示]**&#x200B;を使用します。
* **[!UICONTROL B2B会話体験を管理]** - [!DNL Coworker]にアクセスして、メールをパーソナライズまたは分析します。 [!DNL Coworker]のアクションには、対応するメール権限も必要です。

追加の権限は、次の関連する設定または送信タスクを実行する場合にのみ必要です。

* **[!UICONTROL B2B プログラムの管理]** – まだプログラムが存在しない場合は、プログラムを作成します。
* **[!UICONTROL B2B チャネル設定の管理]**&#x200B;および&#x200B;**[!UICONTROL B2B メール設定の表示]** – 電子メールチャネル設定を作成します。 管理者は、メール配信設定を設定するために&#x200B;**[!UICONTROL B2B メール設定の管理]**&#x200B;も必要です。
* **[!UICONTROL B2B人物ジャーニーを公開]** – 電子メールを送信するジャーニーを公開します。

メールを作成する前に、次の点を確認してください。

* 電子メールは、プログラムまたはそのフォルダーに格納されます。 電子メールを作成する前に、プログラムを定義します。 ジャーニーは、独自のプログラムからのみメールを送信できます。
* メールチャネル設定を選択するには、「**[!UICONTROL アクション]**」電子メール タブを使用します。 管理者は[電子メールチャネル設定](../admin/email-channel-configuration.md)を管理します。
* プログラム内で必要なだけメールを作成できます。

>[!NOTE]
>
>初めて電子メールを送信する場合は、[電子メールの配信品質](../start/email-deliverability.md)と必要な[電子メールチャネル ](../admin/email-channel-configuration.md)が設定されていることを確認してください。

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

>[!BEGINSHADEBOX]

## 現在の制限事項 {#limitations}

* **テストプロファイル、コンテンツのシミュレート、プルーフの送信**&#x200B;は、現在のリリースでは使用できません。 LitmusのレンダリングとSpamAssassin ベースのスパムレポートは、今後のリリースで予定されています。
* **アカウントレベルのパーソナライゼーションとカスタムオブジェクトデータ**&#x200B;は、現在のリリースでは使用できません。 プロファイル属性の利用：
* 既存の[!DNL Marketo Engage] テンプレートの&#x200B;**Velocity-to-Handlebars自動移行**&#x200B;は、リクエストに応じて利用できます。
* **電子メールによるコメントと共同作業** （インラインコメント、@mentions、リクエストとレビューのワークフロー）は、今後のリリースで予定されています。
* **AEM Assets、AEM コンテンツフラグメント、Adobe Express**&#x200B;の統合は、今後のリリースで予定されています。

>[!ENDSHADEBOX]

## 主要概念 {#key-concepts}

個人ジャーニーのメールを作成し、メールコンテンツをオーサリングする前に、次の概念を確認します。

| 概念 | [!DNL Adobe Marketo Optimizer]内 |
| ------- | ---------------------- |
| **_[電子メールデザインスペース](../content/email-authoring.md#email-design-tools)_** | メールコンテンツの作成に使用されるビジュアルキャンバスとデザインツール。 ドラッグ&amp;ドロップ操作のレイアウトコンポーネント、テンプレート、フラグメント、テーマ、パーソナライゼーションエディターが含まれます。 |
| **_[テンプレート](../content/templates.md)_** | 新しいメールの作成に使用できる、再利用可能なメールレイアウト。 これは、Adobeが提供するビルトインサンプルテンプレートまたはチームが作成したカスタムビルトインテンプレートのいずれかです。 |
| **_[ビジュアルフラグメント](../content/fragments.md)_** | 複数のメールに挿入できる、再利用可能なコンテンツブロック（ヘッダー、フッター、CTA、免責条項など）。 フラグメントを更新すると、フラグメントを使用するすべての電子メールに変更が反映されます。 |
| **_[テーマ](../content/email-authoring.md#design-from-scratch)_** | 再利用可能なスタイルプリセット（色、タイポグラフィ、間隔、ボタンスタイル）がメールに適用されます。 |
| **_[Personalization トークン](../content/personalization-expressions.md)_** | Handlebars式（例：`{{profile.firstName}}`）は、送信時に、各受信者のプロファイルデータを使用して解決されます。 |
| **_[スタンドアロン電子メール](#lifecycle)_** | あらゆるジャーニーから独立して存在するメールアセット。 プログラムまたはそのフォルダーの1つで作成され、ドラフトからパブリッシュに移動します。 |
| **_[メールの種類](#email-types)_** | メールの作成時に選択する分類（**[!UICONTROL マーケティング]**&#x200B;または&#x200B;**[!UICONTROL トランザクション]**）。 同意目的でメッセージを処理する方法を[!DNL Marketo Optimizer]に伝えます。 |
| **_[メールアクションを送信](./action-nodes.md#add-an-action-node)_** | チャネル設定とメールコンテンツを使用してメールを配信するジャーニーアクションノード。 |

## メールの種類 {#email-types}

メールを作成するときは、そのタイプを選択します。 このタイプは[!DNL Marketo Optimizer]に同意目的でメッセージを処理する方法を伝えるので、送信する理由と一致するメッセージを選択します。

| タイプ | の使用 |
| ---- | ------- |
| **[!UICONTROL マーケティング]** | 製品リリースのお知らせ、ニュースレター、イベントへの招待などのプロモーションメッセージ。 |
| **[!UICONTROL トランザクション]** | 注文、登録、出荷確認など、個人が行った操作によって期待される操作メッセージ。 |

このタイプは、**[!UICONTROL プロパティ]** タブにメール **[!UICONTROL カテゴリー]**&#x200B;として表示されます。

## プログラムツリーでのメールの作成 {#create-email-from-programs}

プログラムやフォルダーにメールを作成し、ジャーニーとは別に作成します。

1. 左側のナビゲーションで、**[!UICONTROL マーケティング管理]**&#x200B;を展開し、**[!UICONTROL プログラム]**&#x200B;を選択します。

1. プログラムツリーで、_詳細_ アイコン （**...**）をクリックします 電子メールを作成するプログラムまたはフォルダーの横にある「**[!UICONTROL 電子メールを作成]**」を選択します。

   ![ プログラムツリーからメールを作成](./assets/email-create-from-programs-tree.png){width="400"}

1. _[!UICONTROL メールを作成]_ ダイアログで、次のフィールドに入力します。

   * **[!UICONTROL 親]** - （必須）電子メールが保存されるプログラムまたはフォルダー。 開始したプログラムに設定され、別のプログラムまたはプログラムのフォルダーのいずれかに変更できます。

   * **[!UICONTROL メールの種類]** - **[!UICONTROL マーケティング]**&#x200B;または&#x200B;**[!UICONTROL トランザクション]**&#x200B;を選択します（[ メールの種類](#email-types)を参照）。

   * **[!UICONTROL 名前]** - （必須） プログラムツリーに、メールを識別する名前を入力します。

   * **[!UICONTROL 説明]** - （オプション）電子メールとその目的に関するメモをチームに入力します。

   ![電子メールダイアログの作成](./assets/email-create-dialog-programs-tree.png){width="400"}

1. 「**[!UICONTROL 作成]**」をクリックします。

メールは独自のタブで開き、プログラムツリーのプログラムの下にドラフトとして表示されます。 電子メールが開いている間は、[!DNL Coworker]個のプロンプトはその電子メールの範囲に含まれます。

次に、[電子メールを設定](#define-email-properties)、[ アラートを解決](#alerts)、[公開](#publish-email)します。

### メールのプロパティとアクションを定義 {#define-email-properties}

下書きメールには、3つのタブがあります。**[!UICONTROL プロパティ]**、**[!UICONTROL アクション]**、**[!UICONTROL コンテンツ]**。 順番にそれらを処理し、変更を保存します。 プログラムツリーで電子メールを作成すると、電子メールページが開きます。 後でドラフトを開くには、プログラムツリーでメールを選択します。

#### 「プロパティ」タブと「アクション」タブを完了します {#properties-actions-tabs}

1. （オプション）「**[!UICONTROL プロパティ]**」タブに、**[!UICONTROL 説明]**&#x200B;およびメール用に取得するその他の記述情報を入力します。

   ![電子メールのプロパティ タブ ](./assets/email-properties-tab.png){width="800" zoomable="yes"}

1. 「**[!UICONTROL アクション]**」タブを選択し、メールの機能設定を完了します。

   * **[!UICONTROL 電子メール]** – 使用する&#x200B;**[!UICONTROL 電子メールチャネル設定]**&#x200B;を選択または作成します。

     これは、送信者ID、返信先アドレス、サブドメイン、IP プール、メールタイプ（マーケティングまたはトランザクション）、トラッキングを定義する、再利用可能なメール配信設定のセットです。 _表示_ アイコンをクリックして、選択した設定の設定を確認します。

     管理者は、[電子メールチャネル設定](../admin/email-channel-configuration.md)で設定を作成します。

   * **[!UICONTROL ビジネスルール]** - （オプション）ルールセットを選択して、メールアクションにキャッピングルールまたはサイレントアワーのルールを適用します。

     ビジネスルールと、チャネル通信のルールセットを定義およびアクティブ化する方法について詳しくは、[_ビジネスルール_](../admin/business-rules.md)&#x200B;を参照してください。

   * **[!UICONTROL アクションの追跡]** – 電子メールで追跡するアクションのチェックボックスをオンにします。

   ![電子メールチャネル – 「アクション」タブ ](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"}

#### 件名と内容を追加 {#content-tab}

1. 「**[!UICONTROL コンテンツを編集]**」をクリックするか、「**[!UICONTROL コンテンツ]**」タブを選択します。

   ![電子メールコンテンツタブ ](./assets/email-content-tab.png){width="500" zoomable="yes"}

1. 電子メールの件名フィールドに表示する&#x200B;**[!UICONTROL 件名]** テキストを入力します。

   件名は必須です。

   _パーソナライズ_ アイコン（![ パーソナライズアイコン ](../assets/do-not-localize/icon-personalize.svg)）をクリックして、フィールドでパーソナライゼーショントークンを使用します。

1. （オプション）公開プロセス中にメール HTMLのサイズを小さくするには、「**[!UICONTROL HTML サイズを最適化]**」チェックボックスをオンにします。

   これにより、Gmailなどのクライアントでのメールクリッピングを防ぐことができます。 Gmailでは、100 KBを超えるメッセージが切り捨てられます。 詳しくは、[_電子メールのHTML サイズの最適化_](#optimize-html-size)&#x200B;を参照してください。

1. **[!UICONTROL メール本文を編集]**&#x200B;をクリックしてビジュアルデザインツールにアクセスし、[ コンテンツの作成を開始](../content/email-authoring.md)します。

   または、**[!UICONTROL コードエディター]**&#x200B;をクリックして、プレーンHTMLで独自のコンテンツをコーディングすることもできます。 既存のHTMLをメールデザインに再利用する場合は、それをコピーしてエディターに貼り付けることができます。

### アラートの確認 {#alerts}

メールヘッダーの&#x200B;**[!UICONTROL アラート]** ボタンには、[!DNL Adobe Marketo Optimizer]が見つけた問題の数が表示されます。 クリックしてリストを表示します。

![下書きメールのアラートをブロック中](./assets/email-alerts-blocking.png){width="450"}

アラートには、次の2種類があります。

* **ブロックの問題** – これらの問題のいずれかが残っている間、**[!UICONTROL 公開]**&#x200B;は利用できません。メールの&#x200B;_詳細_ メニューには&#x200B;**[!UICONTROL 公開に対する電子メールアラートの解決]**&#x200B;が表示されます。 電子メールを公開する前にすべてのブロックの問題を解決します。

  以下に例を示します。

  * 差出人名が空です
  * 件名がありません
  * メールコンテンツが空です

* **警告** – これらは確認する価値のあることを示していますが、公開を妨げることはありません。 電子メールはアラートを表示できますが、残りのアラートが警告の場合は引き続き公開されます。

  以下に例を示します。

  * メール本文にオプトアウトリンクが存在しません
  * HTMLのテキストバージョンが空です
  * 空のリンクが検出されました
  * 電子メールが100 Kを超えています

## プログラムツリーでのメールの管理 {#manage-emails}

電子メールは、エンベロープのアイコンが付いたプログラムツリーに表示されます。 赤い封筒が下書きを示す。 緑色の封筒は、公開された電子メールをマークします。 _詳細_ アイコン （**...**）をクリックします 電子メールの横に配置して管理します。

![ プログラムツリーの「その他のメール」メニュー](./assets/email-tree-more-menu.png){width="400"}

下書きメールのメニューには、**[!UICONTROL 公開]**、**[!UICONTROL 電子メールのパーソナライズ]**、**[!UICONTROL 電子メールの分析]**、**[!UICONTROL 重複]**、**[!UICONTROL 名前変更]**、**[!UICONTROL 削除]**&#x200B;が含まれます。

公開済みの電子メールの場合、**[!UICONTROL 重複]**&#x200B;が唯一のオプションです。

### 電子メールのパーソナライズと分析 {#personalize-analyze}

メールはドラフトですが、_More_ メニューには2つのコンテンツツールが含まれています。 公開したメールは変更できないので、公開前に実行します。

* **[!UICONTROL 電子メールをパーソナライズ]** – 電子メールが読み込まれた状態で[!DNL Coworker]を開きます。 パーソナライズされたコンテンツをメールに追加するには、ターゲットグループを記述します。 詳しくは、[_ペルソナ別のメールコンテンツのパーソナライズ_](../agents/personalize-content.md)&#x200B;を参照してください。

  ![同僚のメールのパーソナライズ ](./assets/email-personalize-coworker.png){width="700" zoomable="yes"}

* **[!UICONTROL メールを分析]** – 既に作成したコンテンツを確認します。 [既存の電子メールの分析](../agents/personalize-content.md#analyze-existing-email)を参照してください。

### メールの公開 {#publish-email}

送信する準備ができたらメールを公開します。 ジャーニー](#add-email-from-journey)で電子メールを[選択すると、公開された電子メールのみが一覧表示されます。

1. 電子メールにブロッキング [ アラート ](#alerts)がないことを確認してください。

1. プログラムツリーで、_詳細_ アイコン （**...**）をクリックします 電子メールの横にある「**[!UICONTROL 公開]**」を選択します。

1. _[!UICONTROL メールを公開]_&#x200B;確認ダイアログで、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ![電子メールを公開ダイアログ ](./assets/email-publish-dialog.png){width="400"}

電子メールアイコンが緑色に変わります。 メールを選択すると、そのコンテンツ、プロパティ、アクションを要約した読み取り専用ビューが開きます。

![読み取り専用ビューでメールを公開](./assets/email-published-view.png){width="700" zoomable="yes"}

>[!IMPORTANT]
>
>公開は永続的です。 公開された電子メールは、編集、名前の変更、削除、ドラフトに戻すことはできません。 変更を加えるには、[電子メール ](#duplicate-email)を複製します。

### メールの複製 {#duplicate-email}

公開済みメールを変更するには、そのメールを複製します。 オリジナルを変更せずにバリエーションを試すには、ドラフトを複製することもできます。

1. プログラムツリーで、_詳細_ アイコン （**...**）をクリックします 電子メールの横にある「**[!UICONTROL 複製]**」を選択します。

1. _[!UICONTROL 電子メールを複製]_ ダイアログで、必要に応じて&#x200B;**[!UICONTROL 名前]**&#x200B;を変更します。

   デフォルトでは、元の名前の後に`_copy`が続きます。 オプションで、**[!UICONTROL 説明]**&#x200B;を追加します。

   ![電子メールダイアログを複製](./assets/email-duplicate-dialog.png){width="400"}

1. 「**[!UICONTROL 複製]**」をクリックします。

複製は、同じコンテンツと設定を持つドラフトとして作成されます。 変更を加えてから公開します。

## ジャーニーへのメールの追加 {#add-email-from-journey}

メールを送信するには、同じプログラムでジャーニーにメールを追加します。 メールを選択すると、[!DNL Marketo Optimizer]はそのジャーニーのメールのコピーを作成し、そのコピーを自動的に公開します。 メールはプログラムツリーから送信されるので、[最初にメールを作成して公開](#create-email-from-programs)します。

同じメールを複数のジャーニーで使用できます。 選択するたびに、そのジャーニー用に個別のコピーが作成され、各コピーに一意の名前を付けることができます。

### メールを送信アクションのメールを選択 {#select-email-in-journey}

1. ジャーニーを開き、[_アクションを実行_ ノード ](action-nodes.md#add-an-action-node)を選択または追加します。

1. _[!UICONTROL アクションを選択]_&#x200B;で、**[!UICONTROL 電子メールを送信]**&#x200B;を選択します。

1. 「_[!UICONTROL メールソース]_」で、次のいずれかを選択します。

   * **[!UICONTROL プログラムツリーからメールを選択]** - ジャーニーのプログラムまたはそのフォルダーから公開されたメールを使用するには、このオプションを選択します。

   * **[!UICONTROL AIでパーソナライズされた電子メールを使用]** - AIで生成された電子メールを使用するには、このオプションを選択します。 これらのメールは、AIを活用して受信トレイを最適化されており、オファーやCTAにおいて、顧客の要約と回答が反映されています。

   ![ アクションを実行 – メール ソース ](./assets/person-action-node-email-source.png){width="600"}

   ノードには、電子メールを選択するまで空白の電子メール名が表示されます。

1. 「**[!UICONTROL メールを選択]**」をクリックします。

   * **_プログラムツリーの電子メール:_** _[!UICONTROL 電子メールを選択]_ ダイアログで、電子メールを検索して選択します。

     必要に応じて、**[!UICONTROL 電子メールを検索]**&#x200B;してフィルタリングします。 リストから電子メールを選択してプレビューし、件名を確認します。

     ![電子メールダイアログを選択](./assets/email-select-dialog.png){width="600" zoomable="yes"}

     >[!NOTE]
     >
     >ダイアログには、ジャーニープログラムとそのフォルダーから公開されたメールのみが一覧表示されます。 ドラフトは、[公開するまで表示されません](#publish-email)。 電子メールが表示されない場合は、公開済み（緑色のアイコン）があり、正しいプログラムに配置されていることを確認します。

     **[!UICONTROL 名前]**&#x200B;に、ジャーニー内で電子メールに含める必要がある名前を入力します。

     デフォルトでは、元の名前の後に`_copy`が続きます。 ジャーニーのコンテキストで意味のあるものに名前を変更します。

   * **_AI パーソナライズされた電子メール:_** 「_[!UICONTROL AI生成の電子メールを選択]_」ダイアログで、パーソナライズされた電子メールを検索して選択します。

     リストからパーソナライズされたメールを選択します。 ダイアログには、AI ライブラリに保存されている&#x200B;_AI パーソナライズされたメール_&#x200B;が一覧表示されます。 詳しくは、ペルソナ別のメールコンテンツのパーソナライズを参照してください。

     ![AIが生成した電子メールダイアログを選択](./assets/person-action-node-email-select-ai-generated.png){width="450" zoomable="yes"}

1. 「**[!UICONTROL 選択]**」をクリックします。

### ジャーニーメールのコピー {#journey-copy}

コピーがジャーニーに追加され、公開され、オレンジ色のアイコンが付いたプログラムツリーのジャーニーの下に表示されます。 独自のアクション IDがあり、読み取り専用です。

![ プログラムツリー内のメールのジャーニーコピー](./assets/email-journey-copy-tree.png){width="700" zoomable="yes"}

ジャーニーは独自のコピーを保持します。 コンテンツと設定は、メールを選択した時点でコピーされます。 後で元のジャーニーを複製して修正した場合、既存のジャーニーはコピーしたバージョンを引き続き送信します。

オプションの[送信時間の最適化](email-send-time-optimization.md)では、電子メールを選択した後にジャーニーアクションノードを設定します。

### ジャーニーのメールの更新 {#update-email-in-journey}

ジャーニーのコピーは読み取り専用なので、編集するのではなく置き換えます。

1. [元の公開済み電子メールを](#duplicate-email)複製し、ドラフトに変更を加え、[公開します](#publish-email)。

1. ジャーニーで、_メールを送信_ ノードを選択し、_アクションを実行_ パネルのゴミ箱アイコンを使用して削除します。

1. 新しい&#x200B;_メールを送信_ アクションをその場所に追加し、更新されたメールを選択します。

## メールの HTML サイズの最適化 {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="HTML サイズを削減"
>abstract="このオプションを有効にすると、公開時に不要な空白、インデントおよび必須ではないコメントが削除され、メールの HTML が圧縮されます。 これにより、Gmailなどのクライアントでのメールクリッピングを防ぐことができます。 Gmailでは、100 KBを超えるメッセージが切り捨てられます。"

[!DNL Marketo Optimizer] を使用すると、公開プロセス中に不要な空白、インデント、必須ではないコメントが削除され、メール の HTML バージョンが圧縮されます。 HTML サイズを小さくすると、次の操作を実行できます。

* **メールクリッピング**&#x200B;を回避する - Gmail などの一部のメールクライアントでは、100 KB を超えるメッセージが切り捨てられ、受信者が完全なコンテンツを表示できなくなります。
* 受信者のインボックスでの&#x200B;**メールの読み込み時間**&#x200B;を改善する。
* **配信品質**&#x200B;を向上させ、帯域幅の使用を削減する。

この最適化は自動的に適用されません。_[!UICONTROL コンテンツ]_ タブで有効にする必要があります。

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> HTML サイズの削減は、公開時にのみ適用されます。

この最適化は、メールクライアントに対して安全です。

* MSO／Outlook の条件付きコメントが保持されます。
* 実際のコンテンツ、画像、ビデオは変更されません。

>[!NOTE]
>
>メールサイズの削減は、メールの元の HTML 構造によって異なります。 コンテンツが既にコンパクトになっている場合や、メールペイロードが非常に大きい場合は、縮小が最小限になり、クリッピングが完全に妨げられないことがあります。

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
