---
title: ID およびデバイス アクセス ポリシーを実装するための前提条件 - エンタープライズ |用 Microsoft 365Microsoft Docs
description: この記事では、ゼロ トラスト ID とデバイスのアクセス ポリシーと構成を使用するために満たす必要がある前提条件について説明します。
ms.author: dansimp
author: dansimp
manager: dansimp
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
- zerotrust-solution
- highpri
ms.technology: mdo
ms.openlocfilehash: 27c6557219db62d17ebb90e3e5b36169fc397874
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477343"
---
# <a name="prerequisite-work-for-implementing-zero-trust-identity-and-device-access-policies"></a>ゼロ トラスト ID ポリシーとデバイス アクセス ポリシーを実装するための前提条件

この記事では、管理者が推奨されるゼロ トラスト ID とデバイスのアクセス ポリシーを使用し、条件付きアクセスを使用するために満たす必要がある前提条件について説明します。 また、シングル サインオン (SSO) エクスペリエンスを最適にするためのクライアント プラットフォームの構成に推奨される既定値についても説明します。

## <a name="prerequisites"></a>前提条件

推奨されるゼロ トラスト ID ポリシーとデバイス アクセス ポリシーを使用する前に、組織は前提条件を満たす必要があります。 要件は、一覧に示されているさまざまな ID モデルと認証モデルで異なります。

- クラウド専用
- パスワード ハッシュ同期 (PHS) 認証を使用したハイブリッド
- パススルー認証 (PTA) を使用したハイブリッド
- フェデレーション

次の表では、前提条件の機能と、すべての ID モデルに適用される構成について詳しく説明します (ただし、この点を除きます)。

