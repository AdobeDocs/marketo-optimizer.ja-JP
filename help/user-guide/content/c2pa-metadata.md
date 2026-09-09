---
title: C2PA メタデータ
description: Adobe Marketo Optimizerが、生成AIで生成された画像にC2PA メタデータを自動的に適用する方法と、これがコンテンツにもたらす意味をご紹介します。
feature: Assets, Content
role: User
TQID: 'https://experienceleague.adobe.com/DI9vJhE4EsGI4g4X5wz5-kqTjHOZqs6cvqo6Fke-4HU'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 586
ht-degree: 0%

---

# C2PA メタデータ

マーケティング部門は、コンテンツの透明性、AIによる情報開示、アセットの改ざん防止にこれまで以上に懸念しています。 AdobeのContent Authenticity Initiative（CAI）は、[Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) （C2PA）技術標準に準拠したツールを構築しています。 _C2PA メタデータ_&#x200B;は暗号化され、改ざんされやすい情報で、視聴者がコンテンツの系統を理解し、ブランドアセットの整合性を確保するのに役立ちます。 こうした情報には、次のものが含まれます。

* 発行者または署名者 – アセットを認証または署名するためにデジタル署名を発行したエンティティまたは会社に関する情報。
* 発行日 – C2PA メタデータがアセットに適用された日付。
* クレジットと利用状況：名前、ソーシャルメディアのハンドル、その他のID関連情報など、アセットの制作者に関する情報。
* プロセス – アセットに対して行われた編集または変更の記録。
* デバイスの詳細 – アセットの作成または編集に使用したアプリまたはデバイスに関する情報。
* 使用されているAI ツール：アセットの作成に生成AIを使用した場合、使用されているモデルの名前を含めることができます。
* その他の関連情報 – アセットの履歴に関するより多くのコンテキストを提供するのに役立つ追加データも含まれています。

アセット履歴の詳細については、Adobe Content Authenticity [ インスペクションツール ](https://contentauthenticity.adobe.com/inspect)を使用してください。

C2PA メタデータは画像ファイルに保持されます。 生成AIで生成または編集された画像が[!DNL Adobe Marketo Optimizer]にアップロードされるか、またはから書き出されると、そのC2PA メタデータが保持されます。

Adobe CX Enterprise アプリケーション全体でC2PA メタデータを自動的に添付する方法について詳しくは、CX Enterprise ガイドのAI ガイドの&#x200B;[_生成AI コンテンツの透明性_](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}を参照してください。

>[!NOTE]
>
>PDFや埋め込み（base64）ソースから画像を抽出するなど、画像をコンテンツに読み込む方法によっては、元のC2PA メタデータが保持されない場合があります。 このような場合、C2PA メタデータはソースから読み取ることができず、結果に対して作成されません。

>[!BEGINSHADEBOX]

## チャネルを通じたC2PA メタデータの永続性 {#channels}

メールまたはWhatsApp メッセージに画像を含めると、配信された画像のC2PA メタデータも保持されます。

* **電子メール** - _電子メールを送信_ ジャーニーアクションを使用する場合、_Assets_ ライブラリから電子メールコンテンツに画像を追加します。 電子メールが配信されると、受信者はメッセージから画像をダウンロードでき、C2PA メタデータはそのまま維持されます。
* **WhatsApp** - Meta Business アカウントのWhatsApp メッセージテンプレートに画像を追加します。 システムから直接追加することも、_Assets_ ライブラリから画像ファイルをダウンロードすることもできます。 _WhatsAppを送信_ ジャーニーアクションにテンプレートを使用します。 WhatsApp メッセージが配信されると、受信者はメッセージから画像をダウンロードでき、C2PA メタデータはそのまま維持されます。

>[!ENDSHADEBOX]

## 画像生成 {#generate}

>[!INFO]
>
>生成AIの透明性に関する新たな法律が制定されつつあり、Adobeでは、さまざまな地域で適用される要件を満たすために取り組んでいます。 C2PA メタデータは、Adobeがこれらの法律の要件を満たすために使用する来歴ツールです。

生成AIを使用して[!DNL Marketo Optimizer]で電子メールコンテンツの画像を作成する場合、生成された画像にC2PA メタデータが自動的に添付され、ユーザー側での操作は必要ありません。 生成AI ツールは、元のソースを含む既存のメタデータを持つ画像のバリエーションに対して、C2PA メタデータ要素を組み合わせて生成します。

>[!NOTE]
>
>[!DNL Marketo Optimizer]は現在、手動画像編集アクションをサポートしていません。 これらのアクションのC2PA メタデータワークフローは、現時点では適用できません。
