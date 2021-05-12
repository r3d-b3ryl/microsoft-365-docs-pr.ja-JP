---
title: カスタム タイルをアプリ起動ツールに追加する
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'カスタム タイルをアプリ 起動ツールに追加して、メール、ドキュメント、アプリ、SharePoint サイト、外部サイト、その他のリソースへのクイック リンクを作成します。 '
ms.openlocfilehash: 598cfeb75fc811c87519c4479fa8fcab450466c3
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327212"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="69dd0-103">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="69dd0-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="69dd0-104">Microsoft 365 では、アプリ 起動ツールを使用して、メール、予定表、ドキュメント、アプリをすばやく簡単に取得できます (詳細[を参照)。](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="69dd0-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="69dd0-105">これらは、Microsoft 365 で取得するアプリと[、SharePoint ストア](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)または Azure サーバーから追加するカスタム アプリ[AD。](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="69dd0-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="69dd0-p102">SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="69dd0-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![アプリ起動ツール](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="69dd0-111">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="69dd0-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="69dd0-112">グローバル管理者として管理センターにサインインし、[設定] [組織の設定] に移動し、[組織プロファイル]  >  **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="69dd0-113">[組織プロファイル **] タブで** 、[カスタム アプリ起動 **ツールのタイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69dd0-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="69dd0-114">[カスタム **タイルの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69dd0-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="69dd0-p103">新しいタイルの **タイル名** を入力します。名前がタイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="69dd0-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="69dd0-117">タイルの **Web サイトの URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="69dd0-118">これは、ユーザーがアプリ 起動ツールでタイルを選択するときに移動する場所です。</span><span class="sxs-lookup"><span data-stu-id="69dd0-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="69dd0-119">URL で HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="69dd0-120">SharePoint サイト用のタイルを作成する場合、そのサイトへ移動し、URL をコピーし、ここに貼り付けてください。</span><span class="sxs-lookup"><span data-stu-id="69dd0-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="69dd0-121">既定のチーム サイトの URL は次のように表示されます。 `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="69dd0-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="69dd0-122">タイルの **画像の URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="69dd0-123">この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="69dd0-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="69dd0-124">イメージは 60x60 ピクセルで、認証を必要とせずに組織内のすべてのユーザーが利用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69dd0-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="69dd0-125">タイルの **説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="69dd0-126">[マイ アプリ] ページでタイルを選択し、[アプリの詳細] を選択すると、これが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="69dd0-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="69dd0-127">[変更 **の保存] を** 選択して、カスタム タイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="69dd0-128">これでカスタム タイルは、管理者とユーザー用にアプリ起動ツールの [ **すべて**] のタブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="69dd0-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="69dd0-129">前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="69dd0-130">これらの手順は、Microsoft 365 のカスタム タイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="69dd0-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="69dd0-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="69dd0-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="69dd0-132">管理センターで、[設定] [組織 **の設定**] [組織  >    >  **プロファイル] タブに移動** します。</span><span class="sxs-lookup"><span data-stu-id="69dd0-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="69dd0-133">[組織プロファイル **] ページの** [組織の   **カスタム** タイルの追加] の横にある [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69dd0-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="69dd0-134">カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。</span><span class="sxs-lookup"><span data-stu-id="69dd0-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="69dd0-135">[閉 **じる更新]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69dd0-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="69dd0-136">カスタム タイルを削除するには、[カスタム タイル]**ウィンドウから** タイルを選択し、[削除] タイル **を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="69dd0-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="69dd0-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="69dd0-137">What's next?</span></span>

<span data-ttu-id="69dd0-138">アプリ起動ツールにタイルを追加する以外に、ナビゲーション バーにアプリ 起動ツールタイルを追加できます (詳細[については、以下を参照してください](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985))。</span><span class="sxs-lookup"><span data-stu-id="69dd0-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="69dd0-139">組織のブランドに合わせて Microsoft 365 の外観をカスタマイズするには [、「Microsoft 365](../setup/customize-your-organization-theme.md)テーマのカスタマイズ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69dd0-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
