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
ms.openlocfilehash: 8457331f0895c66d1aa0ad54cfc43cd001a9bd9e
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681086"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>準備評価ツールで見つかった問題を修正する

チェックごとに、ツールは 4 つの考えられる結果のいずれかを報告します。

| 結果  | 意味 |
| ----- | ----- |
| 準備完了 | 登録を完了する前に操作は必要ありません。 |
| アドバイザリ | 登録とユーザーにとっての最高のエクスペリエンスを得るには、ツールまたはこの記事の手順に従ってください。 <br><br> 登録を完了することは *できます* が、最初のデバイスを展開する前にこれらの問題を修正する必要があります。 |
| 使用不可能 | これらの問題を修正しないと、**登録は失敗します**。 <br><br> ツールまたはこの記事の手順に従って解決します。 |
| Error | ご使用中の Azure Active Directory (AD) のロールには、このチェックを実行するための十分なアクセス許可がありません。 |

> [!NOTE]
> このツールによって報告された結果は、設定を実行した時点でのみ設定の状態を反映します。 Microsoft Intune、Azure Active Directory、Microsoft 365 のポリシーに後で変更を加えた場合、"準備完了" だったアイテムは "準備ができていない" 状態になります。 Microsoft Managed Desktop 操作に関する問題を回避するには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

