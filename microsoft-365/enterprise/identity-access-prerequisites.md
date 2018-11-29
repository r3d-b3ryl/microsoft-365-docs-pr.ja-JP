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
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869654"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id とデバイスのアクセス ポリシーを実装するための前提条件となる作業

この資料では、推奨される id とデバイスのアクセス ポリシーを展開する前に実装するために必要な前提条件について説明します。条件付きアクセスの技術的な前提条件と同様に、ユーザーに快適に SSO を提供することをお勧め既定のプラットフォームのクライアント構成についても説明します。


## <a name="prerequisites"></a>前提条件

推奨 id とデバイスのアクセス ポリシーを実装する前に、組織が満たす必要のあるいくつかの前提条件があります。お客様の環境に適用するための前提条件を次の表を参照してください。 


| 構成 | クラウドのみ | Active Directory パスワード ハッシュの同期と |  AD FS のフェデレーション |
| :------------- | :-----------: | :--------------: | :------------: |
|  [パスワード ハッシュの同期を構成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)します。これをリークした資格情報を検出するために有効にする必要があり、リスクのことで動作するように条件付きのアクセスをベースします。**注:** これは、パススルー認証 (PTA)、またはフェデレーション認証と同様に、管理の認証を組織で使用するかどうかに関係なく、必要です。 |    | はい | はい |
| 企業に、企業ネットワークに接続されているデバイス上のユーザーに自動的に署名するには、[シームレスなシングル サインオンを有効にする](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)をします。 |  | はい |  |
| [という名前のネットワークを構成](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。Azure AD の識別情報の保護では、収集し、リスク スコアを生成するすべての利用可能なセッション データを分析します。Azure の AD という名前のネットワークの構成で、ネットワークの組織のパブリック IP の範囲を指定することをお勧めします。企業環境の外部からのトラフィックは、リスクの高いスコアとして扱われるようにこれらの範囲からのトラフィックには、リスクの軽減のスコアが与えられます。 | はい  | はい | はい |
|[セルフ サービス パスワード リセット (SSPR) と多要素認証 (MFA) のすべてのユーザーを登録](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)します。Azure の MFA を事前にユーザーを登録することをお勧めします。Azure AD Id の保護は、Azure の MFA の追加のセキュリティ検証を実行します。さらに、記号で快適をお勧めユーザー インストールの[Microsoft ユーザー認証システムのアプリケーション](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)と、デバイス上の Microsoft の企業ポータル アプリケーション。これらは、プラットフォームごとにアプリケーションのストアからインストールすることができます。 | はい | はい | はい |
| [ドメイン参加済み Windows コンピューターの自動デバイス登録を有効にします](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件付きアクセスによって、サービスに接続するデバイスを、ドメイン参加済みデバイスまたは準拠デバイスにすることができます。 Windows コンピューターでこの方法をサポートするには、デバイスを Azure AD に登録する必要があります。  この記事では、自動デバイス登録を構成する方法について説明します。 |   | はい |  はい |
| **サポート チームを用意します**。 MFA を完了できないユーザーのための計画を立てます。 たとえば、そのようなユーザーをポリシーの除外グループに追加する、そのようなユーザーの新しい MFA 情報を登録するなどの方法があります。 こうしたセキュリティに対応する変更を行う前は、実際のユーザーから要請があることを確認する必要があります。 同意を支援するようにユーザーの上司に依頼する方法も効果的です。 | はい | はい | はい |
| [オンプレミス AD へのパスワード ライトバックを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 パスワード ライトバックを構成すると、アカウント侵害の高いリスクが検出された場合に、オンプレミスのパスワードを変更するように Azure AD からユーザーに要請することができます。 Azure AD Connect で 2 つの方法のいずれかを使用して、この機能を有効にすることができます。 Azure AD Connect のセットアップ ウィザードの [オプションの機能] 画面で、または Windows PowerShell を使用してパスワード ライトバックを有効にできます。 |   | はい | はい |
| [Azure Active Directory Id の保護を有効に](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)します。Azure AD の識別情報の保護を使用すると、組織のユーザーに影響を与えず、潜在的な脆弱性を検出し、低、中、高の記号でおよびユーザーへの自動修復のポリシーを構成できます。  | はい | はい | はい |
| [Exchange オンライン](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)と[オンライン ビジネスの Skype](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)の**最新の認証を有効にする**。現代の認証とは、多要素認証 (MFA) を使用するための前提条件です。Office 2016 クライアント、SharePoint Online では、およびビジネスのための OneDrive の最新の認証がデフォルトで有効です。 | はい | はい | はい |
|||||



## <a name="recommended-client-configurations"></a>推奨されるクライアント構成
このセクションでは、Microsoft が推奨する、ユーザーにとって SSO が最も使いやすい既定のプラットフォーム クライアント構成と条件付きアクセスの技術的前提条件について説明します。

### <a name="windows-devices"></a>Windows デバイス
Azure は、オンプレミスと Azure AD の両方で可能な限り途切れなく SSO を使えるように設計されています。そのため、Windows 10 (バージョン 1703 以降) を推奨しています。 職場や学校が支給したデバイスは直接 Azure AD に参加するように構成してください。あるいは、組織でオンプレミス AD ドメイン参加を利用している場合、[自動的かつサイレントで Azure AD に登録されるように構成](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)してください。

BYOD Windows デバイスの場合、ユーザーは "職場または学校アカウントを追加" を利用できます。 Windows 10 で Chrome ブラウザーを利用している場合、Edge/IE の場合と同じようにサインインが円滑に機能するように[拡張機能をインストールする](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)必要があります。 また、組織がドメイン参加済み Windows 7 デバイスを利用している場合、Windows 10 以外のコンピューターのための Microsoft Workplace Join [パッケージ](https://www.microsoft.com/download/details.aspx?id=53554) をインストールし、Azure AD にデバイスを登録できます。

### <a name="ios-devices"></a>iOS デバイス
MFA のポリシーまたは条件付きのアクセスを展開する前にユーザーのデバイス上の[Microsoft ユーザー認証システムのアプリケーション](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールすることをお勧めします。少なくとも、ユーザーが作業を追加することで、Azure AD でそのデバイスを登録またはアカウントを学校に求められたとき、または管理にそのデバイスを登録する Intune 会社のポータル アプリケーションをインストールするときにアプリケーションをインストールしてください。これは条件付きアクセスが構成されているポリシーとは異なります。

### <a name="android-devices"></a>Android デバイス
ユーザーには、条件付きアクセス ポリシーの展開前に、あるいは認証時に要求されたときに [Intune ポータル サイト アプリ](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
)と [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールするように推奨しています。 アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成されている条件付きアクセス ポリシーに依存します。

Android for Work または Samsung Knox をサポートする OEM とバージョンで会社所有デバイス (COD) を規格統一し、Intune MDM ポリシーによるメール アカウントの管理と保護を許可することも推奨されます。


### <a name="recommended-email-clients"></a>推奨される電子メール クライアント
次の電子メール クライアントでは、最新の認証と条件付きのアクセスをサポートします。 

|プラットフォーム|クライアント|バージョン/注|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、2013 [先進認証を有効にする](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)、[必要な更新プログラム](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|iOS 版 Outlook|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|サポートされていません||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム
ドキュメントの保護ポリシーを適用した場合は、次のクライアントが推奨されます。

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

<sup>*</sup>[OneDrive 同期クライアント](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)を使用して条件付きのアクセスを使用する方法の詳細について説明します。

### <a name="office-365-client-support"></a>Office 365 クライアント サポート
Office 365 クライアントのサポートの詳細については、以下の資料を参照してください。
- [Office 365 クライアント アプリケーションのサポート - 条件付きアクセス](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 クライアント アプリケーションのサポート - モバイル アプリケーションの管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 クライアント アプリケーションのサポート - 最新の認証](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>管理者アカウントを保護します。
Azure Active Directory には、定義済みの条件付きアクセス ポリシーを使用して管理者のアクセス権の保護を開始する簡単な方法が用意されています。Azure AD は、内で条件付きアクセスのブレードに移動し、このポリシーを検索-**のベースライン ポリシー: 管理者の MFA を必要とする**。このポリシー] をクリックし、**ポリシーをすぐに使用**を選択します。 

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
- 管理用のみには、Office 365 管理者アカウントを使用します。管理者は、管理者以外の通常の使用を考慮し、職務に関連するタスクの完了に必要な場合は、管理者アカウントのみを使用して別のユーザーが必要です。[Office 365 の管理者](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割は、Office 365 サービスにずっと多くの特権を持っています。
- この[資料](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)で説明したように Azure AD の特権を持つアカウントをセキュリティ保護するためのベスト プラクティスに従います。

## <a name="next-steps"></a>次の手順

[共通 id とデバイスのアクセス ポリシーを構成します。](identity-access-policies.md)

