---
title: サービス単位の基本
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: 新しい追加機能について説明します。
ms.openlocfilehash: c8c472fbf30bb898f9a10eca778ee7c668c8c388
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402416"
---
# <a name="allotment-basics"></a><span data-ttu-id="9916a-103">サービス単位の基本</span><span class="sxs-lookup"><span data-stu-id="9916a-103">Allotment basics</span></span>

<span data-ttu-id="9916a-104">ライセンス認証を使用すると、ライセンスの制限を設定し、選択した製品とライセンスの制限のみにライセンスの割り当ての管理を委任できます。</span><span class="sxs-lookup"><span data-stu-id="9916a-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="9916a-105">サービス単位グループベースのライセンスを使用して、ユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9916a-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="9916a-106">ライセンス制限により、グループ内のユーザーに割り当てられているライセンスの数を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="9916a-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="9916a-107">グループ内のユーザー数が増加しても、割り当てられたライセンスの制限を超えないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9916a-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="9916a-108">また、会社間の管理を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="9916a-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="9916a-109">委任されたサービス単位所有者は管理センターにアクセスできますが、自分が所有しているライセンス数でのみライセンスを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="9916a-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="9916a-110">これにより、組織内でのライセンス管理をより細かく委任できます。</span><span class="sxs-lookup"><span data-stu-id="9916a-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9916a-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="9916a-111">Prerequisites</span></span>

<span data-ttu-id="9916a-112">[グループベースのライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)のライセンス要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="9916a-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="9916a-113">ユーザーが利用できる製品であれば、次のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9916a-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="9916a-114">Office スイートとスタンドアロン製品</span><span class="sxs-lookup"><span data-stu-id="9916a-114">Office suites and standalone products</span></span>
- <span data-ttu-id="9916a-115">エンタープライズおよび Mobility 製品</span><span class="sxs-lookup"><span data-stu-id="9916a-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="9916a-116">Dynamics 365 製品</span><span class="sxs-lookup"><span data-stu-id="9916a-116">Dynamics 365 products</span></span>

<span data-ttu-id="9916a-117">次の製品は、リソースの利用可能性として使用できません。</span><span class="sxs-lookup"><span data-stu-id="9916a-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="9916a-118">Microsoft ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="9916a-118">Microsoft Store apps</span></span>
- <span data-ttu-id="9916a-119">ライセンスがない場合に、ユーザーに直接割り当てられている永続的なソフトウェア、またはソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="9916a-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="9916a-120">Azure リソース</span><span class="sxs-lookup"><span data-stu-id="9916a-120">Azure resources</span></span>

<span data-ttu-id="9916a-121">サービス単位の使用を開始するには、グローバルまたはライセンス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9916a-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="9916a-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="9916a-122">Getting started</span></span>

<span data-ttu-id="9916a-123">この機能は、個人用のプレビューでは少数のお客様のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="9916a-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="9916a-124">参加に興味がある場合は、次のフォームに記入 [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) してください。</span><span class="sxs-lookup"><span data-stu-id="9916a-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
