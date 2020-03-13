---
title: '手順 1: グローバル管理者アカウントを作成して保護する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: グローバル管理者アカウントには、資格情報の侵害から保護できるように特別な対処が必要です。
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544036"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>手順 1: グローバル管理者アカウントを作成して保護する

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>グローバル管理者アカウントを保護する

*これは必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

このセクションでは、管理者アカウントを可能な限り保護することで、組織へのデジタル攻撃を防止できます。 そのためには、次のことを行う必要があります。

- [強力なパスワード](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)を設定したグローバル管理者専用アカウントを 1 つ以上作成し、必要な状況でのみ使用します。
- 必要に応じて特定の管理者ロール (Exchange 管理者やパスワード管理者など) をこのロール専用の他のアカウントや IT 担当員のユーザー アカウントに割り当て、日常的な管理を行います。

専用のグローバル管理者アカウントに対し、次の操作を実行する必要もあります。

1. テスト ユーザー アカウントを使用して、ユーザー アカウント別または条件付きアクセスに基づく Azure 多要素認証 (MFA) 設定をテストし、MFA が予期されているとおりに正しく機能することを確認します。 MFA には、スマートフォンに送信される確認コードなど、セカンダリ認証方式が必要です。
2. MFA を必要とするグローバル管理者アカウントに対して条件付きアクセスポリシーを作成して有効にし、組織で利用可能な最も強力なセカンダリ認証方法を使用します。 詳細については、「[Azure 多要素認証](identity-access-prerequisites.md#protecting-administrator-accounts)」を参照してください。

追加の保護機能については、「[Office 365 グローバル管理者アカウントを保護する](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)」を参照してください。

> [!Note]
> サイバー攻撃のような緊急時の非常事態に対する緊急アカウントは、クラウド専用アカウントになります。 また、クラウド専用ではない (対象または永続的な) グローバル管理者アカウントを所有している場合もあります。 詳細については、「[Azure AD で緊急アクセス用管理者アカウントを管理する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)」を参照してください。

このセクションの結果は次のとおりです。

- グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、専用のグローバル管理者アカウントとなります。 これを確認するには、次の Azure Active Directory PowerShell for Graph コマンドを使用します。 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- サブスクリプションサービスを管理するその他のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。

> [!Note]
> Azure Active Directory PowerShell for Graph モジュールのインストールとサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  テスト ラボ環境でこの構成の実習を行うには、「[グローバル管理者アカウントを保護する テスト ラボ ガイド](protect-global-administrator-accounts-microsoft-365-test-environment.md)」を参照してください。 |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-global-admin)を確認できます。


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>オンデマンドの管理者を設定する

*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

このセクションでは、管理者アカウントが悪意のあるユーザーによる攻撃を受けやすい時間を短縮するために Azure AD Privileged Identity Management (PIM) をセットアップします。 PIM では、必要なときに必要なだけ管理者ロールをオンデマンドで割り当てることができます。  

管理者アカウントは永続的な管理者ではなく、対象管理者となります。 管理者ロールは、誰かが必要とするまで非アクティブとなります。 ライセンス認証プロセスを実行すると、特定の期間、管理者ロールが管理者アカウントに追加されます。 期限を過ぎると、PIM によって管理者アカウントから管理者ロールが削除されます。

PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。 または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。

Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。

サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pim)を確認できます。


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>特権アクセス管理

特権アクセス管理は、Office 365 テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、Office 365 テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。

この手順では、Office 365 テナントの特権アクセス管理を有効にして、組織の Office 365 データおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。Office 365 組織の特権アクセスは、次の 3 つの基本的な手順で開始します。

- 承認者のグループを作成する
- 特権アクセスを有効にする
- 承認ポリシーを作成する

構成が完了すると、特権アクセス管理によって、継続的な特権なしで運用できるようになり、継続的な管理アクセスが原因で発生する脆弱性に対抗する防御層が得られます。定義済みの承認ポリシーが関連付けられているタスクを特権アクセスで実行するには、承認が必要になります。承認ポリシーに含まれているタスクの実行を必要とするユーザーは、そのポリシーで定義されているタスクの実行に必要なアクセス許可を得るために、アクセス承認を要求して承認される必要があります。

Office 365 の特権アクセス管理を有効にするには、「[Office 365 の特権アクセス管理を構成する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」のトピックを参照してください。

詳細については、「[Office 365 の特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」のトピックを参照してください。


|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  テスト ラボ環境でこの構成の実習を行うには、「[特権アクセス管理テスト ラボ ガイド](privileged-access-microsoft-365-enterprise-dev-test-environment.md)」を参照してください。 |
|||

中間チェックポイントとして、この手順に対応する[終了条件](identity-exit-criteria.md#crit-identity-pam)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 2](../media/stepnumbers/Step2.png)| [パスワードをセキュリティで保護する](identity-secure-your-passwords.md) |

