---
title: Id とデバイスを実装するための前提条件となる作業にアクセス ポリシーの Microsoft 365 エンタープライズ |マイクロソフトのドキュメント
description: ID およびデバイス アクセス ポリシーと構成を適用する方法に関する Microsoft の推奨事項のポリシーを説明します。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869654"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id とデバイスのアクセス ポリシーを実装するための前提条件となる作業

この資料では、推奨される id とデバイスのアクセス ポリシーを展開する前に実行する必要のある前提条件について説明します。条件付きアクセスの技術的な前提条件と同様に、ユーザーに快適に SSO を提供することをお勧め既定のプラットフォームのクライアント構成についても説明します。


## <a name="prerequisites"></a>前提条件

推奨 id とデバイスのアクセス ポリシーを実装する前に、組織が満たす必要のあるいくつかの前提条件があります。次の表では、お客様の環境に適用するための前提条件について説明します。 


| 構成 | クラウドのみ | Active Directory パスワード ハッシュの同期と |  パススルー認証 |  AD FS のフェデレーション |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [パスワード ハッシュの同期を構成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)します。これは、リークした資格情報を検出し、リスク ・ ベースの条件付きアクセスのために動作するように有効にする必要があります。**注:** これは、パススルー認証 (PTA)、またはフェデレーション認証と同様に、管理の認証を組織で使用するかどうかに関係なく必要です。 |    | はい | はい | はい |
| [シームレスなシングル サインオンを有効にする](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)が、企業に、企業ネットワークに接続されているデバイス上のユーザーに自動的に署名するにします。 |  | はい | はい |  |
| [という名前のネットワークを構成](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。Azure AD の識別情報の保護では、収集し、リスク スコアを生成するすべての利用可能なセッション データを分析します。Azure の AD という名前のネットワークの構成で、ネットワークの組織のパブリック IP の範囲を指定することをお勧めします。これらの範囲からのトラフィックが、リスクを軽減しスコアを指定し、企業環境の外部からのトラフィックの高いリスク ・ スコアが与えられます。 | はい  | はい | はい | はい |
|[セルフ サービス パスワード リセット (SSPR) と多要素認証 (MFA) のすべてのユーザーを登録](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)します。Azure の MFA を事前にユーザーを登録することをお勧めします。Azure AD Id の保護は、Azure の MFA の追加のセキュリティ検証を実行します。さらに、記号で快適をお勧めユーザー インストールの[Microsoft ユーザー認証システムのアプリケーション](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)と、デバイス上の Microsoft の企業ポータル アプリケーション。これらは、プラットフォームごとにアプリケーションのストアからインストールすることができます。 | はい | はい | はい | はい |
| [ドメインに参加している Windows コンピューターのデバイスの自動登録を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)します。条件付きのアクセスでは、アプリケーションに接続するデバイスには、ドメインに参加している、または準拠して確認します。Windows コンピューターでこれをサポートするには、Azure AD でデバイスを登録してください。 この資料では、デバイスの自動登録を構成する方法について説明します。 |   | はい |  はい |  はい |
| **サポート チームの準備**をします。MFA を実行できないユーザーのための計画があります。これは、ポリシーの除外グループに追加することがまたはそれらの新しい MFA の情報を登録します。これらのセキュリティ上重要な変更のいずれかを行うには、前に実際のユーザーが要求を行っていることを確認する必要があります。ユーザーの者が承認を必要とするは効果的な手順です。 | はい | はい | はい | はい |  
| [構成のパスワードへの書き戻し、オンプレミス AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。パスワードの書き戻しでは、ユーザーは、危険度の高いアカウントの問題が検出された場合、設置型のパスワードを変更を必要とする Azure AD を使用できます。Azure AD 接続を使用して 2 つの方法のいずれかでこの機能を有効にすることができます: Azure AD 接続、セットアップ ウィザードのオプション] 画面で**パスワードの書き戻し**を有効にするか、Windows PowerShell を使用して有効にします。 |   | はい | はい | はい |
| [Azure Active Directory Id の保護を有効に](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)します。Azure AD の識別情報の保護を使用すると、組織のユーザーに影響を与えず、潜在的な脆弱性を検出し、自動修復を低、中、高の記号でおよびユーザー ポリシーを構成できます。  | はい | はい | はい | はい |
| [Exchange オンライン](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)と[オンライン ビジネスの Skype](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)の**最新の認証を有効にする**。現代の認証とは、多要素認証 (MFA) を使用するための前提条件です。Office 2016 クライアント、SharePoint Online では、およびビジネスのための OneDrive の最新の認証がデフォルトで有効です。 | はい | はい | はい | はい |
||||||



## <a name="recommended-client-configurations"></a>推奨されるクライアント構成
このセクションでは、条件付きアクセスの技術的な前提条件と同様に、ユーザーに快適に SSO を提供することをお勧め既定のプラットフォームのクライアント構成について説明します。

### <a name="windows-devices"></a>Windows デバイス
Windows 10 (1703 またはそれ以降のバージョン) をお勧め、スムーズの SSO が発生する設置型と Azure AD の両方に使用可能な Azure が提供するように設計されたようです。作業時間や学校が発行したデバイスを使用して直接 Azure AD を結合するか、それらのデバイス[に自動的に構成されているし Azure AD に自動的に登録](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)する必要がある場合、組織は、オンプレミス AD ドメインへの参加、します。

BYOD Windows デバイスでは、ユーザーは**作業を追加したり学校のアカウント**を使用できます。メモ Windows 10 上のクロムのブラウザーのユーザー、同じサインイン スムーズ エッジと IE のユーザーとしてを取得する[拡張機能をインストール](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)するに必要があります。組織の Windows 7 のデバイスをドメインに参加している場合をインストールできます Microsoft ワークプ レースに参加[登録パッケージをダウンロードする](https://www.microsoft.com/download/details.aspx?id=53554)Windows 以外の 10 のコンピューターのデバイス Azure AD に。

### <a name="ios-devices"></a>iOS デバイス
MFA のポリシーまたは条件付きのアクセスを展開する前にユーザーのデバイス上の[Microsoft ユーザー認証システムのアプリケーション](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールすることをお勧めします。少なくとも、ユーザーの作業を追加することで、Azure AD でそのデバイスを登録するように求められますまたは学校のアカウント、または管理にそのデバイスを登録する Intune 会社のポータル アプリケーションをインストールするときに、アプリケーションをインストールしてください。これは条件付きアクセスが構成されているポリシーとは異なります。

### <a name="android-devices"></a>Android デバイス
ユーザーには、条件付きアクセス ポリシーの展開前に、あるいは認証時に要求されたときに [Intune ポータル サイト アプリ](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)と [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールするように推奨しています。 アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成されている条件付きアクセス ポリシーに依存します。

また、Oem とのメール アカウントを許可する、管理および保護する Intune MDM のポリシーによって、作業時間や Samsung 連盟ノックス ・ Android をサポートするバージョンの企業が所有するデバイス (COD) が標準化されたことをお勧めします。


### <a name="recommended-email-clients"></a>推奨される電子メール クライアント
次の電子メール クライアントでは、最新の認証と条件付きのアクセスをサポートします。 

|プラットフォーム|クライアント|バージョン/注|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、2013[最新の認証を有効にする](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)、[更新プログラムが必要](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS 版 Outlook|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|サポートされていません||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム
セキュリティで保護されたドキュメントのポリシーが適用されているときは、次のクライアントが推奨されます。

|プラットフォーム|Word、Excel または PowerPoint|OneNote|OneDrive アプリ|SharePoint アプリ|OneDrive 同期クライアント|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|サポート|サポート|N/A|N/A|プレビュー<sup>*</sup>|
|Windows 8.1|サポート|サポート|N/A|N/A|プレビュー<sup>*</sup>|
|Windows 10|サポート|サポート|N/A|N/A|プレビュー<sup>*</sup>|
|Windows Phone 10|サポートされていません|サポートされていません|サポート対象外|サポート対象外|サポート対象外|
|Android|サポート|サポートされている|サポートされている|サポート|N/A|
|iOS|サポート|サポートされている|サポートされている|サポート|N/A|
|macOS|パブリック プレビュー|パブリック プレビュー|N/A|N/A|サポートされていません|
|Linux|サポートされていません|サポートされていません|サポートされていません|サポートされていません|サポートされていません|

<sup>*</sup>[OneDrive は、クライアントを同期](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)すると条件付きのアクセスを使用する方法の詳細について説明します。

### <a name="office-365-client-support"></a>Office 365 クライアント サポート
Office 365 クライアントのサポートの詳細については、以下の資料を参照してください。
- [Office 365 クライアント アプリケーションのサポート - 条件付きアクセス](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 クライアント アプリケーションのサポート - モバイル アプリケーションの管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 クライアント アプリケーションのサポート - 最新の認証](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>管理者アカウントを保護します。
Azure AD には、構成済みの条件付きアクセス ポリシーを使用して管理者のアクセス権の保護を開始する簡単な方法が用意されています。Azure AD は、[**条件付きのアクセス**に移動し、このポリシーを検索-**のベースライン ポリシー: 管理者の MFA を必要とする**。このポリシーを選択し、**即座にポリシーを使用**します。 

このポリシーには、次の役割の MFA が必要です。
- グローバル管理者
- SharePoint 管理者
- Exchange 管理者
- 管理者の条件付きアクセス
- セキュリティ管理者

詳細については、 [Azure AD の管理者アカウント用のベースライン セキュリティ ポリシー](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)を参照してください。

追加の推奨事項を以下に示します。
- Azure AD 管理者の Id 管理を使用して、永続的な管理者アカウントの数を減らします。[PIM を使用する](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)を参照してください。 
- 機密性の高いデータへのアクセスを位置または重要な構成設定へのアクセス権を持つ管理者アカウントを管理者から侵害される可能性がありますを使用して、既存の組織を保護するために[使用して Office 365 にアクセス権限の管理](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview)をします。 
- 管理用のみには、Office 365 管理者アカウントを使用します。管理者は、管理者以外の通常の使用を考慮し、職務に関連するタスクの完了に必要な場合は、管理者アカウントのみを使用して別のユーザーが必要です。[Office 365 の管理者](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割は、Office 365 のサービスよりもずっと多くの特権を持っています。
- この[資料](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)で説明したように Azure AD の特権を持つアカウントをセキュリティ保護するためのベスト プラクティスに従います。

## <a name="next-steps"></a>次の手順

[共通 id とデバイスのアクセス ポリシーを構成します。](identity-access-policies.md)

