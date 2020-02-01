---
title: ServiceNow を使用してチケットを作成および追跡する
description: Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。 セキュリティ管理者は、セキュリティで保護されたスコアの推奨事項を ServiceNow に直接送信し、チケットを作成できます。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 26e227b4b1e8047ca962ca9e65b139bacae55e03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599994"
---
# <a name="manage-tickets-through-servicenow"></a>ServiceNow を介してチケットを管理する

Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。 セキュリティ管理者は、 [Microsoft のセキュリティで保護されたスコア](microsoft-secure-score.md)向上アクションを ServiceNow に直接送信して、チケットを作成できます。 インシデント管理チケットと変更管理チケットの両方を作成できます。

## <a name="prerequisites"></a>前提条件

次のものを使用して、Microsoft 365 セキュリティセンターおよび ServiceNow インスタンスへのアクセス権を持っている必要があります。  

* キングストンまたはそれ以降のバージョン
* 管理者の HI 資格情報
* ターゲットベンダーインスタンスに対する管理者権限を持っている

ServiceNow では、ユーザーが ServiceNow インスタンスに既定の設定を保持することをお勧めします。 カスタマイズを行うと、インストールチェックリストと Microsoft 365 セキュリティセンターとの統合を完了する際にエラーが発生する可能性があります。

## <a name="data-exchange"></a>データ交換

Microsoft 365 セキュリティセンターを ServiceNow に接続すると、Microsoft は次の追加データを受け取ります。

* ServiceNow インスタンス名
* ServiceNow クライアント ID
* ServiceNow クライアントシークレット
* ServiceNow アクセス & 更新トークン

Microsoft 365 セキュリティセンターから ServiceNow チケットを作成すると、次のデータが ServiceNow に送信されます。

* チケット作成を開始するユーザー ID
* タスク名
* タスクの説明
* 優先度
* 期限
* 推奨ソース (ユーザーの推奨事項または Microsoft 推奨)
* 推奨カテゴリ (デバイス、データ、アプリ、Id、インフラストラクチャ)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Microsoft 365 セキュリティセンターを ServiceNow に接続する

Microsoft 365 セキュリティセンターのホームページに移動して、ServiceNow 接続カードを表示します。

![ServiceNow を使用していますか](../images/do-you-use-servicenow-250.png)

[ServiceNow に接続] を選択して、[ServiceNow セットアップ] ページに移動します。 指示に従って、Microsoft 365 Connector アプリを承認します。

> [!NOTE]
> Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。 個人の資格情報は使用しないでください。

指示に従って接続を承認した後、Microsoft 365 セキュリティセンター接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの両方の接続状態を表示します。 これで、タスクの作成を開始するための設定が完了しました。

## <a name="create-a-task-and-share-it-to-servicenow"></a>タスクを作成して ServiceNow に共有する

統合がセットアップされたら、特定の Microsoft セキュリティスコア向上アクションに基づいて ServiceNow タスクを作成します。 Microsoft 365 セキュリティセンターポータルで、[セキュリティで保護されたスコア] のすべての改善アクションに移動し、[共有] アイコンを選択します。 ドロップダウンオプションの1つは ServiceNow です。

![セキュリティで保護されたスコアでの ServiceNow 共有](../images/servicenow-share.png)

タスクが生成され、優先度を設定して、名前、説明、または期限を編集できます。 すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信します。

タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。

## <a name="track-tickets"></a>チケットを追跡する

ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。 これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。

![ServiceNow 変更管理チケット](../images/change-management-375.png)  ![ServiceNow インシデント管理チケット](../images/incident-management-375.png)

Microsoft 365 セキュリティセンターで ServiceNow 統合を再プロビジョニングまたは管理するには、いずれかのカードで**servicenow 構成を管理**するを選択します。 そこから、現在の ServiceNow 接続を削除し、チケットの状態名をカスタマイズします。

Microsoft 365 セキュリティセンターで ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および操作できる場所に存在します。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>インストールチェックリストの最初のステップでエラーが表示される (OAuth の作成)

**エラーメッセージ**: 範囲 ' x_mioms_m365ticket ' から ' oauth_entity ' に対する読み取り操作が拒否されました。テーブルのスコープ間のアクセスポリシーが原因です。

アプリでは、ServiceNow インスタンスの管理者が OAuth エンティティを作成して読み取ることができると想定しています。 このエラーは、ServiceNow のインスタンスのカスタマイズによって発生する可能性があります。これにより、OAuth エンティティを作成または読み取ることができるユーザーが制限されます。

**ServiceNow では、ユーザーが既定の機能を維持することをお勧めします。**

"Application レジストリ" テーブルの構成を既定に設定します。

* Label = Application Registeries
* Name = oauth_entity
* = すべてのアプリケーションスコープからアクセス可能
* 読み取り可能 = チェックボックスが選択されている

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 Security & コンプライアンスコネクタ用に作成された OAuth エンティティを検証する方法

ServiceNow で、アプリケーションのレジストリテーブル (**メニュー > System OAuth > アプリケーションレジストリ**) に移動し、自分で作成した OAuth エンティティを割り当てた名前で検索します。

### <a name="logging-in-as-the-integration-user"></a>統合ユーザーとしてログインする

Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。 個人の資格情報は使用しないでください。

1. ServiceNow の [認証] ページに移動します。
2. 個人の資格情報を使用してサインインしている場合は、右上隅にある [リンクし**ない**] を選択します。
3. インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にログインします。  
4. セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [**許可**] を選択します。
5. セットアップの手順を続行します。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 Security & コンプライアンスコネクタのインストールチェックリストで作成した統合ユーザーを検証する方法

ServiceNow でユーザーテーブル **(メニュー > ユーザー管理 > ユーザー**) に移動し、自分で作成した統合ユーザーを割り当てた名前で検索します。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>お客様の会社では、シングルサインオンが有効になっています。これにより、Microsoft 365 セキュリティセンターから ServiceNow に接続できなくなります。

会社でシングルサインオンが有効になっていて、エラーが発生するかログインが失敗した場合は、2つのソリューションのいずれかを実行します。

#### <a name="log-into-servicenow-as-the-integration-user"></a>ServiceNow に統合ユーザーとしてログインします。

1. ServiceNow の [認証] ページに戻ります。
2. 右上隅にある [リンクし**ない**] を選択します。
3. インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にログインします。  
4. セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [**許可**] を選択します。
5. セットアップの手順を続行します。

#### <a name="create-a-security-admin-user"></a>セキュリティ管理者ユーザーを作成する

1. Azure Active Directory のセキュリティ管理者特権を持つユーザーを作成します。 ユーザーは、インストールチェックリストから作成した統合ユーザーと同じ名前とメールアドレスを持っている必要があります。 ログインして接続が完了したら、セキュリティ管理者の役割を削除できます。
2. このユーザーとして Microsoft 365 セキュリティセンターにログインし、セットアップ手順に従います。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>インストールは完了しましたが、チケットが表示されず、共有できません

インストールとセットアップの手順が完了していても、ユーザーがホームページに ServiceNow カードを表示せず、Microsoft のセキュリティスコアから ServiceNow に共有できない場合は、のhttps://security.microsoft.com/ticketProvisioning「プロビジョニング」ページの状態を確認してください。 [**承認**] を選択して、ホームページに戻ります。 カードが表示されます。

