---
title: 構造コンポーネント
description: メール、ランディングページ、フラグメントのレイアウトに構造コンポーネントを使用します。 Marketo Optimizerで列をドラッグし、スタイルを設定して、モバイル表示を設定します。
feature: Content Design Tools
role: User
TQID: 'https://experienceleague.adobe.com/eOGHy4YuwsQwVGCTF18v-os4TZAJhdAvoWoGBA7t3v4'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1645
ht-degree: 6%

---

# 構造コンポーネント {#structure-components}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_structure_components_email"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは、メールの構造をデザインするために使用できるレイアウト要素です。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_structure_components_landing_page"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは、ページの構造のデザイン作成に使用できるレイアウト要素です。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_structure_components_fragment"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは、フラグメントの構造のデザイン作成に使用できるレイアウト要素です。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_structure_components_template"
>title="構造コンポーネントについて"
>abstract="構造コンポーネントは、テンプレートの構造のデザイン作成に使用できるレイアウト要素です。"

ビジュアルデザイン空間で&#x200B;_構造コンポーネント_&#x200B;を使用して、コンテンツの構造を定義します。 シンプルなドラッグ&amp;ドロップ操作で構造要素を追加、移動することで、コンテンツレイアウトの形状をすばやく定義できます。 それぞれの構造コンポーネントは水平方向のスペースにまたがり、それらを積み重ねて垂直方向にレイアウトを構築できます。<!-- Divide each component into columns to form each content block that you need, then add [content components](./content-components.md) inside them to populate the layout. -->

## 構造ライブラリ {#structure-library}

_[!UICONTROL コンポーネント]_ ライブラリの上部にある&#x200B;**[!UICONTROL 構造]** セクションには、使用可能な構造コンポーネントが表示されます。

