---
title: 複数地域環境でのユーザー エクスペリエンス
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Microsoft 365の複数地域環境での SharePoint、OneDrive、および Exchange のユーザー エクスペリエンスについて説明します。
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362380"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="84e8b-103">複数地域環境でのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="84e8b-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="84e8b-104">ここでは、OneDrive 複数地域構成でユーザーが確認できる内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="84e8b-105">Exchange メールボックス</span><span class="sxs-lookup"><span data-stu-id="84e8b-105">Exchange mailbox</span></span>

<span data-ttu-id="84e8b-106">ユーザーの Exchange メールボックスは、優先されるデータの場所にプロビジョニングされ、PDLが変更されると自動的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="84e8b-107">ユーザーは、複数地域の環境でユーザー エクスペリエンスを変えることなく、Outlook および Web 上の Outlook を通常どおりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="84e8b-108">ハブ サイト</span><span class="sxs-lookup"><span data-stu-id="84e8b-108">Hub sites</span></span>

<span data-ttu-id="84e8b-109">SharePoint ハブ サイトは、プロジェクト、部門、または地域の完全で一貫した表現を作成しながら、従業員のためのコンテンツの発見とエンゲージメントを強化します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="84e8b-110">複数地域の環境では、ハブ サイトの地理的な場所に関係なく、サテライトの場所のサイトをハブ サイトに簡単に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="84e8b-111">ユーザーは、サイトの地理的な場所に関係なく、単一の検索エクスペリエンスを通じてハブ全体で検索して結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="84e8b-112">Microsoft 365 アプリ起動ツール</span><span class="sxs-lookup"><span data-stu-id="84e8b-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="84e8b-113">アプリ起動ツールは、Multi-Geo に対応していて、各タイルをワークロードの適切な地域の場所に差し向けます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="84e8b-114">SharePoint と OneDrive のタイルは、ユーザーにプロビジョニングされた地理的な場所に対応する場所をポイントします。</span><span class="sxs-lookup"><span data-stu-id="84e8b-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="84e8b-115">つまり、ユーザーは中央の場所に OneDrive を持っており、その SharePoint タイルは中央の場所にある SP Home をポイントしますが、グループ サイトは PDL に対応する場所にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="84e8b-116">Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="84e8b-116">Office applications</span></span>

<span data-ttu-id="84e8b-117">Office Word、Excel、PowerPoint などのアプリケーションは、ログイン時に各ユーザー OneDrive位置情報を自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive geo-location for each user when they log in.</span></span> <span data-ttu-id="84e8b-118">ユーザーは、自分の OneDrive または SharePoint サイトの地域固有の URL を入力する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="84e8b-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-sync-app"></a><span data-ttu-id="84e8b-119">OneDrive 同期アプリ</span><span class="sxs-lookup"><span data-stu-id="84e8b-119">OneDrive sync app</span></span>

<span data-ttu-id="84e8b-120">OneDrive 同期アプリ (バージョン 17.3.6943.0625 以降) は、ユーザーの適切な地域OneDriveを自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-120">The OneDrive sync app (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive geo location for the user.</span></span> <span data-ttu-id="84e8b-121">同期アプリのサポートには、地域に関係なくグループ ベースのサイトを同期する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84e8b-121">Sync app support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="84e8b-122">Groove 同期クライアントは複数地域ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84e8b-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-location"></a><span data-ttu-id="84e8b-123">OneDrive場所</span><span class="sxs-lookup"><span data-stu-id="84e8b-123">OneDrive location</span></span>

<span data-ttu-id="84e8b-124">ユーザーは、ユーザーのOneDriveの場所にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-124">Users will have their OneDrive provisioned in their preferred data location.</span></span> <span data-ttu-id="84e8b-125">ユーザーが間違った地域の場所 (以前の地域の場所からのブックマークなど) を含む OneDrive URL に移動すると、適切な地域の場所にある OneDrive に自動的にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="84e8b-126">OneDrive iOS および Android</span><span class="sxs-lookup"><span data-stu-id="84e8b-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="84e8b-p107">OneDrive iOS および Android モバイル アプリには、ユーザーの OneDrive ファイルと、ユーザーの地域の場所と関係なくユーザーが共有しているファイルが表示されます。OneDrive モバイル アプリからの検索では、すべての地域の場所から関連する結果が表示されます。これらのアプリの最新バージョンをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="84e8b-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="84e8b-130">詳細については、「[iOS で OneDrive を使う](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247)」および「[Android で OneDrive を使う](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84e8b-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="84e8b-131">OneDrive モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="84e8b-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="84e8b-132">OneDriveモバイル クライアントは複数地域に対応し、すべての地理的位置から関連コンテンツと結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="84e8b-133">検索</span><span class="sxs-lookup"><span data-stu-id="84e8b-133">Search</span></span>

