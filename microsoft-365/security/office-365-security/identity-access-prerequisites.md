---
title: ID およびデバイス アクセス ポリシーを実装するための前提条件作業 - Microsoft 365 enterprise |Microsoft Docs
description: この記事では、ID およびデバイス アクセス ポリシーと構成を使用するために満たす必要がある前提条件について説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: e411eaa7874dee710cbb21dd02a4edd383003def
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142099"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>ID およびデバイス アクセス ポリシーを実装するための前提条件となる作業

この記事では、管理者が推奨 ID とデバイス アクセス ポリシーを使用し、条件付きアクセスを使用するために満たす必要がある前提条件について説明します。 また、最適なシングル サインオン (SSO) エクスペリエンスを得るクライアント プラットフォームを構成するための推奨される既定値も説明します。

## <a name="prerequisites"></a>前提条件

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- Azure

推奨される ID およびデバイス アクセス ポリシーを使用する前に、組織は前提条件を満たす必要があります。 要件は、次に示すさまざまな ID および認証モデルで異なります。

- クラウド専用
- パスワード ハッシュ同期 (PHS) 認証を使用したハイブリッド
- パススルー認証 (PTA) を使用するハイブリッド
- フェデレーション

次の表では、すべての ID モデルに適用される前提条件の機能とその構成について詳しい説明を示します (ただし、特に説明する場合を除く)。

