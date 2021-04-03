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
ms.openlocfilehash: 5a22996ce9e39dc16191ddddc6aa9393de557bbc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579412"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>準備評価ツールで見つかった問題を修正する

チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、アクションは必要ありません。        |
|アドバイザリ    | 登録とユーザーの最適なエクスペリエンスについては、ツールまたはこの記事の手順に従います。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を解決しない場合、登録は失敗します。* ツールまたはこの記事の手順に従って解決します。        |
|Error | 使用している Azure Active Directory (AD) ロールには、このチェックを実行するための十分なアクセス許可が付与されません。 |

> [!NOTE]
> このツールによって報告された結果は、設定を実行した特定の時点でのみ設定の状態を反映します。 後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備ができていない" 状態になる可能性があります。 Microsoft Managed Desktop 操作の問題を回避するには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

Intune の設定には、Microsoft Endpoint Manager 管理センターから [アクセスできます](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>自動パイロット展開プロファイル

Microsoft Managed Desktop デバイスを使用して割り当てられたグループまたは動的グループを対象とする既存の自動パイロット プロファイルを持つ必要があります。 Microsoft Managed Desktop では、Autopilot を使用して新しいデバイスをプロビジョニングします。

**使用不可能**

すべてのデバイスに割り当てられている自動パイロット プロファイルがあります。 手順については、「Windows Autopilot を使用して Intune に Windows デバイスを登録 [する」を参照してください](/mem/autopilot/enrollment-autopilot)。 Microsoft Managed Desktop の登録後、Autopilot ポリシーを設定して、モダン ワークプレース デバイス **-All** Azure ADグループを除外します。

**アドバイザリ**

Autopilot プロファイルが、Microsoft Managed Desktop デバイスを含AD割り当てられた、または動的な Azure クライアント グループを対象とするようにします。 手順については、「Windows Autopilot を使用して Intune に Windows デバイスを登録 [する」を参照してください](/mem/autopilot/enrollment-autopilot)。 Microsoft Managed Desktop の登録後、Autopilot プロファイルにモダン ワークプレース デバイス **-All** Azure ADグループをADします。


### <a name="certificate-connectors"></a>証明書コネクタ

Microsoft Managed Desktop に登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーは発生しません。 以下のアドバイザリの 1 つだけが状況に適用されますので、注意深く確認してください。

**アドバイザリ**

証明書コネクタはありません。 コネクタは必要ない可能性がありますが、Microsoft Managed Desktop デバイスのネットワーク接続に必要かどうかを評価する必要があります。 詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。

**アドバイザリ**

少なくとも 1 つの証明書コネクタにエラーがあります。 Microsoft Managed Desktop デバイスに証明書を提供するためにこのコネクタが必要な場合は、エラーを解決する必要があります。 詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。


**アドバイザリ**

証明書コネクタが 1 つ以上あるので、エラーは報告されません。 ただし、展開の準備として、Microsoft Managed Desktop デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。 詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。


### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーでは、Microsoft Managed Desktop が Intune と Azure の組織 (テナント) で Azure AD 組織 (テナント) を管理AD。

**使用不可能**

すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。 登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。 登録後、Microsoft Endpoint Manager で Microsoft Managed Desktop 条件付きアクセス ポリシーを確認できます。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**アドバイザリ**

条件付きアクセス ポリシーを使用すると、Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理しなくる可能性があります。 登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**エラー**

Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。 このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="device-compliance-policies"></a>デバイス コンプライアンス ポリシー

Azure 組織の Intune デバイス コンプライアンス ポリシー AD Microsoft Managed Desktop デバイスに影響を与える可能性があります。

**使用不可能**

すべてのユーザーを対象とする少なくとも 1 つのコンプライアンス ポリシーがあります。 Microsoft Managed Desktop には、Microsoft 管理デスクトップ デバイスを対象とするコンプライアンス ポリシーが含まれています。  ポリシーを変更して、Microsoft Managed Desktop ユーザーまたはデバイスAD含む特定の Azure クライアント グループを対象とします。 手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](/mem/intune/protect/create-compliance-policy)。

**アドバイザリ**

Microsoft Managed Desktop ユーザーを対象としないコンプライアンス ポリシーを確認します。 手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](/mem/intune/protect/create-compliance-policy)。



### <a name="device-configuration-profiles"></a>デバイス構成プロファイル

Azure 組織の Intune デバイス構成プロファイルAD、Microsoft Manage Desktop デバイスまたはユーザーをターゲットにしなける必要があります。

