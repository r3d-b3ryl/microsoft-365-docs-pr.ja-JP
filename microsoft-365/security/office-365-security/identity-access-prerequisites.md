---
title: ID およびデバイス アクセス ポリシーを実装するための前提条件作業 - エンタープライズ Microsoft 365の|Microsoft Docs
description: この記事では、ID およびデバイス アクセス ポリシーと構成を使用するために満たす必要がある前提条件について説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: ba6a12036d6d6e0b53b930e2b1683781a474d186
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60666724"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>ID およびデバイス アクセス ポリシーを実装するための前提条件作業

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- Azure

この記事では、管理者が推奨 ID およびデバイス アクセス ポリシーを使用し、条件付きアクセスを使用するために満たす必要がある前提条件について説明します。 また、最高のシングル サインオン (SSO) エクスペリエンスを得るクライアント プラットフォームを構成するための推奨される既定値について説明します。

## <a name="prerequisites"></a>前提条件

推奨される ID およびデバイス アクセス ポリシーを使用する前に、組織は前提条件を満たす必要があります。 要件は、次に示すさまざまな ID モデルと認証モデルで異なります。

- クラウド専用
- パスワード ハッシュ同期 (PHS) 認証を使用したハイブリッド
- パススルー認証付きハイブリッド (PTA)
- フェデレーション

次の表では、すべての ID モデルに適用される前提条件の機能と構成について説明します(ただし、特に示す場合を除く)。

