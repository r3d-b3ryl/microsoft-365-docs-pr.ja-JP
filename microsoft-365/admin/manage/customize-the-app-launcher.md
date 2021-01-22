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
description: 'カスタム タイルをアプリ起動ツールに追加して、電子メール、ドキュメント、アプリ、SharePoint サイト、外部サイト、その他のリソースへのクイック リンクを作成します。 '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926236"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="fdbc3-103">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="fdbc3-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="fdbc3-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-104">The admin center is changing.</span></span> <span data-ttu-id="fdbc3-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="fdbc3-106">Microsoft 365 では、アプリ起動ツールを使ってメール、予定表、ドキュメント、アプリにすばやく簡単にアクセスできます ([詳細をご覧ください](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a))。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="fdbc3-107">これらは、Microsoft 365 で取得できるアプリと[、SharePoint ストア](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)または Azure アプリから追加するカスタム アプリ[AD。](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="fdbc3-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="fdbc3-p103">SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![アプリ起動ツール](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="fdbc3-113">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="fdbc3-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="fdbc3-114">グローバル管理者として管理センターにサインインし、[**設定** 組織の設定] に移動して、[組織プロファイル]  >  タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="fdbc3-115">[組織プロファイル **] タブで** 、カスタム アプリ起動 **ツールのタイルを選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="fdbc3-116">[カスタム **タイルの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="fdbc3-117">新しいタイルの **タイル名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="fdbc3-118">名前がタイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="fdbc3-119">タイルの **Web サイトの URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="fdbc3-120">これは、ユーザーがアプリ起動ツールでタイルを選択するときに移動する場所です。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="fdbc3-121">URL で HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="fdbc3-122">ヒント: SharePoint サイトのタイルを作成する場合は、そのサイトに移動し、URL をコピーして、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="fdbc3-123">既定のチーム サイトの URL は次のように表示されます。 `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="fdbc3-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="fdbc3-124">タイルの **画像の URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="fdbc3-125">この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="fdbc3-126">ヒント: 画像は 60x60 ピクセルで、認証を必要とせずに組織内のすべてのユーザーが利用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="fdbc3-127">タイルの **説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="fdbc3-128">You see this when you select the tile on the My apps page and select **App details**.</span><span class="sxs-lookup"><span data-stu-id="fdbc3-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="fdbc3-129">[変更 **の保存] を** 選択して、カスタム タイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="fdbc3-130">これでカスタム タイルは、管理者とユーザー用にアプリ起動ツールの [ **すべて**] のタブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="fdbc3-131">タイルをアプリ アプリに昇格起動ツール</span><span class="sxs-lookup"><span data-stu-id="fdbc3-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="fdbc3-132">アプリ起動ツールアイコンを選択し、[すべてのアプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="fdbc3-133">アプリの新しいタイルを見つけ、省略記号を選択して、[ランチャーにピン留 **めする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="fdbc3-134">前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="fdbc3-135">これらの手順は、Microsoft 365 のカスタム タイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fdbc3-136">自身とユーザーの両方がこれらの手順に従って、[個人用アプリ] ページからアプリ起動ツールへとタイルを昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="fdbc3-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="fdbc3-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="fdbc3-138">管理センターで、[Settings Org   >  **Settings Organization**  >  **profile] タブに移動** </a> します。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="fdbc3-139">[組織プロファイル **] ページで** 、[組織のカスタム タイルの追加] の横にある   **[編集**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="fdbc3-140">カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="fdbc3-141">[更新 **閉じる]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="fdbc3-142">カスタム タイルを削除するには、カスタム タイル ウィンドウ **から** タイルを選択し、[削除] タイル **を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="fdbc3-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="fdbc3-143">What's next?</span></span>

<span data-ttu-id="fdbc3-144">アプリ起動ツールにタイルを追加する以外に、アプリ起動ツールのタイルをナビゲーション バーに追加できます (詳しくは[、以下を参照してください](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985))。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="fdbc3-145">組織のブランドに合わせて Microsoft 365 の外観をカスタマイズするには [、「Microsoft 365](../setup/customize-your-organization-theme.md)テーマをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdbc3-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
