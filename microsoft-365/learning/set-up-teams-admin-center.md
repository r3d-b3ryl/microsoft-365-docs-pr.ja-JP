---
title: 管理センターで Microsoft Viva Learning (プレビュー) をTeamsする
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 管理センターで Microsoft Viva Learning (プレビュー) を構成するTeams説明します。
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625300"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="f6f58-103">管理センターで Microsoft Viva Learning (プレビュー) をTeamsする</span><span class="sxs-lookup"><span data-stu-id="f6f58-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="f6f58-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="f6f58-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="f6f58-105">管理者Teamsビバ ラーニング (プレビュー) をインストールし、管理者センターからアクセス許可ポリシー Teams適用します。</span><span class="sxs-lookup"><span data-stu-id="f6f58-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="f6f58-106">パブリック プレビューの場合は、まず更新ポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f58-106">For Public Preview, you must first set the Update policy.</span></span> <span data-ttu-id="f6f58-107">詳細については、「パブリック プレビュー」TeamsをMicrosoft Teams[してください](/MicrosoftTeams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="f6f58-107">For more details, see the Teams site [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="f6f58-108">管理者センターにサインインTeamsします。</span><span class="sxs-lookup"><span data-stu-id="f6f58-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="f6f58-109">[更新  >  **Teams] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6f58-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="f6f58-110">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f58-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="f6f58-111">更新ポリシーに名前を付け、ポリシーを追加し、[プレビュー機能の表示 **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f6f58-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="f6f58-112">管理者は、ポリシー更新プログラムをユーザーに通知して、ビルドをパブリック プレビューに移動Teams。</span><span class="sxs-lookup"><span data-stu-id="f6f58-112">The admin must notify users of the policy update so that they move their build into Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="f6f58-113">ユーザーは、プロファイル イメージ --> -->を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f58-113">User must select their profile image --> About --> Public Preview.</span></span>
   
        ![ユーザーのプロファイルをTeamsアプリケーションの上部ナビゲーション](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="f6f58-115">ユーザーはパブリック プレビューの条項に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f58-115">User must accept terms of Public Preview.</span></span>

        ![パブリック プレビュー ビルドに切り替える](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="f6f58-117">制限的なポリシーを持ち、Viva Learning を有効にする必要がある組織の場合は、次のセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f6f58-117">For organizations that have restrictive policies and need to enable Viva Learning, follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="f6f58-118">ビバラーニングの設定を管理する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f6f58-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="f6f58-119">これらのタスクを実行するには、管理センター Teams管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f58-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="f6f58-120">組織内のユーザーがビバ ラーニング (プレビュー) を利用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f58-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="f6f58-121">管理センターの左側のナビゲーションTeams、[アプリの管理 **Teams]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f6f58-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![[アプリとアプリのTeams管理] セクションをTeams管理センターの左側のナビゲーション。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="f6f58-123">[アプリの **管理] ページ** の検索ボックスに「 *ビ* バ ラーニング」と入力し、[ビバ ラーニング (プレビュー) ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6f58-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![[アプリの管理] ページで、Teamsを表示する管理センターで管理します。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="f6f58-125">[ビバ **ラーニング (プレビュー)] ページで、次の設定を行** います。</span><span class="sxs-lookup"><span data-stu-id="f6f58-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="f6f58-126">[ **状態] で**、[ **ビバ ラーニング (** プレビュー) を有効にする許可] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f58-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="f6f58-127">[アプリの **設定]** タブの **[アプリ** の設定] で、Microsoft 365管理センターに移動して、学習コンテンツ ソース [を構成します](content-sources-365-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f6f58-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![[状態とアプリの設定] セクションTeams管理センターの [学習] ページ。](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="f6f58-129">[**アプリ設定の管理**]の後、[アクセス許可ポリシーとセットアップ ポリシー] に移動して、組織のプレビューへの参加の一環として、ビバ ラーニング (プレビュー) にアクセスできる必要がある従業員にアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="f6f58-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="f6f58-130">組織が Teams TAP100 プログラムの一部としてリング 4.0 にある場合は、リング 3.0 の承認済みユーザーがビバ ラーニング (プレビュー) にアクセスできる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6f58-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="f6f58-131">プレビューの一環として、Viva Learning (Preview) はリング 3.0 でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="f6f58-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="f6f58-132">組織がリング 4.0 にある場合は、[アプリの管理] ページに [ビバ ラーニング (プレビュー) **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="f6f58-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="f6f58-133">アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、[すべてのアプリを許可する] に設定し、それを Ring 3.0 承認済みユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f58-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="f6f58-134">![TAP-AppsPermission-Plcy ページで、[すべてのアプリを選択できます] が表示されます。](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="f6f58-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="f6f58-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="f6f58-135">Next step</span></span>

[<span data-ttu-id="f6f58-136">管理センターで、ビバ ラーニング (プレビュー) の学習コンテンツ ソースMicrosoft 365構成する</span><span class="sxs-lookup"><span data-stu-id="f6f58-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
