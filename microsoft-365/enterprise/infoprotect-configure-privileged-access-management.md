---
title: '手順 6: Office 365 の特権アクセス管理を構成する'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365 の特権アクセス管理について理解して構成します。
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304157"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="56972-103">手順 6: Office 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="56972-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="56972-104">*この手順はオプションであり、Microsoft 365 Enterprise の E5 および Advanced Compliance バージョンにのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="56972-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="56972-p101">特権アクセス管理は、Office 365 テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、Office 365 テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="56972-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="56972-p102">この手順では、Office 365 テナントの特権アクセス管理を有効にして、組織の Office 365 データおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。Office 365 組織の特権アクセスは、次の 3 つの基本的な手順で開始します。</span><span class="sxs-lookup"><span data-stu-id="56972-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="56972-110">承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="56972-110">Creating an approver's group</span></span>
- <span data-ttu-id="56972-111">特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="56972-111">Enabling privileged access</span></span>
- <span data-ttu-id="56972-112">承認ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="56972-112">Creating approval policies</span></span>

<span data-ttu-id="56972-p103">構成が完了すると、特権アクセス管理によって、継続的な特権なしで運用できるようになり、継続的な管理アクセスが原因で発生する脆弱性に対抗する防御層が得られます。定義済みの承認ポリシーが関連付けられているタスクを特権アクセスで実行するには、承認が必要になります。承認ポリシーに含まれているタスクの実行を必要とするユーザーは、そのポリシーで定義されているタスクの実行に必要なアクセス許可を得るために、アクセス承認を要求して承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="56972-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="56972-116">Office 365 の特権アクセス管理を有効にするには、「[Office 365 の特権アクセス管理を構成する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56972-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="56972-117">詳細については、「[Office 365 の特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56972-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="56972-118">結果</span><span class="sxs-lookup"><span data-stu-id="56972-118">Results</span></span>

<span data-ttu-id="56972-119">この手順の結果、組織にとって重要なデータと構成設定に対する Just-In-Time アクセス制御が有効になり、Office 365 のセキュリティが向上しました。</span><span class="sxs-lookup"><span data-stu-id="56972-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="56972-120">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="56972-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="56972-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="56972-121">Next Step</span></span>

[<span data-ttu-id="56972-122">情報保護インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="56972-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)