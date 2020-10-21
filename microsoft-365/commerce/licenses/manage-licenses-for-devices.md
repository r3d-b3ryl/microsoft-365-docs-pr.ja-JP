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
description: デバイスで使用するためにライセンスをグループに割り当てる方法について説明します。
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638185"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="74f91-103">デバイスのライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="74f91-103">Manage licenses for devices</span></span>

<span data-ttu-id="74f91-104">Microsoft 365 for enterprise (デバイス) または Microsoft 365 Apps for エデュケーション (デバイス) を使用している場合は、Azure AD グループを使用して、デバイスにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="74f91-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="74f91-105">デバイスにライセンスがある場合、そのデバイスを使用するすべてのユーザーは、エンタープライズ向けの Microsoft 365 Apps (以前の Office 365 ProPlus) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="74f91-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="74f91-106">たとえば、組織内のユーザーによって使用される20個のラップトップおよびタブレットがあるとします。</span><span class="sxs-lookup"><span data-stu-id="74f91-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="74f91-107">各デバイスにライセンスを割り当てると、いずれかのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずにエンタープライズ向けの Microsoft 365 アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="74f91-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f91-108">Microsoft 365 用アプリのデバイスベースライセンスは、市販のお客様や教育機関のお客様のためのアドオンライセンスとしてのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="74f91-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="74f91-109">商用のお客様の場合、ライセンスは *Microsoft 365 enterprise 用アプリ (デバイス)* で、エンタープライズアグリーメント/エンタープライズアグリーメントのサブスクリプションを通じてのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="74f91-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="74f91-110">教育機関のお客様の場合、ライセンスは *Microsoft 365 の教育機関向けアプリ (デバイス)* で、教育機関向けの登録 (EES) によってのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="74f91-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="74f91-111">詳細については、「教育の [利用可能性](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)」のブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f91-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="74f91-112">市販の可用性については、Microsoft アカウント担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="74f91-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="74f91-113">最初に、Azure Active Directory 管理センターでグループを作成し、そのグループにデバイスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="74f91-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="74f91-114">デバイスライセンスの詳細については、デバイスの要件、使用できるグループの種類、およびデバイスライセンスを使用するように Microsoft 365 Apps for enterprise を構成する方法について説明します。「 [microsoft 365 アプリ用のデバイスベースライセンス](https://go.microsoft.com/fwlink/p/?linkid=2094216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f91-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f91-115">この記事のタスクを完了するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="74f91-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="74f91-116">デバイスへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="74f91-116">Assign licenses to devices</span></span>

<span data-ttu-id="74f91-117">グループにライセンスを割り当てるときは、グループ内のすべてのデバイスにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="74f91-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="74f91-118">1つのグループに割り当てることができるサブスクリプションは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="74f91-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="74f91-119">Microsoft 365 管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="74f91-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="74f91-120">[ **ライセンス** ] ページで、[ **microsoft 365 apps for エデュケーション (デバイス)** ] または [ **microsoft 365 apps for enterprise (デバイス)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f91-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="74f91-121">次のページでサブスクリプションを選択し、[ **ライセンスの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f91-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="74f91-122">[ **グループへのライセンスの割り当て** ] ウィンドウで、グループ名の入力を開始し、結果からそれを選択して一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="74f91-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="74f91-123">[ **割り当て**] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f91-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="74f91-124">デバイスからライセンスを割り当て解除する</span><span class="sxs-lookup"><span data-stu-id="74f91-124">Unassign licenses from devices</span></span>

<span data-ttu-id="74f91-125">グループからライセンスを割り当てを解除するときは、グループ内のすべてのデバイスからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="74f91-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="74f91-126">すべてのアプリとそれに関連付けられたデータは、読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="74f91-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="74f91-127">管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="74f91-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="74f91-128">[ **ライセンス** ] ページで、[ **microsoft 365 apps for エデュケーション (デバイス)** ] または [ **microsoft 365 apps for enterprise (デバイス)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f91-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="74f91-129">次のページで、サブスクリプションを選択し、[ **その他のアクション**] を選択して、[ **ライセンスの割り当て解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f91-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="74f91-130">[ **ライセンスの割り当ての解除** ] ダイアログボックスで、[ **割り当て**の解除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74f91-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>