---
title: '手順 2: 全体管理者アカウントを保護する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 管理者アカウントについて理解し、管理者アカウントが最大限に保護されるよう構成します。
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869636"
---
# <a name="step-2-protect-global-administrator-accounts"></a>手順 2: 全体管理者アカウントを保護する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、管理者アカウントを可能な限り保護することで、組織へのデジタル攻撃を防止できます。そのためには、次のことを行う必要があります。

- 非常に[強力なパスワード](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)を設定した全体管理者専用アカウントを作成し、必要な状況でのみ使用します。
- 必要に応じて特定の管理者ロール (Exchange 管理者やパスワード管理者など) を IT 担当員のユーザー アカウントに割り当て、日常的な管理を行います。

専用の全体管理者アカウントに対し、次の操作を実行する必要もあります。

1. テスト ユーザー アカウントを使用して、ユーザー アカウント別または条件付きアクセスに基づく多要素認証 (MFA) 設定をテストし、MFA が予期されているとおりに正しく機能することを確認します。MFA は、セカンダリ認証方式 (スマートフォンに送信される確認コードなど) を必要とします。
2. 専用の Office 365 全体管理者アカウントごとに MFA を構成し、組織で使用可能なセカンダリ認証のうち最も強力な認証を使用します。詳細については、「[多要素認証をセットアップする](identity-multi-factor-authentication.md)」を参照してください。
2. 条件付きアクセス ポリシーを使用して、全体管理者アカウントに対して MFA を要求します。詳細については、「[Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts)」 (管理者アカウントの保護) を参照してください。
4. Office 365 Cloud App Security ポリシーを使用して、全体管理者アカウントの活動を監視します。詳細については、[Office 365 のセキュリティ強化の構成](infoprotect-configure-increased-security-office-365.md)に関するページを参照してください。

構成の詳細については、「[Office 365 グローバル管理者アカウントの保護](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)」を参照してください。

> [!Note]
> 組織では、サイバー攻撃などの緊急事態に備えた対策として、全体管理者などの特権アカウントを作成するときにはクラウド専用 ID を使用してください。詳細については、「[Azure AD で緊急アクセス用管理者アカウントを管理する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)」を参照してください。

この手順の結果は次のとおりです。

- サブスクリプションで全体管理者ロールが付与されているユーザー アカウントだけが、新しい専用全体管理者アカウントになります。これを確認するには、次の Windows Azure AD V2 PowerShell コマンドを使用します。 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。

> [!Note]
> Azure AD V2 PowerShell モジュールのインストールとサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: 全体管理者アカウントを保護する](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-global-admin)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [オンデマンド全体管理者をセットアップする](identity-privileged-identity-management.md) |

