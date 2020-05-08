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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'カスタムタイルをアプリ起動ツールに追加することによって、電子メール、ドキュメント、アプリ、SharePoint サイト、外部サイト、その他のリソースへのクイックリンクを作成します。 '
ms.openlocfilehash: 2c0a1cbd2f7c605bc03a55787266c7a627f8e329
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139723"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="00ba7-103">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="00ba7-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="00ba7-104">管理センターが変更されています。</span><span class="sxs-lookup"><span data-stu-id="00ba7-104">The admin center is changing.</span></span> <span data-ttu-id="00ba7-105">ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00ba7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="00ba7-106">Microsoft 365 では、アプリ起動ツールを使用して、電子メール、予定表、ドキュメント、アプリをすばやく簡単に入手できます ([詳細につい](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)ては、こちらを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="00ba7-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)).</span></span> <span data-ttu-id="00ba7-107">これらは、Microsoft 365 で入手できるアプリ、および[SharePoint ストア](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx)または[Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)から追加するカスタムアプリです。</span><span class="sxs-lookup"><span data-stu-id="00ba7-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="00ba7-p103">SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="00ba7-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![アプリ起動ツール](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="00ba7-113">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="00ba7-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="00ba7-114">管理センターで、[**設定** > ] の**設定**に移動し、[**組織プロファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-114">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="00ba7-115">[**組織プロファイル**] タブで、[**カスタムアプリ起動ツールタイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="00ba7-116">[**カスタムタイルの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="00ba7-117">新しいタイルの **タイル名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="00ba7-118">名前がタイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="00ba7-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="00ba7-119">タイルの**web サイトの URL**を入力します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="00ba7-120">これは、アプリ起動ツールでタイルを選択したときにユーザーが移動する場所です。</span><span class="sxs-lookup"><span data-stu-id="00ba7-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="00ba7-121">URL に HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="00ba7-122">ヒント: SharePoint サイトのタイルを作成している場合は、そのサイトに移動し、URL をコピーして、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="00ba7-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="00ba7-123">既定のチームサイトの URL は次のようになります。`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="00ba7-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="00ba7-124">タイルの**イメージの URL**を入力します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="00ba7-125">この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="00ba7-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="00ba7-126">ヒント: 画像は60x60 ピクセルで、組織内のすべてのユーザーが認証を必要とせずに使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ba7-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="00ba7-127">タイルの **説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="00ba7-128">[個人用アプリ] ページでタイルを選択し、[**アプリの詳細**] を選択すると、これが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00ba7-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="00ba7-129">[ **Save changes** ] を選択してカスタムタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="00ba7-130">これでカスタム タイルは、管理者とユーザー用にアプリ起動ツールの [ **すべて**] のタブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="00ba7-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="00ba7-131">タイルをアプリ起動ツールに昇格させる</span><span class="sxs-lookup"><span data-stu-id="00ba7-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="00ba7-132">アプリ起動ツールのアイコンを選択し、[**すべてのアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="00ba7-133">アプリの新しいタイルを見つけ、省略記号を選択して、[**スタート] に [ピン留め] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="00ba7-134">前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="00ba7-135">これらの手順は、Microsoft 365 のカスタムタイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="00ba7-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="00ba7-136">自身とユーザーの両方がこれらの手順に従って、[個人用アプリ] ページからアプリ起動ツールへとタイルを昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ba7-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="00ba7-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="00ba7-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="00ba7-138">管理センターで、[**設定** > の**設定** > ] [<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">組織プロファイル</a>] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-138">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="00ba7-139">[**組織プロファイル**] ページで、[**組織のカスタムタイルの追加**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="00ba7-140">カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。</span><span class="sxs-lookup"><span data-stu-id="00ba7-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="00ba7-141">[**更新プログラム** \>の**クローズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="00ba7-142">カスタムタイルを削除するには、**カスタム**タイルウィンドウでタイルを選択し、[**タイル** > の**削除**を削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00ba7-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="00ba7-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="00ba7-143">What's next?</span></span>

<span data-ttu-id="00ba7-144">アプリ起動ツールにタイルを追加するだけでなく、アプリ起動ツールタイルをナビゲーションバーに追加することもできます ([詳細につい](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)ては、こちらを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="00ba7-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="00ba7-145">組織のブランドに合わせて Microsoft 365 のルックアンドフィールをカスタマイズするには、「 [microsoft 365 テーマをカスタマイズ](../setup/customize-your-organization-theme.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00ba7-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

