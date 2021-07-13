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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: カスタム タイルをアプリ 起動ツールに追加して、メール、ドキュメント、アプリ、SharePointサイト、外部サイト、その他のリソースへのクイック リンクを作成します。
ms.openlocfilehash: 0f4141d08811847e8e27cf35975cfa6c6b1b1192
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393681"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="737f1-103">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="737f1-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="737f1-104">このMicrosoft 365、アプリ 起動ツールを使用してメール、予定表、ドキュメント、アプリにすばやく簡単にアクセスできます (詳細[を参照)。](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="737f1-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="737f1-105">これらのアプリは、Microsoft 365 [SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)ストアまたは Azure AD から追加するカスタム アプリと[AD。](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="737f1-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="737f1-p102">SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="737f1-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![アプリ起動ツール](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="737f1-111">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="737f1-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="737f1-112">グローバル管理者として管理センターにサインインし、[組織] 設定に移動設定、[組織プロファイル] タブ  >  **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="737f1-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="737f1-113">[組織プロファイル **] タブで** 、[カスタム アプリ起動 **ツールのタイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="737f1-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="737f1-114">[カスタム **タイルの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="737f1-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="737f1-p103">新しいタイルの **タイル名** を入力します。名前がタイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="737f1-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="737f1-117">タイルの **Web サイトの URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="737f1-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="737f1-118">これは、ユーザーがアプリ 起動ツールでタイルを選択するときに移動する場所です。</span><span class="sxs-lookup"><span data-stu-id="737f1-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="737f1-119">URL で HTTPS を使用します。</span><span class="sxs-lookup"><span data-stu-id="737f1-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="737f1-120">SharePoint サイト用のタイルを作成する場合、そのサイトへ移動し、URL をコピーし、ここに貼り付けてください。</span><span class="sxs-lookup"><span data-stu-id="737f1-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="737f1-121">既定のチーム サイトの URL は次のように表示されます。 `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="737f1-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="737f1-122">タイルの **画像の URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="737f1-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="737f1-123">この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="737f1-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="737f1-124">イメージは 60x60 ピクセルで、認証を必要とせずに組織内のすべてのユーザーが利用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="737f1-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="737f1-125">タイルの **説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="737f1-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="737f1-126">[マイ アプリ] ページでタイルを選択し、[アプリの詳細] を選択すると、これが **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="737f1-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="737f1-127">[変更 **の保存] を** 選択して、カスタム タイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="737f1-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="737f1-128">これでカスタム タイルは、管理者とユーザー用にアプリ起動ツールの [ **すべて**] のタブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="737f1-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="737f1-129">前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="737f1-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="737f1-130">これらの手順は、ユーザー設定のタイルに必要Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="737f1-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="737f1-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="737f1-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="737f1-132">管理センターで、[組織プロファイル]タブ  >  **設定[組織**  >  **設定] タブに移動** します。</span><span class="sxs-lookup"><span data-stu-id="737f1-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="737f1-133">[組織プロファイル **] ページの** [組織の   **カスタム** タイルの追加] の横にある [編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="737f1-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="737f1-134">カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。</span><span class="sxs-lookup"><span data-stu-id="737f1-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="737f1-135">[閉 **じる更新]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="737f1-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="737f1-136">カスタム タイルを削除するには、[カスタム タイル]**ウィンドウから** タイルを選択し、[削除] タイル **を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="737f1-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="737f1-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="737f1-137">Next steps</span></span>

<span data-ttu-id="737f1-138">アプリ起動ツールにタイルを追加する以外に、ナビゲーション バーにアプリ 起動ツールタイルを追加できます (詳細[については、以下を参照してください](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985))。</span><span class="sxs-lookup"><span data-stu-id="737f1-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="737f1-139">組織のブランドに合わせてMicrosoft 365の外観をカスタマイズするには、「テーマをカスタマイズする」[をMicrosoft 365してください](../setup/customize-your-organization-theme.md)。</span><span class="sxs-lookup"><span data-stu-id="737f1-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="737f1-140">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="737f1-140">Related content</span></span>

<span data-ttu-id="737f1-141">[ユーザーのアプリ 起動ツールにアプリをピン留め](pin-apps-to-app-launcher.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="737f1-141">[Pin apps to your users' app launcher](pin-apps-to-app-launcher.md) (article)</span></span>\
<span data-ttu-id="737f1-142">[ビジネス ユーザー Microsoft 365クライアント (](../setup/upgrade-users-to-latest-office-client.md)記事)にOfficeアップグレードする (記事)</span><span class="sxs-lookup"><span data-stu-id="737f1-142">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>\
<span data-ttu-id="737f1-143">[管理センターでアドインを管理する](../manage/manage-addins-in-the-admin-center.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="737f1-143">[Manage add-ins in the admin center](../manage/manage-addins-in-the-admin-center.md) (article)</span></span>
