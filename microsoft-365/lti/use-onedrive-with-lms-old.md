---
title: '[ツールOneDrive ラーニング相互運用性を使用する'
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 新しいツール相互運用性アプリを使用して、割り当ての作成と採点、コース コンテンツの構築とキュレーション、ファイルOneDrive ラーニング共同作業を行います。
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256986"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="3102a-103">キャンバスMicrosoft OneDrive LTI を使用する</span><span class="sxs-lookup"><span data-stu-id="3102a-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3102a-104">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="3102a-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3102a-105">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="3102a-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="3102a-106">Canvas との統合</span><span class="sxs-lookup"><span data-stu-id="3102a-106">Integrate with Canvas</span></span>

<span data-ttu-id="3102a-107">この統合を実行するユーザーは、Canvas の管理者であり、テナントの管理者Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="3102a-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="3102a-108">テナント管理者アカウントを使用Microsoft Azureポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3102a-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="3102a-109">Azure テナント管理者には、グループ管理者の役割も必要です。</span><span class="sxs-lookup"><span data-stu-id="3102a-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![グループ管理者が強調表示されている](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="3102a-111">LTI ポータルで Microsoft [OneDriveサインインします](https://odltiappnl.azurewebsites.net/admin)。</span><span class="sxs-lookup"><span data-stu-id="3102a-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="3102a-112">サインインを完了するためのアクセス許可を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="3102a-112">Accept the permissions to complete the sign-in.</span></span>

    ![アクセス許可を受け入れる](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="3102a-114">**[LTI テナントの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3102a-114">Select **Add LTI Tenant**.</span></span>

     ![LTI テナントの追加](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="3102a-116">ドロップダウン **から [キャンバスとして LTI コンシューマー** **プラットフォーム** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3102a-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="3102a-117">[ **キャンバスベース URL] を選択し** 、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3102a-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![[キャンバス] を選択し、ベース URL を追加する](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="3102a-119">次の画面には、機密であるフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3102a-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="3102a-120">? **から [次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3102a-120">Select **Next** from ??</span></span> <span data-ttu-id="3102a-121">」ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3102a-121">page.</span></span> <span data-ttu-id="3102a-122">レビュー担当者はここで空白を入力できますか?</span><span class="sxs-lookup"><span data-stu-id="3102a-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="3102a-123">[ **次へ** ] を選択すると、機密の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3102a-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="3102a-124">Azure portal の最後の画面には、Canvas インスタンスを追加するための次の手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3102a-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="3102a-125">この画面から開発者キーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3102a-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="3102a-126">Canvas インスタンスを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="3102a-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="3102a-127">Canvas インスタンスの追加</span><span class="sxs-lookup"><span data-stu-id="3102a-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="3102a-128">Canvas インスタンスで、[管理者開発者キー **] の選択**  >  **を解除します**。</span><span class="sxs-lookup"><span data-stu-id="3102a-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="3102a-129">[開発者 **キー] のドロップダウンで [LTI** キー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3102a-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![LTI 開発者キーを取得する](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="3102a-131">開発者キーをここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3102a-131">Paste the developer keys here.</span></span>

     ![開発者キーを貼り付ける](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="3102a-133">キーが OFF モードで **作成** される</span><span class="sxs-lookup"><span data-stu-id="3102a-133">The key gets created in **OFF** mode</span></span>

   ![オフ モードで作成された開発者キー](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="3102a-135">強調表示されたテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3102a-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="3102a-136">これは、LTI ポータルのクライアント ID Microsoft OneDrive機能します。</span><span class="sxs-lookup"><span data-stu-id="3102a-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="3102a-137">LTI ポータルの **[クライアント ID]** フィールドにテキストMicrosoft OneDrive貼り付け、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3102a-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="3102a-138">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3102a-138">Select **Save**.</span></span>

7. <span data-ttu-id="3102a-139">[LTI テナントの表示] **を選択して設定を表示します**。</span><span class="sxs-lookup"><span data-stu-id="3102a-139">View the settings by selecting **View LTI Tenants**.</span></span>
