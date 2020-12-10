---
title: Microsoft 365 での Insider リスク管理
description: Microsoft 365 で insider リスク管理を構成する方法について説明します。
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
ms.openlocfilehash: 3919523c703cb64ac443b3f0f73484efe9cea670
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613923"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="4da33-104">Microsoft 365 での Insider リスク管理</span><span class="sxs-lookup"><span data-stu-id="4da33-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="4da33-105">従業員には、さまざまなプラットフォームとサービスでデータを作成、管理、共有するためのアクセス権が増えています。</span><span class="sxs-lookup"><span data-stu-id="4da33-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="4da33-106">ほとんどの場合、組織には、コンプライアンス要件と従業員のプライバシー基準を満たす一方で、組織全体のリスクを特定して軽減するためのリソースとツールが制限されています。</span><span class="sxs-lookup"><span data-stu-id="4da33-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="4da33-107">これらのリスクには、偶発的な共有または悪意のある意図により、従業員や組織外の情報のデータ漏洩によってデータが盗まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="4da33-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="4da33-108">Microsoft 365 の Insider リスク管理では、すべてのサービスとサードパーティのインジケーターが使用され、リスクの高いユーザーアクティビティをすばやく特定、トリアージ、および操作することができます。</span><span class="sxs-lookup"><span data-stu-id="4da33-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="4da33-109">Microsoft 365 および Microsoft Graph のログを使用することにより、insider リスク管理では、リスク指標を識別し、これらのリスクを軽減するアクションを実行する特定のポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4da33-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="4da33-110">Microsoft 365 の insider リスク管理を構成する</span><span class="sxs-lookup"><span data-stu-id="4da33-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="4da33-111">組織の内部リスク管理を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4da33-111">Use the following steps to configure insider risk management for your organization:</span></span>

![Insider リスクソリューション insider リスク管理の手順](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="4da33-113">Microsoft 365 での [insider リスク管理](insider-risk-management.md) について</span><span class="sxs-lookup"><span data-stu-id="4da33-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="4da33-114">[Insider リスク管理を計画し、ライセンスを確認](insider-risk-management-plan.md)する</span><span class="sxs-lookup"><span data-stu-id="4da33-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="4da33-115">[Insider リスク管理設定](insider-risk-management-settings.md)を構成する</span><span class="sxs-lookup"><span data-stu-id="4da33-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="4da33-116">コネクタ & の[アクセス許可](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)と[ポリシーの前提条件](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)を構成する</span><span class="sxs-lookup"><span data-stu-id="4da33-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span></span>
5. <span data-ttu-id="4da33-117">[Insider リスク管理ポリシー](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)を作成および構成する</span><span class="sxs-lookup"><span data-stu-id="4da33-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="4da33-118">Insider リスク管理の詳細情報</span><span class="sxs-lookup"><span data-stu-id="4da33-118">More information about insider risk management</span></span>

- [<span data-ttu-id="4da33-119">Insider リスクポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4da33-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="4da33-120">インサイダー リスクのアラートを調査する</span><span class="sxs-lookup"><span data-stu-id="4da33-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="4da33-121">Insider のリスクケースに対処する</span><span class="sxs-lookup"><span data-stu-id="4da33-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)