---
title: Microsoft 365 での特権アクセス管理
description: Microsoft 365 で insider のリスク機能を構成する方法について説明します。
keywords: Microsoft 365、内部者のリスク、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 7fecfd7088f65effd6addddc51c1236c7b2af191
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613871"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="3c87f-104">Microsoft 365 での特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="3c87f-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="3c87f-105">Microsoft Exchange Online の機密情報または重要なネットワーク構成の設定にユーザーがアクセスできるようにすることは、侵害されたアカウントまたは内部の脅威のアクティビティに対して潜在的な経路です。</span><span class="sxs-lookup"><span data-stu-id="3c87f-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="3c87f-106">特権アクセス管理は、機密データへのアクセスを制限したり、重要な構成設定にアクセスしたりすることによって、違反から組織を保護し、コンプライアンスのベストプラクティスに準拠するために役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="3c87f-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="3c87f-107">管理者が継続的にアクセスするのではなく、管理者特権を必要とするタスクに対してジャストインタイムのアクセスルールが実装されています。</span><span class="sxs-lookup"><span data-stu-id="3c87f-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="3c87f-108">Microsoft 365 で Exchange Online の特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、継続的な管理アクセスの脆弱性に対する防御層を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="3c87f-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="3c87f-109">Microsoft 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="3c87f-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="3c87f-110">組織の特権アクセス管理を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c87f-110">Use the following steps to configure privileged access management for your organization:</span></span>

![Insider リスクソリューションの特権アクセス管理の手順](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="3c87f-112">Microsoft 365 での [特権アクセス管理](privileged-access-management-overview.md) について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c87f-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="3c87f-113">[承認者のグループ](privileged-access-management-configuration.md#step-1-create-an-approvers-group)を作成する</span><span class="sxs-lookup"><span data-stu-id="3c87f-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="3c87f-114">[特権アクセス管理](privileged-access-management-configuration.md#step-2-enable-privileged-access)を有効にする</span><span class="sxs-lookup"><span data-stu-id="3c87f-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="3c87f-115">[アクセスポリシー](privileged-access-management-configuration.md#step-3-create-an-access-policy)を作成する</span><span class="sxs-lookup"><span data-stu-id="3c87f-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="3c87f-116">[特権アクセス要求](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)を送信/承認する</span><span class="sxs-lookup"><span data-stu-id="3c87f-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="3c87f-117">特権アクセス管理の詳細情報</span><span class="sxs-lookup"><span data-stu-id="3c87f-117">More information about privileged access management</span></span>

- [<span data-ttu-id="3c87f-118">特権アクセス管理についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3c87f-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)