---
title: テナント間コラボレーションのMicrosoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Microsoft 365コラボレーションがテナントや組織間でどのように機能し、さまざまな組織が安全に連携できるかについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 517e015a463a501ad7b9a295a80531595c650454
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100481"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>テナント間コラボレーションのMicrosoft 365

Fabrikam と Contoso の 2 つの組織にビジネス テナント用のMicrosoft 365があり、複数のプロジェクトで連携したいとします。一部は限られた期間実行され、そのうちの一部は進行中です。 Fabrikam と Contoso を使用すると、さまざまなMicrosoft 365 テナント間で安全な方法で、ユーザーとチームがより効果的に共同作業を行うことができますか? Microsoft 365は、Azure Active Directory (Azure AD) B2B コラボレーションと組み合わせて、いくつかのオプションを提供します。 この記事では、Fabrikam と Contoso が検討できるいくつかの重要なシナリオについて説明します。

テナント間コラボレーション オプションMicrosoft 365、ファイルと会話の一元的な場所の使用、予定表の共有、IM の使用、通信のための音声/ビデオ通話、リソースとアプリケーションへのアクセスのセキュリティ保護などがあります。 次の表を使用して、解決策を選択し、詳細をご確認ください。

## <a name="exchange-online-collaboration-options"></a>Exchange Online のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|別のMicrosoft 365組織と予定表を共有する |管理者は、企業が他の企業と共同作業したり、ユーザーがスケジュール (空き時間情報) を他のユーザーと共有したりできるように、Exchange Onlineのさまざまなレベルの予定表アクセスを設定できます。 | <ul><li>[共有](/exchange/sharing/sharing) </li><li> [組織の関係](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [組織の関係の作成](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [組織の関係の変更](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [組織の関係の削除](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [予定表を外部ユーザーと共有する](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|ユーザーが組織外のユーザーと予定表を共有する方法を制御する | 管理者は、共有ポリシーをユーザーのメールボックスに適用して、共有できるユーザーと付与するアクセス レベルを制御します。 |  <ul><li> [共有ポリシー](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [共有ポリシーの作成](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [メールボックスに共有ポリシーを適用する](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [共有ポリシーの変更、無効化、削除](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|セキュリティ保護されたメール チャネルを構成し、パートナー組織とのメール フローを制御する | 管理者は、パートナー組織またはサービス プロバイダーとのメール交換にセキュリティを適用するコネクタを作成します。 コネクタは、トランスポート層セキュリティ (TLS) による暗号化を適用するだけでなく、パートナーがメールを送信する際のドメイン名または IP アドレス範囲に対する制限を許可します。 |  <ul><li> [メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [コネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [リモート ドメイン](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [メール フローのベスト プラクティス (概要)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Online と OneDrive for Business のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|外部ユーザーとサイトおよびドキュメントを共有する | 管理者は、認証された Microsoft アカウント、認証された職場または学校のアカウント、ゲスト アカウントのいずれかに対して、テナント レベルまたはサイト コレクション レベルでの共有を構成します。 |  <ul><li> [SharePoint Online 環境の外部共有を管理する](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](/sharepoint/restricted-domains-sharing) </li><li> [SharePoint Online を企業間 (B2B) エクストラネット ソリューションとして使用する](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|エンド ユーザーの外部共有を把握して制御する | OneDrive for Business ファイルの所有者および SharePoint Online エンド ユーザーは、サイト共有とドキュメント共有を構成し、共有を把握するための通知を確立します。 |  <ul><li> [OneDrive for Business の外部共有に対する通知をオンにする](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [SharePoint のファイルまたはフォルダを共有する](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>Skype for Business のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Skype for Business Online - 他の Skype for Business ユーザーとの IM、通話、プレゼンス | 管理者は、Skype for Business Online ユーザーの IM の有効化、オーディオ/ビデオ通話の実行、別のMicrosoft 365 テナント内のユーザーとのプレゼンスの確認を行うことができます。 | [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|Skype for Business Online - Skype (コンシューマー) ユーザーとの IM、通話、プレゼンス | 管理者は、Skype for Business Online ユーザーが Skype (コンシューマー) ユーザーとの IM、オーディオ/ビデオ通話、プレゼンスの表示を行えるようにすることができます。 | [Skype for Business ユーザーが Skype の連絡先を追加できるようにする](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Azure AD B2B コラボレーション - 組織のディレクトリ内のグループに外部ユーザーを追加することによるコンテンツ共有 | **Azure AD DC 管理者**、**セキュリティ管理者**、**ユーザー管理者**、**クラウド アプリケーション管理者**、または 1 つのMicrosoft 365 テナントの **グローバル管理者** は、別のMicrosoft 365 テナントのユーザーを招待してディレクトリに参加させたり、それらの外部ユーザーをグループに追加したり、コンテンツへのアクセスを許可SharePoint グループのサイトとライブラリ。 |  <ul><li> [Azure AD B2B コラボレーション プレビューとは何か?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: 新しい更新で企業間のコラボレーションが簡単に](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [外部共有と B2B コラボレーションのAzure Active Directory](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory の B2B コラボレーションの API とカスタマイズ](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD と ID の表示： Azure AD B2B コラボレーション (企業間)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Microsoft 365コラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Microsoft 365 グループ - メール、予定表、OneNote、共有ファイルを一元的に保存する | グループは、Business Essentials プラン、Business Premium プラン、Education プラン、Enterprise E1、E3、E5 プランでサポートされています。 1 つのMicrosoft 365 テナントのユーザーは、グループを作成し、別のMicrosoft 365 テナントのユーザーをゲスト ユーザーとして招待できます。 Dynamics CRM にも適用されます。 |  <ul><li> [Microsoft 365 グループについて](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [ゲストを Microsoft 365 グループに追加する](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Microsoft 365 グループのデプロイ](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Yammer のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Yammer - エンタープライズ ソーシャル メディアを通じたコラボレーション | Yammer 管理者によって外部グループを作成する機能が無効にされていない限り、ユーザーは Yammer での会話によるコラボレーションを行うための外部グループを作成し、記事のいいね! 評価とフォロー、ファイルの共有、チャットをオンラインで行うことができます。 | [Yammer の外部グループを作成して管理する](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Teams のコラボレーション オプション