Intune には Microsoft エンドポイント マネージャー[管理センター](https://endpoint.microsoft.com)を使用してアクセスできます。

### <a name="autopilot-deployment-profile"></a>Autopilot 展開プロファイル

割り当てられたグループまたは動的グループを対象とする既存の Autopilot プロファイルを Microsoft Managed Desiktop デバイスと一緒に持たせるべきではありません。 Microsoft Managed Desktop では、Autopilot を使用して新しいデバイスを構成します。 既存の Autopilot 展開プロファイルがある場合、Microsoft Managed Desktop **Autopilot** 準備テストが成功するには、[すべての対象デバイスを自動パイロットに変換する] 設定を **[** いいえ] に設定する必要があります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | すべてのデバイスに割り当てられている Autopilot プロファイルがあります。 <br><br> 詳細については、「[Autopilot を使用して Intune Windowsデバイスを登録するWindows参照してください](/mem/autopilot/enrollment-autopilot)。 Microsoft Managed Desktop の登録後、Autopilot ポリシーを設定して、モダン **ワーク** プレース デバイス - [すべてのデバイス] グループAzure ADします。
| アドバイザリ | Autopilot プロファイルが、Microsoft Managed Desktop デバイスを含まない割り当て済みの Azure AD グループまたは動的な Azure AD グループを対象としていることを確認します。 <br><br> 詳細については、「[Autopilot を使用して Intune Windowsデバイスを登録するWindows参照してください](/mem/autopilot/enrollment-autopilot)。 Microsoft Managed Desktop の登録後、Autopilot プロファイルをモダン ワークプレース デバイス **-** [すべてのデバイス] グループを除外Azure ADします。 |

### <a name="certificate-connectors"></a>証明書コネクタ

Microsoft Managed Desktop に登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーは発生しません。 次のいずれかのアドバイザリのみが状況に適用されるため、慎重に確認してください。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | 証明書コネクタが存在しません。 コネクタは必要ないようですが、Microsoft Managed Desktop デバイスでネットワーク接続に必要なコネクタがあるかどうかを評価する必要があります。 <br><br> 詳細については、「[Microsoft Managed Desktop の証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)」を参照してください。 |
| アドバイザリ | 少なくとも 1 つの証明書コネクタにエラーがあります。 Microsoft Managed Desltop デバイスに証明書を提供するためにこのコネクタが必要な場合は、エラーを解決する必要があります。 <br><br> 詳細については、「[Microsoft Managed Desktop の証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)」を参照してください。 |
| アドバイザリ | 証明書コネクタが 1 つ以上あるので、エラーは報告されません。 ただし、展開の準備として、Microsoft Managed Desktop デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。 <br><br> 詳細については、「[Microsoft Managed Desktop の証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)」を参照してください。 |

### <a name="company-portal"></a>ポータル サイト

Microsoft Managed Desktop では、IT 管理者が Microsoft Managed Desktop デバイスを使用してユーザーの Intune ポータル サイトをインストールする必要があります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | ユーザー用にポータル サイトインストールされていない。 ポータル サイトを購入し、Intune とビジネス向け Microsoft Store 間の同期を強制します。 <br><br> 詳細については、「[デバイスに Intune ポータル サイトをインストールする](../get-started/company-portal.md)」を参照してください。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

条件付きアクセス ポリシーでは、Microsoft Managed Desktop が Intune および組織 (テナント) Azure AD組織 (テナント) を管理Azure AD。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つ存在します。 <br><br> 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 ただし、失敗すると、登録エクスペリエンス中にエラーが発生する可能性があります。 ベスト プラクティスとして、Microsoft Managed Desktop サービス アカウントを含Azure ADグループを対象とする割り当てを作成します。 <br><br> 登録後、Microsoft エンドポイント マネージャーで Microsoft Managed Desktop の条件付きアクセス ポリシーを確認できます。 これらのサービス アカウントの詳細については、「[標準の操作手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。 |
| アドバイザリ | Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理できなくなる可能性がある条件付きアクセス ポリシーがあります。 <br><br> 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 <br><br> これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| Error | Intune 管理者ロールには、このチェックのための十分なアクセス許可がありません。 また、このチェックを実行するには、次のAzure ADロールを割り当てる必要があります。 <ul><li>セキュリティ閲覧者</li><li>セキュリティ管理者</li><li>条件付きアクセス管理者</li><li>グローバル閲覧者</li><li>デバイス管理者</li></ul>
### <a name="device-compliance-policies"></a>デバイス コンプライアンス ポリシー

組織の Intune デバイス コンプライアンス ポリシー Azure AD Microsoft マネージ デスクトップ デバイスに影響する可能性があります。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | すべてのユーザーを適用するコンプライアンス ポリシーが少なくとも 1 つ存在します。 Microsoft Managed Desktop には、Microsoft Managed Desktop デバイスに適用されるコンプライアンス ポリシーも含まれています。 Microsoft Managed Desktop デバイスに適用される組織によって作成されたすべてのコンプライアンス ポリシーを確認して、競合がないことを確認します。 <br><br> 詳細については、「コンプライアンス ポリシーを[作成する」](/mem/intune/protect/create-compliance-policy)を参照Microsoft Intune。 |

### <a name="device-configuration-profiles"></a>デバイスの構成プロファイル

組織の Intune デバイス構成プロファイルAzure AD、Microsoft Manage Desktop デバイスまたはユーザーを対象とできません。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | すべてのユーザー、すべてのデバイス、またはその両方に適用される構成プロファイルが少なくとも 1 つ存在します。 Microsoft Managed Desktop デバイスを含Azure AD特定のグループに適用するプロファイルをリセットします。 <br><br> 詳細については、「カスタム設定[を使用してプロファイルを作成する](/mem/intune/configuration/custom-settings-configure)」を参照Microsoft Intune。 |
| アドバイザリ | 構成ポリシーに Microsoft Managed Desktop デバイスやユーザーが含まれていないことを確認します。 <br><br> 詳細については、「カスタム設定[を使用してプロファイルを作成する](/mem/intune/configuration/custom-settings-configure)」を参照Microsoft Intune。 |

### <a name="device-type-restrictions"></a>デバイスの種類の制限

Microsoft Managed Desktop デバイスには Intune への登録を許可する必要があります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | Windows デバイスが Intune に登録されないように構成された登録制限ポリシーが、現在少なくとも 1 つあります。 <br><br> [登録制限の設定](/mem/intune/enrollment/enrollment-restrictions-set)の手順に従って、Microsoft Managed Desktop ユーザーを対象とする各登録制限ポリシーを設定し、**Windows (MDM)** 設定を **[許可]** に変更します。 ただし、**個人所有の** **Windows (MDM)** デバイスを **[禁止]** に設定できます。 |

### <a name="enrollment-status-page"></a>登録ステータス ページ

現在、登録ステータス ページ (ESP) が有効になっています。 この機能の Microsoft Managed Desktop パブリック プレビューに参加する場合は、この項目を無視できます。 詳細については、「[Autopilot と登録状態ページでの最初の実行エクスペリエンス](../get-started/esp-first-run.md)」を参照してください。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | ESP の既定のプロファイルが **[アプリケーションとプロファイルの構成の進行状況を表示]** に設定されています。 <br><br> この設定を無効にするか、Azure ADグループへの割り当てに Microsoft Managed Desktop デバイスが含まれるのを確認するには、「登録状態ページのセットアップ」の手順[に従います](/mem/intune/enrollment/windows-enrollment-status)。 |
| アドバイザリ | [アプリとプロファイルの構成の進行状況を表示する] 設定を持つプロファイルが、Microsoft Managed Desktop デバイスを含む Azure ADグループに割り当てられていないか確認します。 <br><br> 詳細については「[登録状態ページの設定](/mem/intune/enrollment/windows-enrollment-status)」を参照してください。 |

### <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

Microsoft は、ビジネス向け Microsoft Storeを使用して、microsoft ポータル サイトデスクトップにアプリを展開します。 このメソッドを使用すると、ユーザーは必要に応じて、アプリ (許可されている場合) Microsoft Project Microsoft Visioなどの一部のアプリをインストールできます。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | ビジネス向け Microsoft Store が有効になっていないか、Intune と同期されていません。 <br><br> 詳細については、「[Microsoft Intune を使ってビジネス向け Microsoft Store から大量購入したアプリの管理方法](/mem/intune/apps/windows-store-for-business)」 と「[デバイスに Intune ポータル サイト](../get-started/company-portal.md)」を参照してください。 |

### <a name="multi-factor-authentication"></a>多要素認証

多要素認証では、Microsoft Managed Desktop が Intune および組織 (テナント) で Azure AD組織 (テナント) を管理Azure AD。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | すべてのユーザーに割り当てられている条件付きアクセス ポリシーでは、必要に応じていくつかの多要素認証ポリシーが設定されています。 <br><br> 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。 <br><br> これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| アドバイザリ | 条件付きアクセス ポリシーで多要素認証が必要になります。これは、Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理する妨げる可能性があります。 <br><br> 登録中に、関連する条件付きアクセス ポリシーから Microsoft Managed Desktop サービス アカウントを除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。 これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| Error | Intune 管理者ロールには、このチェックのための十分なアクセス許可がありません。 また、このチェックを実行するには、次のAzure ADロールを割り当てる必要があります。 <ul><li>セキュリティ閲覧者</li><li>セキュリティ管理者</li><li>条件付きアクセス管理者</li><li>グローバル閲覧者</li><li>デバイス管理者</li></ul>

### <a name="powershell-scripts"></a>PowerShell スクリプト

Windows PowerShell スクリプトは、Microsoft Managed Desktop デバイスを対象とするようには割り当てられません。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | Azure AD 組織内の Windows PowerShell スクリプトが Microsoft Manage Desktop デバイスまたはユーザーを対象としていないことを確認します。 すべてのユーザー、すべてのデバイス、または両方を対象とする PowerShell スクリプトを割り当てない。 Microsoft Managed Desktop デバイスやユーザーを含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 <br><br> 詳細については、「[Intune の Windows 10 デバイスで PowerShell スクリプトを使用する](/mem/intune/apps/intune-management-extension)」を参照してください。 |

### <a name="region"></a>地域

Microsoft Managed Desktop でお客様のリージョンがサポートされている必要があります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | お客様の Azure AD 組織リージョンは、現在 Microsoft Managed Desktop でサポートされていません。 <br><br> 詳細については、「[Microsoft Managed Desktop のサポートされている地域と言語](../service-description/regions-languages.md)」を参照してください。 |
| アドバイザリ | お客様の Azure AD 組織が配置されている 1 つ以上の国は、Microsoft Managed Desktop でサポートされていません。 <br><br> 詳細については、「[Microsoft Managed Desktop のサポートされている地域と言語](../service-description/regions-languages.md)」を参照してください。 |

### <a name="security-baselines"></a>セキュリティ基本計画

セキュリティ ベースライン ポリシーは、Microsoft 管理デスクトップ デバイスを対象とすべきではない。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ ベースライン プロファイルがあります。 Microsoft Managed Desktop デバイスを含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 <br><br> 詳細については、「[Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。 登録中に、すべての Microsoft Managed Desktop デバイスに新しいセキュリティ ベースラインを適用します。 登録後、Microsoft エンドポイント マネージャー の **[構成ポリシー領域]** で Microsoft Managed Desktop セキュリティ ベースライン ポリシーを確認できます。 |
| アドバイザリ | すべてのセキュリティ ベースライン ポリシーから Microsoft Managed Desktop デバイスが除外されていることを確認します。 詳細については、「[Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。 <br><br> 登録中に、すべての Microsoft Managed Desktop デバイスに新しいセキュリティ ベースラインを適用します。 モダン **ワークプレース デバイス - すべての** Azure ADグループは、Microsoft Managed Desktop に登録するときに作成する動的グループです。 登録後に、このグループを除外するために戻ってくる必要があります。 |

### <a name="unlicensed-admins"></a>ライセンスのない管理者

お客様の Azure AD 組織とやり取りするときに "アクセス許可の不足" のエラーを回避するためにこの設定を有効にする必要があります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | **[ライセンスのない管理者へのアクセスを許可する**] を有効にする必要があります。 詳細については、「ゲスト アカウントの [前提条件」を参照してください](/microsoft-365/managed-desktop/get-ready/guest-accounts)。 |

### <a name="windows-apps"></a>Windows アプリ

Microsoft Managed Desktop ユーザーに必要なアプリを確認します。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | Microsoft Managed Desktop ユーザーが持つアプリのインベントリを準備する必要があります。 これらのアプリは Intune で展開する必要があるため、既存の Intune アプリの再利用を評価します。 ポータル サイト ([デバイスに Intune ポータル サイトをインストールする](../get-started/company-portal.md)) と登録状態ページ (ESP) を使用してユーザーにアプリを配布することを検討してください。 <br><br> 詳細については、「[Microsoft Managed Desktop のアプリ](apps.md)」および「[Autopilot と登録状態ページを使った最初の実行エクスペリエンス](../get-started/esp-first-run.md)」を参照してください。 <br><br> Microsoft Endpoint Configuration Manager でMicrosoft アカウント担当者に問い合わせて、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。 |

### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop には、Windows Hello for Business を有効にする必要があります。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | Windows Hello for Business が無効になっているか、設定されていません。 「[Windows Hello for Business ポリシーの作成](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って有効にします。 |

### <a name="windows-10-update-rings"></a>Windows 10 更新リング

Intune の "Windows 10更新リング" のポリシーは、Microsoft Managed Desktop デバイスをターゲットにすることはできません。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。 Microsoft Managed Desktop デバイスを含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 <br><br> 詳細については、「Intune でのソフトウェア[更新プログラムWindows 10管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。 |
| アドバイザリ | モダン ワークプレース デバイス - [すべてのデバイス] グループを除外している更新Azure ADします。 Azure AD ユーザー グループをこれらのポリシーに割り当てた場合は、Microsoft **Managed Desktop** ユーザーを追加するモダン ワークプレース - すべての Azure AD グループ (または同等のグループ) も除外している更新リング ポリシーを確認してください。 <br><br> 詳細については、「Intune でのソフトウェア[更新プログラムWindows 10管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。 モダン ワーク **プレース デバイス - All** と **Modern Workplace -** すべてのユーザー グループはAzure AD Microsoft Managed Desktop に登録するときに作成するグループです。 登録後に、このグループを除外するために戻ってくる必要があります。 |

## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

Azure portal でAzure Active Directory設定に[アクセスできます](https://portal.azure.com)。

### <a name="intune-enrollment"></a>Intune の登録

Azure AD 組織内の Windows 10 デバイスは、Intune に自動的に登録できる必要があります。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | **MDM ユーザー スコープ** が、**[なし]** ではなく、**[一部]** または **[すべて]** に設定されていることを確認します。 <br><br> [一部] を **選択** した場合は、登録後に戻って、[モダン ワークプレース **-** すべてのグループ] グループ、またはすべての Microsoft Azure AD 管理デスクトップ ユーザーを対象とする同等のグループを選択します。 <br><br> 詳細については、「デバイスを使用してデバイスの登録Windows[設定する」を参照Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。 |

### <a name="ad-hoc-subscriptions"></a>アドホック サブスクリプション

"false" に設定すると、状態ローミングが正常に動作しないEnterprise設定を確認する方法について説明します。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | **AllowAdHocSubscriptions** が **True** に設定されていることを確認します。 そうしないと、Enterprise State Roaming が機能しない可能性があります。 <br><br> 詳細については、[Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) を参照してください。 |

### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming を有効にする必要があります。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | Enterprise State Roaming が **[すべての]** または **[選択された]** グループに対して有効になっていることを確認します。 <br><br> 詳細については、「[Azure Active Directory で Enterprise State Roaming を有効にする](/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。 |

### <a name="guest-invitation-settings"></a>ゲスト招待の設定

Microsoft Managed Desktop ではゲスト招待の設定を調整することを推奨しています。というのは、規定の設定では、ディレクトリ内のすべてのユーザーとゲストが、ゲストを招待できるようになっているからです。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | **特定の管理者ロールに割り当てられた** メンバー ユーザーとユーザーは、メンバーアクセス許可を持つゲストを含むゲストを招待できます。有効にする必要があります。 <br><br> 詳細については、「ゲスト アカウントの [前提条件」を参照してください](/microsoft-365/managed-desktop/get-ready/guest-accounts)。 |

### <a name="guest-user-access"></a>ゲスト ユーザー アクセス

Microsoft Managed Desktop では、既定の設定を使用すると、ディレクトリ内のすべてのゲストにメンバーと同じアクセス権を与え、ゲスト アクセスを調整できます。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | **[ゲスト ユーザーは、ディレクトリ オブジェクトのプロパティとメンバーシップへのアクセスが制限されている]** を有効にする必要があります。 <br><br> 詳細については、「ゲスト アカウントの [前提条件」を参照してください](/microsoft-365/managed-desktop/get-ready/guest-accounts)。 |

### <a name="licenses"></a>ライセンス

Microsoft Managed Desktop を使用するには、多くのライセンスが必要です。

| 結果  | 意味 |
| ----- | ----- |
| 準備未完了 | Microsoft Managed Desktop を使用するために必要なすべてのライセンスがありません。 <br><br> 詳細については、「[Microsoft Managed Desktop テクノロジ](../intro/technologies.md)」および「[ライセンスの詳細](prerequisites.md#more-about-licenses)」を参照してください。 |

### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop のサービス アカウント

特定のアカウント名が、Microsoft Managed Desktop サービスを管理するために Microsoft Managed Desktop によって作成されたアカウント名と競合する可能性があります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | Microsoft Managed Desktop によって作成されたアカウント名と競合するアカウント名が少なくとも 1 つ存在します。 Microsoft アカウント担当者と協力して、これらのアカウント名を除外してください。 セキュリティ リスクを最小限に抑えるために、アカウント名をパブリックに一覧表示しません。

### <a name="security-administrator-roles"></a>セキュリティ管理者の役割

特定のセキュリティ ロールを持つユーザーには、Microsoft Defender for Endpoint でそれらのロールが割り当てられている必要があります。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | Azure AD 組織内でこれらのロールのいずれかにユーザーが割り当てられている場合は、Microsoft Defender for Endpoint でもこれらのロールが割り当てられていることを確認します。 そうしないと、これらのロールを持つ管理者は管理ポータルにアクセスできなくなります。 <ul><li>セキュリティ オペレーター</li><li>グローバル閲覧者</li></ul> <br> 詳細については、「[ロールベースのアクセス制御のロールの作成と管理](/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。

### <a name="security-default"></a>セキュリティの既定値

Azure Active Directory のセキュリティの既定値により、Microsoft Managed Desktop がデバイスを管理できなくなります。

| 結果  | 意味 |
| ----- | ----- |
| 使用不可能 | セキュリティの既定値が有効になっています。 セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。 <br><br> 詳細については、「[条件付きアクセス ポリシーを作成する](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。 |

### <a name="self-service-password-reset"></a>セルフサービス パスワードのリセット

セルフサービス パスワード リセット (SSPR) は、Microsoft Managed Desktop サービス アカウントを除くすべての Microsoft Managed Desktop ユーザーに対して有効にすることができます。 <br><br> 詳細については、「[チュートリアル: Azure Active Directory セルフサービス パスワード リセットを使用してユーザーがアカウントのロックを解除したり、パスワードをリセットしたりできるようにする](/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | [ **SSPR 選択** ] 設定に Microsoft Managed Desktop ユーザーが含まれていますが、Microsoft 管理デスクトップ サービス アカウントは除外します。 SSPR が有効になっている場合、Microsoft Managed Desktop サービス アカウントは期待通り動作しません。 |

### <a name="standard-user-role"></a>標準ユーザーの役割

グローバル管理者とデバイス管理者が割り当てられているユーザー Azure Active Directory以外に、Microsoft Managed Desktop ユーザーは、ローカル管理者特権のない標準ユーザーです。 他のすべてのユーザーには、Microsoft Managed Desktop デバイスの起動時に標準ユーザー ロールが割り当てられます。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | Microsoft Managed Desktop ユーザーは、登録後に Microsoft Managed Desktop デバイスに対するローカル管理者特権を持つ必要があります。 |

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive"></a>OneDrive

**[特定のドメインに参加している PC でのみ同期を許可]** 設定は Microsoft Managed Desktop と競合します。 OneDrive の設定には、OneDrive [管理者センター](https://admin.onedrive.com)でアクセスできます。

| 結果  | 意味 |
| ----- | ----- |
| アドバイザリ | **[特定のドメインに参加している PC でのみ同期を許可]** 設定を使用しています。 この設定は、Microsoft Managed Desktop では機能しません。 この設定を無効にします。 代わりに、条件付きOneDriveポリシーを使用するサーバーを設定します。 <br><br> 詳細については、「条件付き [アクセスの展開を計画する」を](/azure/active-directory/conditional-access/plan-conditional-access) 参照してください。 |
