---
title: ランディングページ設定
description: プレースホルダー
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 42%

---


# ランディングページの設定

管理者は、ランディングページの設定が、これらのページを作成および公開するマーケター向けに適切に設定されていることを確認する必要があります。 ブランドを反映し、エンゲージメントを効果的に追跡するランディングページを作成するには、次のふたつの設定タイプが必要です。

* **_サブドメイン_** — ランディングページをホストする場所を設定します。 ランディングページサブドメインを管理して、ドメイン設定をデリゲート、設定、またはデリゲート解除します。
* **_プリセット_** — マーケターがランディングページを一貫して作成および管理できるように、再利用可能な設定（サブドメインやその他のチャネル設定を含む）を定義します。

## サブドメイン {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp_header"
>title="ランディングページのサブドメインのデリゲート"
>abstract="ランディングページで使用するサブドメインを設定します。 既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp"
>title="ランディングページのサブドメインのデリゲート"
>abstract="ランディングページプリセットを作成する前に、ランディングページサブドメインを設定する必要があります。 既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを設定できます。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain"
>title="ランディングページプリセットの作成"
>abstract="ランディングページプリセットを作成するには、サブドメイン名リストから選択するように、少なくとも 1 つの設定済みランディングページサブドメインがあることを確認します。"

設定されたランディングページのサブドメインを確認するには、**[!UICONTROL 管理]** > **[!UICONTROL チャネル]**&#x200B;に移動します。 ナビゲーションパネルの&#x200B;_[!UICONTROL ランディングページ]_&#x200B;で、**[!UICONTROL ランディングページサブドメイン]**&#x200B;を選択します。

<!-- ![Channel configurations - landing page subdomains](./assets/config-channels-landing-pages-subdomains.png){width="800" zoomable="yes"} -->

**ステータス**&#x200B;列には、サブドメインの作成とデリゲーションのプロセスに関する情報が表示されます。

* _[!UICONTROL ドラフト]_: サブドメインのデリゲーションはドラフトとして保存されます。 サブドメイン名をクリックして、作成プロセスを再開します。
* _[!UICONTROL 処理中]_: サブドメインは、使用する前に必要な複数の構成チェックを通じて処理中です。
* _[!UICONTROL 成功]_: チェックを正常に通過したサブドメインで、メッセージの配信に使用できます。
* _[!UICONTROL 失敗]_: サブドメインのデリゲーションが送信された後、1つまたは複数のチェックに失敗しました。

>[!NOTE]
>
>ランディングページプリセットを[作成](#lp-presets)する前に、ランディングページに使用するサブドメインを設定する必要があります。 既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。

ランディングページのサブドメイン設定は、すべての環境に共通の&#x200B;**です**。 したがって、

* ランディングページのサブドメインにアクセスして編集するには、本番稼働用サンドボックスにおける&#x200B;**[!UICONTROL ランディングページサブドメインの管理]**&#x200B;権限が必要です。

* ランディングページのサブドメインを変更すると、本番稼働用サンドボックスにも影響します。

<!-- 
### Use an existing subdomain {#lp-existing-subdomain}

To use a subdomain that is already delegated to Adobe:

1. Click **[!UICONTROL Set up landing page subdomain]**.

    ![](assets/lp_set-up-subdomain.png)

1. For _[!UICONTROL Configuration type]_, choose **[!UICONTROL Use delegated domain]**.

    ![](assets/lp_use-delegated-subdomain.png)

1. Enter the prefix that you want to display in the landing page URL.

    Only alpha-numeric characters and hyphens are allowed.

    >[!CAUTION]
    >
    >Do not use `cdn` or `data` prefixes as these are reserved for internal use. You should also avoid other restricted or reserved prefixes, such as `dmarc` or `spf`.

1. Select a delegated subdomain from the list.

    You cannot select a subdomain that is already used as landing page subdomain.
    
    ![](assets/lp_prefix-and-subdomain.png)

    You cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your landing pages, you cannot use 'marketing2.yourcompany.com'. However, when multi-level subdomains are supported for landing pages, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.

    >[!CAUTION]
    >
    >If you select a domain that was delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), you must create the DNS record on your hosting platform. To generate the DNS record, the process is the same as when you configure a new landing page subdomain.

