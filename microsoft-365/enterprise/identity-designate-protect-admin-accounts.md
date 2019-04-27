---
title: '手順 2: 特権 ID をセキュリティで保護する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 管理者アカウントについて理解し、管理者アカウントが最大限に保護されるよう構成します。
ms.openlocfilehash: 0be82fc6f431001c69e79a0a26007c54a87424c3
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353089"
---
# <a name="step-2-secure-your-privileged-identities"></a>手順 2: 特権 ID をセキュリティで保護する

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>グローバル管理者アカウントを保護する

*これは必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

このセクションでは、管理者アカウントを可能な限り保護することで、組織へのデジタル攻撃を防止できます。 そのためには、次のことを行う必要があります。

- 非常に[強力なパスワード](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)を設定した全体管理者専用アカウントを作成し、必要な状況でのみ使用します。
- 必要に応じて特定の管理者ロール (Exchange 管理者やパスワード管理者など) を IT 担当員のユーザー アカウントに割り当て、日常的な管理を行います。

専用の全体管理者アカウントに対し、次の操作を実行する必要もあります。

1. テスト ユーザー アカウントを使用して、ユーザー アカウント別または条件付きアクセスに基づく多要素認証 (MFA) 設定をテストし、MFA が予期されているとおりに正しく機能することを確認します。MFA は、セカンダリ認証方式 (スマートフォンに送信される確認コードなど) を必要とします。
2. 専用の Office 365 全体管理者アカウントごとに MFA を構成し、組織で使用可能なセカンダリ認証のうち最も強力な認証を使用します。詳細については、「[多要素認証をセットアップする](identity-multi-factor-authentication.md#identity-mfa)」を参照してください。
2. 条件付きアクセス ポリシーを使用して、全体管理者アカウントに対して MFA を要求します。詳細については、「[Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts)」 (管理者アカウントの保護) を参照してください。

構成の詳細については、「[Office 365 グローバル管理者アカウントの保護](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)」を参照してください。

> [!Note]
> 組織では、サイバー攻撃などの緊急事態に備えた対策として、全体管理者などの特権アカウントを作成するときにはクラウド専用 ID を使用してください。詳細については、「[Azure AD で緊急アクセス用管理者アカウントを管理する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)」を参照してください。

このセクションの手順を実行すると次のような結果が得られます。

- グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。 これを確認するには、次の Azure Active Directory PowerShell for Graph コマンドを使用します。 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。

> [!Note]
> Azure Active Directory PowerShell for Graph モジュールのインストールとサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: 全体管理者アカウントを保護する](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-global-admin)を確認できます。


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>オンデマンド グローバル管理者をセットアップする

*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

このセクションでは、グローバル管理者アカウントが悪意のあるユーザーによる攻撃を受けやすい時間を短縮するために Azure AD Privileged Identity Management (PIM) をセットアップします。 PIM では、必要なときに必要なだけ全体管理者ロールをオンデマンドで割り当てることができます。  

全体管理者アカウントは永続的な管理者になるのではなく、対象の管理者になります。全体管理者ロールは、だれかに必要とされるまで非アクティブとなります。その後、アクティブ化プロセスを完了し、一定の時間、全体管理者アカウントに全体管理者ロールを追加します。この時間が経過すると、PIM で全体管理者アカウントから全体管理者ロールが削除されます。

PIM は、Microsoft 365 Enterprise E5 に含まれる、Azure Active Directory Premium P2 で利用可能です。あるいは、全体管理者アカウントに対して個々の Azure Active Directory Premium P2 ライセンスを購入することもできます。

Azure AD テナントと全体管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。

サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pim)を確認できます。


## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [ハイブリッド ID の構成](identity-azure-ad-connect.md) |

