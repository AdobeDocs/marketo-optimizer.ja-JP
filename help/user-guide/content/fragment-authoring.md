---
title: フラグメント作成
description: ビジュアルデザインツールで再利用可能なコンテンツフラグメントを作成します。Marketo Optimizerでは、電子メールやテンプレートの構造、アセット、パーソナライゼーション、条件付きコンテンツ、リンクされたURL トラッキングを追加できます。
TQID: 'https://experienceleague.adobe.com/KbnYkUMVfjBv5ST55WwAqYiMDkynwSw4BKIP0bsE-DI'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 3%

---

# フラグメントオーサリング

[&#x200B; フラグメントを作成した後](./fragments.md#create-fragments)、ビジュアルデザインスペースを使用して、フラグメント内の構造とコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## アセットの追加 {#add-assets}

ビジュアルデザイン領域で、左側のナビゲーションバーの&#x200B;_Assets_ （![Assetsアイコン &#x200B;](../assets/do-not-localize/icon-assets-me.svg)）アイコンを選択し、[!DNL Marketo Optimizer] アセットライブラリから画像アセットを参照して選択します。

画像アセットを選択、置換、またはアップロードする手順については、[&#x200B; コンテンツのオーサリングにアセットを使用](./digital-asset-management.md#assets-authoring)を参照してください。

## レイヤー、設定、スタイルの移動 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## コンテンツのパーソナライズ {#personalize-content}

[!DNL Marketo Optimizer]は、パーソナライゼーションにHandlebars構文を使用しています。 トークンは、送信時に各受信者のプロファイルデータの値に置き換えられます。

_パーソナライゼーションを追加するには&#x200B;:_

1. テキストコンポーネントを選択し、ツールバーの「_パーソナライゼーションを追加_」（![&#x200B; パーソナライズのアイコン &#x200B;](../assets/do-not-localize/icon-personalize.svg)）アイコンをクリックします。
1. パーソナライゼーションダイアログで、左側のスキーマツリーを参照し、プロファイル属性を選択します。 エディターは、対応するHandlebars式（例：`{{profile.firstName}}`）を挿入します。
1. 必要に応じて、欠落しているデータを処理するフォールバック値（例：`{{profile.firstName | default: "there"}}`）を追加します。
1. **[!UICONTROL 確認]**&#x200B;または&#x200B;**[!UICONTROL 挿入]**&#x200B;をクリックします。 式がフィールド内にインラインで表示されます。

式エディターツールと構文について詳しくは、[Personalization エディター](./personalization-expressions.md)を参照してください。

## リンクされたURL トラッキングを編集 {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
