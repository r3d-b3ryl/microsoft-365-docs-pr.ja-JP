---
title: 「デバイスのライセンスを管理する」
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: デバイスで使用するためにライセンスをグループに割り当てる方法について説明します。
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242322"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="42abf-103">「デバイスのライセンスを管理する」</span><span class="sxs-lookup"><span data-stu-id="42abf-103">Manage licenses for devices</span></span>

<span data-ttu-id="42abf-104">Office 365 ProPlus for 教育 (デバイス) を使用している場合は、Azure AD グループを使用して、デバイスにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="42abf-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="42abf-105">デバイスにライセンスがある場合は、そのデバイスを使用するすべてのユーザーが Office 365 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="42abf-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="42abf-106">たとえば、組織内のユーザーによって使用される20個のラップトップおよびタブレットがあるとします。</span><span class="sxs-lookup"><span data-stu-id="42abf-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="42abf-107">各デバイスにライセンスを割り当てると、デバイスのいずれかにログインする各ユーザーは、自分のライセンスを必要とせずに Office 365 を使用します。</span><span class="sxs-lookup"><span data-stu-id="42abf-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42abf-108">Office 365 ProPlus (デバイス) は、教育用の A3 および A5 ボリュームライセンスのお客様のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="42abf-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="42abf-109">最初に、Azure Active Directory 管理センターでグループを作成し、そのグループにデバイスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="42abf-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="42abf-110">デバイスの要件、使用できるグループの種類、Office 365 ProPlus を使用してデバイスライセンスを使用するように構成する方法など、デバイスのライセンスの詳細については、「 [device licensing For office 365 ProPlus For 教育のお客様](https://go.microsoft.com/fwlink/p/?linkid=2094216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42abf-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42abf-111">この記事のタスクを完了するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42abf-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="42abf-112">デバイスへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="42abf-112">Assign licenses to devices</span></span>

<span data-ttu-id="42abf-113">グループにライセンスを割り当てるときは、グループ内のすべてのデバイスにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="42abf-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="42abf-114">1つのグループに割り当てることができるサブスクリプションは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="42abf-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="42abf-115">Microsoft 365 管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="42abf-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="42abf-116">[**ライセンス**] ページで、[ **Office 365 ProPlus for 教育 (デバイス)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42abf-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="42abf-117">[ **Office 365 ProPlus (デバイス)** ] ページで、サブスクリプションを選択し、[**ライセンスの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42abf-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="42abf-118">[**グループへのライセンスの割り当て**] ウィンドウで、グループ名の入力を開始し、結果からそれを選択して一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="42abf-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="42abf-119">[**割り当て**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42abf-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="42abf-120">デバイスからライセンスを割り当て解除する</span><span class="sxs-lookup"><span data-stu-id="42abf-120">Unassign licenses from devices</span></span>

<span data-ttu-id="42abf-121">グループからライセンスを割り当てを解除するときは、グループ内のすべてのデバイスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="42abf-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="42abf-122">すべてのアプリとそれに関連付けられたデータは、読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="42abf-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="42abf-123">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="42abf-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="42abf-124">[**ライセンス**] ページで、[ **Office 365 ProPlus for 教育 (デバイス)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42abf-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="42abf-125">[ **Office 365 ProPlus (デバイス)** ] ページで、サブスクリプションを選択し、[**その他のアクション**] を選択して、[**ライセンスの割り当て解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42abf-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="42abf-126">[**ライセンスの割り当ての解除**] ダイアログボックスで、[**割り当て**の解除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42abf-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>