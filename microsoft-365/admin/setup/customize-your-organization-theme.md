---
title: 組織のテーマをカスタマイズする
f1.keywords:
- CSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Microsoft 365 の既定のテーマを変更し、会社のロゴや色と一致するようにカスタマイズする方法について説明します。 '
ms.openlocfilehash: f3ba6021205289426ee78f16c7d0678e4b81ef75
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779859"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a><span data-ttu-id="8d62f-103">組織の Microsoft 365 テーマをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8d62f-103">Customize the Microsoft 365 theme for your organization</span></span>

<span data-ttu-id="8d62f-104">Microsoft 365 for business サブスクリプションの管理者は、組織内のすべてのユーザーについて、トップナビゲーションバーに表示される既定のテーマを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-104">As the admin of your Microsoft 365 for business subscription, you can change the default theme that appears in the top navigation bar for everyone in the organization:</span></span> 

- <span data-ttu-id="8d62f-105">会社のロゴを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-105">Add your company logo.</span></span>
- <span data-ttu-id="8d62f-106">ブランドの他の部分と一致するように色を変更します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-106">Change the colors to match the rest of your brand.</span></span> 
- <span data-ttu-id="8d62f-107">ユーザーが自分のロゴを選択したときに移動先リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-107">Add a destination link users go when they select your logo.</span></span> 
  
## <a name="customize-your-theme-in-the-admin-center"></a><span data-ttu-id="8d62f-108">管理センターでテーマをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8d62f-108">Customize your theme in the admin center</span></span>

