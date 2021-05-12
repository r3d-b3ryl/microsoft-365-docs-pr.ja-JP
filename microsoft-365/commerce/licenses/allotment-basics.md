---
title: Allotment の基本
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
description: 新しいアロットメント機能について学習します。
ms.date: 03/17/2021
ms.openlocfilehash: 0910673ce54f3f977ed8ecbc3d6c77ac2ebad0cc
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331696"
---
# <a name="allotment-basics"></a><span data-ttu-id="87780-103">Allotment の基本</span><span class="sxs-lookup"><span data-stu-id="87780-103">Allotment basics</span></span>

<span data-ttu-id="87780-104">ライセンス割り当てでは、ライセンス制限を設定し、ライセンス割り当ての管理を選択した製品とライセンス制限にのみ委任できます。</span><span class="sxs-lookup"><span data-stu-id="87780-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="87780-105">Allotments は、グループ ベースのライセンスを使用して、ユーザーにライセンスを割り当てします。</span><span class="sxs-lookup"><span data-stu-id="87780-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="87780-106">ライセンス制限により、グループ内のユーザーに割り当てられるライセンスの数を制御できます。</span><span class="sxs-lookup"><span data-stu-id="87780-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="87780-107">したがって、グループ内のユーザー数が増えても、割り当てに設定したライセンス制限内にとどまる必要があります。</span><span class="sxs-lookup"><span data-stu-id="87780-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="87780-108">また、アロットメントの管理を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="87780-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="87780-109">委任された割り当ての所有者は管理センターにアクセスできますが、所有する割り当て内のライセンスのみを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="87780-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="87780-110">これにより、組織内のライセンス管理のより詳細な委任が提供されます。</span><span class="sxs-lookup"><span data-stu-id="87780-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87780-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="87780-111">Prerequisites</span></span>

<span data-ttu-id="87780-112">グループ ベースのライセンスのライセンス要件を満 [たす必要があります](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="87780-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="87780-113">ユーザーが使用できる任意の製品で割り当てを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87780-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="87780-114">Officeスイートとスタンドアロン製品</span><span class="sxs-lookup"><span data-stu-id="87780-114">Office suites and standalone products</span></span>
- <span data-ttu-id="87780-115">エンタープライズおよびモビリティ製品</span><span class="sxs-lookup"><span data-stu-id="87780-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="87780-116">Dynamics 365 製品</span><span class="sxs-lookup"><span data-stu-id="87780-116">Dynamics 365 products</span></span>

<span data-ttu-id="87780-117">次の製品は、アロットメントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="87780-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="87780-118">Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="87780-118">Microsoft Store apps</span></span>
- <span data-ttu-id="87780-119">永続的なソフトウェア、またはライセンスがない場合にユーザーに直接割り当てられるソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="87780-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="87780-120">Azure リソース</span><span class="sxs-lookup"><span data-stu-id="87780-120">Azure resources</span></span>

<span data-ttu-id="87780-121">割り当ての開始には、グローバル管理者またはライセンス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="87780-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="87780-122">作業を開始する</span><span class="sxs-lookup"><span data-stu-id="87780-122">Getting started</span></span>

<span data-ttu-id="87780-123">このアロットメント機能は、プライベート プレビューで使用できるユーザー数はわずかです。</span><span class="sxs-lookup"><span data-stu-id="87780-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="87780-124">参加する場合は、次のフォームに入力します [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) 。</span><span class="sxs-lookup"><span data-stu-id="87780-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>