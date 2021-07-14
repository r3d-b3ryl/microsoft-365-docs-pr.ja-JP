---
title: インサイダーリスクMicrosoft 365
description: インサイダー リスク管理を構成する方法については、Microsoft 365。
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
ms.openlocfilehash: bee4c2d01579733ff7b1c5583b00cdd48e437af2
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430542"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="5cb8f-104">インサイダーリスクMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="5cb8f-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="5cb8f-105">従業員は、幅広いプラットフォームとサービスでデータを作成、管理、共有するためのアクセスが増えています。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="5cb8f-106">ほとんどの場合、組織には、コンプライアンス要件と従業員のプライバシー基準を満たしながら、組織全体のリスクを特定および軽減するためのリソースとツールが限られています。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="5cb8f-107">これらのリスクには、従業員を退出してデータを盗み、偶発的な過剰共有や悪意のある意図による組織外の情報のデータ漏洩が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="5cb8f-108">Microsoft 365の Insider リスク管理は、サービスとサードパーティのインジケーターの全幅を使用して、リスクの高いユーザー アクティビティをすばやく特定し、トリアージし、行動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="5cb8f-109">Microsoft 365 および Microsoft Graph のログを使用すると、インサイダー リスク管理を使用して、リスク インジケーターを特定し、これらのリスクを軽減するためのアクションを実行するための特定のポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

<span data-ttu-id="5cb8f-110">以下のビデオを見て、組織の価値、文化、およびユーザー エクスペリエンスを優先しながら、組織がリスクを防止、検出、および含むのに役立つインサイダー リスク管理の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-110">Watch the videos below to learn how insider risk management can help your organization prevent, detect, and contain risks while prioritizing your organization values, culture, and user experience:</span></span>
<br>
<br>

<span data-ttu-id="5cb8f-111">**開発に関するインサイダー&管理ソリューション**:</span><span class="sxs-lookup"><span data-stu-id="5cb8f-111">**Insider risk management solution & development**:</span></span>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

<span data-ttu-id="5cb8f-112">**Insider リスク管理ワークフロー**:</span><span class="sxs-lookup"><span data-stu-id="5cb8f-112">**Insider risk management workflow**:</span></span>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="5cb8f-113">インサイダー リスク管理を構成Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cb8f-113">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="5cb8f-114">組織のインサイダー リスク管理を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cb8f-114">Use the following steps to configure insider risk management for your organization:</span></span>

![Insider リスク ソリューションのインサイダー リスク管理手順](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="5cb8f-116">インサイダー[リスク管理の詳細については](insider-risk-management.md)、Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cb8f-116">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="5cb8f-117">インサイ [ダー リスク管理を計画し、ライセンスを確認する](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="5cb8f-117">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="5cb8f-118">内部 [リスク管理の設定を構成する](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5cb8f-118">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="5cb8f-119">アクセス [許可とポリシー](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) の [前提条件をコネクタ&構成する](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span><span class="sxs-lookup"><span data-stu-id="5cb8f-119">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span></span>
5. <span data-ttu-id="5cb8f-120">インサイダー リスク管理 [ポリシーの作成と構成](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="5cb8f-120">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="5cb8f-121">インサイダー リスク管理の詳細</span><span class="sxs-lookup"><span data-stu-id="5cb8f-121">More information about insider risk management</span></span>

- [<span data-ttu-id="5cb8f-122">インサイダー リスク ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="5cb8f-122">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="5cb8f-123">インサイダー リスク アクティビティを調査する</span><span class="sxs-lookup"><span data-stu-id="5cb8f-123">Investigate insider risk activities</span></span>](insider-risk-management-activities.md)
- [<span data-ttu-id="5cb8f-124">インサイダー リスク ケースに関する法律</span><span class="sxs-lookup"><span data-stu-id="5cb8f-124">Act on insider risk cases</span></span>](insider-risk-management-cases.md)