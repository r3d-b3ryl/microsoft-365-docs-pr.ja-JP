---
title: Id およびデバイスアクセスポリシーを実装するための前提条件-エンタープライズ向け Microsoft 365 |Microsoft Docs
description: Id およびデバイスアクセスポリシーと構成を実装する前の前提条件について説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 034dd31309c783e8b231a113d2bda5ccb1888d5b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950762"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Id およびデバイスアクセスポリシーを実装するための前提条件

この記事では、推奨される id とデバイスのアクセスポリシーを展開する前に実装する必要がある前提条件について説明します。 この記事では、推奨される既定のプラットフォームクライアント構成についても説明します。これには、ユーザーに最適なシングルサインオン (SSO) の機能、および条件付きアクセスの技術的な前提条件が提供されます。

## <a name="prerequisites"></a>前提条件

推奨される id とデバイスのアクセスポリシーを実装する前に、365 365 次のような前提条件を満たす必要があります。

- クラウド専用
- パスワードハッシュ同期 (PHS) 認証を使用するハイブリッド
- パススルー認証を使用したハイブリッド (PTA)
- 分散

次の表では、すべての id モデルに適用される必要な機能とその構成について詳しく説明しています (記載されている場合を除く)。 

| 構成 | 例外 |
| :------------- | :-----------: |
|  [PHS を構成](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)します。  これを有効にして、リークした資格情報を検出し、リスクベースの条件付きアクセスに対して動作するようにする必要があります。 **注:** これは、組織がフェデレーション認証を使用しているかどうかに関係なく必要になります。 |  クラウド専用 |
| ユーザーが組織のネットワークに接続されている組織のデバイス上にいるときに、ユーザーに対して自動的にサインインするために、[シームレスなシングルサインオンを有効](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)にします。 | クラウドのみとフェデレーション  |
| [名前付きネットワークを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection は使用できるすべてのセッション データを収集し、分析してリスク スコアを生成します。 「Networks configuration」という名前の Azure AD で、組織のパブリック IP 範囲をネットワークに指定することをお勧めします。 これらの範囲から来たトラフィックにはリスクスコアが減少し、組織環境外からのトラフィックにはより高いリスクスコアが与えられます。 | |
|[セルフサービスのパスワードのリセット (SSPR) および多要素認証 (MFA) に対して、すべてのユーザーを登録](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)します。 事前に Azure 多要素認証を使用するようにユーザーを登録することをお勧めします。 Azure AD Identity Protection は、Azure の多要素認証を使用して、追加のセキュリティ検証を実行します。 さらに、お客様のデバイスに [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) と Microsoft ポータルサイトアプリをインストールすることをお勧めします。 これらは、各プラットフォームのアプリストアからインストールできます。 | |
| ドメインに参加している[Windows コンピューターの自動デバイス登録を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)します。 条件付きアクセスでは、アプリに接続されているデバイスがドメインに参加しているか、準拠しているかを確認します。 Windows コンピューターでこの方法をサポートするには、デバイスを Azure AD に登録する必要があります。  この記事では、自動デバイス登録を構成する方法について説明します。 | クラウド専用 |
| **サポート チームを用意します**。 MFA を完了できないユーザーのための計画を立てます。 これにより、それらをポリシー除外グループに追加したり、新しい MFA 情報を登録したりすることができます。 これらのセキュリティで保護された変更を行う前に、実際のユーザーが要求を行っていることを確認する必要があります。 同意を支援するようにユーザーの上司に依頼する方法も効果的です。 | |  
| [オンプレミス AD へのパスワード ライトバックを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 パスワードの書き戻しを使用すると、高リスクなアカウントの侵害が検出されたときに、ユーザーがオンプレミスのパスワードを変更するよう要求することができます。 この機能を有効にするには、次の2つの方法のいずれかを使用します。 Azure AD Connect セットアップウィザードの [オプション機能] 画面で **パスワードの書き戻し** を有効にするか、Windows PowerShell で有効にすることができます。 | クラウド専用 |
| [AZURE AD パスワード保護を構成](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)します。 Azure AD パスワード保護は、既知の弱いパスワードとその亜種を検出してブロックすることができます。また、組織固有のその他の弱い用語をブロックすることもできます。 既定のグローバル禁止パスワードリストは、Azure AD テナント内のすべてのユーザーに自動的に適用されます。 カスタム禁止パスワードリストには、追加のエントリを定義できます。 ユーザーがパスワードを変更または再設定すると、これらの禁止されたパスワードの一覧がチェックされ、強力なパスワードの使用が強制されます。 | |
| [Azure Active Directory Id 保護を有効に](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)します。 Azure AD Id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動修復ポリシーを低、中、高のサインインリスクとユーザーのリスクに構成できます。  | |
| [Exchange online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)と[Skype for business online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)の**先進認証を有効に**します。 先進認証は、MFA を使用するための前提条件です。 モダン認証は、Office 2016 クライアント、SharePoint、OneDrive for business では既定で有効になっています。 |  |
|||

## <a name="recommended-client-configurations"></a>推奨されるクライアント構成
このセクションでは、ユーザーに最適な SSO を提供するために推奨される既定のプラットフォームクライアント構成について説明します。また、条件付きアクセスの技術的な前提条件についても説明します。

### <a name="windows-devices"></a>Windows デバイス
Azure は、オンプレミスと Azure AD の両方で最もスムーズな SSO を提供するように設計されているため、Windows 10 (バージョン2004以降) をお勧めします。 職場または学校で発行されたデバイスは、Azure AD に直接参加するように構成するか、または組織がオンプレミスの AD ドメイン参加を使用している場合は、それらのデバイスを [自動的に AZURE ad に登録する](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)ように構成する必要があります。

BYOD Windows デバイスでは、ユーザーは **職場または学校のアカウントの追加**を使用できます。 Windows 10 デバイス上の Google Chrome ブラウザーのユーザーは、Microsoft Edge ユーザーと同じスムーズなサインインを得るために [拡張機能をインストール](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) する必要があることに注意してください。 また、組織がドメインに参加している Windows 8 または8.1 デバイスを使用している場合は、Microsoft Workplace Join を Windows 10 以外のコンピューターにインストールすることもできます。 [パッケージをダウンロード](https://www.microsoft.com/download/details.aspx?id=53554) して、デバイスを Azure AD に登録します。

### <a name="ios-devices"></a>iOS デバイス
条件付きアクセスまたは MFA ポリシーを展開する前に、ユーザーデバイスに [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) をインストールすることをお勧めします。 アプリは少なくとも、職場または学校のアカウントを追加したり、Intune ポータルサイトアプリをインストールしてデバイスを管理に登録したりすることによって、ユーザーが Azure AD にデバイスを登録するように求められたときにインストールする必要があります。 これは、構成された条件付きアクセスポリシーによって異なります。

### <a name="android-devices"></a>Android デバイス
条件付きアクセスポリシーを展開する前、または特定の認証試行中に必要に応じて、 [Intune Company Portal アプリ](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) と [Microsoft Authenticator アプリ](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) をインストールすることをお勧めします。 アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成された条件付きアクセスポリシーによって異なります。

また、組織所有のデバイスを Oem および Android for Work または Samsung Knox をサポートするバージョンに標準化して、メールアカウントを Intune MDM ポリシーで管理および保護することをお勧めします。


### <a name="recommended-email-clients"></a>推奨される電子メール クライアント
次の電子メールクライアントは、モダン認証と条件付きアクセスをサポートしています。 

|プラットフォーム|クライアント|バージョン/注|
|:-------|:-----|:------------|
|**Windows**|Outlook|2019、2016、2013 <BR> [先進認証を有効にする](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)、 [必要な更新プログラム](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019および2016|
|**Linux**|サポートされていません||
|||

### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム

セキュリティで保護されたドキュメントポリシーが適用されている場合は、次のクライアントが推奨されます。

|プラットフォーム|Word/Excel/PowerPoint|OneNote|OneDrive アプリ|SharePoint アプリ|[OneDrive 同期クライアント](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 8.1|サポート済み|サポート済み|該当なし|該当なし|サポート済み|
|Windows 10|サポート済み|サポート済み|該当なし|該当なし|サポート済み|
|Android|サポート済み|サポート済み|サポート済み|サポート済み|N/A|
|iOS|サポート済み|サポート済み|サポート済み|サポート済み|N/A|
|macOS|サポート済み|サポート済み|該当なし|該当なし|サポートされていません|
|Linux|非サポート|非サポート|非サポート|非サポート|非サポート|

### <a name="microsoft-365-client-support"></a>Microsoft 365 のクライアント サポート

Microsoft 365 でのクライアントサポートの詳細については、次の記事を参照してください。

- [Microsoft 365 クライアントアプリケーションのサポート-条件付きアクセス](microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 クライアントアプリのサポート-モダン認証](microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>管理者アカウントを保護する

Microsoft 365 E3 または E5、または個別の Azure AD Premium P1 または P2 ライセンスを使用している場合は、手動で作成された条件付きアクセスポリシーを使用して、管理者アカウントに MFA を要求することができます。 詳細については、「 [条件付きアクセス: 管理者に MFA を必要とする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) 」を参照してください。

条件付きアクセスをサポートしていない Microsoft 365 または Office 365 のエディションでは、 [セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) を有効にして、すべてのアカウントで MFA を必須にすることができます。

その他の推奨事項を以下に示します。

- [AZURE AD 特権 Id 管理](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started)を使用して、永続的な管理アカウントの数を減らします。 
- [特権アクセス管理を使用](../compliance/privileged-access-management-overview.md) して、機密データへの永続的なアクセス権を持つ既存の特権のある管理者アカウントを使用したり、重要な構成設定にアクセスしたりすることができる侵害から組織を保護します。 
- [Microsoft 365 管理者](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)*の*役割が割り当てられている個別のアカウントを作成して使用します。 管理者は、管理者が通常使用できない専用のユーザーアカウントを持っていて、役割またはジョブ関数に関連付けられているタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。 
- Azure AD で権限のあるアカウントを保護するための [ベストプラクティス](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) に従います。

## <a name="next-step"></a>次の手順

[![手順 2: 共通 id を構成し、条件付きアクセスポリシーにアクセスする](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[共通 id およびデバイスアクセスポリシーを構成する](identity-access-policies.md)
