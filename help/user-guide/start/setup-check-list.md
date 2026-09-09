---
title: セットアップチェックリスト
description: ユーザーアクセス設定やメール配信品質インフラストラクチャなど、Marketo Optimizer インスタンスの初期セットアップタスクを完了します。
TQID: 'https://experienceleague.adobe.com/XEPKIa88-L7mdPz1opKegY1pdEF4Qyls0nLVJBQSaJk'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 11%

---

# チェックリストを設定

プロビジョニングされた[!DNL Marketo Optimizer] インスタンスで機能を有効にするには、次のタスクを実行します。

## ユーザーアクセスを有効にする {#enable-user-access}

プロビジョニングが完了し、サンドボックスがバインドされている場合は、チームとユーザーに[!DNL Journey Optimizer B2B Edition] アクセスを設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong> 製品へのアクセスおよび権限の提供 </strong> ユーザーの場合</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Admin ConsoleでJourney Optimizer B2B edition製品プロファイルを作成する（1回限り/初期設定のみ）</td>
<td><a href="./user-management.md#create-profile">プロファイルを作成</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Admin Consoleでのユーザーグループの追加</td>
<td><a href="./user-management.md#add-user-group">ユーザーグループを追加</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Admin Consoleのユーザーグループに製品プロファイルを割り当てます</td>
<td><a href="./user-management.md#assign-profile">製品プロファイルの割り当て</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Admin Consoleのユーザーグループにユーザーを追加する</td>
<td><a href="./user-management.md#add-users">ユーザの追加</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>組み込みの役割を編集するか、製品権限でカスタム役割を作成できます</td>
<td><a href="./user-management.md#edit-role-permissions">役割の編集</a> <br/> <a href="./user-management.md#create-a-custom-role"> カスタム役割の作成</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Adobe Experience Platformのロールにユーザーまたはグループを追加する</td>
<td><a href="./user-management.md#add-users-to-a-role"> ユーザーを追加</a> <br/><a href="./user-management.md#add-user-groups-to-a-role"> グループを追加</a></td>
</tr>
</tbody>
</table>

## メールの配信品質 {#email-deliverability}

マーケターがジャーニーから電子メールを送信できるようにする前に、サブドメインのデリゲーション、電子メール認証、チャネル設定など、組織向けの送信インフラストラクチャを設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>メールの配信品質とチャネル設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Adobeへのサブドメインのデリゲート（完全デリゲートまたはCNAME）</td>
<td><a href="./email-deliverability.md#delegate-fully-delegated">完全に委任</a> <br/> <a href="./email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>サブドメインのDMARCの設定</td>
<td><a href="./email-deliverability.md#configure-dmarc">DMARCの設定</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>IP プールの確認と割り当て</td>
<td><a href="./email-deliverability.md#review-ip-pool">IP プールの確認</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>メールチャネル設定の作成</td>
<td><a href="../admin/email-channel-configuration.md#create-email-channel-configuration">メールチャネルの設定</a></td>
</tr>
</tbody>