**使用不可能**

すべてのユーザー、すべてのデバイス、または両方を対象とする構成プロファイルが少なくとも 1 つあります。 Microsoft Managed Desktop デバイスを含AD特定の Azure サーバー グループをターゲットにするようにプロファイルをリセットします。 手順については [、「Microsoft Intune でカスタム設定を使用してプロファイルを作成する」を参照してください](/mem/intune/configuration/custom-settings-configure)。

**アドバイザリ**

Microsoft Managed Desktop デバイスまたはユーザーを含めなかった構成ポリシーが含まれるか確認します。 手順については [、「Microsoft Intune でカスタム設定を使用してプロファイルを作成する」を参照してください](/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>デバイスの種類の制限

Microsoft Managed Desktop デバイスは、Intune への登録を許可されている必要があります。

**使用不可能**

現在、少なくとも 1 つの登録制限ポリシーが Intune への Windows デバイスの登録を防止するように構成されています。 「Microsoft Managed Desktop ユーザーを対象とする登録制限ポリシーごとに登録制限を設定する」の手順に従い **、Windows (MDM)** 設定を [許可] に **変更します**。 [](/mem/intune/enrollment/enrollment-restrictions-set) ただし、個人所有の **Windows (MDM)** デバイスを [ブロック] に **設定できます**。 


### <a name="enrollment-status-page"></a>[登録の状態] ページ

現在、登録状態ページ (ESP) が有効になっています。 この機能の Microsoft Managed Desktop パブリック プレビューに参加する場合は、このアイテムを無視できます。 詳細については [、「First-run experience with Autopilot」および「登録状態ページ」を参照してください](../get-started/esp-first-run.md)。

**使用不可能**

ESP の既定のプロファイルが [アプリとプロファイルの構成の進行状況 **を表示する] に設定されています**。 この設定を無効にするか、「登録状態ページの設定」の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれるのを [確認します](/mem/intune/enrollment/windows-enrollment-status)。

**アドバイザリ**

[アプリとプロファイルの構成の進行状況を表示する] 設定を持つプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないか確認します。 詳細については、「登録状態 [ページの設定」を参照してください](/mem/intune/enrollment/windows-enrollment-status)。

### <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

Microsoft Store for Business を使用し、Microsoft Managed Desktop にポータル サイト アプリを展開し、ユーザーが Microsoft Project や Microsoft Visio などの一部のアプリを必要に応じてインストールできます (許可されている場合)。

**使用不可能**

Microsoft Store for Business は有効になっていないか、Intune と同期されません。 詳細については [、「Microsoft Store for Business](/mem/intune/apps/windows-store-for-business) から Microsoft Intune で購入したボリューム アプリを管理する方法」および「デバイスに Intune ポータル をインストールする方法」 [を参照してください](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多要素認証

多要素認証では、Microsoft Managed Desktop が Intune および Azure 組織 (テナント) で Azure AD 組織 (テナント) を管理AD。


**使用不可能**

すべてのユーザーに割り当てられている条件付きアクセスポリシーでは、必要に応じていくつかの多要素認証ポリシーが設定されています。 登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**アドバイザリ**

条件付きアクセス ポリシーで多要素認証が必要になります。Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理する妨げる可能性があります。 登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**エラー**

Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。 このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="powershell-scripts"></a>PowerShell スクリプト

Windows PowerShellは、Microsoft Managed Desktop デバイスを対象とする方法では割り当てできません。  

**アドバイザリ**

組織の Azure Windows PowerShellスクリプトAD Microsoft Manage Desktop デバイスまたはユーザーを対象とされていないことを確認します。 すべてのユーザー、すべてのデバイス、または両方を対象とする PowerShell スクリプトを割り当てない。 ポリシーを変更して、Microsoft Managed Desktop デバイスまたはユーザーを含AD特定の Azure AD グループを対象とする割り当てを使用します。 詳細については [、「Use PowerShell scripts on Windows 10 devices in Intune」を参照してください](/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>Region

地域は Microsoft Managed Desktop でサポートされている必要があります。

**使用不可能**

現在、Azure AD組織の地域は Microsoft Managed Desktop でサポートされていません。 詳細については [、「Microsoft Managed Desktop でサポートされている地域と言語」を参照してください](../service-description/regions-languages.md)。

**アドバイザリ**

Azure 組織が所属する 1 つ以上のADは、Microsoft Managed Desktop ではサポートされていません。 詳細については [、「Microsoft Managed Desktop でサポートされている地域と言語」を参照してください](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>セキュリティベースライン

セキュリティ ベースライン ポリシーは、Microsoft 管理デスクトップ デバイスを対象とすべきではありません。

**使用不可能**

すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティ 基準プロファイルがあります。 ポリシーを変更して、Microsoft 管理デスクトップ デバイスを含AD特定の Azure サーバー グループを対象とする割り当てを使用します。 手順については、「セキュリティ 基準 [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](/mem/intune/protect/security-baselines)。 登録時に、Microsoft Managed Desktop のすべてのデバイスに新しいセキュリティ 基準を適用します。 登録後、Microsoft Endpoint Manager の [構成ポリシー]領域で Microsoft Managed Desktop セキュリティ 基準ポリシーを確認できます。

**アドバイザリ**

Microsoft Managed Desktop デバイスを除外しているセキュリティ 基準ポリシーを必ず確認します。 手順については、「セキュリティ 基準 [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](/mem/intune/protect/security-baselines)。 登録時に、Microsoft Managed Desktop のすべてのデバイスに新しいセキュリティ 基準を適用します。 モダン **Workplace Devices -All** Azure AD グループは、Microsoft Managed Desktop に登録するときに作成する動的グループなので、登録後にこのグループを除外するために戻ってくる必要があります。 


### <a name="windows-apps"></a>Windows アプリ

Microsoft Managed Desktop ユーザーに必要なアプリを確認します。

**アドバイザリ**

Microsoft Managed Desktop ユーザーが持つアプリのインベントリを準備する必要があります。 これらのアプリは Intune によって展開する必要があるから、既存の Intune アプリの再利用を評価します。 ポータル サイトの使用を検討する (「デバイスに [Intune ポータル](../get-started/company-portal.md) サイトをインストールする」および「登録状態ページ (ESP)」を参照)、ユーザーにアプリを配布します。 詳細については [、「Apps in Microsoft Managed Desktop](apps.md) and First-run experience with [Autopilot and the Enrollment Status Page」を参照してください](../get-started/esp-first-run.md)。

Microsoft Endpoint Configuration Manager で Microsoft アカウント担当者にクエリを求め、Intune に移行する準備ができているアプリや調整が必要なアプリを特定できます。


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop では、Windows Hello for Business を有効にする必要があります。

**使用不可能**

Windows Hello for Business が無効になっています。 「Windows Hello for Business ポリシーの作成」 [の手順に従って有効にする](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**アドバイザリ**

Windows Hello for Business は設定されていない。 「ビジネス向け Windows Hello for Business ポリシーの作成 [」の手順に従って有効にしてください](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。


### <a name="windows-10-update-rings"></a>Windows 10 の更新プログラム リング

Intune の "Windows 10 更新プログラム リング" ポリシーは、Microsoft マネージ デスクトップ デバイスを対象としなく必要があります。

**使用不可能**

すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。 ポリシーを変更して、Microsoft 管理デスクトップ デバイスを含AD特定の Azure サーバー グループを対象とする割り当てを使用します。 手順については、「Intune で [Windows 10 ソフトウェア更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。

**アドバイザリ**

最新の Workplace Devices **-All Azure** ADグループを除外している更新リング ポリシーをADしてください。 これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、Microsoft **Managed Desktop** ユーザーを追加するモダン Workplace -All Azure AD グループ (または同等のグループ) も除外している更新リング ポリシーを確認してください。 手順については、「Intune で [Windows 10 ソフトウェア更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。 モダン ワークプレース デバイス **-All** および **Modern Workplace -All** Azure AD グループは、Microsoft Managed Desktop に登録するときに作成するグループなので、登録後にこのグループを除外するために戻ってくる必要があります。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

Azure Active Directory の設定には [、Azure](https://portal.azure.com)ポータルからアクセスできます。

### <a name="intune-enrollment"></a>Intune の登録

Azure 組織の Windows 10 AD Intune に自動的に登録できる必要があります。

**アドバイザリ**

MDM User スコープ **が [一部] または** [すべて] **に設定されているの** に **、None** は設定 **されていないか確認します**。 [一部] を **選択** した場合は、登録後に戻って、すべての Microsoft 管理デスクトップユーザーを対象とするグループまたは同等のグループの Modern **Workplace -All** Azure AD グループを選択します。  「Microsoft [Intune を使用して Windows デバイスの登録をセットアップする」を参照してください](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。


### <a name="ad-hoc-subscriptions"></a>アドホック サブスクリプション

("false" に設定されている場合) エンタープライズ状態ローミングが正常に動作しない可能性がある設定を確認する方法について説明します。

**アドバイザリ**

**AllowAdHocSubscriptions が True** に設定されている必要 **があります**。 それ以外の場合、エンタープライズ状態ローミングが機能しない可能性があります。 詳細については [、「Set-MsolCompanySettings」を参照してください](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

エンタープライズ状態ローミングを有効にする必要があります。

**アドバイザリ**

[すべて] または [選択したグループ] に対して **エンタープライズ状態ローミング****が有効になっているか確認** します。 詳細については [、「Enable Enterprise State Roaming in Azure Active Directory」を参照してください](/azure/active-directory/devices/enterprise-state-roaming-enable)。

### <a name="licenses"></a>ライセンス

Microsoft Managed Desktop を使用するには、多数のライセンスが必要です。

**準備ができていない**

Microsoft Managed Desktop を使用するために必要なすべてのライセンスを持っている必要はありません。 詳細については [、「Microsoft Managed Desktop テクノロジ」および「](../intro/technologies.md) ライセンス [の詳細」を参照してください](prerequisites.md#more-about-licenses)。


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop サービス アカウント

一部のアカウント名は、Microsoft Managed Desktop サービスを管理するために Microsoft Managed Desktop によって作成されたアカウント名と競合する可能性があります。

**使用不可能**

Microsoft Managed Desktop によって作成されたアカウント名と競合するアカウント名が少なくとも 1 つあります。 これらのアカウント名を除外するには、Microsoft アカウント担当者と一緒に作業します。 セキュリティ リスクを最小限に抑えるために、アカウント名を一般に一覧表示する必要があります。 


### <a name="security-administrator-roles"></a>セキュリティ管理者の役割

特定のセキュリティ ロールを持つユーザーには、それらの役割が Microsoft Defender for Endpoint に割り当てられている必要があります。

**アドバイザリ**

Azure AD組織でこれらの役割に割り当てられているユーザーがある場合は、それらの役割も Microsoft Defender for Endpoint に割り当てられている必要があります。 それ以外の場合、これらの役割を持つ管理者は管理ポータルにアクセスできません。

- セキュリティ オペレーター
- グローバル閲覧者

詳細については、「役割ベースの [アクセス制御の役割を作成および管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>セキュリティの既定値

Azure Active Directory のセキュリティの既定値では、Microsoft Managed Desktop がデバイスを管理できません。

**使用不可能**

セキュリティの既定値を有効にしています。 セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。 詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>セルフサービス のパスワードのリセット

セルフサービス パスワードリセット (SSPR) は、Microsoft Managed Desktop サービス アカウントを除くすべての Microsoft 管理デスクトップ ユーザーに対して有効にできます。 詳細については、「チュートリアル: ユーザーが自分のアカウントのロックを解除したり、Azure Active Directory セルフサービス のパスワードリセットを使用してパスワードをリセットしたりするようにする」 [を参照してください](/azure/active-directory/authentication/tutorial-enable-sspr)。

**アドバイザリ**

SSPR **Selected 設定** に Microsoft Managed Desktop ユーザーが含まれていますが、Microsoft Managed Desktop サービス アカウントは除外します。 SSPR が有効になっている場合、Microsoft Managed Desktop サービス アカウントは期待通り動作しません。  


### <a name="standard-user-role"></a>標準ユーザー ロール

グローバル管理者とデバイス管理者の Azure ADロールに割り当てられているユーザー以外は、Microsoft Managed Desktop ユーザーは、ローカル管理者特権のない標準ユーザーです。 Microsoft Managed Desktop デバイスを起動すると、他のすべてのユーザーに標準のユーザー ロールが割り当てられます。

**アドバイザリ**

Microsoft Managed Desktop ユーザーは、登録後に Microsoft Managed Desktop デバイスに対するローカル管理者特権を持つ必要があります。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

[ **特定のドメインに参加** している PC でのみ同期を許可する] 設定は、Microsoft マネージ デスクトップと競合します。 OneDrive 管理センターで OneDrive の設定に [アクセスできます](https://admin.onedrive.com)。

**アドバイザリ**

[特定のドメインに参加している PC でのみ同期を許可 **する] 設定を使用** しています。 この設定は、Microsoft Managed Desktop では機能しません。 この設定を無効にし、代わりに条件付きアクセス ポリシーを使用する OneDrive を設定します。 ヘルプについては [、「条件付きアクセスの展開を計画する](/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。