<span data-ttu-id="84e8b-134">各地域の場所には、独自の検索インデックスと検索センターがあります。</span><span class="sxs-lookup"><span data-stu-id="84e8b-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="84e8b-135">ユーザーが検索すると、クエリがすべての地域の場所に送信され、返される結果が結合されてランク付けされ、ユーザーが統合された結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="84e8b-136">ユーザーは、自分の地理的位置に関係なく、すべての地域の場所から結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="84e8b-137">詳細[については、「Configure Search for OneDriveマルチジオ](configure-search-for-multi-geo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84e8b-137">See [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="84e8b-138">サポートされている検索クライアントは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84e8b-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="84e8b-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="84e8b-139">OneDrive</span></span>

-   <span data-ttu-id="84e8b-140">Delve</span><span class="sxs-lookup"><span data-stu-id="84e8b-140">Delve</span></span>

-   <span data-ttu-id="84e8b-141">SharePoint Home</span><span class="sxs-lookup"><span data-stu-id="84e8b-141">SharePoint Home</span></span>

-   <span data-ttu-id="84e8b-142">検索センター</span><span class="sxs-lookup"><span data-stu-id="84e8b-142">The Search Center</span></span>

-   <span data-ttu-id="84e8b-143">SharePoint 検索 API を使用するカスタムの検索アプリケーション</span><span class="sxs-lookup"><span data-stu-id="84e8b-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="84e8b-144">SharePoint Home</span><span class="sxs-lookup"><span data-stu-id="84e8b-144">SharePoint Home</span></span> 

<span data-ttu-id="84e8b-145">[SharePoint-Geo] では、ユーザー SharePoint場所によって決定された場所で、ユーザーのホームがホストOneDriveされます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive location.</span></span> <span data-ttu-id="84e8b-146">たとえば、ユーザーが自分の OneDrive をヨーロッパのサテライトの場所でホストしている場合、その SharePoint ホームはヨーロッパからレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="84e8b-147">SharePoint ホームには、地理的な場所に関係なく、ユーザーに関連するすべてのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84e8b-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="84e8b-148">**フォローしているサイト、サイトからのニュース、最近のサイト、よく使うサイト、そしておすすめのサイト**</span><span class="sxs-lookup"><span data-stu-id="84e8b-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="84e8b-149">ユーザーが当該コンテンツに対する権限を持っている限り、コンテンツがホストされている地理的な場所に関係なく、これらすべてのコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="84e8b-150">**おすすめリンク**</span><span class="sxs-lookup"><span data-stu-id="84e8b-150">**Features Links**</span></span>

<span data-ttu-id="84e8b-151">管理者は、各地理的な場所に対応して、SharePoint ホームのおすすめリンクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="84e8b-152">これにより、管理者は各地域の SP ホームでその地域のユーザーに適したリンクをおすすめできます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="84e8b-153">SharePoint モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="84e8b-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="84e8b-154">SharePoint モバイル クライアントは複数地域に対応し、すべての地理的位置から関連コンテンツと結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="84e8b-155">共有</span><span class="sxs-lookup"><span data-stu-id="84e8b-155">Sharing</span></span>

<span data-ttu-id="84e8b-156">連絡先の選択のエクスペリエンスでは、地理的な場所に関係なくすべてのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="84e8b-157">これにより、ユーザーは、同じ地域または他のテナントの地域内の他のユーザーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="84e8b-158">異なる地域の場所からのコンテンツは、ユーザーのOneDrive の [自分と共有] ビューに表示され、ホストされている地域の場所に関係なく、シングル Sign-On エクスペリエンスでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="84e8b-159">Teams のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="84e8b-159">Teams Experience</span></span>

<span data-ttu-id="84e8b-160">Teamsは複数地域サービスです。</span><span class="sxs-lookup"><span data-stu-id="84e8b-160">Teams is a multi-geo service.</span></span> <span data-ttu-id="84e8b-161">OneDrive ファイルと最近表示したファイルは、ユーザーの地理的な場所に関係なく表示されます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="84e8b-162">@メンションはすべての地理的な場所からのユーザーに機能します。</span><span class="sxs-lookup"><span data-stu-id="84e8b-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="84e8b-163">ユーザー プロファイル</span><span class="sxs-lookup"><span data-stu-id="84e8b-163">User profiles</span></span>

<span data-ttu-id="84e8b-p113">ユーザー プロファイル情報は、ユーザーの地域の場所でマスター管理されます。ユーザーを選択すると、そのユーザーにとって適切な地域の場所に転送され、完全なプロファイルの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="84e8b-166">Delve がオフの場合、SharePoint の従来の (複数地域に対応していない) プロファイル エクスペリエンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84e8b-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


