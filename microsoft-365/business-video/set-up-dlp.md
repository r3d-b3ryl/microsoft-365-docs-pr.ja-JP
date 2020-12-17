---
title: データの損失を防止する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702912"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="fef5e-103">DLP を使用してデータ損失を防止する</span><span class="sxs-lookup"><span data-stu-id="fef5e-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="fef5e-104">データ損失防止ポリシーは、社会保障番号や医療記録など、ビジネスの機密情報を特定して保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fef5e-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="fef5e-105">演習</span><span class="sxs-lookup"><span data-stu-id="fef5e-105">Try it!</span></span>

1. <span data-ttu-id="fef5e-106">To get started, go to the [admin center,](https://admin.microsoft.com)and select **Setup**.</span><span class="sxs-lookup"><span data-stu-id="fef5e-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="fef5e-107">下にスクロールして **データ損失防止の** 設定を行い、[表示] を選択し、[管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="fef5e-108">ポリシーを編集するには、ポリシーを選択し、[ポリシーの編集] **を** 選択して、変更する内容を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="fef5e-109">たとえば、[場所] **を選択して** スキャンする項目を変更します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="fef5e-110">Microsoft Teams のコンテンツのスキャンを有効にするには、トグル スイッチを **オン** の位置に切り替え、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="fef5e-111">ポリシー設定を編集するには、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="fef5e-112">検出された機密性の高いコンテンツの量と量が多いコンテンツに適用される個別のルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fef5e-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="fef5e-113">ボリュームの少ないルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-113">Expand your low volume rule.</span></span> <span data-ttu-id="fef5e-114">Choose **Edit rule**.</span><span class="sxs-lookup"><span data-stu-id="fef5e-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="fef5e-115">設定を確認し、必要に応じて調整します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="fef5e-116">たとえば、電子メール テキストの **カスタマイズと** ポリシー ヒント テキストの **カスタマイズを選択できます**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="fef5e-117">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-117">Select **Save**.</span></span>
1. <span data-ttu-id="fef5e-118">高ボリューム ルールに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="fef5e-119">[保存 **] を** 選択し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="fef5e-120">新しいポリシーを作成するには、[ポリシーの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="fef5e-121">カスタム ポリシーを作成するか、テンプレートを使用して開始できます。</span><span class="sxs-lookup"><span data-stu-id="fef5e-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="fef5e-122">たとえば、HIPAA ポリシーを作成するには、[医療と健康] テンプレートを選択し、[米国の医療保険法 **(HIPAA)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="fef5e-123">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-123">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-124">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="fef5e-125">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-125">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-126">スキャンする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-126">Choose the locations to scan.</span></span> <span data-ttu-id="fef5e-127">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-127">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-128">保護するコンテンツの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="fef5e-129">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-129">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-130">機密情報が検出された場合の対応を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="fef5e-131">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-131">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-132">アクセスをカスタマイズし、アクセス許可を上書きします。</span><span class="sxs-lookup"><span data-stu-id="fef5e-132">Customize your access and override permissions.</span></span> <span data-ttu-id="fef5e-133">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-133">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-134">ポリシーを有効にするときに選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="fef5e-135">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fef5e-135">Select **Next**.</span></span>
1. <span data-ttu-id="fef5e-136">設定を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fef5e-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="fef5e-137">ポリシーが有効にされた後、記載された機密情報を含む電子メールがブロックされ、その情報を送信しようとした送信者に警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fef5e-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>