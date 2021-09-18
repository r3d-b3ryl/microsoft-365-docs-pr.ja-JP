---
title: 準備評価ツールで見つかった問題を修正する
description: ツールが見つけた各問題に対して実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 9332483dffa9fc67bf319cc57aef89d25c866843
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2021
ms.locfileid: "59443997"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>準備評価ツールで見つかった問題を修正する

チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、アクションは必要ありません。        |
|アドバイザリ    | 登録とユーザーの最適なエクスペリエンスについては、ツールまたはこの記事の手順に従います。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を解決しない場合、登録は失敗します。* ツールまたはこの記事の手順に従って解決します。        |
|Error | 使用Azure Active Directory (AD) ロールには、このチェックを実行するための十分なアクセス許可が付与されません。 |

> [!NOTE]
> このツールによって報告された結果は、設定を実行した特定の時点でのみ設定の状態を反映します。 後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備完了" になる可能性があります。 ポリシーを変更する前Microsoft マネージド デスクトップ、この記事で説明されている特定の設定を確認してください。

## <a name="microsoft-intune-settings"></a>Microsoft Intune設定

Intune の設定には、管理センターのMicrosoft エンドポイント マネージャー[アクセスできます](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>自動パイロット展開プロファイル

割り当てられたグループまたは動的グループをターゲットとする既存の Autopilot プロファイルを、Microsoft マネージド デスクトップする必要があります。 Microsoft マネージド デスクトップを使用して新しいデバイスをプロビジョニングします。 既存の Autopilot 展開プロファイルがある場合は、Autopilot が成功するために管理デスクトップ準備テストを行う場合は、[すべての対象デバイスを自動パイロットに変換する] 設定を "No" に設定する必要があります。

**使用不可能**

すべてのデバイスに割り当てられている自動パイロット プロファイルがあります。 手順については[、「Autopilot を使用Windows Intune にデバイスを登録する」を参照Windowsしてください](/mem/autopilot/enrollment-autopilot)。 登録Microsoft マネージド デスクトップ後、Autopilot ポリシーを設定して、モダン **Workplace デバイス -All** Azure ADグループをADします。

**アドバイザリ**

Autopilot プロファイルが、割り当てられたまたは動的な Azure ADデバイスを含Microsoft マネージド デスクトップしてください。 手順については[、「Autopilot を使用Windows Intune にデバイスを登録する」を参照Windowsしてください](/mem/autopilot/enrollment-autopilot)。 登録Microsoft マネージド デスクトップ、Autopilot プロファイルを設定して、モダン Workplace **デバイス -All** Azure ADグループを除外します。


### <a name="certificate-connectors"></a>証明書コネクタ

Microsoft マネージド デスクトップ に登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーは発生しません。 以下のアドバイザリの 1 つだけが状況に適用されますので、注意深く確認してください。

**アドバイザリ**

証明書コネクタはありません。 コネクタは必要ない可能性がありますが、デバイスのネットワーク接続に必要かどうかを評価Microsoft マネージド デスクトップがあります。 詳細については、「証明書とネットワーク プロファイルを準備する」[を参照Microsoft マネージド デスクトップ。](certs-wifi-lan.md)

**アドバイザリ**

少なくとも 1 つの証明書コネクタにエラーがあります。 デバイスに証明書を提供するためにこのコネクタが必要Microsoft マネージド デスクトップ、エラーを解決する必要があります。 詳細については、「証明書とネットワーク プロファイルを準備する」[を参照Microsoft マネージド デスクトップ。](certs-wifi-lan.md)


**アドバイザリ**

証明書コネクタが 1 つ以上あるので、エラーは報告されません。 ただし、展開の準備として、デバイスのコネクタを再利用するためにプロファイルを作成Microsoft マネージド デスクトップがあります。 詳細については、「証明書とネットワーク プロファイルを準備する」[を参照Microsoft マネージド デスクトップ。](certs-wifi-lan.md)

### <a name="company-portal"></a>ポータル サイト

Microsoft マネージド デスクトップ IT 管理者は、ユーザーがデバイスを使用Intune ポータル サイトユーザー用にMicrosoft マネージド デスクトップする必要があります。 

**使用不可能**

ユーザーに対ポータル サイトインストールされていない。 Intune ポータル サイト同期を強制的に行い、Intune とデバイス間の同期をビジネス向け Microsoft Store。 詳細については、「デバイスにインストール[するIntune ポータル サイト」を参照してください](../get-started/company-portal.md)。


### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーは、Intune Microsoft マネージド デスクトップ Azure AD組織 (テナント) の管理を妨AD。

**使用不可能**

すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。 登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 登録後、条件付きアクセス ポリシー Microsoft マネージド デスクトップを確認Microsoft エンドポイント マネージャー。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**アドバイザリ**

条件付きアクセス ポリシーを使用すると、Microsoft マネージド デスクトップサービスを管理Microsoft マネージド デスクトップがあります。 登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**エラー**

Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。 このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="device-compliance-policies"></a>デバイス コンプライアンス ポリシー

Azure 組織の Intune デバイス コンプライアンス ポリシー ADデバイスにMicrosoft マネージド デスクトップがあります。

**アドバイザリ**

すべてのユーザーを適用する少なくとも 1 つのコンプライアンス ポリシーがあります。 Microsoft マネージド デスクトップデバイスに適用されるコンプライアンス ポリシー Microsoft マネージド デスクトップ含まれます。 組織が作成した、競合が発生Microsoft マネージド デスクトップデバイスに適用されるコンプライアンス ポリシーを確認します。 手順については、「コンプライアンス ポリシー[を作成する」を参照Microsoft Intune。](/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>デバイス構成プロファイル

Azure 組織の Intune デバイス構成プロファイルAD、Microsoft Manage Desktop デバイスまたはユーザーをターゲットにしなける必要があります。

**使用不可能**

すべてのユーザー、すべてのデバイス、または両方に適用される少なくとも 1 つの構成プロファイルがあります。 プロファイルをリセットして、特定の Azure ADデバイスを含Microsoft マネージド デスクトップします。 手順については、「カスタム設定[を使用してプロファイルを作成する」を参照Microsoft Intune。](/mem/intune/configuration/custom-settings-configure)

**アドバイザリ**

構成ポリシーにデバイスまたはユーザーが含Microsoft マネージド デスクトップしてください。 手順については、「カスタム設定[を使用してプロファイルを作成する」を参照Microsoft Intune。](/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>デバイスの種類の制限

Microsoft マネージド デスクトップ Intune への登録を許可する必要があります。

**使用不可能**

現在、Intune でのデバイスへの登録を許可Windows、少なくとも 1 つの登録制限ポリシーが構成されています。 「ユーザーを対象 [](/mem/intune/enrollment/enrollment-restrictions-set)とする登録制限ポリシーごとに登録制限を設定し、Microsoft マネージド デスクトップ **(MDM)** 設定を [許可] に変更Windows手順に従 **います**。 ただし、個人所有のデバイス **(MDM)** Windowsを [ブロック] に **設定できます**。 


### <a name="enrollment-status-page"></a>[登録の状態] ページ

現在、登録状態ページ (ESP) が有効になっています。 この機能のパブリック プレビュー Microsoft マネージド デスクトップ参加する場合は、このアイテムを無視できます。 詳細については [、「First-run experience with Autopilot」および「登録状態ページ」を参照してください](../get-started/esp-first-run.md)。

**使用不可能**

ESP の既定のプロファイルが [アプリとプロファイルの構成の進行状況 **を表示する] に設定されています**。 この設定を無効にするか、Azure AD グループへの割り当てに Microsoft マネージド デスクトップ デバイスが含まれるのを確認するには、「登録状態ページのセットアップ」の手順に[従います](/mem/intune/enrollment/windows-enrollment-status)。

**アドバイザリ**

[アプリとプロファイルの構成の進行状況を表示する] 設定を持つプロファイルが、デバイスを含む Azure AD グループに割りMicrosoft マネージド デスクトップしてください。 詳細については、「登録状態 [ページの設定」を参照してください](/mem/intune/enrollment/windows-enrollment-status)。

### <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

ビジネス向け Microsoft Store ポータル サイト アプリを Microsoft マネージド デスクトップ に展開して、Microsoft Project や Microsoft Visio などの一部のアプリを必要に応じてインストールできます (許可されている場合)。

**使用不可能**

ビジネス向け Microsoft Store有効になっていないか、Intune と同期されていない場合。 詳細については、「How [to manage volume purchased](/mem/intune/apps/windows-store-for-business) apps from the ビジネス向け Microsoft Store Microsoft Intune デバイスIntune ポータル サイトインストールする」を[参照してください](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多要素認証

多要素認証では、Intune Microsoft マネージド デスクトップ Azure AD組織 (テナント) を管理AD。


**使用不可能**

すべてのユーザーに割り当てられている条件付きアクセスポリシーでは、必要に応じていくつかの多要素認証ポリシーが設定されています。 登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**アドバイザリ**

条件付きアクセス ポリシーでは、複数要素認証が必要になります。この場合、Microsoft マネージド デスクトップサービスを管理Microsoft マネージド デスクトップがあります。 登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**エラー**

Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。 このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="powershell-scripts"></a>PowerShell スクリプト

Windows PowerShellデバイスをターゲットとする方法では、スクリプトを割りMicrosoft マネージド デスクトップできません。  

**アドバイザリ**

組織の Azure Windows PowerShellスクリプトAD Microsoft Manage Desktop デバイスまたはユーザーを対象とされていないことを確認します。 すべてのユーザー、すべてのデバイス、または両方を対象とする PowerShell スクリプトを割り当てない。 ポリシーを変更して、特定の Azure ADデバイスまたはユーザーを含Microsoft マネージド デスクトップ割り当てを使用します。 詳細については、「Intune のデバイスで PowerShell スクリプトを[使用するWindows 10を参照してください](/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>地域

地域は、地域でサポートされているMicrosoft マネージド デスクトップ。

**使用不可能**

Azure AD組織の地域は、現在、ユーザーがサポートMicrosoft マネージド デスクトップ。 詳細については、「サポートされている[地域Microsoft マネージド デスクトップ言語」を参照してください](../service-description/regions-languages.md)。

**アドバイザリ**

Azure 組織が所属する 1 つ以上のADは、ユーザーがサポートMicrosoft マネージド デスクトップ。 詳細については、「サポートされている[地域Microsoft マネージド デスクトップ言語」を参照してください](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>セキュリティベースライン

セキュリティ ベースライン ポリシーは、すべてのデバイスを対象Microsoft マネージド デスクトップする必要があります。

**使用不可能**

すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティ 基準プロファイルがあります。 ポリシーを変更して、特定の Azure ADデバイスを含Microsoft マネージド デスクトップします。 手順については[、「Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。 登録中に、すべてのデバイスに新しいセキュリティ 基準をMicrosoft マネージド デスクトップします。 登録後、セキュリティ ベースライン ポリシー Microsoft マネージド デスクトップ構成ポリシー領域で確認Microsoft エンドポイント マネージャー。 

**アドバイザリ**

デバイスから除外するセキュリティ 基準ポリシー Microsoft マネージド デスクトップします。 手順については[、「Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。 登録中に、すべてのデバイスに新しいセキュリティ 基準をMicrosoft マネージド デスクトップします。 モダン **ワークプレース デバイス -All** Azure AD グループは、Microsoft マネージド デスクトップ に登録するときに作成する動的グループなので、登録後にこのグループを除外するために戻ってくる必要があります。 

### <a name="unlicensed-admins"></a>ライセンスのない管理者

Azure 組織とやり取りするときに"アクセス許可の不足" エラーを回避するには、この設定ADがあります。 

**使用不可能**

**ライセンスのない管理者へのアクセスを許可するを有効** にする必要があります。 手順については、「ゲスト アカウント [の前提条件」を参照してください](/microsoft-365/managed-desktop/get-ready/guest-accounts)。

### <a name="windows-apps"></a>Windowsアプリ

ユーザーに提供するアプリMicrosoft マネージド デスクトップ確認します。

**アドバイザリ**

ユーザーに提供するアプリのインベントリをMicrosoft マネージド デスクトップする必要があります。 これらのアプリは Intune によって展開する必要があるから、既存の Intune アプリの再利用を評価します。 ユーザーにアプリポータル サイトする場合は、「[](../get-started/company-portal.md)デバイスIntune ポータル サイトをインストールする」と「登録状態ページ (ESP)」を参照してください)。 詳細については、「自動パイロット[でのアプリのMicrosoft マネージド デスクトップ](apps.md)実行エクスペリエンス」および「登録状態ページ」[を参照してください](../get-started/esp-first-run.md)。

Intune に移行する準備ができているアプリや調整が必要なアプリMicrosoft Endpoint Configuration Manager Microsoft アカウント担当者に問い合わせください。


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft マネージド デスクトップビジネスWindows Hello有効にする必要があります。

**アドバイザリ**

Windows Helloは無効になっているか、セットアップされません。 [ビジネス向けビジネス ポリシーの作成] の手順[に従ってWindows Helloを有効にしてください](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。


### <a name="windows-10-update-rings"></a>Windows 10リング

Intune の "Windows 10リング" ポリシーは、すべてのデバイスを対象Microsoft マネージド デスクトップできません。

**使用不可能**

すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。 ポリシーを変更して、特定の Azure ADデバイスを含Microsoft マネージド デスクトップします。 手順については[、「Intune でソフトウェアWindows 10更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。

**アドバイザリ**

最新の Workplace Devices **-All Azure** ADグループを除外している更新リング ポリシーをADしてください。 これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、Microsoft マネージド デスクトップ ユーザーを追加するモダン **Workplace -All** Azure AD グループ (または同等のグループ) も除外している更新リング ポリシーを確認してください。 手順については[、「Intune でソフトウェアWindows 10更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。 モダン ワークプレース デバイス **-All** および **Modern Workplace -All** Azure AD グループは、Microsoft マネージド デスクトップ に登録するときに作成するグループなので、登録後にこのグループを除外するために戻ってくる必要があります。


## <a name="azure-active-directory-settings"></a>Azure Active Directory設定

Azure portal でAzure Active Directory設定に[アクセスできます](https://portal.azure.com)。

### <a name="intune-enrollment"></a>Intune の登録

Windows 10組織の Azure ADデバイスは、Intune に自動的に登録できる必要があります。

**アドバイザリ**

MDM User スコープ **が [一部] または** [すべて] **に設定されているの** に **、None** は設定 **されていないか確認します**。 [一部] を **選択** した場合は、登録後に戻り、すべてのユーザーを対象とするグループまたは同等のグループに対してモダン Workplace **-All** Azure AD グループをMicrosoft マネージド デスクトップします。  「[デバイスを使用してデバイスの登録Windows設定する」を参照](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)Microsoft Intune。

### <a name="ad-hoc-subscriptions"></a>アドホック サブスクリプション

("false" に設定されている場合) 状態ローミングが正しく動作Enterprise設定を確認する方法について説明します。

**アドバイザリ**

**AllowAdHocSubscriptions が True** に設定されている必要 **があります**。 それ以外の場合Enterprise状態ローミングが機能しない場合があります。 詳細については [、「Set-MsolCompanySettings」を参照してください](/powershell/module/msonline/set-msolcompanysettings)。


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise状態ローミングを有効にする必要があります。

**アドバイザリ**

[すべて] または [選択Enterprise] の **状態ローミングが** 有効 **になっているか確認** します。 詳細については、「Enable Enterprise ステート ローミング」[を参照Azure Active Directory。](/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>ライセンス

ライセンスを使用するには、多数のライセンスMicrosoft マネージド デスクトップ。

**準備ができていない**

ユーザーが使用する必要があるすべてのライセンスを持っているMicrosoft マネージド デスクトップ。 詳細については[、「Microsoft マネージド デスクトップ」](../intro/technologies.md)および「[ライセンスの詳細」を参照してください](prerequisites.md#more-about-licenses)。


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft マネージド デスクトップ サービス アカウント

一部のアカウント名は、サービスを管理するためにMicrosoft マネージド デスクトップアカウント名とMicrosoft マネージド デスクトップがあります。

**使用不可能**

ユーザーが作成したアカウント名と競合するアカウント名が少なくとも 1 つMicrosoft マネージド デスクトップ。 これらのアカウント名を除外するには、Microsoft アカウント担当者と一緒に作業します。 セキュリティ リスクを最小限に抑えるために、アカウント名を一般に一覧表示する必要があります。 


### <a name="security-administrator-roles"></a>セキュリティ管理者の役割

特定のセキュリティ ロールを持つユーザーには、それらの役割が Microsoft Defender for Endpoint に割り当てられている必要があります。

**アドバイザリ**

Azure AD組織でこれらの役割に割り当てられているユーザーがある場合は、それらの役割も Microsoft Defender for Endpoint に割り当てられている必要があります。 それ以外の場合、これらの役割を持つ管理者は管理ポータルにアクセスできません。

- セキュリティ オペレーター
- グローバル閲覧者

詳細については、「役割ベースの [アクセス制御の役割を作成および管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>セキュリティの既定値

セキュリティの既定値はAzure Active DirectoryデバイスMicrosoft マネージド デスクトップ管理できません。

**使用不可能**

セキュリティの既定値を有効にしています。 セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。 詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>セルフサービス のパスワードのリセット

セルフサービス パスワード リセット (SSPR) は、サービス アカウントを除くすべてのユーザー Microsoft マネージド デスクトップ有効Microsoft マネージド デスクトップできます。 詳細については、「チュートリアル: ユーザーが自分のアカウントのロックを解除したり、セルフサービス パスワードのリセットを使用してパスワードAzure Active Directory[を有効にする」を参照してください](/azure/active-directory/authentication/tutorial-enable-sspr)。

**アドバイザリ**

SSPR **Selected 設定** にユーザーが含Microsoft マネージド デスクトップサービス アカウントMicrosoft マネージド デスクトップしてください。 Microsoft マネージド デスクトップ SSPR が有効な場合、サービス アカウントは期待通り動作しません。  


### <a name="standard-user-role"></a>標準ユーザー ロール

グローバル管理者とデバイス管理者の Azure ADロールが割り当てられているユーザー以外に、Microsoft マネージド デスクトップユーザーはローカル管理者特権のない標準ユーザーです。 他のすべてのユーザーには、デバイスを起動するときに標準のユーザー ロールMicrosoft マネージド デスクトップされます。

**アドバイザリ**

Microsoft マネージド デスクトップユーザーは、登録後に自分のデバイスに対してローカルMicrosoft マネージド デスクトップ特権を持つ必要があります。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

[**特定のドメインに参加** している PC でのみ同期を許可する] の設定は、特定のドメインと競合Microsoft マネージド デスクトップ。 管理センターでOneDrive設定OneDrive[アクセスできます](https://admin.onedrive.com)。

**アドバイザリ**

[特定のドメインに参加している PC でのみ同期を許可 **する] 設定を使用** しています。 この設定は、この設定ではMicrosoft マネージド デスクトップ。 この設定を無効にし、代わりに条件付OneDriveポリシーを使用する方法を設定します。 ヘルプについては [、「条件付きアクセスの展開を計画する](/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。
