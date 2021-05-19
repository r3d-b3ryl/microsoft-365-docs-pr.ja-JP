---
title: デバイスのライセンスを管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: デバイスで使用するグループにライセンスを割り当てる方法について学習します。
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535664"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="b1c8c-103">デバイスのライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="b1c8c-103">Manage licenses for devices</span></span>

<span data-ttu-id="b1c8c-104">Education (デバイス) Microsoft 365 Apps for enterprise (デバイス) または Microsoft 365 Appsがある場合は、Azure AD グループを使用してデバイスにライセンスを割りADできます。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="b1c8c-105">デバイスにライセンスがある場合、そのデバイスを使用するユーザーは、Microsoft 365 Apps for enterpriseを使用Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="b1c8c-106">たとえば、組織内のユーザーが使用する 20 台のノート PC とタブレットがあるとします。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="b1c8c-107">各デバイスにライセンスを割り当てると、1 つのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずにMicrosoft 365 Apps for enterpriseを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1c8c-108">一部の商用Microsoft 365 Apps for enterprise一部の教育顧客向けアドオン ライセンスとしてのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="b1c8c-109">商用のお客様の場合、ライセンスは Microsoft 365 Apps for enterprise *(デバイス)* であり、サブスクリプションのEnterprise Agreement/Enterprise Agreement利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="b1c8c-110">教育のお客様の場合、ライセンスはMicrosoft 365 Apps (デバイス) であり、Education ソリューションの登録 *(EES)* を通じてのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="b1c8c-111">詳細については、教育の可用性に関するブログ投稿 [を参照してください](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="b1c8c-112">商用利用の場合は、Microsoft アカウント担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="b1c8c-113">まず、管理センターでグループをAzure Active Directoryし、そのグループにデバイスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="b1c8c-114">デバイスの要件、使用できるグループの種類、デバイス ライセンスを使用する Microsoft 365 Apps for enterprise を構成する方法など、デバイス ライセンスの詳細については、「Microsoft 365 Apps for enterprise のデバイス ベースのライセンス」[を参照してください](/deployoffice/device-based-licensing)。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1c8c-115">この記事のタスクを完了するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="b1c8c-116">デバイスへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="b1c8c-116">Assign licenses to devices</span></span>

<span data-ttu-id="b1c8c-117">グループにライセンスを割り当てると、グループ内のすべてのデバイスにライセンスが割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="b1c8c-118">割り当て可能なサブスクリプションは、1 つのグループに 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="b1c8c-119">管理センター Microsoft 365、[課金ライセンス]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="b1c8c-120">[ライセンス **] ページで**、[教育Microsoft 365 Apps **(デバイス)** または Microsoft 365 Apps for enterprise **(デバイス) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="b1c8c-121">次のページで、サブスクリプションを選択し、[ライセンスの割り当て **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="b1c8c-122">[グループに **ライセンスを割り当** てる] ウィンドウで、グループ名の入力を開始し、結果から選択してリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="b1c8c-123">[割り **当て] を** 選択し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="b1c8c-124">デバイスからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="b1c8c-124">Unassign licenses from devices</span></span>

<span data-ttu-id="b1c8c-125">グループからライセンスの割り当てを解除すると、グループ内のすべてのデバイスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="b1c8c-126">その後、すべてのアプリとその関連データが読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="b1c8c-127">管理センターで、[課金ライセンス]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="b1c8c-128">[ライセンス **] ページで**、[教育Microsoft 365 Apps **(デバイス)** または Microsoft 365 Apps for enterprise **(デバイス) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="b1c8c-129">次のページで、サブスクリプションを選択し、3 つのドット (その他のアクション) を選択し、[ライセンスの割り当て解除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-129">On the next page, choose a subscription, select the three dots (more actions), and then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="b1c8c-130">[ライセンスの **割り当て解除] ダイアログ** ボックスで、[割り当 **て解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b1c8c-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
