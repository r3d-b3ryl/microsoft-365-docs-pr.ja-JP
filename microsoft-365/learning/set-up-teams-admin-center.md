---
title: 管理センターで Microsoft Viva ラーニング (プレビュー) をTeamsする
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 管理センターで Microsoft Viva ラーニング (プレビュー) を構成するTeams説明します。
ms.openlocfilehash: 99e63210e8f8c10e3721c35fb69df7880c7e1929
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290221"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="f7ab0-103">管理センターで Microsoft Viva ラーニング (プレビュー) をTeamsする</span><span class="sxs-lookup"><span data-stu-id="f7ab0-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="f7ab0-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="f7ab0-105">管理者Teams、テナント内のユーザーに対して Viva ラーニング (プレビュー) を有効にするには、特定の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="f7ab0-106">これらの手順は、テナントの有効化方法 (パブリック [](set-up-teams-admin-center.md#public-preview-tenants)プレビューまたは [*プライベート* プレビュー (またはベータ) によって異なります](set-up-teams-admin-center.md#private-preview-tenants)。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="f7ab0-107">パブリック プレビュー テナント</span><span class="sxs-lookup"><span data-stu-id="f7ab0-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="f7ab0-108">パブリック プレビュー テナントの管理者の手順</span><span class="sxs-lookup"><span data-stu-id="f7ab0-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="f7ab0-109">ビバ ラーニング (Preview) はまだ一般に利用できないので、特定のユーザーまたはグループの機能を有効にしてアクセス許可を設定するには、特定の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="f7ab0-110">ビバ ユーザー (プレビュー) ユーザーラーニングパブリック プレビュー機能を有効にする。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="f7ab0-111">a.</span><span class="sxs-lookup"><span data-stu-id="f7ab0-111">a.</span></span> <span data-ttu-id="f7ab0-112">パブリック Teams機能を有効にするには、更新ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="f7ab0-113">「パブリック[Microsoft Teams」を参照してください](/microsoftteams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="f7ab0-114">b.</span><span class="sxs-lookup"><span data-stu-id="f7ab0-114">b.</span></span> <span data-ttu-id="f7ab0-115">ビバ テスト (プレビュー) テストを実行するユーザーまたはラーニングポリシーを有効にする。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="f7ab0-116">「ユーザー [とグループにポリシーを割り当てる」を参照してください](/microsoftteams/assign-policies-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="f7ab0-117">Viva ユーザー (プレビュー) ユーザーのアプリラーニングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="f7ab0-118">a.</span><span class="sxs-lookup"><span data-stu-id="f7ab0-118">a.</span></span> <span data-ttu-id="f7ab0-119">現在グローバル ポリシーの一部である場合をしない限り、アプリのアクセス許可ポリシーですべての Microsoft アプリを許可します。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="f7ab0-120">「[アプリのアクセス許可ポリシーを管理する」を参照Microsoft Teams。](/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="f7ab0-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="f7ab0-121">b.</span><span class="sxs-lookup"><span data-stu-id="f7ab0-121">b.</span></span> <span data-ttu-id="f7ab0-122">ビバ テスト (プレビュー) テストを実行するユーザーまたはラーニングポリシーを有効にする。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="f7ab0-123">「ユーザー [とグループにポリシーを割り当てる」を参照してください](/microsoftteams/assign-policies-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3. <span data-ttu-id="f7ab0-124">Viva ラーニング (Preview) をテストするユーザーに対して、ビルド クライアントをパブリック プレビューに切り替[Teams。](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="f7ab0-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7ab0-125">パブリック プレビュー テナントの場合ラーニング製品のリリースまで、Teams 管理センターの管理アプリにはビバ Teams (プレビュー) は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="f7ab0-126">ただし、有効になっているパブリック プレビュー ユーザーは、Teams アプリ ストアでビバ ラーニング (プレビュー) を検索し、適切なポリシーとアクセス許可が設定された後で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="f7ab0-127">パブリック プレビュー テナントのユーザー手順</span><span class="sxs-lookup"><span data-stu-id="f7ab0-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="f7ab0-128">前に説明したポリシーを有効にすることで、パブリック プレビュー[](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants)テストを有効にしたユーザーは、[](/microsoftteams/public-preview-doc-updates#enable-public-preview)クライアントでパブリック プレビューに切りTeamsがあります。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="f7ab0-129">ユーザーは、[パブリック プレビューについて]でプロファイル >  >  **を選択する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-129">Users must select their profile image > **About** > **Public Preview**.</span></span>

    ![ユーザーのプロファイルをTeamsアプリケーションの上部ナビゲーション](../media/learning/learning-app-select-profile-teams.png)

2. <span data-ttu-id="f7ab0-131">ユーザーはパブリック プレビューの使用条件に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![パブリック プレビュー ビルドに切り替える](../media/learning/learning-app-switch-to-public-preview.png)

3. <span data-ttu-id="f7ab0-133">これで、ユーザーはアプリ ストアラーニングでビバ Teams ラーニング (プレビュー) を見つけて使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="f7ab0-134">プライベート プレビュー テナント</span><span class="sxs-lookup"><span data-stu-id="f7ab0-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="f7ab0-135">プライベート プレビュー (またはベータ) テナントの管理者の手順</span><span class="sxs-lookup"><span data-stu-id="f7ab0-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="f7ab0-136">プライベート プレビュー テナントの場合、有効にする必要がある追加のポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="f7ab0-137">ただし、組織内ラーニングで、ビバ ファイル (プレビュー) を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="f7ab0-138">管理センターの左側のナビゲーションTeams、[アプリの管理 **Teams]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![[アプリとアプリのTeams管理] セクションをTeams管理センターの左側のナビゲーション。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="f7ab0-140">[アプリの **管理] ページ** の検索ボックスに *「Viva* ラーニング」と入力し、[ビバ ラーニング **(プレビュー) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![[アプリの管理] ページで、Teamsを表示する管理センターで管理します。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="f7ab0-142">[ビバ **ラーニング (プレビュー) ページ** の[状態]で、[ビバ モードを有効にする許可ラーニング (プレビュー) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7ab0-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![ラーニングとアプリの設定] セクションTeams管理センターの [アプリの設定] ページを開きます。](../media/learning/learning-app-teams-learning-page.png)

<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="f7ab0-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="f7ab0-144">Next step</span></span>

[<span data-ttu-id="f7ab0-145">ビデオ ウィンドウで、ビバ ラーニング (プレビュー) の学習コンテンツ ソースを構成Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="f7ab0-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