|構成|例外|
|---|:---:|
|[PHS を構成します](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  これは、漏洩した資格情報を検出し、リスクベースの条件付きアクセスに対応するために有効にする必要があります。 **注:** これは、組織がフェデレーション認証を使用するかどうかに関係なく必要です。|クラウド専用|
|[シームレスなシングル サインオンを有効にして](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) 、組織のネットワークに接続されている組織のデバイスでユーザーを自動的にサインインします。|クラウド専用およびフェデレーション|
|[名前付きネットワークを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection は使用できるすべてのセッション データを収集し、分析してリスク スコアを生成します。 Azure または名前付きネットワーク構成では、組織のネットワークのパブリック IP 範囲AD指定することをお勧めします。 これらの範囲からのトラフィックにはリスク スコアが低下し、組織環境外からのトラフィックには高いリスク スコアが与えられる。||
|[セルフサービスによるパスワードのリセット (SSPR)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)と多要素認証 (MFA) に対してすべてのユーザーを登録します。 Azure AD多要素認証のユーザーを登録することをお勧めします。 Azure AD Identity Protection は、Azure AD 多要素認証を使用して、追加のセキュリティ検証を実行します。 また、最適なサインイン エクスペリエンスを提供するために、ユーザーがデバイスに [Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) アプリと Microsoft ポータル サイト アプリをインストールすることをお勧めします。 これらは、プラットフォームごとにアプリ ストアからインストールできます。||
|[ドメインに参加している Windows コンピューターのデバイスの自動登録を有効にします](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件付きアクセスでは、アプリに接続しているデバイスがドメインに参加しているか、準拠しているかが確認されます。 Windows コンピューターでこの方法をサポートするには、デバイスを Azure AD に登録する必要があります。  この記事では、自動デバイス登録を構成する方法について説明します。|クラウド専用|
|**サポート チームを用意します**。 MFA を完了できないユーザーのための計画を立てます。 ポリシーの除外グループにユーザーを追加したり、新しい MFA 情報を登録したりします。 これらのセキュリティに依存する変更を行う前に、実際のユーザーが要求を行っている必要があります。 同意を支援するようにユーザーの上司に依頼する方法も効果的です。||
|[オンプレミス AD へのパスワード ライトバックを構成します](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 パスワードの書き戻しによりADリスクの高いアカウント侵害が検出された場合に、Azure ADユーザーがオンプレミスのパスワードを変更するように要求できます。 Azure AD Connect を使用してこの機能を有効にするには、Azure AD Connectセットアップ ウィザードのオプション機能画面でパスワードの書き戻しを有効にするか、Windows PowerShell を使用して有効にします。|クラウド専用|
|[Azure ADパスワード保護を構成します](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。 Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。||
|[Azure Active Directory Identity Protection を有効にします](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。 Azure AD Identity Protection を使用すると、組織の ID に影響を与える可能性のある脆弱性を検出し、自動修復ポリシーを低、中、高のサインイン リスクとユーザー リスクに構成できます。||
|**Exchange** Online と Skype for Business [Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) の [モダン認証を有効にします](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 MFA を使用するには、最新の認証が必要です。 モダン認証は、Office 2016 および 2019 のクライアント、SharePoint、OneDrive for Business に対して既定で有効になっています。||
|

## <a name="recommended-client-configurations"></a>推奨されるクライアント構成

このセクションでは、ユーザーに最適な SSO エクスペリエンスを提供するために推奨される既定のプラットフォーム クライアント構成と、条件付きアクセスの技術的な前提条件について説明します。

### <a name="windows-devices"></a>Windows デバイス

Windows 10 (バージョン 2004 以降) をお勧めします。Azure は、オンプレミスと Azure の両方で可能な限りスムーズな SSO エクスペリエンスを提供するように設計AD。 Azure AD に直接参加するように、または組織がオンプレミスの AD ドメイン参加を使用している場合は、それらのデバイスを Azure AD に自動的にサイレント 登録するように構成する必要 [があります](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

BYOD Windows デバイスの場合、ユーザーは [仕事用または学校用アカウント **の追加] を使用できます**。 Windows 10 デバイスの Google Chrome ブラウザーのユーザー[](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)は、Microsoft Edge ユーザーと同じスムーズなサインイン エクスペリエンスを実現するために拡張機能をインストールする必要があります。 また、組織にドメインに参加している Windows 8 または 8.1 デバイスがある場合は、Windows 10 以外のコンピューター用に Microsoft Workplace Join をインストールできます。 [パッケージをダウンロードして、](https://www.microsoft.com/download/details.aspx?id=53554) デバイスを Azure AD。

### <a name="ios-devices"></a>iOS デバイス

条件付きアクセスポリシーまたは MFA ポリシーを展開する前に、ユーザー デバイスに [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) アプリをインストールすることをお勧めします。 少なくとも、ユーザーが Azure AD にデバイスを登録するように求める場合は、少なくとも、アプリをインストールする必要があります。また、ユーザーが Intune ポータル サイト アプリをインストールしてデバイスを管理に登録する場合にも、アプリをインストールする必要があります。 これは、構成されている条件付きアクセス ポリシーによって異なります。

### <a name="android-devices"></a>Android デバイス

条件付きアクセス ポリシーを展開する前、または特定の認証試行中に必要な場合は、ユーザーが [Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) ポータル サイト アプリと [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) アプリをインストールすることをお勧めします。 アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成されている条件付きアクセス ポリシーによって異なります。

また、組織が所有するデバイスは、Android for Work または Samsung Knox をサポートする OEM とバージョンで標準化し、メール アカウントを許可し、Intune MDM ポリシーで管理および保護することをお勧めします。

### <a name="recommended-email-clients"></a>推奨される電子メール クライアント

次の電子メール クライアントは、最新の認証と条件付きアクセスをサポートしています。

|プラットフォーム|クライアント|バージョン/注|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [モダン認証を有効にする](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [必要な更新プログラム](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 および 2016|
|**Linux**|サポートされていません||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム

セキュリティで保護されたドキュメント ポリシーが適用されている場合は、次のクライアントをお勧めします。

|プラットフォーム|Word/Excel/PowerPoint|OneNote|OneDrive アプリ|SharePoint アプリ|[OneDrive 同期クライアント](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|サポート|サポート|N/A|N/A|サポート|
|Windows 10|サポート|サポート|N/A|N/A|サポート|
|Android|サポート|サポート|サポート|サポート|N/A|
|iOS|サポート|サポート|サポート|サポート|N/A|
|macOS|サポート|サポート|N/A|N/A|サポートされていません|
|Linux|サポート対象外|サポート対象外|サポート対象外|サポート対象外|サポート対象外|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365 のクライアント サポート

Microsoft 365 でのクライアント サポートの詳細については、次の記事を参照してください。

- [Microsoft 365 クライアント アプリのサポート - 条件付きアクセス](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 クライアント アプリのサポート - 多要素認証](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>管理者アカウントの保護

Microsoft 365 E3 または E5 の場合、または別の Azure AD Premium P1 または P2 ライセンスを使用する場合は、手動で作成した条件付きアクセス ポリシーを使用して管理者アカウントに MFA を要求できます。 詳細 [については、「条件付きアクセス: 管理者に MFA を要求する」](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) を参照してください。

条件付きアクセスをサポートしていない Microsoft 365 または Office 365 のエディションでは、セキュリティ[](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)の既定値を有効にして、すべてのアカウントに MFA を要求できます。

その他の推奨事項を次に示します。

- [Azure AD Privileged Identity Management を使用](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started)して、永続的な管理アカウントの数を減らします。
- [特権アクセス管理を](../../compliance/privileged-access-management-overview.md) 使用して、機密データへの永続的なアクセスまたは重要な構成設定へのアクセス権を持つ既存の特権管理者アカウントを使用する可能性のある侵害から組織を保護します。
- 管理専用の [Microsoft 365 管理者](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)ロールが割り当てられている個別の *アカウントを作成して使用します*。 管理者は、管理者以外の通常の使用のために独自のユーザー アカウントを持ち、自分の役割またはジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。
- Azure [AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) で特権アカウントをセキュリティ保護するためのベスト プラクティスに従AD。

## <a name="next-step"></a>次の手順

[![手順 2: 共通 ID を構成し、条件付きアクセス ポリシーにアクセスする](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[共通の ID ポリシーとデバイス アクセス ポリシーを構成する](identity-access-policies.md)
