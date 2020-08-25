---
title: ServiceNow チケットを Microsoft 365 セキュリティセンターおよびコンプライアンスセンターに統合する
description: Microsoft 365 セキュリティセンターおよびコンプライアンスセンターから ServiceNow のチケットを作成および追跡する方法について説明します。
keywords: security, Microsoft 365, M365, コンプライアンス, コンプライアンスセンター, セキュリティセンター, ServiceNow, チケット, tasks, 雪, connection
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 12ac7d0a3d07749e16443e645f50de8fda185658
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866781"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>ServiceNow チケットを Microsoft 365 セキュリティセンターおよびコンプライアンスセンターに統合する

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow は、企業がエンタープライズ運用のためにデジタルワークフローを管理するのに役立つ、よく使用されるクラウドコンピューティングプラットフォームです。 現在、プラットフォームは IT ワークフロー、従業員ワークフロー、および顧客ワークフローを備えています。 [ServiceNow の詳細情報](https://www.servicenow.com/)

Microsoft は、お客様が ServiceNow と提携して、IT 管理者が両方のプラットフォームでチケットとタスクを簡単に管理できるようにしています。 [Microsoft 365 セキュリティセンター](overview-security-center.md) と [microsoft 365 コンプライアンスセンター](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) では、ServiceNow でチケットをネイティブに作成および追跡する機能が強化されています。

- [**セキュリティセンターで ServiceNow チケットを管理する**](tickets-security-center.md)
- **コンプライアンスセンターで ServiceNow チケットを管理する** (近日中)

## <a name="prerequisites"></a>前提条件

Microsoft 365 セキュリティセンターまたはコンプライアンスセンターと、次のものを含む ServiceNow インスタンスへのアクセス権を持っている必要があります。  

* キングストンまたはそれ以降のバージョン
* 管理者の HI 資格情報
* ターゲットベンダーインスタンスに対する管理者権限を持っている

ServiceNow では、ユーザーが ServiceNow インスタンスに既定の設定を保持することをお勧めします。 カスタマイズを行うと、インストールチェックリストと Microsoft 365 セキュリティセンターとの統合を完了する際にエラーが発生する可能性があります。

## <a name="data-exchange"></a>データ交換

Microsoft 365 セキュリティセンターまたはコンプライアンスセンターを ServiceNow に接続すると、Microsoft は次の追加データを受け取ります。

* ServiceNow インスタンス名
* ServiceNow クライアント ID
* ServiceNow クライアントシークレット
* ServiceNow アクセス & 更新トークン

Microsoft 365 セキュリティセンターまたはコンプライアンスセンターから ServiceNow チケットを作成すると、次のデータが ServiceNow に送信されます。

* チケット作成を開始するユーザー ID
* タスク名
* タスクの説明
* 優先度
* 期限
* 推奨ソース (ユーザーの推奨事項または Microsoft 推奨)
* 推奨カテゴリ (デバイス、データ、アプリ、Id、インフラストラクチャ)

## <a name="connect-to-servicenow"></a>ServiceNow への接続

[Microsoft 365 セキュリティセンターで servicenow チケットを作成および追跡](tickets-security-center.md)するには、servicenow に接続する方法を参照してください。 Microsoft 365 コンプライアンスセンターからの接続は近日に予定されています。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>インストールチェックリストの最初のステップでエラーが表示される (OAuth の作成)

**エラーメッセージ**: 範囲 ' x_mioms_m365ticket ' から ' oauth_entity ' に対する読み取り操作が拒否されました。テーブルのスコープ間のアクセスポリシーが原因です。

アプリでは、ServiceNow インスタンスの管理者が OAuth エンティティを作成して読み取ることができると想定しています。 このエラーは、OAuth エンティティを作成または読み取ることができるユーザーを制限する ServiceNow のインスタンスのカスタマイズによって発生する可能性があります。

**ServiceNow では、ユーザーが既定の機能を維持することをお勧めします。**

"Application レジストリ" テーブルの構成を既定に設定します。

* Label = Application Registeries
* Name = oauth_entity
* = すべてのアプリケーションスコープからアクセス可能
* 読み取り可能 = チェックボックスが選択されている

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 Security & コンプライアンスコネクタ用に作成された OAuth エンティティを検証する方法

ServiceNow で、[アプリケーション**レジストリ] テーブル (メニュー > System OAuth > アプリケーションレジストリ**) に移動します。 自分で作成した OAuth エンティティを、割り当てた名前で検索します。

### <a name="signing-in-as-the-integration-user"></a>統合ユーザーとしてのサインイン

Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーのサインインとパスワードを使用していることを確認してください。 個人の資格情報は使用しないでください。

1. ServiceNow の [認証] ページに移動します。
2. 個人の資格情報を使用してサインインしている場合は、右上隅にある [リンクし **ない** ] を選択します。
3. インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にサインインします。  
4. セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [ **許可** ] を選択します。
5. セットアップの手順を続行します。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 Security & コンプライアンスコネクタのインストールチェックリストで作成した統合ユーザーを検証する方法

ServiceNow でユーザーテーブル **(メニュー > ユーザー管理 > ユーザー**) に移動し、自分で作成した統合ユーザーを割り当てた名前で検索します。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>お客様の会社では、シングルサインオンが有効になっています。これにより、Microsoft 365 セキュリティセンターから ServiceNow に接続できなくなります。

会社でシングルサインオンが有効になっていて、エラーが発生するかサインインに失敗した場合は、2つのソリューションのいずれかを実行します。

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>統合ユーザーとして ServiceNow にサインインする

1. ServiceNow の [認証] ページに戻ります。
2. 右上隅にある [リンクし **ない** ] を選択します。
3. インストールチェックリストから、以前に作成した統合ユーザーとして ServiceNow にサインインします。  
4. セキュリティ + コンプライアンスコネクタが ServiceNow アカウントに接続できるかどうかを確認する、ServiceNow ページの [ **許可** ] を選択します。
5. セットアップの手順を続行します。

#### <a name="create-a-security-admin-user"></a>セキュリティ管理者ユーザーを作成する

1. Azure Active Directory のセキュリティ管理者特権を持つユーザーを作成します。 ユーザーは、インストールチェックリストから作成した統合ユーザーと同じ名前とメールアドレスを持っている必要があります。 サインインして接続が完了したら、セキュリティ管理者の役割を削除できます。
2. このユーザーとして Microsoft 365 セキュリティセンターにサインインし、セットアップ手順に従います。

### <a name="ip-filtering"></a>IP フィルタリング

IP フィルタリングを有効にしている場合は、IP アドレスを明示的に許可する必要があります。 ServiceNow で IP 範囲を許可する方法については、「 [Ip アドレスのアクセス制御](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 」を参照してください。 許可する IP アドレスの一覧については、「 [AZURE ip の範囲とサービスタグ-パブリッククラウド](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 」を参照してください。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>インストールは完了しましたが、チケットが表示されず、共有できません

インストールとセットアップの手順が完了していても、ユーザーがホームページに ServiceNow カードを表示せず、Microsoft のセキュリティスコアから ServiceNow に共有できない場合は、の「プロビジョニング」ページの状態を確認して https://security.microsoft.com/ticketProvisioning ください。 [ **承認** ] を選択して、ホームページに戻ります。 カードが表示されます。

## <a name="resources"></a>リソース

- [セキュリティセンターで ServiceNow チケットを管理する](tickets-security-center.md)