|共有の目的|管理操作|使い方に関する情報|
|:-----|:-----|:-----|
|組織外のユーザーと Teams でコラボレーションを行う | 招待するMicrosoft 365 テナントの **ユーザー管理者** または **グローバル管理者** は、Teamsで外部コラボレーションを有効にする必要があります。 グローバル管理者とチームの所有者は、Teams でコラボレーションを行うために、メール アドレスを持つすべてのユーザーを招待できるようになります。  <br/> 管理者は、既にテナント内にいるゲストを管理して編集することもできます。 |  <ul><li> [ゲスト アクセスを認証する](/microsoftteams/teams-dependencies) </li><li> [Teams でゲスト アクセスをオンまたはオフにする](/microsoftteams/set-up-guests) </li><li> [PowerShell を使用してゲスト アクセスを制御する](/microsoftteams/guest-access-powershell) </li><li> [ゲスト アクセスのチェックリスト](/microsoftteams/guest-access-checklist) </li><li> [ゲスト ユーザーを表示する](/microsoftteams/view-guests) </li><li> [ゲスト ユーザー情報を編集する](/microsoftteams/edit-guests-information) </li></ul> |
|チームの所有者は、ゲストを招待し、ゲストがチーム内でコラボレーションを行う方法を管理することができる。  |チームの所有者は、自分のチーム内でゲストが実行できる操作をさらに制御することができます。 |  <ul><li> [ゲストを追加する](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [チームにゲストを追加する](/microsoftteams/add-guests) </li><li> [Teams でのゲスト アクセスを管理する](/microsoftteams/manage-guests) </li><li> [チームまたはチャネルにいるユーザーを確認する](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|他のテナントからのゲストは、Teams 内のコンテンツを表示し、他のメンバーとコラボレーションすることができる | なし。 | [ゲストのエクスペリエンスについて](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Power BI のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Power BI を使用すれば、外部ゲスト ユーザーはリンクを介して共有されたコンテンツを使用できます。 これにより、組織内のユーザーは、セキュリティで保護された方法で組織全体にコンテンツを配布できます。<br/> | Power BI 管理者は、ユーザーが組織内のコンテンツを表示するために外部ユーザーを招待できるかどうかを制御できます。| [Azure AD B2B で外部ゲスト ユーザーに Power BI コンテンツを配布する](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>テナント間コラボレーションのMicrosoft 365に関する注意事項

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>ユーザー アカウント、ライセンス、サブスクリプション、および記憶域の共有

各組織は、独自のユーザー アカウント、ID、セキュリティ グループ、サブスクリプション、ライセンス、および記憶域を保持しています。 ユーザーは、Microsoft 365のコラボレーション機能を共有ポリシーとセキュリティ設定と共に使用して、会社の資産の制御を維持しながら、必要な情報へのアクセスを提供します。

- **ユーザー アカウント:** オンプレミスの Active Directory Domain Services 内のテナントまたはパーティション間でアカウントを共有または複製することはできません。

- **ライセンス &amp; サブスクリプション:** Microsoft 365では、ライセンス プラン (SKU またはMicrosoft 365 プランとも呼ばれます) からのライセンスにより、ユーザーはそれらのプランに対して定義されているMicrosoft 365 サービスにアクセスできます。

- **Storage:** Microsoft 365 ライセンス プランでは、SharePoint Online のソフトウェアの境界と制限は、メールボックスストレージの制限とは別に管理されます。 メールボックスの保存制限は、Exchange Online を使用して設定および管理されます。 どちらのシナリオでも、テナント間でストレージを共有することはできません。

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Microsoft 365 テナント間でドメイン名前空間を共有できますか?

その必要はありません。 fabrikam.com や tailspintoys.com などの組織のドメイン名は、1 つのMicrosoft 365 テナントにのみ関連付けて使用できます。 各テナントには、独自の名前空間が必要です。 UPN、SMTP、および SIP 名前空間をテナント間で共有することはできません。

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>ハイブリッド コンポーネントとテナント間コラボレーションMicrosoft 365はどうでしょうか?

Exchange 組織や Azure AD Connect などのオンプレミスのハイブリッド コンポーネントは、複数のテナント間で分割することはできません。
