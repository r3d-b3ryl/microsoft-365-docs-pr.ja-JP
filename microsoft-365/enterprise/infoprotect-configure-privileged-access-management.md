---
title: '手順 7: 特権アクセス管理を構成する'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 特権アクセス管理について理解し、構成します。
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636990"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="24bf9-103">手順 7: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="24bf9-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="24bf9-104">*この手順はオプションであり、Microsoft 365 Enterprise の E5 および Advanced Compliance バージョンにのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="24bf9-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="24bf9-106">特権アクセス管理は、テナント内のタスクベースのアクティビティに対してジャストインタイムアクセスを指定するポリシーを構成することで有効になります。</span><span class="sxs-lookup"><span data-stu-id="24bf9-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="24bf9-107">機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="24bf9-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="24bf9-108">たとえば、テナント内の組織のメールボックスの設定にアクセスして変更するために、明示的な承認を必要とする特権アクセス管理ポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="24bf9-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="24bf9-109">この手順では、テナントで特権アクセス管理を有効にし、組織のデータおよび構成設定へのタスクベースのアクセスに対して追加のセキュリティを提供する特権アクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="24bf9-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="24bf9-110">組織での特権アクセスを開始するには、次の3つの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="24bf9-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="24bf9-111">承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="24bf9-111">Creating an approver's group</span></span>
- <span data-ttu-id="24bf9-112">特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="24bf9-112">Enabling privileged access</span></span>
- <span data-ttu-id="24bf9-113">承認ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="24bf9-113">Creating approval policies</span></span>

<span data-ttu-id="24bf9-p103">構成が完了すると、特権アクセス管理によって、継続的な特権なしで運用できるようになり、継続的な管理アクセスが原因で発生する脆弱性に対抗する防御層が得られます。定義済みの承認ポリシーが関連付けられているタスクを特権アクセスで実行するには、承認が必要になります。承認ポリシーに含まれているタスクの実行を必要とするユーザーは、そのポリシーで定義されているタスクの実行に必要なアクセス許可を得るために、アクセス承認を要求して承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="24bf9-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="24bf9-117">特権アクセス管理を有効にするには、「[特権アクセス管理を構成](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)する」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24bf9-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="24bf9-118">詳細については、「[特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24bf9-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="24bf9-120">テスト ラボ環境でこの構成の実習を行うには、「[特権アクセス管理テスト ラボ ガイド](privileged-access-microsoft-365-enterprise-dev-test-environment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24bf9-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="24bf9-121">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step7)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="24bf9-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="24bf9-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="24bf9-122">Next Step</span></span>

[<span data-ttu-id="24bf9-123">情報保護インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="24bf9-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
