---
title: デバイスのライセンスを管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: デバイスで使用するグループにライセンスを割り当てる方法について学習します。
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911484"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="a71c7-103">デバイスのライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="a71c7-103">Manage licenses for devices</span></span>

<span data-ttu-id="a71c7-104">Microsoft 365 Apps for enterprise (device) または Microsoft 365 Apps for Education (device) をお持ちのお客様は、Azure AD グループを使用してデバイスにライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="a71c7-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="a71c7-105">デバイスにライセンスがある場合、そのデバイスを使用するユーザーは、Microsoft 365 Apps for enterprise (以前は 365 ProPlus という名前Office使用できます。</span><span class="sxs-lookup"><span data-stu-id="a71c7-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="a71c7-106">たとえば、組織内のユーザーが使用する 20 台のノート PC とタブレットがあるとします。</span><span class="sxs-lookup"><span data-stu-id="a71c7-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="a71c7-107">各デバイスにライセンスを割り当てると、1 つのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずに Microsoft 365 Apps for enterprise を使用します。</span><span class="sxs-lookup"><span data-stu-id="a71c7-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a71c7-108">Microsoft 365 Apps for enterprise のデバイス ベースのライセンスは、一部の商用ユーザーおよび一部の教育ユーザー向けアドオン ライセンスとしてのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="a71c7-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="a71c7-109">商用ユーザーの場合、ライセンスは *Microsoft 365 Apps for enterprise (device)* であり、サブスクリプションのマイクロソフトエンタープライズ契約/マイクロソフトエンタープライズ契約利用できます。</span><span class="sxs-lookup"><span data-stu-id="a71c7-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="a71c7-110">教育のお客様の場合、ライセンスは *Microsoft 365 Apps for Education (デバイス)* であり、Education ソリューション (EES) の登録でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="a71c7-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="a71c7-111">詳細については、教育の可用性に関するブログ投稿 [を参照してください](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)。</span><span class="sxs-lookup"><span data-stu-id="a71c7-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="a71c7-112">商用利用の場合は、Microsoft アカウント担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a71c7-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="a71c7-113">まず、Azure Active Directory 管理センターでグループを作成し、そのグループにデバイスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71c7-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="a71c7-114">デバイスの要件、使用できるグループの種類、およびデバイス ライセンスを使用する Microsoft 365 Apps for enterprise を構成する方法など、デバイス ライセンスの詳細については [、「Microsoft 365 Apps for](/deployoffice/device-based-licensing)enterprise 用デバイス ベースのライセンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a71c7-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a71c7-115">この記事のタスクを完了するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a71c7-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="a71c7-116">デバイスへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="a71c7-116">Assign licenses to devices</span></span>

<span data-ttu-id="a71c7-117">グループにライセンスを割り当てると、グループ内のすべてのデバイスにライセンスが割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="a71c7-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="a71c7-118">割り当て可能なサブスクリプションは、1 つのグループに 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="a71c7-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="a71c7-119">Microsoft 365 管理センターで、[課金ライセンス]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a71c7-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a71c7-120">[ライセンス **] ページで\*\*\*\*、[Microsoft 365 Apps for Education (デバイス)]** または **[Microsoft 365 Apps for enterprise (device) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a71c7-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="a71c7-121">次のページで、サブスクリプションを選択し、[ライセンスの割り当て **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a71c7-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="a71c7-122">[グループに **ライセンスを割り当** てる] ウィンドウで、グループ名の入力を開始し、結果から選択してリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="a71c7-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="a71c7-123">[割り **当て] を** 選択し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a71c7-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="a71c7-124">デバイスからのライセンスの割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="a71c7-124">Unassign licenses from devices</span></span>

<span data-ttu-id="a71c7-125">グループからライセンスの割り当てを解除すると、グループ内のすべてのデバイスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="a71c7-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="a71c7-126">その後、すべてのアプリとその関連データが読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a71c7-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="a71c7-127">管理センターで、[課金ライセンス]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。</span><span class="sxs-lookup"><span data-stu-id="a71c7-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a71c7-128">[ライセンス **] ページで\*\*\*\*、[Microsoft 365 Apps for Education (デバイス)]** または **[Microsoft 365 Apps for enterprise (device) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a71c7-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="a71c7-129">次のページで、サブスクリプションを選択し、[その他のアクション] **を選択し**、[ライセンスの割り当 **て解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a71c7-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="a71c7-130">[ライセンスの **割り当て解除] ダイアログ** ボックスで、[割り当 **て解除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a71c7-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>