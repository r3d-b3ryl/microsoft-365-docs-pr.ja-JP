---
title: 展開グループへのデバイスの割り当て
description: デバイスを配置する展開グループを指定する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985638"
---
# <a name="assign-devices-to-a-deployment-group"></a><span data-ttu-id="0cee4-104">展開グループへのデバイスの割り当て</span><span class="sxs-lookup"><span data-stu-id="0cee4-104">Assign devices to a deployment group</span></span>

<span data-ttu-id="0cee4-105">Microsoft マネージド デスクトップさまざまな展開グループにデバイスを割り当てることができますが、管理ポータルを使用して、デバイスがデバイスに割り当てられているグループを指定または変更できます。</span><span class="sxs-lookup"><span data-stu-id="0cee4-105">Microsoft Managed Desktop will assign devices to the various deployment groups, but you can specify or change group a device is assigned to a device by using the Admin portal.</span></span> <span data-ttu-id="0cee4-106">デバイスの登録後、またはユーザーが登録した後で割り当てを変更します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-106">You change the assignment after a device is registered or after a user has enrolled.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cee4-107">割り当てを変更すると、そのグループに固有のポリシーがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0cee4-107">If you change the assignment, policies that are specific to that group will be applied to the device.</span></span> <span data-ttu-id="0cee4-108">この変更により、最新バージョンの Windows 10 (新機能や品質更新プログラムを含む) がインストールされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0cee4-108">The change might install the latest version of Windows 10 (including any new feature or quality updates).</span></span> <span data-ttu-id="0cee4-109">最初は少数のデバイスを移動してから、結果のユーザー エクスペリエンスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0cee4-109">It's best to move just a few devices at first and then check the resulting user experience.</span></span> <span data-ttu-id="0cee4-110">特定の更新プログラムがデバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-110">Be aware that certain updates will restart the device.</span></span> <span data-ttu-id="0cee4-111">割り当てる適切なデバイスが選択されているのをもう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-111">Double-check that you've selected the right devices to assign.</span></span> <span data-ttu-id="0cee4-112">割り当てを有効にするには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0cee4-112">It can take up to 24 hours for the assignment to take effect.</span></span>

<span data-ttu-id="0cee4-113">展開グループにデバイスを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-113">To assign devices to a deployment group, follow these steps.</span></span> <span data-ttu-id="0cee4-114">別のデバイスを別のグループに移動する場合は、グループごとにこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-114">If you want to move separate devices to different groups, repeat these steps for each group.</span></span>

1. <span data-ttu-id="0cee4-115">[Microsoft エンドポイント マネージャー] で、左側 **のウィンドウで**[デバイス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-115">In Microsoft Endpoint Manager, select **Devices** in the left pane.</span></span> <span data-ttu-id="0cee4-116">[デバイス]**セクションMicrosoft マネージド デスクトップ[** デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0cee4-116">In the **Microsoft Managed Desktop** section, select **Devices**.</span></span>
2. <span data-ttu-id="0cee4-117">割り当てるデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-117">Select the devices you want to assign.</span></span> <span data-ttu-id="0cee4-118">選択したデバイスはすべて、指定したグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0cee4-118">All selected devices will be assigned to the group you specify.</span></span>
3. <span data-ttu-id="0cee4-119">メニューから **[デバイスの操作** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-119">Select **Device actions** from the menu.</span></span>
4. <span data-ttu-id="0cee4-120">[デバイス **をグループに割り当てる] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0cee4-120">Select **Assign device to group**.</span></span> <span data-ttu-id="0cee4-121">フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="0cee4-121">A fly-in opens.</span></span>
5. <span data-ttu-id="0cee4-122">ドロップダウン メニューを使用して、デバイスを移動するグループを選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0cee4-122">Use the drop-down menu to select the group to move devices to, and then select **Save**.</span></span> <span data-ttu-id="0cee4-123">割 **り当てられたグループは** **Pending に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="0cee4-123">The **Group assigned by** will change to **Pending**.</span></span>

<span data-ttu-id="0cee4-124">割り当てが完了すると、[グループの割り当て] が **[管理者**] (変更を行ったと示されます) に変更され、[グループ] 列に新しいグループの割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cee4-124">When the assignment is complete, **Group assigned by** will change to **Admin** (indicated that you made the change) and the **Group** column will show the new group assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="0cee4-125">デバイスが "エラー" または "保留中" の登録状態にある場合は、他のグループにデバイスを移動できません。</span><span class="sxs-lookup"><span data-stu-id="0cee4-125">You can't move devices to other groups if they're in the "error" or "pending" registration state.</span></span>
>
><span data-ttu-id="0cee4-126">デバイスが適切に削除されていない場合は、状態が "準備完了" と表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0cee4-126">If a device hasn't been properly removed, it could show a status of "ready."</span></span> <span data-ttu-id="0cee4-127">このようなデバイスを移動すると、移動が完了しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0cee4-127">If you move such a device, it's possible that the move won't complete.</span></span> <span data-ttu-id="0cee4-128">手順 5 で **[Pending]** に変更によって割り当てられたグループが表示しない場合は、Intune でデバイスを検索して利用可能なデバイスを確認します。</span><span class="sxs-lookup"><span data-stu-id="0cee4-128">If you don't see **Group assigned by** change to **Pending** in Step 5, check that the device is available by searching for it in Intune.</span></span> <span data-ttu-id="0cee4-129">詳細については、「[Intuneでデバイスの詳細を確認する](/mem/intune/remote-actions/device-inventory)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cee4-129">For more information, see [See device details in Intune](/mem/intune/remote-actions/device-inventory).</span></span>