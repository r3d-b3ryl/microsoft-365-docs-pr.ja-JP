---
title: Microsoft マネージドデスクトップの構成可能な設定のリファレンス
description: Microsoft マネージドデスクトップで構成可能な設定のカテゴリを設定する
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a405f96ee7a113197fbc9c237779db3e3e5e5ca
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42632985"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="649f4-104">構成可能な設定のリファレンス-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="649f4-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="649f4-105">このトピックでは、Microsoft Managed Desktop を使用してユーザーが構成できる設定カテゴリの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="649f4-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="649f4-106">各設定カテゴリには、要件、ベストプラクティス、および設定カテゴリをカスタマイズする方法に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="649f4-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="649f4-107">デスクトップの背景画像</span><span class="sxs-lookup"><span data-stu-id="649f4-107">Desktop background picture</span></span>
<span data-ttu-id="649f4-108">組織内の Microsoft マネージドデスクトップデバイスのデスクトップの背景画像をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="649f4-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="649f4-109">これを使用して、会社ブランドまたはマーケティング資料を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="649f4-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="649f4-110">Requirements</span><span class="sxs-lookup"><span data-stu-id="649f4-110">Requirements</span></span>

<span data-ttu-id="649f4-111">デスクトップの背景画像では、これらの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="649f4-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="649f4-112">画像ファイル形式-.jpg、jpeg、または .png</span><span class="sxs-lookup"><span data-stu-id="649f4-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="649f4-113">ファイルの場所-信頼された安全な http (https) の場所でホストします。</span><span class="sxs-lookup"><span data-stu-id="649f4-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="649f4-114">許可されていません-Http およびファイル共有 (unc) の場所はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="649f4-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="649f4-115">デスクトップの背景画像をカスタマイズおよび展開する</span><span class="sxs-lookup"><span data-stu-id="649f4-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="649f4-116">**カスタムデスクトップの背景画像を追加するには**</span><span class="sxs-lookup"><span data-stu-id="649f4-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="649f4-117">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="649f4-117">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="649f4-118">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="649f4-119">[**構成可能**なワークスペース] で、[**デスクトップの背景画像**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="649f4-120">使用する画像の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="649f4-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="649f4-121">変更を保存してテストグループに展開するには、[**ステージ展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="649f4-122">ブラウザーの開始ページ</span><span class="sxs-lookup"><span data-stu-id="649f4-122">Browser start pages</span></span>
<span data-ttu-id="649f4-123">ユーザーが Microsoft Edge を起動すると、ブラウザーのスタートページが個々のタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="649f4-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="649f4-124">ユーザーが頻繁に使用するサイトのセットを簡単に開くことができるようにするには、各サイトのブラウザーのスタートページを追加します。</span><span class="sxs-lookup"><span data-stu-id="649f4-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="649f4-125">Requirements</span><span class="sxs-lookup"><span data-stu-id="649f4-125">Requirements</span></span>

<span data-ttu-id="649f4-126">ブラウザーの開始ページには、イントラネットまたはインターネットサイト用の完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="649f4-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="649f4-127">内部サイトが構成されている場合、これらのサイトへのアクセスが許可されるのは、社内ネットワークに接続されている場合、または VPN 接続を使用して接続している場合のみであることをユーザーに知らせてください。</span><span class="sxs-lookup"><span data-stu-id="649f4-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="649f4-128">ブラウザーのスタートページをカスタマイズおよび展開する</span><span class="sxs-lookup"><span data-stu-id="649f4-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="649f4-129">**ブラウザーの開始ページを追加するには**</span><span class="sxs-lookup"><span data-stu-id="649f4-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="649f4-130">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="649f4-130">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="649f4-131">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="649f4-132">[**構成可能**なワークスペース] で、[**ブラウザーの開始ページ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="649f4-133">[ **Add start page**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="649f4-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="649f4-134">[**ブラウザーの開始ページの追加] ページ**で、使用するサイトの URL を入力し、[**開始ページの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="649f4-135">その他のブラウザーのスタートページについて、手順1-5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="649f4-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="649f4-136">変更を保存してテストグループに展開するには、[**ステージ展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="649f4-137">エンタープライズモードのサイトリストの場所</span><span class="sxs-lookup"><span data-stu-id="649f4-137">Enterprise mode site list location</span></span>

<span data-ttu-id="649f4-138">Microsoft Edge との互換性の問題があることがわかっている特定の web サイトとアプリがある場合は、エンタープライズモードサイトリストを使用して、Internet Explorer 11 を使用して web サイトを自動的に開くことができます。</span><span class="sxs-lookup"><span data-stu-id="649f4-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="649f4-139">また、イントラネットサイトが Microsoft Edge で正常に動作しないことがわかっている場合は、Internet Explorer 11 を使用してすべてのイントラネットサイトを開くように設定できます。</span><span class="sxs-lookup"><span data-stu-id="649f4-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="649f4-140">エンタープライズモードを使用することは、Microsoft Edge を既定のブラウザーとして引き続き使用でき、アプリが Internet Explorer 11 で引き続き動作することを保証することを意味します。</span><span class="sxs-lookup"><span data-stu-id="649f4-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="649f4-141">エンタープライズモードのサイトリストの詳細については、「[エンタープライズモードおよびエンタープライズモードのサイトリスト](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="649f4-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="649f4-142">Https://の場所、またはエンタープライズモードサイトリストをホストしている内部共有の場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="649f4-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="649f4-143">Requirements</span><span class="sxs-lookup"><span data-stu-id="649f4-143">Requirements</span></span>

<span data-ttu-id="649f4-144">エンタープライズモードのサイトリストファイルでは、これらの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="649f4-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="649f4-145">ファイル形式-[ファイルの要件](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)を満たす XML ファイル</span><span class="sxs-lookup"><span data-stu-id="649f4-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="649f4-146">ファイルの場所-内部の https の場所にあるホストファイル。</span><span class="sxs-lookup"><span data-stu-id="649f4-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="649f4-147">許可されていません-内部ファイル共有 *(たとえば、*/) をホストすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="649f4-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="649f4-148">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="649f4-148">Best practices</span></span>

<span data-ttu-id="649f4-149">これらのベストプラクティスは、お客様が IT インフラストラクチャを近代化するための意思決定を支援するために提供されています。</span><span class="sxs-lookup"><span data-stu-id="649f4-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="649f4-150">**限られた数のサイトを選択**する-Microsoft Managed Desktop は、microsoft Edge を優先ブラウザーとして使用して、組織の全体的なセキュリティを向上させ、ユーザーにとっての利便性を向上させます。</span><span class="sxs-lookup"><span data-stu-id="649f4-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="649f4-151">このリストに含まれるほとんどのサイトは、多くのセキュリティ機能を含まない古いバージョンのブラウザーを必要とする従来の web アプリに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="649f4-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="649f4-152">別のサイト、または古いブラウザーを必要としない web アプリを検討**してください**。</span><span class="sxs-lookup"><span data-stu-id="649f4-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="649f4-153">または、新しいブラウザーを使用できるようにサイトを更新することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="649f4-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="649f4-154">新しいブラウザーは最新のテクノロジを使用して、セキュリティを向上させます。</span><span class="sxs-lookup"><span data-stu-id="649f4-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="649f4-155">エンタープライズサイトモードリストの場所をカスタマイズおよび展開する</span><span class="sxs-lookup"><span data-stu-id="649f4-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="649f4-156">**エンタープライズサイトモードリストの場所を追加するには**</span><span class="sxs-lookup"><span data-stu-id="649f4-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="649f4-157">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="649f4-157">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="649f4-158">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="649f4-159">[**構成可能**なワークスペース] で、[**エンタープライズモードのサイトリストの場所**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="649f4-160">サイトリストの https の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="649f4-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="649f4-161">変更を保存してテストグループに展開するには、[**ステージ展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="649f4-162">信頼済みサイト</span><span class="sxs-lookup"><span data-stu-id="649f4-162">Trusted sites</span></span>

<span data-ttu-id="649f4-163">信頼済みサイトを使用すると、さまざまなサイトのセキュリティゾーンをカスタマイズしたり、サイトを使用できる場所をカスタマイズしたりできます。</span><span class="sxs-lookup"><span data-stu-id="649f4-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="649f4-164">セキュリティゾーンには次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="649f4-164">Security zones include:</span></span> 
- <span data-ttu-id="649f4-165">ゾーン1–ローカルイントラネットゾーン</span><span class="sxs-lookup"><span data-stu-id="649f4-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="649f4-166">ゾーン2–信頼済みサイトゾーン</span><span class="sxs-lookup"><span data-stu-id="649f4-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="649f4-167">ゾーン3–インターネットゾーン</span><span class="sxs-lookup"><span data-stu-id="649f4-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="649f4-168">ゾーン 4-制限付きサイトゾーン</span><span class="sxs-lookup"><span data-stu-id="649f4-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="649f4-169">Requirements</span><span class="sxs-lookup"><span data-stu-id="649f4-169">Requirements</span></span>

<span data-ttu-id="649f4-170">信頼済みサイトごとにイントラネットまたはインターネットサイトの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="649f4-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="649f4-171">信頼済みサイトをカスタマイズおよび展開する</span><span class="sxs-lookup"><span data-stu-id="649f4-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="649f4-172">**信頼済みサイトを追加するには**</span><span class="sxs-lookup"><span data-stu-id="649f4-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="649f4-173">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="649f4-173">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="649f4-174">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="649f4-175">[**構成可能**なワークスペース] で、[**信頼済みサイト**] を選択し、[**信頼済みサイトの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="649f4-176">[**信頼済みサイトの追加**] で、URL を入力し、セキュリティゾーンを選択して、[**信頼済みサイトの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="649f4-177">追加する各信頼済みサイトについて、手順1-4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="649f4-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="649f4-178">変更を保存してテストグループに展開するには、[**ステージ展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="649f4-179">**信頼済みサイトを削除するには**</span><span class="sxs-lookup"><span data-stu-id="649f4-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="649f4-180">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="649f4-180">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="649f4-181">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="649f4-182">[**構成可能**なワークスペース] で、[**信頼済みサイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="649f4-183">削除するサイトを選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="649f4-184">削除する信頼済みサイトごとに、手順1-4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="649f4-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="649f4-185">変更を保存してテストグループに展開するには、[**ステージ展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="649f4-186">プロキシ</span><span class="sxs-lookup"><span data-stu-id="649f4-186">Proxy</span></span>
<span data-ttu-id="649f4-187">組織のネットワークプロキシ設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="649f4-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="649f4-188">プロキシサーバーとポート番号を追加して、プロキシサイトの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="649f4-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="649f4-189">Microsoft マネージドデスクトップには、サービスの動作に必要な既定のプロキシ例外のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="649f4-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="649f4-190">既定の除外リストは、Microsoft Managed Desktop service によってのみ変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="649f4-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="649f4-191">詳細については、「 [Microsoft マネージドデスクトップのネットワーク構成](../get-ready/network.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="649f4-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="649f4-192">Microsoft マネージドデスクトップポータルで追加するプロキシサイトの例外は、Microsoft Managed Desktop service に含まれている既定のプロキシ例外に追加されます。</span><span class="sxs-lookup"><span data-stu-id="649f4-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="649f4-193">既定のプロキシ例外リストの更新は、常に顧客展開より優先されます。</span><span class="sxs-lookup"><span data-stu-id="649f4-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="649f4-194">これは、既定のプロキシ例外リストの展開が存在する場合に、段階的な展開が一時停止することを意味します。</span><span class="sxs-lookup"><span data-stu-id="649f4-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="649f4-195">Requirements</span><span class="sxs-lookup"><span data-stu-id="649f4-195">Requirements</span></span>

<span data-ttu-id="649f4-196">プロキシサーバーおよびプロキシサイトの例外については、これらの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="649f4-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="649f4-197">有効なサーバーアドレスとポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="649f4-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="649f4-198">Url は有効な http サイトである必要があります</span><span class="sxs-lookup"><span data-stu-id="649f4-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="649f4-199">プロキシをカスタマイズおよび展開する</span><span class="sxs-lookup"><span data-stu-id="649f4-199">Customize and deploy proxies</span></span>

<span data-ttu-id="649f4-200">**個別のプロキシサイトの例外を追加するには**</span><span class="sxs-lookup"><span data-stu-id="649f4-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="649f4-201">[Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインする</span><span class="sxs-lookup"><span data-stu-id="649f4-201">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="649f4-202">[**設定**] で、[**構成可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="649f4-203">[**構成可能**なワークスペース] で、[**プロキシ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="649f4-204">プロキシサーバーの**アドレス**と**ポート番号**を入力し、[**プロキシ例外の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="649f4-205">有効な http サイトの URL を入力し、[**プロキシ例外の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="649f4-206">追加する各信頼済みサイトについて、手順1-5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="649f4-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="649f4-207">変更を保存してテストグループに展開するには、[**ステージ展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="649f4-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="649f4-208">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="649f4-208">Additional resources</span></span>
- [<span data-ttu-id="649f4-209">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="649f4-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="649f4-210">構成可能な設定を展開する</span><span class="sxs-lookup"><span data-stu-id="649f4-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
