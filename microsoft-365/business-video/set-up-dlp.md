---
title: データの損失を防止する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: データ損失防止ポリシーの設定を管理する方法について説明します。
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580440"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="4029a-103">DLP によるデータ損失の防止</span><span class="sxs-lookup"><span data-stu-id="4029a-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="4029a-104">データ損失防止ポリシーは、社会保障番号や医療記録など、ビジネスの機密情報を特定して保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4029a-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="4029a-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="4029a-105">Try it!</span></span>

1. <span data-ttu-id="4029a-106">開始するには、管理センターに移動し [、[](https://admin.microsoft.com)セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="4029a-107">[データ損失防止 **の設定] まで下にスクロールし、[** 表示] を選択し、[管理] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="4029a-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="4029a-108">ポリシーを編集するには、ポリシーを選択し、[ポリシーの編集] **を** 選択し、変更する内容を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="4029a-109">たとえば、[場所] **を選択** して、スキャンする場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="4029a-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="4029a-110">Microsoft Teams でコンテンツのスキャンを有効にするには、トグル スイッチを **[オン** ] の位置に切り替え、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="4029a-111">ポリシー設定を編集するには、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="4029a-112">検出された機密コンテンツの量が少ない、大量に適用される個別のルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4029a-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="4029a-113">ボリュームの少ないルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="4029a-113">Expand your low volume rule.</span></span> <span data-ttu-id="4029a-114">[ルール **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="4029a-115">設定を確認し、必要に応じて調整します。</span><span class="sxs-lookup"><span data-stu-id="4029a-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="4029a-116">たとえば、[電子メール テキストのカスタマイズ] **と [** ポリシー ヒント テキストの **カスタマイズ] を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="4029a-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="4029a-117">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-117">Select **Save**.</span></span>
1. <span data-ttu-id="4029a-118">ハイ ボリューム ルールに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4029a-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="4029a-119">[保存 **] を** 選択し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="4029a-120">新しいポリシーを作成するには、[ポリシーの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="4029a-121">カスタム ポリシーを作成するか、テンプレートから開始できます。</span><span class="sxs-lookup"><span data-stu-id="4029a-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="4029a-122">たとえば、HIPAA ポリシーを作成するには、[医療と健康] テンプレートを選択し、[米国健康保険法 **(HIPAA) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="4029a-123">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-123">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-124">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4029a-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="4029a-125">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-125">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-126">スキャンする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-126">Choose the locations to scan.</span></span> <span data-ttu-id="4029a-127">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-127">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-128">保護するコンテンツの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="4029a-129">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-129">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-130">機密情報が検出された場合に発生する情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="4029a-131">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-131">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-132">アクセスをカスタマイズし、アクセス許可を上書きします。</span><span class="sxs-lookup"><span data-stu-id="4029a-132">Customize your access and override permissions.</span></span> <span data-ttu-id="4029a-133">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-133">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-134">ポリシーを有効にしたい場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="4029a-135">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4029a-135">Select **Next**.</span></span>
1. <span data-ttu-id="4029a-136">設定を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4029a-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="4029a-137">ポリシーを有効にした後、説明された機密情報を含む電子メールがブロックされ、その情報を送信しようとした送信者に警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4029a-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>