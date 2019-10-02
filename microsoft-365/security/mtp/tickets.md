---
title: ServiceNow を使用してチケットを作成および追跡する
description: Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。 これにより、セキュリティ管理者は、セキュリティで保護されたスコアを ServiceNow に直接送信して、チケットを作成することができます。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350334"
---
# <a name="manage-tickets-through-servicenow"></a>ServiceNow によるチケットの管理

Microsoft 365 セキュリティセンターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。 これにより、セキュリティ管理者は、 [Microsoft のセキュリティで保護されたスコア](microsoft-secure-score.md)向上アクションを ServiceNow に直接送信して、チケットを作成することができます。 インシデント管理チケットと変更管理チケットの両方を作成できます。

## <a name="prerequisites"></a>前提条件

次のものを使用して、Microsoft 365 セキュリティセンターおよび ServiceNow インスタンスへのアクセス権を持っている必要があります。  

* キングストンまたはそれ以降のバージョン
* 管理者の HI 資格情報
* ターゲットベンダーインスタンスに対する管理者権限を持っている

ServiceNow では、ServiceNow インスタンスのボックス設定 (既定値) を保持することをお勧めします。  カスタマイズを行うと、インストールチェックリストと Microsoft 365 セキュリティセンターとの統合を完了する際にエラーが発生する可能性があります。

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

Microsoft 365 セキュリティセンターのホームページに移動します。これには、ServiceNow を使用しているかどうかを確認するカードが表示されます。

![ServiceNow を使用していますか](../images/do-you-use-servicenow-250.png)

その後、ServiceNow set up ページに送信されます。ここでは、Microsoft 365 Connector アプリを承認する手順について説明します。

Microsoft 365 セキュリティセンターと ServiceNow 間の接続を認証するときは、個人の資格情報ではなく、インストール手順で作成した統合ユーザーログインとパスワードを使用してください。

指示に従って接続を承認した後、Microsoft 365 セキュリティセンター接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの両方の接続状態を表示できます。 これで、タスクの作成を開始するための設定が完了しました。

## <a name="create-a-task-and-share-it-to-servicenow"></a>タスクを作成して ServiceNow に共有する

統合がセットアップされると、特定の Microsoft セキュリティスコア向上アクションに基づいて ServiceNow タスクを作成できます。 Microsoft 365 セキュリティセンターポータルで、[セキュリティで保護されたスコア] のすべての改善アクションに移動し、[共有] アイコンを選択します。 ドロップダウンオプションの1つは ServiceNow です。

![セキュリティで保護されたスコアでの ServiceNow 共有](../images/servicenow-share.png)

タスクが生成されます。ここで、優先度を設定して、名前、説明、または期限を編集できます。 すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信できます。

タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。

## <a name="track-tickets"></a>チケットを追跡する

ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。 これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。

![ServiceNow 変更管理チケット](../images/change-management-375.png)  ![ServiceNow インシデント管理チケット](../images/incident-management-375.png)

Microsoft 365 セキュリティセンターで ServiceNow 統合を再プロビジョニングまたは管理するには、いずれかのカードで**servicenow 構成を管理**するを選択します。 その後、現在の ServiceNow 接続を削除して、チケットの状態名をカスタマイズできます。

Microsoft 365 セキュリティセンターに ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および処理される場で有効になります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>インストールチェックリストの最初のステップでエラーが表示される (OAuth の作成)

**エラーメッセージ**: スコープ ' x_mioms_m365ticket ' から ' oauth_entity ' に対する読み取り操作が拒否されました。テーブルのスコープ間のアクセスポリシーが原因です。

アプリでは、ServiceNow インスタンスの管理者が OAuth エンティティを作成して読み取ることができると想定しています。 このエラーは、ServiceNow のインスタンスのカスタマイズによって発生する可能性があります。これにより、OAuth エンティティを作成または読み取ることができるユーザーが制限されます。 ServiceNow では、ユーザーが既定の機能を使い続けることが推奨されます。

"Application レジストリ" テーブルの構成を既定に設定します。

* Label = Application Registeries
* Name = oauth_entity
* = すべてのアプリケーションスコープからアクセス可能
* 読み取り可能 = チェックボックスが選択されている

**ServiceNow では、ユーザーが既定の機能を使い続けることが推奨されます。**

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 Security & コンプライアンスコネクタ用に作成された OAuth エンティティを検証するにはどうすればよいですか?

ServiceNow で、アプリケーションのレジストリテーブル (メニュー > System OAuth > アプリケーションレジストリ) に移動し、自分が作成した OAuth エンティティ (割り当てた名前) を見つけます。

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 Security & コンプライアンスコネクタのインストールチェックリストの手順2で作成した統合ユーザーを検証するにはどうすればよいですか?

ServiceNow で [ユーザー] テーブル (> [ユーザー管理 > ユーザー)] を選び、自分で作成した統合ユーザー (割り当てられた名前) を見つけます。

Microsoft 365 セキュリティセンターと ServiceNow 間の接続を認証するときは、個人の資格情報ではなく、インストール手順で作成した統合ユーザーログインとパスワードを使用してください。

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a>インストールを完了し、手順をセットアップしましたが、そのホームページに ServiceNow カードが表示されず、Microsoft Secure Score の [共有] アイコンが表示されません

にhttps://security.microsoft.com/ticketProvisioningアクセスして、[プロビジョニング] ページの状態を確認します。 [**保存**してホームページに戻る] を選択します。 カードが表示されます。
