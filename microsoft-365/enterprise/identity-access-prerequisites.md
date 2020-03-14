---
title: Id およびデバイスアクセスポリシーを実装するための前提条件-Microsoft 365 Enterprise |Microsoft Docs
description: ID およびデバイス アクセス ポリシーと構成を適用する方法に関する Microsoft の推奨事項のポリシーを説明します。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: c1af88f489072490777cc6f2c7edfc66fd038bdf
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633605"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id およびデバイスアクセスポリシーを実装するための前提条件

この記事では、推奨される id とデバイスのアクセスポリシーを展開する前に実装する必要がある前提条件について説明します。 この記事では、ユーザーに最適な SSO を提供するために推奨される既定のプラットフォームクライアント構成、および条件付きアクセスの技術的な前提条件についても説明します。


## <a name="prerequisites"></a>前提条件

推奨される id とデバイスのアクセスポリシーを実装する前に、組織が満たす必要があるいくつかの前提条件があります。 次の表では、ご使用の環境に適用される前提条件について説明します。 


| 構成 | クラウドのみ | Active Directory のパスワードハッシュ同期 |  パススルー認証 |  AD FS とのフェデレーション |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [パスワードハッシュの同期を構成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)します。これを有効にして、リークした資格情報を検出し、リスクベースの条件付きアクセスに対して動作するようにする必要があります。 **注:** これは、パススルー認証 (PTA)、フェデレーション認証など、組織で管理された認証を使用するかどうかに関係なく必要になります。 |    | はい | はい | はい |
| ユーザーが会社のネットワークに接続されている場合に、ユーザーに対して自動的にサインインするために、[シームレスなシングルサインオンを有効](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)にします。 |  | はい | はい |  |
| [名前付きネットワークを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection は使用できるすべてのセッション データを収集し、分析してリスク スコアを生成します。 「Networks configuration」という名前の Azure AD で、組織のパブリック IP 範囲をネットワークに指定することをお勧めします。 これらの範囲から来たトラフィックにはリスクスコアが減少し、企業環境外からのトラフィックにはより高いリスクスコアが与えられます。 | はい  | はい | はい | はい |
|[セルフサービスのパスワードのリセット (SSPR) および多要素認証 (MFA) に対して、すべてのユーザーを登録](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)します。 事前に Azure MFA のユーザーを登録することをお勧めします。 Azure AD Identity Protection は Azure MFA を利用して、追加のセキュリティ検証を実行します。 さらに、お客様のデバイスに[Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)と Microsoft ポータルサイトアプリをインストールすることをお勧めします。 これらは、各プラットフォームのアプリストアからインストールできます。 | はい | はい | はい | はい |
| ドメインに参加している[Windows コンピューターの自動デバイス登録を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)します。 条件付きアクセスでは、アプリに接続されているデバイスがドメインに参加しているか、準拠しているかを確認します。 Windows コンピューターでこの方法をサポートするには、デバイスを Azure AD に登録する必要があります。  この記事では、自動デバイス登録を構成する方法について説明します。 |   | はい |  はい |  はい |
| **サポート チームを用意します**。 MFA を完了できないユーザーのための計画を立てます。 これにより、それらをポリシー除外グループに追加したり、新しい MFA 情報を登録したりすることができます。 これらのセキュリティで保護された変更を行う前に、実際のユーザーが要求を行っていることを確認する必要があります。 同意を支援するようにユーザーの上司に依頼する方法も効果的です。 | はい | はい | はい | はい |  
| [オンプレミス AD へのパスワード ライトバックを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 パスワードの書き戻しを使用すると、高リスクなアカウントの侵害が検出されたときに、ユーザーがオンプレミスのパスワードを変更するよう要求することができます。 この機能を有効にするには、次の2つの方法のいずれかを使用します。 Azure AD Connect セットアップウィザードの [オプション機能] 画面で**パスワードの書き戻し**を有効にするか、Windows PowerShell で有効にすることができます。 |   | はい | はい | はい |
| [Azure Active Directory Id 保護を有効に](https://docs.microsoft.com/azure/active-directory/identity-protection/enable)します。 Azure AD Id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動修復ポリシーを低、中、高のサインインリスクとユーザーのリスクに構成できます。  | はい | はい | はい | はい |
| [Exchange online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)と[Skype for business online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)の**先進認証を有効に**します。 モダン認証は、多要素認証 (MFA) を使用するための前提条件です。 モダン認証は、Office 2016 クライアント、SharePoint Online、および OneDrive for business では既定で有効になっています。 | はい | はい | はい | はい |
||||||



## <a name="recommended-client-configurations"></a>推奨されるクライアント構成
このセクションでは、ユーザーに最適な SSO を提供するために推奨される既定のプラットフォームクライアント構成について説明します。また、条件付きアクセスの技術的な前提条件についても説明します。

### <a name="windows-devices"></a>Windows デバイス
Azure は、オンプレミスと Azure AD の両方で最もスムーズな SSO を提供するように設計されているため、Windows 10 (バージョン1703以降) をお勧めします。 職場または学校で発行されたデバイスは、Azure AD に直接参加するように構成するか、または組織がオンプレミスの AD ドメイン参加を使用している場合は、それらのデバイスを[自動的に AZURE ad に登録する](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)ように構成する必要があります。

BYOD Windows デバイスでは、ユーザーは**職場または学校のアカウントの追加**を使用できます。 Windows 10 の Chrome ブラウザーユーザーは、エッジ/IE ユーザーと同じスムーズなサインインを得るために[拡張機能をインストール](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)する必要があることに注意してください。 また、組織がドメインに参加している Windows 7 デバイスを使用している場合は、Microsoft Workplace Join を Windows 10 以外のコンピューターにインストールすることができます。[パッケージをダウンロード](https://www.microsoft.com/download/details.aspx?id=53554)して、デバイスを Azure AD に登録します。

### <a name="ios-devices"></a>iOS デバイス
条件付きアクセスや MFA ポリシーを展開する前に、ユーザーのデバイスに [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールすることを推奨しています。 アプリは少なくとも、職場または学校のアカウントを追加したり、Intune ポータルサイトアプリをインストールしてデバイスを管理に登録したりすることによって、ユーザーが Azure AD にデバイスを登録するように求められたときにインストールする必要があります。 これは、構成されている条件付きアクセス ポリシーに依存します。

### <a name="android-devices"></a>Android デバイス
ユーザーには、条件付きアクセス ポリシーの展開前に、あるいは認証時に要求されたときに [Intune ポータル サイト アプリ](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)と [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールするように推奨しています。 アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成されている条件付きアクセス ポリシーに依存します。

また、電子メールアカウントを Intune MDM ポリシーで管理および保護するために Android for Work または Samsung Knox for microsoft をサポートする Oem およびバージョンでは、企業所有のデバイス (COD) を標準で使用することをお勧めします。


### <a name="recommended-email-clients"></a>推奨される電子メール クライアント
次の電子メールクライアントは、モダン認証と条件付きアクセスをサポートしています。 

|プラットフォーム|クライアント|バージョン/注|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、2013[モダン認証を有効にする](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)、[必要な更新プログラム](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|非サポート||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム
セキュリティで保護されたドキュメントポリシーが適用されている場合は、次のクライアントが推奨されます。

|プラットフォーム|Word/Excel/PowerPoint|OneNote|OneDrive アプリ|SharePoint アプリ|OneDrive 同期クライアント|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|サポートされている|サポートされている|該当なし|該当なし|プレビュー<sup>*</sup>|
|Windows 8.1|サポートされている|サポートされている|該当なし|該当なし|プレビュー<sup>*</sup>|
|Windows 10|サポートされている|サポートされている|該当なし|該当なし|プレビュー<sup>*</sup>|
|Windows Phone 10|非サポート|非サポート|サポート対象外|サポート対象外|サポート対象外|
|Android|サポートされている|サポートされている|サポートされている|サポートされている|N/A|
|iOS|サポートされている|サポートされている|サポートされている|サポートされている|N/A|
|macOS|パブリック プレビュー|パブリック プレビュー|該当なし|該当なし|サポートされていません|
|Linux|非サポート|非サポート|非サポート|非サポート|非サポート|

<sup>*</sup>[OneDrive 同期クライアント](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)での条件付きアクセスの使用方法について説明します。

### <a name="office-365-client-support"></a>Office 365 クライアント サポート
Office 365 クライアントサポートの詳細については、次の記事を参照してください。
- [Office 365 クライアントアプリケーションのサポート-条件付きアクセス](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 クライアントアプリケーションのサポート-モバイルアプリケーション管理](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 クライアントアプリのサポート-モダン認証](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>管理者アカウントを保護する
Azure AD では、事前に構成された条件付きアクセスポリシーを使用して管理者アクセスの保護を開始する簡単な方法を提供します。 Azure AD で、**条件付きアクセス**に移動して、このポリシーを探します。**ベースラインポリシー: 管理者に MFA を必須にする (プレビュー)**。 このポリシーを選択し、[**すぐにポリシーを使用する**] を選択します。 

このポリシーには、次の役割に対する MFA が必要です。
- 全体管理者
- SharePoint 管理者
- Exchange 管理者
- 条件付きアクセス管理者
- セキュリティ管理者

詳細については、「 [AZURE AD 管理者アカウントのベースラインセキュリティポリシー](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)」を参照してください。

その他の推奨事項を以下に示します。
- Azure AD Privileged Identity Management を利用し、永続的管理者アカウントの数を減らします。 「 [PIM の使用を開始する」を](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started)参照してください。 
- [Office 365 で特権アクセス管理を使用](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)して、既存の特権のある管理者アカウントを使用して機密性の高いデータにアクセスしたり、重要な構成設定にアクセスしたりすることができる侵害から組織を保護します。 
- 管理者アカウントを使用するのは管理者のみです。 管理者は、管理者が通常使用しないユーザーアカウントを持っていて、自分のジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。 [Office 365 の管理者](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割には、office 365 サービスよりもはるかに多くの特権があります。
- この[記事](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)で説明されているように、Azure AD で特権アカウントを保護するためのベストプラクティスに従います。

## <a name="next-steps"></a>次のステップ

[共通 id およびデバイスアクセスポリシーを構成する](identity-access-policies.md)