| アイコン | コンポーネント | 説明 |
| ----- | ----------- | ----------- |
| ![1:1列アイコン ](../assets/do-not-localize/icon-design-structure-1-1.png) | [!UICONTROL 1:1列] | スペースの幅を埋める1列のコンテナ。 |
| ![1:2列アイコン ](../assets/do-not-localize/icon-design-structure-1-2.png) | [!UICONTROL 1:2列左] | 1:2の比率を使用してスペースの幅を埋める2列のコンテナ。 最初の（左）列は幅の3分の1を占め、2番目の（右）列は残りの3分の2を占めます。 |
| ![1:3列アイコン ](../assets/do-not-localize/icon-design-structure-1-3.png) | [!UICONTROL 1:3列左] | 1:3の比率を使用してスペースの幅を埋める2列のコンテナ。 第1の（左）列は幅の4分の1を占め、第2の（右）列は残りの3分の4を占める。 |
| ![2:1列アイコン ](../assets/do-not-localize/icon-design-structure-2-1.png) | [!UICONTROL 2:1列右] | 2:1の比率を使用してスペースの幅を埋める2列のコンテナ。 最初の（左）列は幅の3分の2を占め、2番目の（右）列は残りの3分の1を占めます。 |
| ![2:2列アイコン ](../assets/do-not-localize/icon-design-structure-2-2.png) | [!UICONTROL 2:2列] | 2:2の比率を使用してスペースの幅を埋める2列のコンテナ。 左右の列の幅は同じです。 |
| ![3:1列アイコン ](../assets/do-not-localize/icon-design-structure-3-1.png) | [!UICONTROL 3:1列右] | 3:1の比率を使用してスペースの幅を埋める2列のコンテナ。 最初の（左）列は幅の4分の3 （75%）を占め、2番目の（右）列は残りの4分の1 （25%）を占めます。 |
| ![3:3列アイコン ](../assets/do-not-localize/icon-design-structure-3-3.png) | [!UICONTROL 3:3列] | 3:3の比率を使用してスペースの幅を埋める3列コンテナ。 3つの列はすべて幅が同じです。 |
| ![4:4列アイコン ](../assets/do-not-localize/icon-design-structure-4-4.png) | [!UICONTROL 4:4列] | スペースの幅を埋めるために4:4の比率を使用する4列のコンテナ。 4つの列はすべて幅が同じです。 |
| ![n:n列アイコン ](../assets/do-not-localize/icon-design-structure-n-n.png) | [!UICONTROL n:n列] | 定義した列に従ってスペースを埋める、カスタマイズ可能な列構造。 列数（2から10の間）を設定し、各列の幅を個別に設定します。 [詳細情報](#change-nn-columns) |

## 構造コンポーネントを追加 {#add-structure-components}

メール、ランディングページ、フラグメントのコンテンツをデザインする際には、それぞれの構造コンポーネントを追加してレイアウトを作成します。 左側の&#x200B;**[!UICONTROL 構造]** セクションから項目をドラッグし、キャンバスにドロップします。 ツールバーを使用して列を選択し、右側のパネルの「_設定_」タブと「_スタイル_」タブを使用して、選択したコンポーネントまたは列のパラメーターを定義できます。

![構造をキャンバスにドラッグします](assets/content-design-add-structure.png){width="800" zoomable="yes"}

### コンポーネントツールバー {#component-toolbar}

ツールバーは、カンバスで選択したときにカンバスに表示されます。 使用可能なツールを使用すると、列を選択してコンポーネント関数を適用する簡単な方法を提供できます。

![構造コンポーネントツールバー](../assets/do-not-localize/toolbar-structure.png){width="150"}

| ツール | 名前 | 使用方法 |
| ---- | ---- | ----- |
| ![条件付きコンテンツを有効にする](../assets/do-not-localize/toolbar-button-enable-conditional-content.png){width="40"} | 条件付きコンテンツの有効化 | （メールとフラグメント） コンポーネントの条件付きバリアントを有効にします。 |
| ![列を選択](../assets/do-not-localize/toolbar-button-column-select.png){width="100"} | 列を選択 | 番号で列を選択します。 列を選択すると、列の設定とスタイルを適用できます。 |
| ![複製](../assets/do-not-localize/toolbar-button-duplicate.png){width="40"} | 複製 | コンポーネントのコピーを作成し、以下に直接追加します。 |
| ![削除](../assets/do-not-localize/toolbar-button-delete.png){width="40"} | 削除 | コンポーネントを削除します。 |

### コンポーネント設定 {#component-settings}

コンポーネントを追加すると、ビジュアルデザインスペースでコンポーネントが選択され、右側のパネルにそのプロパティが表示されます。 デフォルトでは、_[!UICONTROL 設定]_ タブが表示されます。 また、いつでも構造コンポーネントを選択して、設定を変更することもできます。

#### 表示オプション

デスクトップまたはモバイルデバイスの表示からコンポーネントを除外する場合は、**[!UICONTROL 表示オプション]**&#x200B;設定を変更します。 デフォルトの&#x200B;_[!UICONTROL すべてのデバイスに表示]_&#x200B;では、すべてのデバイスで表示が有効になります。

![構造コンポーネント ](assets/content-components-display-options.png){width="400" zoomable="yes"}の表示オプション

別の設定を選択して、デバイスタイプ別にコンポーネントを排他的にします。

* _[!UICONTROL デスクトップデバイスでのみ表示]_ - コンポーネントをデスクトップデバイスに表示し、モバイルデバイスに対して除外する場合は、この設定を選択します。
* _[!UICONTROL モバイルデバイスでのみ表示]_ – この設定は、スマートフォンやタブレットなどのモバイルデバイスにコンポーネントを表示し、デスクトップデバイスに対しては除外する場合に選択します。

#### ヘッダーとフッター

構造コンポーネントは、メールメッセージまたはランディングページのHTML ヘッダーまたはフッターとして指定できます。 キャンバスで構造コンポーネントを選択した状態で、**[!UICONTROL ヘッダー]**&#x200B;または&#x200B;**[!UICONTROL フッター]** オプションをクリックします。 ヘッダーまたはフッターは1つだけ指定でき、別のコンポーネントが割り当てられている場合、このオプションは使用できません。

![構造コンポーネントがヘッダーとして設定されました](assets/structure-component-settings-header.png){width="600" zoomable="yes"}

ヘッダーまたはフッターの指定を削除するには、コンポーネントを選択し、オプションをクリックして削除します。

### 積み重ね列 {#stacked-columns}

小さい画面または表示ウィンドウの場合、デフォルト設定を変更しない限り、構造コンポーネントの列は積み重ねとして表示されます。 複数列構造コンポーネントを選択した状態で、切り替えスライダーを右に移動して、**[!UICONTROL モバイルで列をスタックしない]**&#x200B;設定を変更します。

![ モバイルで列をスタックしない](assets/structure-component-settings-stack-columns.png){width="250"}

## コンポーネントスタイル {#component-styles}

コンポーネントを追加すると、ビジュアルデザインスペースでコンポーネントが選択され、右側のパネルにそのプロパティが表示されます。 また、いつでもコンポーネントを選択して、設定やスタイルを変更することもできます。

### 背景 {#background}

右側のパネルで「_[!UICONTROL スタイル]_」タブを選択した状態で、**[!UICONTROL 背景]** セクションを使用して、構造コンポーネントの背景として使用するカラーとオプションの画像を定義します。

#### [!UICONTROL 背景色]

チェックボックスを選択し、カラーの正方形をクリックして、ピッカーからカラーを選択します。 RGB、HSL、HSB、または16進数値を入力すると、カラーを選択できます。 または、カラースライダーとカラーフィールドを使用してカラーを選択します。

![背景カラーピッカー](assets/content-components-styles-background-color.png){width="300"}

#### [!UICONTROL 背景画像] {#background-image}

切り替えセレクターを移動して、背景画像の設定を有効にします。

![ アセットセレクターを使用した構造コンポーネントの背景画像設定](assets/structure-components-background-image-settings.png){width="250"}

「**[!UICONTROL アセットを選択]**」をクリックしてアセットセレクターを開き、[Assets ライブラリ ](./digital-asset-management.md#assets-authoring)から画像を選択できます。

**[!UICONTROL 画像の配置]** オプションを使用して、画像が構造コンポーネントをどのように塗りつぶすかを選択します。 プレースメント設定は、標準の[HTML背景画像塗りつぶしと整列属性](https://www.w3schools.com/html/html_images_background.asp){target="_blank"}に従います。

![構造コンポーネントの背景画像プレースメントのプレビュー](assets/structure-component-styles-background-image.png){width="250"}

### その他のスタイル {#other-styles}

その他の構造コンポーネントスタイルを適用して、メールメッセージまたはランディングページでの表示を調整できます。 これらの組み込みオプション以外のスタイル設定については、[ コンテンツのカスタム CSSの追加](./design-custom-css.md)を参照してください。

+++境界

{{styles-border}}

+++

+++マージン

{{styles-margin}}

+++

+++アドバンス

{{styles-advanced}}

+++

## 列 {#columns}

コンポーネントツールバーの「_列を選択_」ツールを使用して、列を選択します。 次に、列ツールバーを使用して、列の選択を変更したり、列を削除したり、列に条件付きコンテンツのバリエーションを適用したりできます。 列のパラメーターは、右側の&#x200B;_[!UICONTROL 設定]_ タブと&#x200B;_[!UICONTROL スタイル]_ タブに表示されます。

![列ツールバー](../assets/do-not-localize/toolbar-column.png){width="500"}

| ツール | 名前 | 使用方法 |
| ---- | ---- | ----- |
| — | 列をクリア | 列のコンテンツをクリアします。 列ツールバー図の最初のツールを参照してください。 |
| ![条件付きコンテンツを有効にする](../assets/do-not-localize/toolbar-button-enable-conditional-content.png){width="40"} | 条件付きコンテンツの有効化 | （メールとフラグメント）列の条件付きバリアントを有効にします。 |
| ![列を選択](../assets/do-not-localize/toolbar-button-column-select.png){width="100"} | 列を選択 | 番号で列を選択します。 列を選択すると、設定とスタイルを適用できます。 |

### n:n列を変更 {#change-nn-columns}

列の幅は、ほとんどの構造コンポーネントで静的です。 _[!UICONTROL n:n列]_ コンポーネントを追加すると、列数と列サイズを変更できます。 n:n列コンポーネントは、幅が同じ5列（20%）で始まります。

>[!NOTE]
>
>各列のサイズは、構造コンポーネントの全幅の10%未満にすることはできません。 削除できるのは空の列のみです。

カンバスでコンポーネントを選択した状態で、右側のパネルの「**[!UICONTROL 列数]**」オプションを使用して、列数を変更します。 上下の矢印アイコンをクリックして、列数を増減するか、フィールドに数値を入力します。

![列数設定](assets/structure-components-n-n-columns-number.png){width="650" zoomable="yes"}

カンバスで、列サイズ アイコンを移動して、選択した列の幅を調整します。 幅を増減すると、隣接する列も調整され、すべての列がコンポーネント幅の100%を占めるようになります。

![列のサイズ変更](assets/structure-components-n-n-columns-resize.png){width="500" zoomable="yes"}

### 列スタイル {#column-styles}

カンバスで列を選択した状態で、その列に適用するスタイルを設定できます。

+++背景

* **[!UICONTROL 背景色]** - チェックボックスを選択し、色の正方形をクリックして、ピッカーから色を選択します。 RGB、HSL、HSB、または16進数値を入力すると、カラーを選択できます。 または、カラースライダーとカラーフィールドを使用してカラーを選択することもできます。

  ![背景カラーピッカー](assets/content-components-styles-background-color.png){width="300"}

* **[!UICONTROL 背景画像]** - トグルセレクターを移動して、背景画像設定を有効にします。

  ![ スタイルパネルの列の背景画像の設定](assets/structure-components-background-image-settings.png){width="250"}

  アセットソースタイプを選択し、[画像ファイルを選択](#background-image)。

+++

+++境界

{{styles-border}}

+++

+++配置

{{styles-alignment-v}}

+++

+++マージン

{{styles-margin}}

+++

+++アドバンス

{{styles-advanced}}

+++

## ナビゲーションツリー {#navigation-tree}

ビジュアルデザイン空間では、ナビゲーションツリーを使用して、列やコンテンツなどの構造コンポーネントにアクセスできます。 左側の&#x200B;_[!UICONTROL ナビゲーションツリー]_ アイコン（![ ナビゲーションツリーアイコン ](../assets/do-not-localize/icon-navigation-tree.svg)）をクリックすると、ツリーが表示されます。

![ コンテンツレイヤーにアクセス ](assets/content-design-layers.png){width="800" zoomable="yes"}

_[!UICONTROL Body]_&#x200B;要素は、ツリー構造のルートです。 ツリー内のコンポーネントまたは列の子要素のいずれかをクリックして、キャンバス上で選択します。 右側の&#x200B;_[!UICONTROL 設定]_ タブと&#x200B;_[!UICONTROL スタイル]_ タブには、そのコンポーネントまたは列のパラメーターが表示されます。

![ ビジュアルデザインスペースに表示される列コンポーネント ](assets/content-design-layers-column-select.png){width="800" zoomable="yes"}
