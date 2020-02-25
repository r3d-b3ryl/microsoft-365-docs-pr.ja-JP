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
ms.openlocfilehash: ad6ef53a4a75f6ab8eb8bb66af4858c80fbc4596
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254988"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="4c9a2-103">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="4c9a2-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="4c9a2-p101">Office 365 では、Office 365 アプリ起動ツールを使って、メール、予定表、ドキュメント、アプリに簡単かつ迅速にたどり着くことができます ([詳細については、こちらを参照してください](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx))。これらのアイテムには、Office 365 から得られるアプリをはじめ、[SharePoint ストア](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx)や [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher) から追加したカスタム アプリも含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="4c9a2-p102">SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Office 365 アプリ起動ツール](../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="4c9a2-111">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="4c9a2-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="4c9a2-112">管理センターで、[**設定** > ] の**設定**に移動し、[**組織プロファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="4c9a2-113">[**組織プロファイル**] タブで、[**カスタムアプリ起動ツールタイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="4c9a2-114">[**カスタムタイルの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="4c9a2-115">新しいタイルの **タイル名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="4c9a2-116">名前がタイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="4c9a2-117">タイルの**web サイトの URL**を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="4c9a2-118">これは、アプリ起動ツールでタイルを選択したときにユーザーが移動する場所です。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="4c9a2-119">URL に HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="4c9a2-120">ヒント: SharePoint サイトのタイルを作成している場合は、そのサイトに移動し、URL をコピーして、ここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="4c9a2-121">既定のチームサイトの URL は次のようになります。`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="4c9a2-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="4c9a2-122">タイルの**イメージの URL**を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="4c9a2-123">この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="4c9a2-124">ヒント: 画像は60x60 ピクセルで、組織内のすべてのユーザーが認証を必要とせずに使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="4c9a2-125">タイルの **説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="4c9a2-126">[個人用アプリ] ページでタイルを選択し、[**アプリの詳細**] を選択すると、これが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="4c9a2-127">[ **Save changes** ] を選択してカスタムタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="4c9a2-128">これでカスタム タイルは、管理者とユーザー用にアプリ起動ツールの [ **すべて**] のタブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="4c9a2-129">タイルをアプリ起動ツールに昇格させる</span><span class="sxs-lookup"><span data-stu-id="4c9a2-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="4c9a2-130">アプリ起動ツールのアイコンを選択し、[**すべてのアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="4c9a2-131">アプリの新しいタイルを見つけ、省略記号を選択して、[**スタート] に [ピン留め] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="4c9a2-p108">前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。次の手順は、Office 365 でのカスタム タイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4c9a2-134">自身とユーザーの両方がこれらの手順に従って、[個人用アプリ] ページからアプリ起動ツールへとタイルを昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="4c9a2-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="4c9a2-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="4c9a2-136">管理センターで、[**設定** > ] [<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">組織プロファイル</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-136">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> page.</span></span>
    
2. <span data-ttu-id="4c9a2-137">[**組織プロファイル**] ページで、[**組織のカスタムタイルの追加**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="4c9a2-138">カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="4c9a2-139">[**更新プログラム** \>の**クローズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="4c9a2-140">カスタムタイルを削除するには、**カスタム**タイルウィンドウでタイルを選択し、[**タイル** > の**削除**を削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="4c9a2-141">次の作業</span><span class="sxs-lookup"><span data-stu-id="4c9a2-141">What's next?</span></span>

<span data-ttu-id="4c9a2-p109">タイルをアプリ起動ツールに追加するだけでなく、アプリ起動ツールのタイルを Office 365 ナビゲーションバーに追加できます ([詳細情報](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx))。 Office 365 の外観をカスタマイズし、企業ブランドにマッチさせる方法については、「[Office 365 テーマをカスタマイズする](../setup/customize-your-organization-theme.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9a2-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