1. <span data-ttu-id="8d62f-109">管理センターで、[設定] [ **Settings** \> **組織設定**] ページに移動し、[**組織プロファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-109">In the admin center, go to the **Settings** \> **Org Settings** page, and then choose the **Organization profile** tab.</span></span>

2. <span data-ttu-id="8d62f-110">[**組織プロファイル**] タブで、[**カスタムテーマ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-110">On the **Organization profile** tab, choose **Custom themes**.</span></span>

3. <span data-ttu-id="8d62f-111">[**税関**theme] パネルで、組織に必要なテーマ要素を変更します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-111">On the **Customs themes** panel, change the theme elements that you want for your organization:</span></span>
    
    - <span data-ttu-id="8d62f-112">**カスタムロゴイメージを使用**する: URL からイメージを使用するか、イメージをアップロードするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-112">**Use a custom logo image**: Choose whether to use an image from a URL or to upload an image.</span></span> <span data-ttu-id="8d62f-113">URL を使用する場合は、URL が HTTPS を使用しており、画像は任意のサイズの任意の形式の 200 x 30 ピクセルであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8d62f-113">If you use a URL, make sure that the URL uses HTTPS and that the image is 200 x 30 pixels of any format of any size.</span></span> <span data-ttu-id="8d62f-114">200 x 30 ピクセル、JPG、PNG、GIF、または SVG 形式のロゴを 10 KB 未満でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-114">You can upload a logo under 10 KB that is 200 x 30 pixels in JPG, PNG, GIF, or SVG format.</span></span>

      > [!NOTE]
      > <span data-ttu-id="8d62f-115">SharePoint モバイルアプリにロゴが表示されるようにするには、SVG 画像のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-115">For the logo to appear in the SharePoint mobile app, use only SVG images.</span></span> <span data-ttu-id="8d62f-116">他の形式でアップロードされた画像は、アプリに表示されません。</span><span class="sxs-lookup"><span data-stu-id="8d62f-116">Images uploaded in any other format don't display in the app.</span></span> <span data-ttu-id="8d62f-117">ロゴは、SharePoint モバイルアプリでクリックできません。</span><span class="sxs-lookup"><span data-stu-id="8d62f-117">Logos are not clickable in the SharePoint Mobile app.</span></span>

    - <span data-ttu-id="8d62f-118">**ロゴをクリックできるよう**にする: ナビゲーションバーのロゴは、会社のリソースへのリンクとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-118">**Make logo clickable**: You can use your logo in the navigation bar as a link to any company resource.</span></span> <span data-ttu-id="8d62f-119">ここには、http://または https://から始まるロゴの URL を入力できます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-119">You can enter the URL for the logo here, starting with http:// or https://.</span></span> <span data-ttu-id="8d62f-120">これはオプションです。</span><span class="sxs-lookup"><span data-stu-id="8d62f-120">This is optional.</span></span>

    - <span data-ttu-id="8d62f-121">**[背景画像の選択]**: 画像を選択して、1366 x 50 ピクセルの解像度で、自分の JPG、PNG、GIF をアップロードします。これは、15 KB 未満です。</span><span class="sxs-lookup"><span data-stu-id="8d62f-121">**Select background image**: Select the image and upload your own JPG, PNG, or GIF with a resolution of 1366 x 50 pixels, no larger than 15 KB.</span></span> <span data-ttu-id="8d62f-122">背景の画像が各ページ上部のナビゲーション バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-122">The background image appears in the top navigation bar on every page.</span></span>

      > [!NOTE]
      > <span data-ttu-id="8d62f-123">テキストを含む画像が期待どおりに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d62f-123">Images that contain text might not display as expected.</span></span> <span data-ttu-id="8d62f-124">ナビゲーションバーの右側と左側に表示される組み込み要素は、サービスによって異なる場合があり、これらの要素によってテキストが隠されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d62f-124">Built-in elements that appear on the right and left sides of the navigation bar can vary across services, and your text might be obscured by those elements.</span></span> 

    - <span data-ttu-id="8d62f-125">[**ナビゲーションバーの色**]: ナビゲーションバーの背景に使用する色を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-125">**Navigation bar color**: Select a color to use for the background of the navigation bar.</span></span> <span data-ttu-id="8d62f-126">ナビゲーションバーは、すべてのページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-126">The navigation bar appears at the top on every page.</span></span>

    - <span data-ttu-id="8d62f-127">**テキストとアイコン**:ナビゲーション バー上部のテキストとアイコンに使用する色を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-127">**Text and icons**: Select a color to use for the text and icons on the top navigation bar.</span></span>

    - <span data-ttu-id="8d62f-128">**アクセントの色**: 特定のアプリケーションのボタンやテキストのように、ナビゲーションバーボタンのホバー色とページのアクセントに使用する色を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-128">**Accent color**: Select a color to use for the navigation bar button hover color and page accents like buttons and text on certain applications.</span></span>

    - <span data-ttu-id="8d62f-129">**ユーザーがテーマを上書きできないよう**にする: この切り替えを反転して、ユーザーがテーマの選択で自分のテーマを選択できないようにします。</span><span class="sxs-lookup"><span data-stu-id="8d62f-129">**Prevent users from overriding theme**: Flip this toggle to prevent users from choosing their own theme from our theme selection.</span></span> <span data-ttu-id="8d62f-130">これにより、ユーザーがハイコントラストテーマを設定することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="8d62f-130">This doesn't prevent users from being able to set a high contrast theme.</span></span>

    - <span data-ttu-id="8d62f-131">[**ユーザー名を表示**する]: ユーザーがサインインしているときに、ページの右上にあるアカウント管理者へのエントリポイントでユーザーの完全な名前を表示するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-131">**Show the user name**: Choose whether to show a user's full name at the entry point to the account manager in the top right of the page when the user is signed in.</span></span> <span data-ttu-id="8d62f-132">既定では、写真がアップロードされていない場合、ユーザーは自分の写真またはそのイニシャルを表示します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-132">By default, users see their photo or their initials, if no photo was uploaded.</span></span>
    
4. <span data-ttu-id="8d62f-133">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-133">Select **Save changes**.</span></span>
    
<span data-ttu-id="8d62f-134">管理センターでは、すぐに新しいテーマを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-134">You can see your new theme in the admin center right away.</span></span> <span data-ttu-id="8d62f-135">少し時間が経過すると、Outlook のページ、SharePoint、 [iOS 用の sharepoint モバイルアプリ](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a)、および[Android 用の sharepoint モバイルアプリ](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284)を含む、Microsoft 365 全体でそのことがわかります。</span><span class="sxs-lookup"><span data-stu-id="8d62f-135">After a short delay, you can see it throughout Microsoft 365, including on pages in Outlook, SharePoint, [SharePoint mobile app for iOS](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a), and [SharePoint mobile app for Android](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284).</span></span>

<span data-ttu-id="8d62f-136">カスタム アイコンまたはカスタム カラーはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-136">You can remove your custom icon or custom colors at any time.</span></span> <span data-ttu-id="8d62f-137">[テーマ] ページに戻り、[**カスタムテーマの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-137">Just return to the theme page and select **Remove custom theming**.</span></span>
  
## <a name="best-practices"></a><span data-ttu-id="8d62f-138">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="8d62f-138">Best Practices</span></span>

- <span data-ttu-id="8d62f-139">**ロゴイメージ**: すべての画面とすべてのズームレベルで、ロゴが高解像度で表示されるように、SVG ファイルタイプを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-139">**Logo image**: Use an SVG file type so that your logo appears at high resolution on all screens and at all zoom levels.</span></span>

- <span data-ttu-id="8d62f-140">**ユーザー設定の色**: 選択した**ロゴの画像**に対して、高いコントラスト比で**ナビゲーションバーの背景色**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-140">**Custom colors**: Choose a **Nav bar background color** with a high contrast ratio with the **Logo image** that you picked.</span></span> <span data-ttu-id="8d62f-141">すべてのテキストとアイコンが明確に表示されるように、**ナビゲーションバーの背景色**に対してハイコントラスト比率を使用して、**テキストとアイコン**の色を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-141">Choose a **Text and icons** color with a high contrast ratio to the **Nav bar background color** so that all text and icons are clearly visible.</span></span>

- <span data-ttu-id="8d62f-142">**アクセントの色**: 白または明るい背景に適切に表示されるものを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-142">**Accent color**: Pick one that shows up well on a white or light background.</span></span> <span data-ttu-id="8d62f-143">アクセント色は、白色または明るい背景上に表示される一部のリンクやボタンに色を付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d62f-143">The accent color is used to color some links and buttons that show up on a white or light background.</span></span> <span data-ttu-id="8d62f-144">たとえば、アクセントの色を使用して、ユーザーの受信トレイおよび Office.com ポータルページで要素の色を設定します。</span><span class="sxs-lookup"><span data-stu-id="8d62f-144">For example, the accent color is used to color elements in a user's inbox and on their Office.com portal page.</span></span> 
  
- <span data-ttu-id="8d62f-145">**コントラスト比**: テキスト、アイコン、またはボタンの色と背景色の間で推奨されるコントラスト比率は、4.5: 1 です。</span><span class="sxs-lookup"><span data-stu-id="8d62f-145">**Contrast ratio**: The recommended contrast ratio between text, icon, or button color and background color is 4.5:1.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8d62f-146">関連記事</span><span class="sxs-lookup"><span data-stu-id="8d62f-146">Related articles</span></span>

[<span data-ttu-id="8d62f-147">カスタム タイルをアプリ起動ツールに追加する</span><span class="sxs-lookup"><span data-stu-id="8d62f-147">Add custom tiles to the My apps page and app launcher</span></span>](../manage/customize-the-app-launcher.md)
  
  
