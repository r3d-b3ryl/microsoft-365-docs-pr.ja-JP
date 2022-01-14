---
title: 準備評価ツールで見つかった問題を修正する
description: ツールで検出された各問題に対して実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 89815cbfa1e2488e45280fe57da0c69e15aafa69
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034739"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>準備評価ツールで見つかった問題を修正する

チェックごとに、ツールは 4 つの考えられる結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に操作は必要ありません。        |
|アドバイザリ    | 登録とユーザーにとっての最高のエクスペリエンスを得るには、ツールまたはこの記事の手順に従ってください。 登録を完了することは *できます* が、最初のデバイスを展開する前にこれらの問題を修正する必要があります。        |
|使用不可能 | これらの問題を修正しないと、*登録は失敗します*。 ツールまたはこの記事の手順に従って解決します。        |
|Error | ご使用中の Azure Active Directory (AD) のロールには、このチェックを実行するための十分なアクセス許可がありません。 |

> [!NOTE]
> このツールによって報告された結果には、実行した特定の時点での設定の状態のみが反映されます。 後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合は、"準備完了" だったアイテムが "準備ができていません" になる可能性があります。 Microsoft Managed Desktop 操作に関する問題を回避するには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

Intune には Microsoft エンドポイント マネージャー[管理センター](https://endpoint.microsoft.com)を使用してアクセスできます。

### <a name="autopilot-deployment-profile"></a>Autopilot 展開プロファイル

割り当てられたグループまたは動的グループを対象とする既存の Autopilot プロファイルを Microsoft Managed Desiktop デバイスと一緒に持たせるべきではありません。 Microsoft Managed Desktop では、Autopilot を使用して新しいデバイスをプロビジョニングします。 既存の Autopilot 展開プロファイルがある場合は、Autopilot 用のマネージド デスクトップ準備度テストを成功させるために "対象となるすべてのデバイスを Autopilot に変換する" を "いいえ" に設定する必要があります。

**使用不可能**

すべてのデバイスに割り当てられている Autopilot プロファイルがあります。 手順については「[Windows Autopilot</a>を使用して Intune で Windows デバイスを登録する](/mem/autopilot/enrollment-autopilot)」を参照してください。 Microsoft Managed Desktop 登録後、Autopilot ポリシーを設定して、**Modern Workplace Devices - All** Azure AD グループを除外します。

**アドバイザリ**

Autopilot プロファイルが、Microsoft Managed Desktop デバイスを含まない割り当て済みの Azure AD グループまたは動的な Azure AD グループを対象としていることを確認します。 手順については「[Windows Autopilot</a>を使用して Intune で Windows デバイスを登録する](/mem/autopilot/enrollment-autopilot)」を参照してください。 Microsoft Managed Desktop 登録後、Autopilot プロファイルを設定して **Modern Workplace Devices -All** Azure AD グループを除外します。


### <a name="certificate-connectors"></a>証明書コネクタ

Microsoft Managed Desktop に登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーは発生しないはずです。 次のいずれかのアドバイザリのみが状況に適用されるため、慎重に確認してください。

**アドバイザリ**

証明書コネクタが存在しません。 コネクタは必要ないようですが、Microsoft Managed Desktop デバイスでネットワーク接続に必要なコネクタがあるかどうかを評価する必要があります。 詳細については、「[Microsoft Managed Desktop の証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)」を参照してください。

**アドバイザリ**

少なくとも 1 つの証明書コネクタにエラーがあります。 Microsoft Managed Desltop デバイスに証明書を提供するためにこのコネクタが必要な場合は、エラーを解決する必要があります。 詳細については、「[Microsoft Managed Desktop の証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)」を参照してください。


**アドバイザリ**

証明書コネクタが少なくとも 1 つ存在し、エラーは報告されません。 ただし、展開の準備として、Microsoft Managed Desktop デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。 詳細については、「[Microsoft Managed Desktop の証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)」を参照してください。

### <a name="company-portal"></a>ポータル サイト

Microsoft Managed Desktop では、IT 管理者が Microsoft Managed Desktop デバイスを使用してユーザーの Intune ポータル サイトをインストールする必要があります。 

**使用不可能**

ユーザー用のポータル サイトがインストールされていません。 ポータル サイトを購入し、Intune とビジネス向け Microsoft Store 間の同期を強制します。 詳細については、「[デバイスに Intune ポータル サイトをインストールする](../get-started/company-portal.md)」を参照してください。


### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーを使用して、Microsoft Managed Desktop が Intune とAzure AD でAzure AD組織 (テナント) を管理できないようにすることはできません。

**使用不可能**

すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つ存在します。 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。 登録後、Microsoft エンドポイント マネージャーで Microsoft Managed Desktop の条件付きアクセス ポリシーを確認できます。 これらのサービス アカウントの詳細については、「[標準の操作手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。

**アドバイザリ**

Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理できなくなる可能性がある条件付きアクセス ポリシーがあります。 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。 これらのサービス アカウントの詳細については、「[標準の操作手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。

**エラー**

Intune 管理者ロールには、このチェックのための十分なアクセス許可がありません。 また、このチェックを実行するには、次の Azure AD ロールのいずれかが割り当てられている必要があります:

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="device-compliance-policies"></a>デバイス コンプライアンス ポリシー

Azure AD 組織内の Intune デバイス コンプライアンス ポリシーは、Microsoft Managed Desktop デバイスに影響を与える可能性があります。

**アドバイザリ**

すべてのユーザーを適用するコンプライアンス ポリシーが少なくとも 1 つ存在します。 Microsoft Managed Desktop には、Microsoft Managed Desktop デバイスに適用されるコンプライアンス ポリシーも含まれています。 Microsoft Managed Desktop デバイスに適用される組織によって作成されたすべてのコンプライアンス ポリシーを確認して、競合がないことを確認します。 手順については、「[Microsoft Intune でコンプライアンス ポリシーを作成する](/mem/intune/protect/create-compliance-policy)」を参照してください。



### <a name="device-configuration-profiles"></a>デバイスの構成プロファイル

Azure AD 組織内の Intune デバイス構成プロファイルは、Microsoft Manage Desktop デバイスまたはユーザーを対象にすることはできません。

**使用不可能**

すべてのユーザー、すべてのデバイス、またはその両方に適用される構成プロファイルが少なくとも 1 つ存在します。 プロファイルをリセットして、Microsoft Managed Desktopデバイスを含まない特定のAzure AD グループに適用します。 手順については、「[Microsoft Intune でカスタム設定を使用してプロファイルを作成する](/mem/intune/configuration/custom-settings-configure)」を参照してください。

**アドバイザリ**

構成ポリシーに Microsoft Managed Desktop デバイスやユーザーが含まれていないことを確認します。 手順については、「[Microsoft Intune でカスタム設定を使用してプロファイルを作成する](/mem/intune/configuration/custom-settings-configure)」を参照してください。



### <a name="device-type-restrictions"></a>デバイスの種類の制限

Microsoft Managed Desktop デバイスには Intune への登録を許可する必要があります。

**使用不可能**

Windows デバイスが Intune に登録されないように構成された登録制限ポリシーが、現在少なくとも 1 つあります。 [登録制限の設定](/mem/intune/enrollment/enrollment-restrictions-set)の手順に従って、Microsoft Managed Desktop ユーザーを対象とする各登録制限ポリシーを設定し、**Windows (MDM)** 設定を **[許可]** に変更します。 ただし、**個人所有の** **Windows (MDM)** デバイスを **[禁止]** に設定できます。 


### <a name="enrollment-status-page"></a>登録ステータス ページ

現在、登録ステータス ページ (ESP) が有効になっています。 この機能の Microsoft Managed Desktop パブリック プレビューに参加する場合は、この項目を無視できます。 詳細については、「[Autopilot と登録状態ページでの最初の実行エクスペリエンス](../get-started/esp-first-run.md)」を参照してください。

**使用不可能**

ESP の既定のプロファイルが **[アプリケーションとプロファイルの構成の進行状況を表示]** に設定されています。 この設定を無効にするか、「[登録ステータス ページの設定](/mem/intune/enrollment/windows-enrollment-status)」の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれていないことを確認します。

**アドバイザリ**

**[アプリケーションとプロファイル構成の進行状況の表示]** 設定のあるプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないことを確認します。 詳細については「[登録状態ページの設定](/mem/intune/enrollment/windows-enrollment-status)」を参照してください。

### <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

ビジネス向け Microsoft Store を使用し、Microsoft Managed Desktop にポータル サイト アプリを展開して、ユーザーが必要に応じて Microsoft Project や Microsoft Visio などの一部のアプリ (許可されている場合) をインストールできるようにします。

**使用不可能**

ビジネス向け Microsoft Store が有効になっていないか、Intune と同期されていません。 詳細については、「[Microsoft Intune を使ってビジネス向け Microsoft Store から大量購入したアプリの管理方法](/mem/intune/apps/windows-store-for-business)」 と「[デバイスに Intune ポータル サイト](../get-started/company-portal.md)」を参照してください。

### <a name="multifactor-authentication"></a>多要素認証

多要素認証では、Microsoft Managed Desktop が Intune とAzure AD で Azure AD 組織 (テナント) を管理できないようにすることはできません。


**使用不可能**

すべてのユーザーに割り当てられている条件付きアクセス ポリシーに対して、**「必要]** として設定された多要素認証ポリシーがいくつかあります。 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。 これらのサービス アカウントの詳細については、「[標準の操作手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。

**アドバイザリ**

Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理できなくなる可能性がある条件付きアクセス ポリシーで多要素認証が必要になっています。 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。 これらのサービス アカウントの詳細については、「[標準の操作手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。

**エラー**

Intune 管理者ロールには、このチェックのための十分なアクセス許可がありません。 また、このチェックを実行するには、次の Azure AD ロールのいずれかが割り当てられている必要があります:

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="powershell-scripts"></a>PowerShell スクリプト

Windows PowerShell スクリプトは、Microsoft Managed Desktop デバイスを対象とするようには割り当てられません。  

**アドバイザリ**

Azure AD 組織内の Windows PowerShell スクリプトが Microsoft Manage Desktop デバイスまたはユーザーを対象としていないことを確認します。 すべてのユーザー、すべてのデバイス、またはその両方を対象とする PowerShell スクリプトを割り当てないでください。 Microsoft Managed Desktop デバイスやユーザーを含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 詳細については、「[Intune の Windows 10 デバイスで PowerShell スクリプトを使用する](/mem/intune/apps/intune-management-extension)」を参照してください。

### <a name="region"></a>地域

Microsoft Managed Desktop でお客様のリージョンがサポートされている必要があります。

**使用不可能**

お客様の Azure AD 組織リージョンは、現在 Microsoft Managed Desktop でサポートされていません。 詳細については、「[Microsoft Managed Desktop のサポートされている地域と言語](../service-description/regions-languages.md)」を参照してください。

**アドバイザリ**

お客様の Azure AD 組織が配置されている 1 つ以上の国は、Microsoft Managed Desktop でサポートされていません。 詳細については、「[Microsoft Managed Desktop のサポートされている地域と言語](../service-description/regions-languages.md)」を参照してください。


### <a name="security-baselines"></a>セキュリティ基本計画

セキュリティ ベースライン ポリシーは、どのMicrosoft Managed Desktop デバイスも対象にしないでください。

**使用不可能**

すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ ベースライン プロファイルがあります。 Microsoft Managed Desktop デバイスを含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 手順については、「[セキュリティ ベースラインを使用して Intune で Windows 10 デバイスを構成する](/mem/intune/protect/security-baselines)」をご覧ください。 登録中に、すべての Microsoft Managed Desktop デバイスに新しいセキュリティ ベースラインを適用します。 登録後、Microsoft エンドポイント マネージャー の **[構成ポリシー領域]** で Microsoft Managed Desktop セキュリティ ベースライン ポリシーを確認できます。

**アドバイザリ**

すべてのセキュリティ ベースライン ポリシーから Microsoft Managed Desktop デバイスが除外されていることを確認します。 手順については、「[セキュリティ ベースラインを使用して Intune で Windows 10 デバイスを構成する](/mem/intune/protect/security-baselines)」をご覧ください。 登録中に、すべての Microsoft Managed Desktop デバイスに新しいセキュリティ ベースラインを適用します。 **Modern Workplace Devices -All** Azure AD グループは、Microsoft Managed Desktop 登録時に作成される動的グループであるため、登録後に戻りこのグループを除外する必要があります。 

### <a name="unlicensed-admins"></a>ライセンスのない管理者

お客様の Azure AD 組織とやり取りするときに "アクセス許可の不足" のエラーを回避するためにこの設定を有効にする必要があります。 

**使用不可能**

**[ライセンスのない管理者へのアクセスを許可する**] を有効にする必要があります。 手順については、「[ゲスト アカウントの前提条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)」を参照してください。

### <a name="windows-apps"></a>Windows アプリ

Microsoft Managed Desktop ユーザーに必要なアプリを確認します。

**アドバイザリ**

Microsoft Managed Desktop ユーザーが持つアプリのインベントリを準備する必要があります。 これらのアプリは Intune で展開する必要があるため、既存の Intune アプリの再利用を評価します。 ポータル サイト ([デバイスに Intune ポータル サイトをインストールする](../get-started/company-portal.md)) と登録状態ページ (ESP) を使用してユーザーにアプリを配布することを検討してください。 詳細については、「[Microsoft Managed Desktop のアプリ](apps.md)」および「[Autopilot と登録状態ページを使った最初の実行エクスペリエンス](../get-started/esp-first-run.md)」を参照してください。

Microsoft Endpoint Configuration Manager でMicrosoft アカウント担当者に問い合わせて、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop には、Windows Hello for Business を有効にする必要があります。

**アドバイザリ**

Windows Hello for Business が無効になっているか、設定されていません。 「[Windows Hello for Business ポリシーの作成](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って有効にします。


### <a name="windows-10-update-rings"></a>Windows 10 更新リング

Intune の "Windows 10更新リング" のポリシーは、Microsoft Managed Desktop デバイスをターゲットにすることはできません。

**使用不可能**

すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。 Microsoft Managed Desktop デバイスを含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 手順については、「[Intune で Windows 10 ソフトウェア更新プログラムを管理する](/mem/intune/protect/windows-update-for-business-configure)」を参照してください。

**アドバイザリ**

**Modern Workplace Devices -All** Azure AD グループを除外した更新リング ポリシーがあることを確認します。 これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、あらゆるリング ポリシーから Microsoft Managed Desktop ユーザーを追加した **Modern Workplace -All** Azure AD グループ (または同等のグループ) が除外されていることを確認してください。 手順については、「[Intune で Windows 10 ソフトウェア更新プログラムを管理する](/mem/intune/protect/windows-update-for-business-configure)」を参照してください。 **Modern Workplace Devices -All** と **Modern Workplace -All** Azure AD グループはどちらも、Microsoft Managed Desktop に登録するときに作成されるグループであるため、登録後に戻りこのグループを除外する必要があります。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

[Azure portal](https://portal.azure.com) で Azure Active Directory 設定にアクセスできます。

### <a name="intune-enrollment"></a>Intune の登録

Azure AD 組織内の Windows 10 デバイスは、Intune に自動的に登録できる必要があります。

**アドバイザリ**

**MDM ユーザー スコープ** が、**[なし]** ではなく、**[一部]** または **[すべて]** に設定されていることを確認します。 **[一部]** を選択した場合、登録後に戻り、Microsoft Managed Desktop ユーザー全員を対象にしている **グループ** の **Modern Workplace -All** Azure AD グループ、またはすべての Microsoft Managed Desktop ユーザーを対象とする同等のグループを選択します。  「[Microsoft Intune を使用して Windows デバイスの登録を設定する](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)」を参照してください。

### <a name="ad-hoc-subscriptions"></a>アドホック サブスクリプション

("false" に設定されている場合) Enterprise State Roaming が正しく機能しない可能性がある設定を確認する方法をアドバイスします。

**アドバイザリ**

**AllowAdHocSubscriptions** が **True** に設定されていることを確認します。 そうしないと、Enterprise State Roaming が機能しない可能性があります。 詳細については、[Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) を参照してください。


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming を有効にする必要があります。

**アドバイザリ**

Enterprise State Roaming が **[すべての]** または **[選択された]** グループに対して有効になっていることを確認します。 詳細については、「[Azure Active Directory で Enterprise State Roaming を有効にする](/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。

### <a name="guest-invitation-settings"></a>ゲスト招待の設定

Microsoft Managed Desktop ではゲスト招待の設定を調整することを推奨しています。というのは、規定の設定では、ディレクトリ内のすべてのユーザーとゲストが、ゲストを招待できるようになっているからです。

**アドバイザリ**

**[メンバー ユーザーおよび特定の管理者の役割に割り当てられたユーザーが、メンバーのアクセス許可を持つゲストを含むゲスト ユーザーを招待できる]** が有効にされている必要があります。 手順については、「[ゲスト アカウントの前提条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)」を参照してください。

### <a name="guest-user-access"></a>ゲスト ユーザー アクセス

Microsoft Managed Desktop ではゲスト ユーザー アクセスを調整することを推奨しています。というのは、規定の設定では、ディレクトリ内のすべてのゲスト ユーザーが、メンバーと同じアクセス権を持つことを許されているからです。

**アドバイザリ**

**[ゲスト ユーザーは、ディレクトリ オブジェクトのプロパティとメンバーシップへのアクセスが制限されている]** を有効にする必要があります。 手順については、「[ゲスト アカウントの前提条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)」を参照してください。

### <a name="licenses"></a>ライセンス

Microsoft Managed Desktop を使用するには、いくつかのライセンスが必要です。

**準備未完了**

Microsoft Managed Desktop を使用するために必要なすべてのライセンスがありません。 詳細については、「[Microsoft Managed Desktop テクノロジ](../intro/technologies.md)」および「[ライセンスの詳細](prerequisites.md#more-about-licenses)」を参照してください。


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop のサービス アカウント

特定のアカウント名が、Microsoft Managed Desktop サービスを管理するために Microsoft Managed Desktop によって作成されたアカウント名と競合する可能性があります。

**使用不可能**

Microsoft Managed Desktop によって作成されたアカウント名と競合するアカウント名が少なくとも 1 つ存在します。 Microsoft アカウント担当者と協力して、これらのアカウント名を除外してください。 セキュリティ リスクを最小限に抑えるために、アカウント名をパブリックに一覧表示しません。 


### <a name="security-administrator-roles"></a>セキュリティ管理者の役割

特定のセキュリティ ロールを持つユーザーには、Microsoft Defender for Endpoint でそれらのロールが割り当てられている必要があります。

**アドバイザリ**

Azure AD 組織内でこれらのロールのいずれかにユーザーが割り当てられている場合は、Microsoft Defender for Endpoint でもこれらのロールが割り当てられていることを確認します。 そうしないと、これらのロールを持つ管理者は管理ポータルにアクセスできなくなります。

- セキュリティ オペレーター
- グローバル閲覧者

詳細については、「[ロールベースのアクセス制御のロールの作成と管理](/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。


### <a name="security-default"></a>セキュリティの既定値

Azure Active Directory のセキュリティの既定値により、Microsoft Managed Desktop がデバイスを管理できなくなります。

**使用不可能**

セキュリティの既定値が有効になっています。 セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。 詳細については、「[条件付きアクセス ポリシーを作成する](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。

### <a name="self-service-password-reset"></a>セルフサービス パスワードのリセット

セルフサービス パスワード リセット (SSPR) は、Microsoft Managed Desktop サービス アカウントを除くすべての Microsoft Managed Desktop ユーザーに対して有効にすることができます。 詳細については、「[チュートリアル: Azure Active Directory セルフサービス パスワード リセットを使用してユーザーがアカウントのロックを解除したり、パスワードをリセットしたりできるようにする](/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。

**アドバイザリ**

SSPR の **[選択済み]** 設定には Microsoft Managed Desktop ユーザーが含まれ、Microsoft Managed Desktop サービス アカウントは除外されていることを確認してください。 Microsoft Managed Desktop サービス アカウントは、SSPR が有効になっていると想定どおりに動作しません。  


### <a name="standard-user-role"></a>標準ユーザーの役割

グローバル管理者とデバイス管理者の Azure AD ロールが割り当てられているユーザー以外は、Microsoft Managed Desktop ユーザーは、ローカル管理者特権を持たない標準ユーザーになります。 他のすべてのユーザーには、Microsoft Managed Desktop デバイスの起動時に標準ユーザー ロールが割り当てられます。

**アドバイザリ**

Microsoft Managed Desktop ユーザーは、登録後にMicrosoft Managed Desktop デバイスに対するローカル管理者特権を持たなくなります。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

**[特定のドメインに参加している PC でのみ同期を許可]** 設定は Microsoft Managed Desktop と競合します。 OneDrive の設定には、OneDrive [管理者センター](https://admin.onedrive.com)でアクセスできます。

**アドバイザリ**

**[特定のドメインに参加している PC でのみ同期を許可]** 設定を使用しています。 この設定は、Microsoft Managed Desktop では機能しません。 この設定を無効にし、代わりに条件付きアクセス ポリシーを使用するように OneDrive を設定します。 ヘルプについては「[条件付きアクセスの展開の計画](/azure/active-directory/conditional-access/plan-conditional-access)」を参照してください。
