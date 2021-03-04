---
title: Microsoft 365 での特権アクセス管理
description: Microsoft 365 全体でインサイダー リスク機能を構成する方法について説明します。
keywords: Microsoft 365、インサイダー リスク、コンプライアンス
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
- m365solution-scenario
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423810"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="e6dd2-104">Microsoft 365 での特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="e6dd2-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="e6dd2-105">一部のユーザーが機密情報や重要なネットワーク構成設定にアクセスすると、Microsoft Exchange Onlineアカウントや内部脅威アクティビティの潜在的な経路になります。</span><span class="sxs-lookup"><span data-stu-id="e6dd2-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="e6dd2-106">特権アクセス管理は、組織を侵害から保護するのに役立ち、機密データへの永続的なアクセスや重要な構成設定へのアクセスを制限することで、コンプライアンスのベスト プラクティスを満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6dd2-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="e6dd2-107">管理者が一定のアクセス権を持つ代わりに、管理者特権のアクセス許可を必要とするタスクに対して Just-in-time アクセス ルールが実装されます。</span><span class="sxs-lookup"><span data-stu-id="e6dd2-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="e6dd2-108">Microsoft 365 で Exchange Online の特権アクセス管理を有効にすると、組織はゼロの特権で動作し、管理者アクセスの永続的な脆弱性に対する防御層を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e6dd2-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="e6dd2-109">Microsoft 365 の特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="e6dd2-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="e6dd2-110">組織の特権アクセス管理を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6dd2-110">Use the following steps to configure privileged access management for your organization:</span></span>

![Insider リスク ソリューションの特権アクセス管理手順](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="e6dd2-112">Microsoft 365 [での特権](privileged-access-management-overview.md) アクセス管理の詳細</span><span class="sxs-lookup"><span data-stu-id="e6dd2-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="e6dd2-113">承認者 [のグループを作成する](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="e6dd2-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="e6dd2-114">特権 [アクセス管理を有効にする](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="e6dd2-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="e6dd2-115">アクセス ポリシー [の作成](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="e6dd2-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="e6dd2-116">特権アクセス要求 [の送信および承認](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="e6dd2-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="e6dd2-117">特権アクセス管理の詳細</span><span class="sxs-lookup"><span data-stu-id="e6dd2-117">More information about privileged access management</span></span>

- [<span data-ttu-id="e6dd2-118">特権アクセス管理に関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e6dd2-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)