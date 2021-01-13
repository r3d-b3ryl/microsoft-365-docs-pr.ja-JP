---
title: 準備評価ツールで見つかった問題を修正する
description: ツールが見つけた問題ごとに実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ada6bb8ef66e3414a375a151b45d4871e306e825
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841073"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>準備評価ツールで見つかった問題を修正する

チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、何もする必要はありません。        |
|アドバイザリ    | 登録とユーザーの最適なエクスペリエンスを得る場合は、ツールまたはこの記事の手順に従ってください。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を解決しない場合、登録は失敗します。* ツールまたはこの記事の手順に従って解決します。        |
|Error | 使用している Azure Active Director (AD) ロールに、このチェックを実行するための十分なアクセス許可が付与されません。 |

> [!NOTE]
> このツールによって報告される結果には、設定を実行した特定の時点での設定の状態だけが反映されます。 後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備ができていない" 状態になる可能性があります。 Microsoft マネージド デスクトップの操作で問題が発生しないようにするには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

Intune の設定には、Microsoft Endpoint Manager 管理センターから [アクセスできます](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>Autopilot 展開プロファイル

Microsoft マネージド デスクトップで使用される割り当て済みグループまたは動的グループを対象とする既存の Autopilot プロファイルは使用できません。 Microsoft マネージド デスクトップでは、Autopilot を使用して新しいデバイスをプロビジョニングします。

**使用不可能**

すべてのデバイスに割り当てられている Autopilot プロファイルがある。 手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。 Microsoft マネージド デスクトップの登録後、Autopilot ポリシーを設定して **、Modern Workplace Devices -All** Azure AD グループを除外します。

**アドバイザリ**

Autopilot プロファイルが、登録時に作成される Microsoft マネージド デスクトップ デバイスを含む、割り当て済みまたは動的な Azure AD グループを対象とするようにします。 手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。 Microsoft マネージド デスクトップの登録後、Autopilot ポリシーを設定して **、Modern Workplace Devices -All** Azure AD グループを除外します。


### <a name="certificate-connectors"></a>証明書コネクタ

Microsoft マネージド デスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーは発生しません。 次の勧告の 1 つだけが状況に適用されます。そのため、慎重に確認してください。

**アドバイザリ**

証明書コネクタは存在しない。 コネクタは必要ない可能性がありますが、Microsoft マネージド デスクトップ デバイスへのネットワーク接続に必要かどうかを評価する必要があります。 詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。

**アドバイザリ**

少なくとも 1 つの証明書コネクタにエラーがあります。 Microsoft マネージド デスクトップ デバイスへの接続にこのコネクタが必要な場合は、エラーを解決する必要があります。 詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。


**アドバイザリ**

証明書コネクタが 1 つ以上あるので、エラーは報告されません。 ただし、Microsoft マネージド デスクトップ デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。 詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。


### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

Azure 組織の条件付きアクセス ポリシー AD、Microsoft Manage Desktop ユーザーを対象にしなけずにしてください。

**使用不可能**

すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。 登録時に作成される Microsoft マネージド デスクトップ サービス アカウントの Azure AD グループを含む特定の Azure AD グループをターゲットにするようにポリシーをリセットします。 手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。

**アドバイザリ**

モダン Workplace Service アカウント **Azure** グループを除外した条件付きアクセス ポリシー ADしてください。 手順については、「条件付きアクセス [の調整」を参照してください](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。 モダン **Workplace Service アカウント** Azure ADグループは、登録時にサービス用に作成される動的なグループです。 登録後に、このグループを除外するために戻ってくる必要があります。 これらのサービス アカウントの詳細については、「標準の運用手順 [」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**エラー**

Intune 管理者ロールには、このチェックのための十分なアクセス許可が付与されません。 このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="device-compliance-policies"></a>デバイス コンプライアンス ポリシー

Azure 組織の Intune デバイス コンプライアンス ポリシー AD Microsoft マネージド デスクトップ ユーザーを対象にしなけずにしてください。

**使用不可能**

すべてのユーザーを対象とするコンプライアンス ポリシーが少なくとも 1 つあります。 Microsoft マネージド デスクトップ ユーザーを含AD特定の Azure AD グループをターゲットにするようにポリシーをリセットします。 手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。

**アドバイザリ**

Microsoft マネージド デスクトップ ユーザーが含まれるコンプライアンス ポリシーを含めなかったか確認します。 手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。



### <a name="device-configuration-policies"></a>デバイス構成ポリシー

Azure 組織の Intune デバイス構成ポリシー AD Microsoft Manage Desktop デバイスまたはユーザーを対象にしなけずにしてください。

**使用不可能**

少なくとも 1 つの構成ポリシーで、すべてのユーザー、すべてのデバイス、または両方を対象とします。 Microsoft マネージド デスクトップ デバイスを含AD特定の Azure AD グループをターゲットにするようにポリシーをリセットします。 手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。

**アドバイザリ**

Microsoft マネージド デスクトップ デバイスまたはユーザーが含まれるコンプライアンス ポリシーを含めなかったか確認します。 手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>デバイスの種類の制限

Microsoft マネージド デスクトップ デバイスは、Intune への登録を許可する必要があります。

**使用不可能**

「登録の制限 [を設定する」の手順に従って、](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 設定を [許可] に **変更します**。


### <a name="enrollment-status-page"></a>[登録の状態] ページ

現在、登録ステータス ページ (ESP) が有効になっています。 この機能のパブリック プレビューに参加している場合は、この項目を無視できます。 詳細については [、「Autopilot の初回実行エクスペリエンス](../get-started/esp-first-run.md)と [登録状態] ページ」を参照してください。

**使用不可能**

ESP の既定のプロファイルは、[アプリとプロファイルの構成 **の進行状況を表示する] に設定されています**。 この設定を無効にするか、「登録状態の設定」ページの手順に従って、Azure AD グループへの割り当てに Microsoft マネージド デスクトップ デバイスが含まれるのを確認 [します](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。

**アドバイザリ**

[アプリとプロファイルの構成の進行状況の表示] 設定を持つプロファイルが、Microsoft マネージド デスクトップ デバイスを含む Azure AD グループに割り当てられていないか確認します。 詳細については、「登録状態 [ページのセットアップ」を参照してください](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。

### <a name="intune-enrollment"></a>Intune 登録

Azure 組織の Windows 10 デバイスAD Intune に自動的に登録する必要があります。

**アドバイザリ**

MDM ユーザー スコープが [なし] ではなく [ **一部]** または [ **すべて]** に設定されている必要 **があります**。 [一部] **を選択** した場合は、登録後に戻って、 **モダン Workplace -All** Azure AD グループを選択 **します**。


### <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

ビジネス向け Microsoft Store を使用して、ポータル サイトをダウンロードして、Microsoft Project や Microsoft Visio などの一部のアプリを展開できます。

**使用不可能**

ビジネス向け Microsoft Store が有効になっていないか、Intune と同期されていない。 詳細については、ビジネス向け Microsoft Store からボリューム購入したアプリを [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) で管理し、デバイスに Intune ポータル サイトをインストールする方法を [参照してください](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多要素認証

多要素認証を Microsoft マネージド デスクトップ サービス アカウントに誤って適用しないようにする必要があります。


**使用不可能**

すべてのユーザーに割り当てられている条件付きアクセス ポリシーに対して、いくつかの多要素認証 (MFA) ポリシーが "必須" に設定されている。 Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。 詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。

**アドバイザリ**

MFA を必要とする条件付きアクセス ポリシーで **、Modern Workplace -All** Azure ADしてください。 詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。 **Modern Workplace -All** Azure AD グループは、Microsoft マネージド デスクトップに登録するときに作成される動的なグループです。そのため、登録後にこのグループを除外するために戻ってくる必要があります。

**エラー**

Intune 管理者ロールには、このチェックのための十分なアクセス許可が付与されません。 このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="powershell-scripts"></a>PowerShell スクリプト

Windows PowerShellは、Microsoft マネージド デスクトップ デバイスをターゲットとする方法では割り当てできません。  

**アドバイザリ**

Azure Windows PowerShellのスクリプトが、Microsoft ADデスクトップ デバイスやユーザーを対象としなにされていないことを確認します。 PowerShell スクリプトを、すべてのユーザー、すべてのデバイス、または両方を対象に割り当てない。 Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。 詳細については、「Intune で [Windows 10 デバイスで PowerShell](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)スクリプトを使用する」を参照してください。

### <a name="region"></a>Region

お客様の地域は、Microsoft マネージド デスクトップでサポートされている必要があります。

**使用不可能**

Azure AD組織の地域は、Microsoft マネージド デスクトップでは現在サポートされていません。 詳細については [、Microsoft マネージド デスクトップでサポートされている地域と言語を参照してください](../service-description/regions-languages.md)。

**アドバイザリ**

組織の Azure ADがある国の 1 つ以上は、Microsoft マネージド デスクトップではサポートされていません。 詳細については [、Microsoft マネージド デスクトップでサポートされている地域と言語を参照してください](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>セキュリティ基本計画

セキュリティ基本ポリシーは、Microsoft マネージド デスクトップ デバイスを対象としなにしろ。

**使用不可能**

すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティベースライン プロファイルがあります。 Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。 手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。

**アドバイザリ**

Microsoft マネージド デスクトップ デバイスを除外したセキュリティ基本ポリシーを確認します。 手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。 **Modern Workplace Devices -All** Azure AD グループは、Microsoft マネージド デスクトップに登録するときに作成される動的なグループです。そのため、登録後にこのグループを除外するために戻ってくる必要があります。


### <a name="windows-apps"></a>Windows アプリ

Microsoft マネージド デスクトップ ユーザーに必要なアプリを確認します。

**アドバイザリ**

Microsoft マネージド デスクトップ ユーザーが持つアプリのインベントリを準備する必要があります。 これらのアプリは Intune で展開する必要があるから、既存の Intune アプリの再利用を評価します。 ポータル サイトの使用を検討します (「デバイスへの [Intune ポータル](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) サイトのインストールと登録状態ページ (ESP)」を参照して、ユーザーにアプリを配布します。 詳細については [、「Microsoft マネージド](apps.md) デスクトップのアプリ」と [「Autopilot](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)による初回実行時エクスペリエンス」および「登録状態ページ」を参照してください。

Microsoft Endpoint Configuration Manager で Microsoft アカウント担当者にクエリを求め、Intune に移行する準備ができているアプリや調整が必要なアプリを特定できます。


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft マネージド デスクトップでは、Windows Hello for Business を有効にする必要があります。

**使用不可能**

Windows Hello for Business は無効です。 「Windows Hello for Business ポリシーを作成する」の [手順に従って有効にする](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**アドバイザリ**

Windows Hello for Business がセットアップされていない。 「Windows Hello for Business ポリシーを作成する」の手順 [に従って有効にしてください](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。


### <a name="windows-10-update-rings"></a>Windows 10 の更新リング

Intune の "Windows 10 更新リング" ポリシーは、Microsoft マネージド デスクトップ デバイスをターゲットにしなけずにしてください。

**使用不可能**

すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。 Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。 手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。

**アドバイザリ**

モダン Workplace **Devices -All** Azure AD グループから除外した更新リング ポリシーを確認します。 これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、Microsoft マネージド デスクトップ ユーザーを含む **Modern Workplace -All** Azure AD グループも除外している更新リング ポリシーを必ず除外してください。 手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。 Modern **Workplace Devices -All** グループと **Modern Workplace -All** Azure AD グループの両方に、Microsoft マネージド デスクトップに登録するときに作成したグループが割り当てられるので、登録後にこのグループを除外するために戻ってくる必要があります。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

Azure Portal で Azure Active Directory の設定に [アクセスできます](https://portal.azure.com)。

### <a name="ad-hoc-subscriptions"></a>アドホック サブスクリプション

("false" に設定されている場合)、エンタープライズ状態ローミングが正しく動作しない可能性がある設定を確認する方法について説明します。

**アドバイザリ**

**AllowAdHocSubscriptions** が **True** に設定されています。 それ以外の場合、Enterprise State Roaming が機能しない可能性があります。 詳細については [、「Set-MsolCompanySettings」を参照してください](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming を有効にする必要があります。

**アドバイザリ**

[すべて] または [選択したグループ] に対して Enterprise State Roaming が有効 **になっているか確認** します。 詳細については [、「Azure Active Directory でエンタープライズ状態ローミングを有効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。

### <a name="licenses"></a>ライセンス

Microsoft マネージド デスクトップを使用するには、多数のライセンスが必要です。

**準備ができていない**

Microsoft マネージド デスクトップを使用するために必要なライセンスの一部を持っている必要はありません。 詳細については [、Microsoft マネージド デスクトップテクノロジとライセンス](../intro/technologies.md) の [詳細を参照してください](prerequisites.md#more-about-licenses)。


### <a name="security-account-names"></a>セキュリティ アカウント名

一部のセキュリティ アカウント名は、Microsoft マネージド デスクトップで作成された名前と競合する可能性があります。

**使用不可能**

Microsoft マネージド デスクトップで作成されたアカウント名と競合するアカウント名が少なくとも 1 つあります。 Microsoft アカウント担当者と一緒に、これらのアカウント名を除外します。


### <a name="security-administrator-roles"></a>セキュリティ管理者ロール

特定のセキュリティ ロールを持つユーザーには、それらの役割が Microsoft Defender for Endpoint に割り当てられている必要があります。

**アドバイザリ**

Azure AD 組織でこれらの役割に割り当てられているユーザーがある場合は、それらのユーザーに、エンドポイント用 Microsoft Defender でこれらの役割も割り当てられている必要があります。 そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできません。

- セキュリティ オペレーター
- グローバル閲覧者

詳細については、「役割ベースのアクセス [制御の役割を作成および管理する」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>セキュリティの既定値

Azure Active Directory のセキュリティの既定値により、Microsoft マネージド デスクトップでデバイスを管理できません。

**使用不可能**

セキュリティの既定値を有効にしています。 セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。 詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>セルフサービスによるパスワードのリセット

セルフサービスによるパスワードリセット (SSPR) は、Microsoft マネージド デスクトップ サービス アカウントを除くすべての Microsoft マネージド デスクトップ ユーザーに対して有効にする必要があります。 詳細については、「チュートリアル: Azure Active Directory のセルフサービス によるパスワードのリセットを使用して、ユーザーが自分のアカウントのロックを解除したり、パスワード [をリセットしたりできる」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。

**アドバイザリ**

[SSPR の選択 **]** 設定に Microsoft マネージド デスクトップ デバイスが含まれていますが、Microsoft マネージド デスクトップ サービス アカウントは除外します。 SSPR が有効な場合、Microsoft マネージド デスクトップ サービス アカウントは期待通り動作しません。  


### <a name="standard-user-role"></a>標準ユーザー ロール

グローバル管理者とデバイス管理者の Azure AD ロールが割り当てられているユーザー以外に、Microsoft マネージド デスクトップ ユーザーはローカル管理者特権のない標準ユーザーです。 他のすべてのユーザーには、Microsoft マネージド デスクトップ デバイスの起動時に標準のユーザー ロールが割り当てられます。

**アドバイザリ**

Microsoft マネージド デスクトップ ユーザーは、登録後に Microsoft マネージド デスクトップ デバイスに対するローカル管理者特権を持つ必要があります。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

特定 **のドメインに参加している PC** でのみ同期を許可する設定は、Microsoft マネージド デスクトップと競合します。 OneDrive 管理センターで OneDrive の設定に [アクセスできます](https://admin.onedrive.com)。

**アドバイザリ**

特定のドメインに参加している PC でのみ同期を許可 **する設定を使用** している。 この設定は、Microsoft マネージド デスクトップでは機能しません。 この設定を無効にし、代わりに条件付きアクセス ポリシーを使用する OneDrive を設定します。 ヘルプ [については、「条件付きアクセスの展開を計画する](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。