1. Click **[!UICONTROL Submit]**.

   The subdomain is displayed in the list with the _[!UICONTROL Processing]_ status. For more on subdomains' statuses, see TBD.

    ![](assets/lp_subdomain-processing.png)

   >[!IMPORTANT]
   >
   >The subdomain is not ready for use until Adobe performs the required checks, which can take **_up to 4 hours_**.

   When the checks are successful, the subdomain is listed with the _[!UICONTROL Success]_ status and it is ready to use for creating landing page presets.
-->

### 新しいサブドメインを設定 {#lp-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_lp_subdomain_dns"
>title="一致する DNS レコードを生成"
>abstract="新しいランディングページのサブドメインを設定するには、Journey Optimizer B2B インターフェイスに表示されるアドビのネームサーバー情報をコピーし、ドメインホストソリューションに貼り付けて、一致する DNS レコードを生成する必要があります。 チェックが正常に完了すると、ランディングページプリセットの作成にサブドメインを使用する準備が整います。"

1. **[!UICONTROL ランディングページサブドメインの設定]**&#x200B;をクリックします。

1. _[!UICONTROL 設定タイプ]_&#x200B;で、**[!UICONTROL 独自のドメインを追加]**&#x200B;を選択します。

1. デリゲートするサブドメインを指定します。

   >[!IMPORTANT]
   >
   >* 既存のランディングページのサブドメインは使用できません。
   >
   >* サブドメインでは大文字は使用できません。

   <!-- ![Landing page subdomain set up](./assets/config-channels-landing-pages-subdomain-setup.png){width="500" zoomable="yes"} -->

   無効なサブドメインをアドビにデリゲートすることはできません。 組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。

   ランディングページでは、複数レベルのサブドメインがサポートされています。 例えば、`email.marketing.yourcompany.com`を使用できます。

1. 表示されたレコードをコピーするか、CSV ファイルをダウンロードしてから、ドメインホスティングソリューションに移動して、一致するDNS レコードを生成します。

   DNS サーバーに配置するレコードが表示されます。

1. DNS レコードがドメインホスティングソリューションに生成されていることを確認します。

   すべての設定が正しい場合は、確認チェックボックスを選択し、**[!UICONTROL 送信]**&#x200B;をクリックします。

   <!-- ![Landing page subdomain set up with DNS records](./assets/config-channels-landing-pages-subdomain-setup-dns.png){width="500" zoomable="yes"} -->

   新しいランディングページサブドメインを設定すると、常に CNAME レコードを指すようになります。

   サブドメインのデリゲーションが送信されると、サブドメインは&#x200B;_[!UICONTROL 処理中]_&#x200B;のステータスでリストに表示されます。

   >[!IMPORTANT]
   >
   >Adobeが必要なチェックを実行するまで、サブドメインは使用できません。これには&#x200B;**_最大4時間_**&#x200B;かかる場合があります。

   チェックが成功すると、サブドメインは&#x200B;_[!UICONTROL 成功]_ ステータスで一覧表示され、ランディングページプリセットの作成に使用できる状態になります。

   ホスティングソリューションで検証レコードを作成しなかった場合、サブドメインは&#x200B;_[!UICONTROL 失敗]_&#x200B;とマークされます。

### サブドメインのデリゲート解除 {#undelegate-subdomain}

1. [!DNL Journey Optimizer] で、サブドメインに関連付けられているすべてのランディングページを非公開にします。

