---
title: 高度なアーキテクチャ
description: 双方向同期、エンティティ待ち時間、テナントデータの分離など、Marketo OptimizerとMarketo Engageを接続するデータアーキテクチャについて説明します。
role: User, Admin
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 1%

---


# 高レベルのアーキテクチャ

[!DNL Adobe Marketo Optimizer]は[!DNL Adobe Marketo Engage]と統合して、B2B リードの全体像を把握します。 双方向の信頼できる同期により、[!DNL Marketo Engage]と[!DNL Marketo Optimizer]の整合性が維持され、両方のプラットフォームで、人物、会社、カスタムオブジェクト、アクティビティの単一の共有ビューが提供されます。 高性能でほぼリアルタイムのデータフローにより、記録を最新かつ実用的なものに保つことができ、キャンペーンやジャーニーはリードがエンゲージした瞬間に対応することができます。

## データ基盤

[!DNL Marketo Optimizer]と[!DNL Marketo Engage]は、下流の分析のフィード中に同期を維持する共通のデータ基盤を共有しています。

![Marketo OptimizerとMarketo Engageのアーキテクチャ図。2つの製品のサービス、ランタイム、データストアがMicrosoft AzureとAWSでどのように接続されているかを示します](./assets/marketo-optimizer-architecture.svg)

大まかなレベルでは：

* **[!DNL Marketo Engage]Core**&#x200B;は、リードおよびカスタムオブジェクトデータの決定的なソースであり、キャプチャ時のデータの整合性を確保します。
* **データブローカー層**&#x200B;は、[!DNL Marketo Engage]と[!DNL Marketo Optimizer]の間のデータの移動を調整し、共有データとレプリケートされたデータを実用的ですぐに使用できる環境に集約します。 このやりとり全体が、単一の共有AWS Aurora インスタンス内で実行され、大規模なB2B オーケストレーションのためのクローズドループ基盤となります。
* **アクティビティ**&#x200B;は定義されたパスに従います。最初に[!DNL Marketo Engage] データベースに書き込まれ、Apache SOLRでインデックス作成され、その後アクティビティパイプラインに公開されます。これにより、[!DNL Marketo Optimizer]は即座に認識されます。 ジャーニーランタイムは、アクティビティを処理してSnowflakeに書き込み、運用データを分析対応の状態に変換します。 そこから、アクティビティが[!DNL Adobe Experience Platform]個のデータセットと[!DNL Adobe Customer Journey Analytics]個のデータセットにレプリケートされ、レポートが強化されます。
* 異なるエンティティのタイプが異なる速度と方向で同期し、鮮度とシステムの整合性のバランスを取ります。

| [!DNL Marketo Engage] エンティティ | 方向を同期 | 遅延 |
| --- | --- | --- |
| リード | 双方向 | &lt; 1秒 |
| 会社 | 双方向 | &lt; 1秒 |
| カスタムオブジェクト | 一方向 | &lt; 5秒 |
| アクティビティ | 一方向 | &lt; 5秒 |
| プログラムメンバーシップ | 同期されていません | — |
| アセット | 同期されていません | — |

リードと企業は、重複したデータコピーを作成することなく、両方の方向ですばやく更新できます。 カスタムオブジェクトは数秒以内にレプリケートされるため、[!DNL Marketo Engage]のスキーマ更新は、アクティブなジャーニーですぐに実行できます。 プログラムメンバーシップとAssetsは、システムの速度と整合性を維持するために、意図的に同期から除外されます。

この遅延がほぼゼロの設計により、分析ダッシュボードと下流のシステムにほぼリアルタイムでデータを入力できるようになり、ライブキャンペーンの最適化と優先度の高いリードの迅速なフォローアップが可能になります。

### データの分離とテナント化

* 顧客データは、製品データ同期と分析アーキテクチャの一部として、[!DNL Marketo Engage]、[!DNL Marketo Optimizer]、[!DNL Experience Platform]の間で共有されます。
* データはテナントごとに論理的に分離され、Adobeのセキュリティ制御によって保護されます。
* データは、暗号化された安全なチャネルを通じて転送され、業界標準の暗号化とアクセス制御を利用して、Adobe managed services内に保存されます。
* データの種類によっては、セキュリティとテナントの分離を維持しながら、レポート機能と分析機能をサポートするために、[!DNL Marketo Engage]と[!DNL Marketo Optimizer]の間で情報を同期したり、[!DNL Experience Platform]にレプリケートしたりすることができます。
