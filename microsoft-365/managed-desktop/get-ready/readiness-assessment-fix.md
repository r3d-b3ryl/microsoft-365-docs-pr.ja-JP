---
title: 準備評価ツールによって検出された問題を修正します。
description: ツールによって検出された各問題に対して実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 642de80e1a133f212b7afb6774d9aab2eeaabdbf
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941411"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>準備評価ツールによって検出された問題を修正します。

チェックが行われるたびに、ツールは次の4つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前にアクションを実行する必要はありません。        |
|アドバイザリ    | このツールまたはこの記事の手順に従って、登録とユーザーのための最適な操作を行います。 登録は完了 *でき* ますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を修正しない場合、登録は失敗します。* このツールまたはこの記事に記載されている手順に従って解決してください。        |
|Error | 使用している Azure Active Director (AD) の役割には、このチェックを実行するための十分な権限がありません。 |

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

### <a name="autopilot-deployment-profile"></a>自動操縦展開プロファイル

Microsoft マネージドデスクトップによって使用される、割り当てられたグループまたは動的なグループを対象とした既存の自動操縦プロファイルはありません。 Microsoft Managed Desktop は、自動操縦を使用して新しいデバイスをプロビジョニングします。

**使用不可能**

すべてのデバイスに割り当てられている自動操縦プロファイルがあります。 手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。 Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。

**アドバイザリ**

自動操縦プロファイルが、登録時に作成される Microsoft マネージドデスクトップデバイスを含まない、割り当てられた、または動的な Azure AD グループを対象としていることを確認します。 手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。 Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。


### <a name="certificate-connectors"></a>証明書コネクタ

Microsoft マネージドデスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーはありません。 状況に応じて、次のいずれかのアドバイザリが適用されますので、慎重に確認してください。

**アドバイザリ**

証明書コネクタが存在しません。 コネクタは必要ありませんが、Microsoft マネージドデスクトップデバイスへのネットワーク接続について必要な場合があるかどうかを評価する必要があります。 詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。

**アドバイザリ**

少なくとも1つの証明書コネクタにエラーがあります。 このコネクタを Microsoft マネージドデスクトップデバイスに接続するために必要な場合は、このエラーを解決する必要があります。 詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。


**アドバイザリ**

少なくとも1つの証明書コネクタがあり、エラーは報告されていません。 ただし、Microsoft マネージドデスクトップデバイスでコネクタを再利用するには、プロファイルを作成する必要がある場合があります。 詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。


### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

Azure AD 組織の条件付きアクセスポリシーで、Microsoft 管理デスクトップユーザーを対象としないようにする必要があります。

**使用不可能**

すべてのユーザーを対象とする条件付きアクセスポリシーが少なくとも1つあります。 登録時に作成される Microsoft マネージドデスクトップサービスアカウントの Azure AD グループが含まれていない特定の Azure AD グループを対象とするようにポリシーをリセットします。 手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。

**アドバイザリ**

