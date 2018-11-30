---
title: '手順 3: オンデマンドで全体管理者をセットアップする'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Privileged Identity Management について理解し、構成します。
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869190"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="aa7b0-103">手順 3: オンデマンドで全体管理者をセットアップする</span><span class="sxs-lookup"><span data-stu-id="aa7b0-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="aa7b0-104">*この手順はオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="aa7b0-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="aa7b0-p101">この手順では、全体管理者アカウントが悪意のあるユーザーによる攻撃を受けやすい時間を短縮するために Azure AD Privileged Identity Management (PIM) をセットアップします。PIM では、必要なときに必要なだけ全体管理者ロールをオンデマンドで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="aa7b0-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="aa7b0-p102">全体管理者アカウントは永続的な管理者になるのではなく、対象の管理者になります。全体管理者ロールは、だれかに必要とされるまで非アクティブとなります。その後、アクティブ化プロセスを完了し、一定の時間、全体管理者アカウントに全体管理者ロールを追加します。この時間が経過すると、PIM で全体管理者アカウントから全体管理者ロールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="aa7b0-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="aa7b0-p103">PIM は、Microsoft 365 Enterprise E5 に含まれる、Azure Active Directory Premium P2 で利用可能です。あるいは、全体管理者アカウントに対して個々の Azure Active Directory Premium P2 ライセンスを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa7b0-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="aa7b0-113">Azure AD テナントと全体管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7b0-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="aa7b0-114">サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7b0-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="aa7b0-115">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-pim)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aa7b0-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="aa7b0-116">次の手順</span><span class="sxs-lookup"><span data-stu-id="aa7b0-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="aa7b0-117">パスワードのリセットを簡素化する</span><span class="sxs-lookup"><span data-stu-id="aa7b0-117">Simplify password resets</span></span>](identity-password-reset.md) |