|構成|例外|ライセンス|
|---|:---:|---|
|[PHS を構成します](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  これは、漏洩した資格情報を検出し、リスクベースの条件付きアクセスに対してそれらの資格情報を操作するために有効にする必要があります。 **メモ：** これは、組織がフェデレーション認証を使用しているかどうかに関係なく必要です。|クラウド専用|Microsoft 365 E3 または E5|
|[シームレス シングル サインオンを有効にすると](/azure/active-directory/connect/active-directory-aadconnect-sso) 、組織のネットワークに接続されている組織のデバイス上にユーザーが自動的にサインインします。|クラウド専用とフェデレーション|Microsoft 365 E3 または E5|
|[名前付き場所を構成します](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)。 Azure AD Identity Protection は使用できるすべてのセッション データを収集し、分析してリスク スコアを生成します。 Azure AD の名前付き場所の構成で、ネットワークに対する組織のパブリック IP 範囲を指定することをお勧めします。 これらの範囲から送信されるトラフィックにはリスク スコアが低下し、組織の環境外からのトラフィックにはリスク スコアが高くなります。||Microsoft 365 E3 または E5|
|[セルフサービス パスワード リセット (SSPR) と多要素認証 (MFA) のすべてのユーザーを登録](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)します。 事前に Azure AD 多要素認証にユーザーを登録することをお勧めします。 Azure AD Identity Protection では、Azure AD 多要素認証を使用して、追加のセキュリティ検証を実行します。 さらに、最適なサインイン エクスペリエンスを実現するために、ユーザーがデバイスに [Microsoft Authenticator アプリ](/azure/active-directory/user-help/microsoft-authenticator-app-how-to)と Microsoft ポータル サイト アプリをインストールすることをお勧めします。 これらは、プラットフォームごとにアプリ ストアからインストールできます。||Microsoft 365 E3 または E5|
|[ドメインに参加している Windows コンピューターのデバイスの自動登録を有効にします](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件付きアクセスでは、アプリに接続しているデバイスがドメインに参加しているか準拠していることを確認します。 Windows コンピューターでこの方法をサポートするには、デバイスを Azure AD に登録する必要があります。  この記事では、自動デバイス登録を構成する方法について説明します。|クラウド専用|Microsoft 365 E3 または E5|
|**サポート チームを用意します**。 MFA を完了できないユーザーのための計画を立てます。 これは、ポリシー除外グループに追加したり、新しい MFA 情報を登録したりする可能性があります。 これらのセキュリティに依存する変更のいずれかを行う前に、実際のユーザーが要求を行っていることを確認する必要があります。 同意を支援するようにユーザーの上司に依頼する方法も効果的です。||Microsoft 365 E3 または E5|
|[オンプレミス AD へのパスワード ライトバックを構成します](/azure/active-directory/active-directory-passwords-getting-started)。 パスワード ライトバックを使用すると、リスクの高いアカウント侵害が検出されたときに、ユーザーがオンプレミスのパスワードを変更することを Azure AD に要求できます。 この機能は、Azure AD Connect セットアップのオプション機能画面で **パスワード ライトバック** を有効にするか、Windows PowerShellを使用して有効にするかの 2 つの方法のいずれかで有効にすることができます。|クラウド専用|Microsoft 365 E3 または E5|
|[Azure AD パスワード保護を構成します](/azure/active-directory/authentication/concept-password-ban-bad)。 Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。||Microsoft 365 E3 または E5|
|[Azure Active Directory Identity Protection を有効にします](/azure/active-directory/identity-protection/overview-identity-protection)。 Azure AD Identity Protection を使用すると、組織の ID に影響を与える潜在的な脆弱性を検出し、低、中、高のサインイン リスクとユーザー リスクに対する自動修復ポリシーを構成できます。||E5 セキュリティ アドオンを使用したMicrosoft 365 E5またはMicrosoft 365 E3|
|[Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)と [Skype for Business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) の **先進認証を有効にします**。 最新の認証は、MFA を使用するための前提条件です。 最新の認証は、Office 2016 および 2019 クライアント、SharePoint、およびOneDrive for Businessに対して既定で有効になっています。||Microsoft 365 E3 または E5|
|Azure AD [の継続的アクセス評価を有効にします](microsoft-365-continuous-access-evaluation.md)。 継続的なアクセス評価では、アクティブなユーザー セッションがプロアクティブに終了し、ほぼリアルタイムでテナント ポリシーの変更が適用されます。||Microsoft 365 E3 または E5|

## <a name="recommended-client-configurations"></a>推奨されるクライアント構成

このセクションでは、ユーザーに最適な SSO エクスペリエンスを提供するために推奨される既定のプラットフォーム クライアント構成と、条件付きアクセスの技術的前提条件について説明します。

### <a name="windows-devices"></a>Windows デバイス

Windows 11またはWindows 10 (バージョン 2004 以降) をお勧めします。Azure は、オンプレミスと Azure AD の両方で可能な限りスムーズな SSO エクスペリエンスを提供するように設計されています。 職場または学校が発行したデバイスは、Azure AD に直接参加するように構成する必要があります。組織がオンプレミスの AD ドメイン参加を使用している場合は、それらのデバイスを [自動的に Azure AD に自動的かつサイレントに登録するように構成](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)する必要があります。

BYOD Windows デバイスの場合、ユーザーは **職場または学校アカウントの追加** を使用できます。 Windows 11またはWindows 10 デバイス上の Google Chrome ブラウザーのユーザーは、Microsoft Edge ユーザーと同じスムーズ[な](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)サインイン エクスペリエンスを得るために拡張機能をインストールする必要があることに注意してください。 また、組織にドメインに参加しているWindows 8または 8.1 デバイスがある場合は、Windows 10 以外のコンピューターに Microsoft Workplace Join をインストールできます。 [パッケージをダウンロードして、](https://www.microsoft.com/download/details.aspx?id=53554) デバイスを Azure AD に登録します。

### <a name="ios-devices"></a>iOS デバイス

条件付きアクセスポリシーまたは MFA ポリシーを展開する前に [、ユーザー デバイスに Microsoft Authenticator アプリ](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) をインストールすることをお勧めします。 少なくとも、ユーザーが職場または学校アカウントを追加してデバイスを Azure AD に登録するように求められた場合や、Intuneポータル サイト アプリをインストールしてデバイスを管理に登録するときに、アプリをインストールする必要があります。 これは、構成された条件付きアクセス ポリシーによって異なります。

### <a name="android-devices"></a>Android デバイス

条件付きアクセス ポリシーが展開される前、または特定の認証試行中に必要な場合は、ユーザーが[Intune ポータル サイト アプリ](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)と [Microsoft Authenticator アプリ](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)をインストールすることをお勧めします。 アプリのインストール後、Azure AD または Intune にデバイスを登録するように要求されることがあります。 これは、構成された条件付きアクセス ポリシーによって異なります。

また、組織所有のデバイスは、Android for Work または Samsung Knox をサポートする OEM およびバージョンで標準化され、メール アカウントを許可し、Intune MDM ポリシーによって管理および保護されることをお勧めします。

### <a name="recommended-email-clients"></a>推奨される電子メール クライアント

次の電子メール クライアントでは、先進認証と条件付きアクセスがサポートされています。

|プラットフォーム|クライアント|バージョン/注|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [先進認証を有効にする](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [必要な更新プログラム](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 年と 2016 年|
|**Linux**|サポートされていません||

### <a name="recommended-client-platforms-when-securing-documents"></a>ドキュメントをセキュリティで保護するときに推奨されるクライアント プラットフォーム

セキュリティで保護されたドキュメント ポリシーが適用されている場合は、次のクライアントをお勧めします。

|プラットフォーム|Word/Excel/PowerPoint|OneNote|OneDrive アプリ|SharePoint アプリ|[OneDrive 同期クライアント](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 11またはWindows 10|サポート|サポート|該当なし|該当なし|サポートされている|
|Windows 8.1|サポート|サポートされている|該当なし|該当なし|サポート|
|Android|サポートされている|サポートされている|サポート|サポート|N/A|
|iOS|サポートされている|サポート|サポート|サポート|N/A|
|macOS|サポート|サポートされている|該当なし|該当なし|サポートされていません|
|Linux|非サポート|非サポート|非サポート|非サポート|非サポート|

### <a name="microsoft-365-client-support"></a>Microsoft 365 のクライアント サポート

Microsoft 365 でのクライアント サポートの詳細については、次の記事を参照してください。

- [Microsoft 365 クライアント アプリのサポート - 条件付きアクセス](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 クライアント アプリのサポート - 多要素認証](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>管理者アカウントの保護

Microsoft 365 E3または E5、または個別のAzure AD Premium P1または P2 ライセンスの場合は、手動で作成された条件付きアクセス ポリシーを持つ管理者アカウントに対して MFA を要求できます。 詳細については、「 [条件付きアクセス: 管理者に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) 」を参照してください。

条件付きアクセスをサポートしていない Microsoft 365 またはOffice 365のエディションの場合は、[セキュリティの既定値](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)ですべてのアカウントに MFA を要求することができます。

その他の推奨事項を次に示します。

- [Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started)を使用して、永続的な管理アカウントの数を減らします。
- [特権アクセス管理を使用して](../../compliance/privileged-access-management-overview.md) 、機密データへの永続的なアクセスまたは重要な構成設定へのアクセスで既存の特権管理者アカウントを使用する可能性がある侵害から組織を保護します。
- *管理用にのみ* [Microsoft 365 管理者ロール](../../admin/add-users/about-admin-roles.md)が割り当てられている個別のアカウントを作成して使用します。 管理者は、通常の非管理者用の独自のユーザー アカウントを持ち、自分のロールまたはジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。
- Azure AD で特権アカウントをセキュリティで保護するための [ベスト プラクティス](/azure/active-directory/admin-roles-best-practices) に従ってください。

## <a name="next-step"></a>次のステップ

[![手順 2: 一般的なゼロ トラスト ID を構成し、条件付きアクセス ポリシーにアクセスします。](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png#lightbox)](identity-access-policies.md)

[一般的なゼロ トラスト ID ポリシーとデバイス アクセス ポリシーを構成する](identity-access-policies.md)