**モダンワークプレースサービスアカウント** の Azure AD グループを除外している条件付きアクセスポリシーがあることを確認してください。 手順については、「 [条件付きアクセスを調整](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)する」を参照してください。 **モダン Workplace Service Accounts** Azure AD group は、登録時にサービスに対して作成する動的なグループです。 登録後にこのグループを除外するには、戻る必要があります。 これらのサービスアカウントの詳細については、「 [標準の運用手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。

**Error**

Intune 管理者の役割には、このチェックに十分な権限がありません。 このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="device-compliance-policies"></a>デバイスコンプライアンスポリシー

Azure AD 組織の Intune デバイスコンプライアンスポリシーでは、Microsoft Managed Desktop ユーザーを対象としないようにする必要があります。

**使用不可能**

すべてのユーザーを対象とするコンプライアンスポリシーが少なくとも1つあります。 Microsoft Managed Desktop ユーザーを含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。 手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。

**アドバイザリ**

コンプライアンスポリシーに Microsoft Managed Desktop のユーザーが含まれていないことを確認してください。 手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。



### <a name="device-configuration-policies"></a>デバイス構成ポリシー

Azure AD 組織の Intune デバイス構成ポリシーでは、Microsoft 管理デスクトップデバイスまたはユーザーを対象としてはなりません。

**使用不可能**

すべてのユーザー、すべてのデバイス、またはその両方を対象とする構成ポリシーが、少なくとも1つあります。 Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。 手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。

**アドバイザリ**

コンプライアンスポリシーに、Microsoft マネージドデスクトップデバイスやユーザーが含まれていないことを確認してください。 手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。



### <a name="device-type-restrictions"></a>デバイスの種類の制限

Microsoft マネージドデスクトップデバイスでは、Intune への登録が許可されている必要があります。

**使用不可能**

「 [登録の制限を設定](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) する」の手順に従って、設定を [ **許可** ] に変更します。


### <a name="enrollment-status-page"></a>登録の状態ページ

現在、登録状態ページ (ESP) が有効になっています。 この機能のパブリックプレビューに参加している場合は、この項目を無視できます。 詳細については、「 [自動操縦による初回実行時の動作」および「登録の状態」ページ](../get-started/esp-first-run.md)を参照してください。

**使用不可能**

**アプリケーションとプロファイルの構成の進行状況を示す** ように、ESP の既定のプロファイルが設定されている。 この設定を無効にするか、[ [登録状態の設定] ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれないようにします。

**アドバイザリ**

[ **アプリとプロファイルの構成の進行状況]** の設定を含むすべてのプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないことを確認してください。 詳細については、「 [登録の状態を設定する」ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)を参照してください。

### <a name="intune-enrollment"></a>Intune の登録

Azure AD 組織の Windows 10 デバイスは、自動的に Intune に登録する必要があります。

**アドバイザリ**

MDM ユーザースコープが **一部** または **すべて** に設定されていることを確認し、 **[なし** ] をオンにします。 **一部** を選択した場合は、登録した後に戻って、 **グループ** の **モダンワークプレースすべて** の Azure AD グループを選択します。


### <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

Microsoft Store for Business を使用して、会社のポータルをダウンロードして Microsoft Project や Microsoft Visio などの一部のアプリを展開できるようにしています。

**使用不可能**

Microsoft Store for Business が有効になっていないか、Intune と同期されていません。 詳細については、「microsoft [Store For Business For Business With Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 」と「 [デバイス上に intune ポータルサイトをインストール](../get-started/company-portal.md)する」を参照してください。

### <a name="multi-factor-authentication"></a>多要素認証

多要素認証は、誤って Microsoft Managed Desktop service アカウントに適用されてはなりません。


**使用不可能**

すべてのユーザーに割り当てられている条件付きアクセスポリシーについて、"required" として設定されている多要素認証 (MFA) ポリシーがあります。 Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。

**アドバイザリ**

MFA を必要とする条件付きアクセスポリシーが、 **モダンワークプレースすべて** の Azure AD グループを除外していることを確認してください。 詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。 **モダンワークプレースすべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的なグループです。そのため、登録後にこのグループを除外する必要があります。

**Error**

Intune 管理者の役割には、このチェックに十分な権限がありません。 このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。

- セキュリティ閲覧者
- セキュリティ管理者
- 条件付きアクセス管理者
- グローバル閲覧者
- デバイス管理者


### <a name="powershell-scripts"></a>PowerShell スクリプト

Windows PowerShell スクリプトは、Microsoft マネージドデスクトップデバイスを対象とする方法では割り当てられません。  

**アドバイザリ**

Azure AD 組織の Windows PowerShell スクリプトが、Microsoft 管理デスクトップデバイスまたはユーザーを対象としないようにしてください。 PowerShell スクリプトを割り当てないでください。すべてのユーザー、すべてのデバイス、またはその両方を対象とします。 Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 詳細については、「 [Windows 10 デバイスでの Intune での PowerShell スクリプトの使用](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)」を参照してください。

### <a name="region"></a>地域

お客様の地域は、Microsoft マネージドデスクトップでサポートされている必要があります。

**使用不可能**

Azure AD 組織の地域は、Microsoft マネージドデスクトップで現在サポートされていません。 詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。

**アドバイザリ**

Azure AD 組織が配置されている1つ以上の国が Microsoft マネージドデスクトップでサポートされていません。 詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。


### <a name="security-baselines"></a>セキュリティベースライン

セキュリティベースラインポリシーでは、Microsoft マネージドデスクトップデバイスを対象としてはなりません。

**使用不可能**

すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ基準プロファイルがあります。 Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。

**アドバイザリ**

Microsoft マネージドデスクトップデバイスを除外しているセキュリティベースラインポリシーがあることを確認してください。 手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。 **モダン Workplace Devices-すべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。


### <a name="windows-apps"></a>Windows アプリ

Microsoft Managed Desktop users が所有しているアプリを確認します。

**アドバイザリ**

Microsoft Managed Desktop ユーザーに割り当てるアプリのインベントリを準備する必要があります。 これらのアプリが Intune によって展開可能であることを確認してください。 詳細については、「 [Microsoft マネージドデスクトップのアプリ](apps.md)」を参照してください。

Microsoft エンドポイント構成マネージャーのクエリを Microsoft アカウント担当者に依頼して、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft マネージドデスクトップでは、Windows Hello for Business を有効にする必要があります。

**使用不可能**

Windows Hello for Business は無効になっています。 「 [Create a Windows Hello For Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 」の手順に従って、これを有効にします。

**アドバイザリ**

Windows Hello for Business がセットアップされていません。 「 [Create a Windows Hello For business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って、これを有効にします。


### <a name="windows-10-update-rings"></a>Windows 10 の更新リング

Intune の "Windows 10 update ring" ポリシーで、Microsoft マネージドデスクトップデバイスを対象としないようにする必要があります。

**使用不可能**

すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。 Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。 手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。

**アドバイザリ**

**モダンワークプレースのすべて** の Azure AD グループを除外しているすべての更新リングポリシーを確認してください。 手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。 **モダン Workplace Devices-すべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定


### <a name="ad-hoc-subscriptions"></a>アドホックサブスクリプション

"False" に設定されている設定をチェックする方法を確認する方法を説明します。エンタープライズ状態の移動が正常に動作しない可能性があります。

**アドバイザリ**

**AllowAdHocSubscriptions** が **True** に設定されていることを確認します。 それ以外の場合、エンタープライズ状態ローミングは機能しない可能性があります。 詳細については、「 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)」を参照してください。


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

エンタープライズ状態ローミングを有効にする必要があります。

**アドバイザリ**

エンタープライズ状態の移動が、 **すべて** のグループまたは **選択した** グループに対して有効になっていることを確認します。 詳細については、「 [Azure Active Directory でエンタープライズ状態のローミングを有効にする](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。

### <a name="licenses"></a>ライセンス

Microsoft マネージドデスクトップを使用するには、いくつかのライセンスが必要です。

**準備ができていない**

Microsoft マネージドデスクトップを使用するために必要なすべてのライセンスがありません。 詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」および「 [ライセンスについ](prerequisites.md#more-about-licenses)て」を参照してください。


### <a name="security-account-names"></a>セキュリティアカウント名

一部のセキュリティアカウント名は、Microsoft マネージドデスクトップによって作成されたものと競合する可能性があります。

**使用不可能**

Microsoft マネージドデスクトップによって作成されたアカウントと競合する、少なくとも1つのアカウント名がある。 Microsoft アカウントの担当者と協力して、これらのアカウント名を除外します。


### <a name="security-administrator-roles"></a>セキュリティ管理者の役割

特定のセキュリティロールを持つユーザーは、エンドポイントの Microsoft Defender で割り当てられている必要があります。

**アドバイザリ**

これらの役割のいずれかが Azure AD 組織に割り当てられている場合は、エンドポイントの Microsoft Defender にこれらの役割が割り当てられていることを確認してください。 そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできなくなります。

- セキュリティ閲覧者
- セキュリティ オペレーター
- グローバル閲覧者

詳細については、「 [役割ベースのアクセス制御の役割を作成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。


### <a name="security-default"></a>既定のセキュリティ

Azure Active Directory のセキュリティの既定値を使用すると、Microsoft Managed Desktop がデバイスを管理できなくなります。

**使用不可能**

セキュリティの既定値がオンになっている。 セキュリティの既定値をオフにして、条件付きアクセスポリシーを設定します。 詳細については、「 [一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。

### <a name="self-service-password-reset"></a>セルフサービスによるパスワードのリセット

Microsoft Managed Desktop service アカウントを除くすべてのユーザーに対して、セルフサービスのパスワードのリセット (SSPR) を有効にする必要があります。 詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。

**アドバイザリ**

SSPR が **選択** した設定に、Microsoft managed desktop デバイスは含まれていますが、Microsoft managed desktop service アカウントを除外していることを確認してください。 SSPR が有効になっている場合、Microsoft マネージドデスクトップサービスアカウントは期待どおりに機能しません。  


### <a name="standard-user-role"></a>標準ユーザーの役割

グローバル管理者およびデバイス管理者の Azure AD ロールを割り当てられているユーザー以外は、Microsoft Managed Desktop ユーザーは、ローカル管理者特権を持たない標準ユーザーになります。 他のすべてのユーザーには、Microsoft マネージドデスクトップデバイスを起動するときに、標準のユーザー役割が割り当てられます。

**アドバイザリ**

Microsoft マネージドデスクトップのユーザーには、登録後の Microsoft マネージドデスクトップデバイスに対するローカル管理者権限がありません。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

### <a name="onedrive-for-business"></a>OneDrive for Business

[ **特定のドメインに参加している pc でのみ同期を許可** する] の設定は、Microsoft マネージドデスクトップと競合します。

**アドバイザリ**

[ **特定のドメインに参加している pc でのみ同期を許可** する] 設定を使用している。 この設定は、Microsoft マネージドデスクトップでは使用できません。 この設定を無効にし、代わりに、条件付きアクセスポリシーを使用するように OneDrive for Business を設定します。 ヘルプについて [は、「Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。