|構成|例外|ライセンス|
|---|:---:|---|
|[PHS を構成します](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  漏洩した資格情報を検出し、リスクベースの条件付きアクセスに対応するには、これを有効にする必要があります。 **注:** これは、組織がフェデレーション認証を使用するかどうかに関係なく必要です。|クラウド専用|Microsoft 365 E3 または E5|
|[シームレスなシングル サインオンを有効](/azure/active-directory/connect/active-directory-aadconnect-sso) にして、組織ネットワークに接続されている組織デバイスでユーザーが自動的にサインインします。|クラウド専用とフェデレーション|Microsoft 365 E3 または E5|
|[名前付き場所を構成します](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)。 Azure AD Identity Protection は使用できるすべてのセッション データを収集し、分析してリスク スコアを生成します。 名前付き場所の構成で、ネットワークの組織のパブリック IP Azure AD指定することをお勧めします。 これらの範囲からのトラフィックにはリスク スコアが低下し、組織環境外からのトラフィックにはリスク スコアが高くなります。||Microsoft 365 E3 または E5|
|[セルフサービス パスワード リセット (SSPR)](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)および多要素認証 (MFA) に対してすべてのユーザーを登録します。 多要素認証のユーザーをAzure ADに登録することをお勧めします。 Azure ADIDENTITY Protection では、多要素認証Azure ADを使用して、追加のセキュリティ検証を実行します。 さらに、最適なサインイン エクスペリエンスを得る場合は、ユーザーがデバイス[](/azure/active-directory/user-help/microsoft-authenticator-app-how-to)に Microsoft Authenticator アプリと Microsoft ポータル サイト アプリをインストールすることをお勧めします。 これらは、プラットフォームごとにアプリ ストアからインストールできます。||Microsoft 365 E3 または E5|
|[ドメインに参加しているコンピューターのデバイスの自動登録をWindowsします](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件付きアクセスでは、アプリに接続するデバイスがドメインに参加しているか、準拠しているかが確認されます。 Windows コンピューターでこの方法をサポートするには、デバイスを Azure AD に登録する必要があります。  この記事では、自動デバイス登録を構成する方法について説明します。|クラウド専用|Microsoft 365 E3 または E5|
|**サポート チームを用意します**。 MFA を完了できないユーザーのための計画を立てます。 ポリシー除外グループに追加したり、新しい MFA 情報を登録したりします。 これらのセキュリティに敏感な変更を行う前に、実際のユーザーが要求を行っている必要があります。 同意を支援するようにユーザーの上司に依頼する方法も効果的です。||Microsoft 365 E3 または E5|
|[オンプレミス AD へのパスワード ライトバックを構成します](/azure/active-directory/active-directory-passwords-getting-started)。 パスワード ライトバックを使用Azure ADリスクの高いアカウント侵害が検出された場合に、ユーザーがオンプレミスのパスワードを変更する必要があります。 Azure AD Connect を使用してこの機能を有効にするには、Azure AD Connect セットアップのオプション機能画面でパスワード ライトバックを有効にするか、Windows PowerShell 経由で有効にします。|クラウド専用|Microsoft 365 E3 または E5|
|[パスワード保護Azure AD構成します](/azure/active-directory/authentication/concept-password-ban-bad)。 Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。||Microsoft 365 E3 または E5|
|[[ID Azure Active Directoryを有効にする] をクリックします](/azure/active-directory/identity-protection/overview-identity-protection)。 Azure ADIdentity Protection を使用すると、組織の ID に影響を与える潜在的な脆弱性を検出し、自動修復ポリシーを低、中、高のサインイン リスクとユーザー リスクに構成できます。||Microsoft 365 E5またはMicrosoft 365 E3 E5 セキュリティ アドオンを使用する|
|**[オンライン] と**[[オンライン](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)Exchange Online最新の [Skype for Business有効にします](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 最新の認証は、MFA を使用する前提条件です。 最新の認証は、2016 および 2019 Officeクライアント、SharePoint、およびOneDrive for Business。||Microsoft 365 E3 または E5|
|[ユーザーに対して継続的な](microsoft-365-continuous-access-evaluation.md)アクセス評価Azure AD。 継続的なアクセス評価は、アクティブなユーザー セッションを積極的に終了し、ほぼリアルタイムでテナント ポリシーの変更を適用します。||Microsoft 365 E3 または E5|
|

## <a name="recommended-client-configurations"></a>推奨されるクライアント構成

このセクションでは、ユーザーに最高の SSO エクスペリエンスを提供することをお勧めする既定のプラットフォーム クライアント構成と、条件付きアクセスの技術的前提条件について説明します。

### <a name="windows-devices"></a>Windows デバイス

Azure は、オンプレミスとWindows 10の両方で可能な限りスムーズな SSO エクスペリエンスを提供するように設計されているので、Windows 10 (バージョン 2004 以降) をお勧Azure AD。 Azure AD に直接参加するように、または組織がオンプレミスの AD ドメイン参加を使用している場合は、これらのデバイスを自動的にサイレント 登録するように Azure AD に構成する必要[があります](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

BYOD デバイスWindows、ユーザーは [仕事または学校の **アカウントの追加] を使用できます**。 デバイス上の Google Chrome ブラウザーのユーザー Windows 10ユーザーと同[](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)じスムーズなサインイン エクスペリエンスを得る拡張機能をインストールするMicrosoft Edge注意してください。 また、組織にドメインに参加しているWindows 8 8.1 デバイスがある場合は、Microsoft Workplace Join を非ユーザーのコンピューター Windows 10できます。 [パッケージをダウンロードしてデバイスをデバイス](https://www.microsoft.com/download/details.aspx?id=53554)に登録Azure AD。

### <a name="ios-devices"></a>iOS デバイス

条件付きアクセスポリシーまたは MFA [Microsoft Authenticator展開](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)する前に、ユーザー デバイスにアプリをインストールすることをお勧めします。 少なくとも、ユーザーが仕事または学校のアカウントを追加してデバイスを Azure AD に登録するか、Intune ポータル アプリをインストールしてデバイスを管理に登録するときに、アプリをインストールする必要があります。 これは、構成されている条件付きアクセス ポリシーによって異なります。

### <a name="android-devices"></a>Android デバイス

条件付きアクセス ポリシーを展開[する前Intune ポータル サイト、](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)または特定の認証Microsoft Authenticator場合は、ユーザーがアプリとアプリをインストールすることをお勧めします。 [](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成されている条件付きアクセス ポリシーによって異なります。

また、組織が所有するデバイスは、Android for Work または Samsung Knox をサポートする OEM およびバージョンで標準化され、メール アカウントを許可し、Intune MDM ポリシーによって管理および保護することをお勧めします。

### <a name="recommended-email-clients"></a>推奨される電子メール クライアント

次の電子メール クライアントは、モダン認証と条件付きアクセスをサポートしています。

|プラットフォーム|クライアント|バージョン/注|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [モダン認証を有効にする](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [必須の更新プログラム](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 年と 2016 年|
|**Linux**|サポートされていません||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム

セキュリティで保護されたドキュメント ポリシーが適用されている場合は、次のクライアントをお勧めします。

|プラットフォーム|Word/Excel/PowerPoint|OneNote|OneDrive アプリ|SharePoint アプリ|[OneDrive 同期クライアント](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|サポート|サポート|該当なし|該当なし|サポート|
|Windows 10|サポート|サポート|該当なし|該当なし|サポート|
|Android|サポート|サポート|サポート|サポート|N/A|
|iOS|サポート|サポート|サポート|サポート|N/A|
|macOS|サポート|サポート|該当なし|該当なし|サポートされていません|
|Linux|非サポート|非サポート|非サポート|非サポート|非サポート|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365 のクライアント サポート

クライアント サポートの詳細については、Microsoft 365記事を参照してください。

- [Microsoft 365クライアント アプリのサポート - 条件付きアクセス](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365クライアント アプリのサポート - 多要素認証](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>管理者アカウントの保護

ユーザー Microsoft 365 E3 E5 または個別の Azure AD Premium P1または P2 ライセンスを使用する場合は、手動で作成された条件付きアクセス ポリシーを使用して管理者アカウントに MFA を要求できます。 詳細 [については、「条件付きアクセス: 管理者に MFA を要求する」](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) を参照してください。

条件付きアクセスをMicrosoft 365またはOffice 365のエディションでは、セキュリティの既定値を有効にして、すべてのアカウントに[](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)MFA を要求できます。

その他の推奨事項を次に示します。

- 永続的[Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started)アカウントの数を減らすには、次の情報を使用します。
- [特権アクセス管理を使用](../../compliance/privileged-access-management-overview.md) して、機密データへの永続的なアクセスまたは重要な構成設定へのアクセスを持つ既存の特権管理者アカウントを使用する可能性のある侵害から組織を保護します。
- 管理者の役割にのみ割り当てられている個別 [Microsoft 365を作成して](../../admin/add-users/about-admin-roles.md)*使用します*。 管理者は、通常の非管理用に独自のユーザー アカウントを持ち、役割またはジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。
- 特権[アカウントをセキュリティ](/azure/active-directory/admin-roles-best-practices)で保護するためのベスト プラクティスに従って、Azure AD。

## <a name="next-step"></a>次の手順

[![手順 2: 共通 ID を構成し、条件付きアクセス ポリシーにアクセスします。](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[共通 ID とデバイス アクセス ポリシーを構成する](identity-access-policies.md)