1. ランディングページサブドメインがCNAME レコードを指している場合は、ホスティングソリューションからCNAME レコードを削除します（元のメールサブドメインがある場合は削除しないでください）。

   <!--
    >[!NOTE]
    >
    >A landing page subdomain can point to a CNAME record because it was either an [existing subdomain](#lp-use-existing-subdomain) delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), or a [new landing page subdomain](#lp-configure-new-subdomain) that you configured. 
    -->

1. デリゲートを解除するサブドメインについては、Adobe担当者にお問い合わせください。

Adobeがリクエストを処理すると、サブドメインのインベントリページにデリゲートされていないドメインが表示されなくなります。

<!-- 
old marketo way for Prime?

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->

## プリセット {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain_header"
>title="ランディングページプリセットの作成"
>abstract="ランディングページを構築して Journey Optimizer B2B Edition 全体で利用するには、使用するサブドメインを含むランディングページプリセットを作成する必要があります。"

マーケターがランディングページを作成する際に、ランディングページを作成して[!DNL Journey Optimizer B2B Edition]を通じて活用できるように、ランディングページプリセットを選択する必要があります。 プリセットには、ランディングページに使用するサブドメインが含まれています。

プリセットを設定する前に、_[!UICONTROL 成功]_ ステータスのランディングページサブドメインが少なくとも1つ設定されていることを確認してください。

設定されたランディングページプリセットを確認するには、**[!UICONTROL 管理]** > **[!UICONTROL チャネル]**&#x200B;に移動します。 ナビゲーションパネルの&#x200B;_[!UICONTROL ランディングページ]_&#x200B;で、**[!UICONTROL ランディングページプリセット]**&#x200B;を選択します。

<!-- ![Channel configurations - landing page presets](./assets/config-channels-landing-pages-presets.png){width="800" zoomable="yes"} -->

任意のプリセット名をクリックして、ランディングページプリセットの詳細にアクセスします。

### ランディングページプリセットの作成 {#lp-create-preset}

1. 「**[!UICONTROL ランディングページプリセットを作成]**」をクリックします。

1. プリセットの名前と説明を入力します。

   名前は文字（A～Z）で始め、英数字、アンダースコア `_`、ドット `.`、ハイフン `-` しか使用できません。

1. ランディングページサブドメインを選択します。

   <!-- ![Landing page preset with name, description, and subdomain](./assets/config-channels-landing-pages-preset-create.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >サブドメインを選択できるようにするには、1 つ以上のランディングページサブドメインが設定済みであることを確認します。

   選択したサブドメインに対応する設定が表示されます。

1. 「**[!UICONTROL ランディングページサブドメインと同じ]**」オプションをオンにすると、**[!UICONTROL トラッキング URL]** のランディングページサブドメインを選択できます。

   <!-- [Learn more about tracking](../email/message-tracking.md) -->

   <!-- ![Landing page preset with subdomain settings](./assets/config-channels-landing-pages-preset-subdomain-settings.png){width="500" zoomable="yes"} -->

   例えば、ランディングページ URLが`pages.mail.luma.com`、トラッキング URLが`data.mail.luma.com`の場合、トラッキングサブドメインとして使用する`pages.mail.luma.com`を選択できます。

   <!-- 
    >[!CAUTION]
    >
    >The selected landing page subdomain is used to specify the **[!UICONTROL Tracking URL]**and **[!UICONTROL Image Delivery URL]** if that subdomain was created using an [existing subdomain](#use-an-existing-subdomain).
    >
    >If the subdomain was created using the [Add your own domain](#configure-a-new-subdomain) option, the primary subdomain (such as the first delegated subdomain) is used instead. We don't have the existing option right now.
    -->

1. 「**[!UICONTROL 送信]**」をクリックして、ランディングページプリセットの作成を確定します。

   <!--You can also save the preset as draft and resume its configuration later on.-->

   ランディングページプリセットを作成すると、_[!UICONTROL アクティブ]_&#x200B;状態でリストに表示され、ランディングページの作成に使用できるようになりました。