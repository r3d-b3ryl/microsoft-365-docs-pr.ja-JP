---
title: Microsoft 365 の Insider リスク管理
description: Microsoft 365 でインサイダー リスク管理を構成する方法について説明します。
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
ms.openlocfilehash: 644fe1894cddcfea5bd45fcbd68e168ea8a1dca8
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423578"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="eec8a-104">Microsoft 365 の Insider リスク管理</span><span class="sxs-lookup"><span data-stu-id="eec8a-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="eec8a-105">従業員は、幅広いプラットフォームとサービスでデータを作成、管理、共有するためのアクセスが増えています。</span><span class="sxs-lookup"><span data-stu-id="eec8a-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="eec8a-106">ほとんどの場合、組織には、コンプライアンス要件と従業員のプライバシー基準を満たしながら、組織全体のリスクを特定および軽減するためのリソースとツールが限られています。</span><span class="sxs-lookup"><span data-stu-id="eec8a-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="eec8a-107">これらのリスクには、従業員を退出してデータを盗み、偶発的な過剰共有や悪意のある意図による組織外の情報のデータ漏洩が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eec8a-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="eec8a-108">Microsoft 365 の Insider リスク管理では、サービスとサードパーティのインジケーターの全幅を使用して、リスクの高いユーザー アクティビティをすばやく特定し、トリアージし、行動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eec8a-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="eec8a-109">Microsoft 365 および Microsoft Graph のログを使用すると、インサイダー リスク管理を使用して、リスク インジケーターを特定し、これらのリスクを軽減するためのアクションを実行するための特定のポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="eec8a-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="eec8a-110">Microsoft 365 のインサイダー リスク管理を構成する</span><span class="sxs-lookup"><span data-stu-id="eec8a-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="eec8a-111">組織のインサイダー リスク管理を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="eec8a-111">Use the following steps to configure insider risk management for your organization:</span></span>

![Insider リスク ソリューションのインサイダー リスク管理手順](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="eec8a-113">Microsoft 365 [のイン](insider-risk-management.md) サイダー リスク管理の詳細</span><span class="sxs-lookup"><span data-stu-id="eec8a-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="eec8a-114">インサイ [ダー リスク管理を計画し、ライセンスを確認する](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="eec8a-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="eec8a-115">内部 [リスク管理の設定を構成する](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eec8a-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="eec8a-116">アクセス [許可とポリシー](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) の [前提条件をコネクタ&構成する](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span><span class="sxs-lookup"><span data-stu-id="eec8a-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span></span>
5. <span data-ttu-id="eec8a-117">インサイダー リスク管理 [ポリシーの作成と構成](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="eec8a-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="eec8a-118">インサイダー リスク管理の詳細</span><span class="sxs-lookup"><span data-stu-id="eec8a-118">More information about insider risk management</span></span>

- [<span data-ttu-id="eec8a-119">インサイダー リスク ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="eec8a-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="eec8a-120">インサイダー リスクのアラートを調査する</span><span class="sxs-lookup"><span data-stu-id="eec8a-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="eec8a-121">インサイダー リスク ケースに関する法律</span><span class="sxs-lookup"><span data-stu-id="eec8a-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)