---
title: Microsoft Managed Desktop の構成可能な設定リファレンス
description: Microsoft Managed Desktop で構成可能な設定のカテゴリを設定する
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917706"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="eb617-104">構成可能な設定リファレンス - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="eb617-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="eb617-105">このトピックでは、Microsoft Managed Desktop で構成できる設定カテゴリの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="eb617-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="eb617-106">各設定カテゴリには、要件、ベスト プラクティス、設定カテゴリのカスタマイズ方法に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb617-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="eb617-107">デスクトップの背景画像</span><span class="sxs-lookup"><span data-stu-id="eb617-107">Desktop background picture</span></span>
<span data-ttu-id="eb617-108">組織内の Microsoft Managed Desktop デバイスのデスクトップの背景画像をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="eb617-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="eb617-109">これを使用して、会社のブランドまたはマーケティング 資料を適用できます。</span><span class="sxs-lookup"><span data-stu-id="eb617-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="eb617-110">要件</span><span class="sxs-lookup"><span data-stu-id="eb617-110">Requirements</span></span>

<span data-ttu-id="eb617-111">デスクトップの背景画像では、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb617-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="eb617-112">ピクチャ ファイル形式 - .jpg、jpeg、または .png</span><span class="sxs-lookup"><span data-stu-id="eb617-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="eb617-113">ファイルの場所 - 信頼できるセキュリティで保護された http (https) の場所でホストします。</span><span class="sxs-lookup"><span data-stu-id="eb617-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="eb617-114">許可されていません - Http とファイル共有 (unc) の場所はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eb617-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="eb617-115">デスクトップの背景画像をカスタマイズして展開する</span><span class="sxs-lookup"><span data-stu-id="eb617-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="eb617-116">**カスタム デスクトップの背景画像を追加するには**</span><span class="sxs-lookup"><span data-stu-id="eb617-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="eb617-117">Microsoft Endpoint Manager に [サインインし、[](https://endpoint.microsoft.com/) デバイス] メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb617-117">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="eb617-118">[Microsoft Managed Desktop] セクションを探し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-118">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="eb617-119">[設定 **] ワークスペース** で、[デスクトップの **背景画像] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-119">In **Settings** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="eb617-120">使用する画像の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb617-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="eb617-121">[ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb617-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="eb617-122">ブラウザーの開始ページ</span><span class="sxs-lookup"><span data-stu-id="eb617-122">Browser start pages</span></span>
<span data-ttu-id="eb617-123">ユーザーが Microsoft Edge を起動すると、ブラウザーの開始ページが個々のタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="eb617-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="eb617-124">ユーザーが頻繁に使用する一連のサイトを簡単に開く場合は、サイトごとにブラウザーの開始ページを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb617-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="eb617-125">要件</span><span class="sxs-lookup"><span data-stu-id="eb617-125">Requirements</span></span>

<span data-ttu-id="eb617-126">ブラウザーのスタート ページにイントラネットまたはインターネット サイトの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb617-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="eb617-127">内部サイトが構成されている場合、これらのサイトへのアクセスは、社内ネットワークに接続されている場合、または VPN 接続に接続されている場合にのみ許可されていることをユーザーに知らせて下さい。</span><span class="sxs-lookup"><span data-stu-id="eb617-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="eb617-128">ブラウザーの開始ページのカスタマイズと展開</span><span class="sxs-lookup"><span data-stu-id="eb617-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="eb617-129">**ブラウザーの開始ページを追加するには**</span><span class="sxs-lookup"><span data-stu-id="eb617-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="eb617-130">Microsoft Endpoint Manager に [サインインし、[](https://endpoint.microsoft.com/) デバイス] メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb617-130">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="eb617-131">[Microsoft Managed Desktop] セクションを探し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-131">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="eb617-132">[設定 **] ワークスペースで** 、[ブラウザーの **開始ページ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-132">In **Settings** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="eb617-133">[スタート **ページの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="eb617-134">[ **ブラウザーの開始ページの追加]** で、使用するサイトの URL を入力し、[スタート ページの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="eb617-135">追加のブラウザーの開始ページについては、手順 1 ~ 5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb617-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="eb617-136">[ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb617-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="eb617-137">エンタープライズ モードのサイト一覧の場所</span><span class="sxs-lookup"><span data-stu-id="eb617-137">Enterprise mode site list location</span></span>

<span data-ttu-id="eb617-138">Microsoft Edge との互換性に問題がある特定の Web サイトとアプリがある場合は、エンタープライズ モード サイト一覧を使用して、web サイトが 11 を使用して自動的に開Internet Explorerできます。</span><span class="sxs-lookup"><span data-stu-id="eb617-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="eb617-139">また、イントラネット サイトが Microsoft Edge で正しく動作しない場合は、すべてのイントラネット サイトを自動的に 11 を使用して開Internet Explorerできます。</span><span class="sxs-lookup"><span data-stu-id="eb617-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="eb617-140">エンタープライズ モードを使用すると、Microsoft Edge を既定のブラウザーとして引き続き使用できる一方で、アプリが 11 で引き続き動作Internet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="eb617-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="eb617-141">エンタープライズ モード サイトリストの詳細については [、「Enterprise Mode and Enterprise Mode Site Lists」を参照してください](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。</span><span class="sxs-lookup"><span data-stu-id="eb617-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="eb617-142">エンタープライズ モード サイト一覧 https:// ホストしている内部共有の場所、または場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb617-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="eb617-143">要件</span><span class="sxs-lookup"><span data-stu-id="eb617-143">Requirements</span></span>

<span data-ttu-id="eb617-144">エンタープライズ モードのサイト 一覧ファイルでは、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb617-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="eb617-145">ファイル形式 - ファイル要件を満たす [XML ファイル](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="eb617-145">File format - XML file that meets [file requirements](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="eb617-146">ファイルの場所 - 内部 https の場所にファイルをホストします。</span><span class="sxs-lookup"><span data-stu-id="eb617-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="eb617-147">許可されない - *//sharename* のような内部ファイル共有でのホスティングは許可されません</span><span class="sxs-lookup"><span data-stu-id="eb617-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="eb617-148">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="eb617-148">Best practices</span></span>

<span data-ttu-id="eb617-149">これらのベスト プラクティスは、お客様が IT インフラストラクチャの最新化を決定する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb617-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="eb617-150">**限られた数の** サイトを選択します。 Microsoft Managed Desktop は、組織の全体的なセキュリティとユーザーの使いやすさを向上させるために、優先ブラウザーとして Microsoft Edge を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb617-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="eb617-151">この一覧のほとんどのサイトは、古いバージョンのブラウザーを必要とする従来の Web アプリ向けで、多くのセキュリティ機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb617-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="eb617-152">**別のサイトを検討** する – 古いブラウザーを必要としない別のサイトまたは Web アプリを検討してください。</span><span class="sxs-lookup"><span data-stu-id="eb617-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="eb617-153">または、新しいブラウザーを使用できるようサイトを更新する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="eb617-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="eb617-154">新しいブラウザーは最新のテクノロジを使用し、セキュリティの向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb617-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="eb617-155">エンタープライズ サイト モードの一覧の場所をカスタマイズして展開する</span><span class="sxs-lookup"><span data-stu-id="eb617-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="eb617-156">**エンタープライズ サイト モードの一覧の場所を追加するには**</span><span class="sxs-lookup"><span data-stu-id="eb617-156">**To add an enterprise site mode list location**</span></span>

1. <span data-ttu-id="eb617-157">Microsoft Endpoint Manager に [サインインし、[](https://endpoint.microsoft.com/) デバイス] メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb617-157">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="eb617-158">[Microsoft Managed Desktop] セクションを探し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-158">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="eb617-159">[設定 **] ワークスペース** で、[エンタープライズ モード **のサイト一覧の場所] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-159">In **Settings** workspace, select **Enterprise mode site list location**.</span></span> 
4. <span data-ttu-id="eb617-160">サイト一覧の https の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb617-160">Enter the https location for your site list.</span></span> 
5. <span data-ttu-id="eb617-161">[ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb617-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="eb617-162">信頼済みサイト</span><span class="sxs-lookup"><span data-stu-id="eb617-162">Trusted sites</span></span>

<span data-ttu-id="eb617-163">信頼済みサイトを使用すると、さまざまなサイトのセキュリティ ゾーンやサイトを使用できる場所をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="eb617-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="eb617-164">セキュリティ ゾーンには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb617-164">Security zones include:</span></span> 
- <span data-ttu-id="eb617-165">ゾーン 1 – ローカル イントラネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="eb617-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="eb617-166">ゾーン 2 – 信頼済みサイト ゾーン</span><span class="sxs-lookup"><span data-stu-id="eb617-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="eb617-167">ゾーン 3 – インターネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="eb617-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="eb617-168">ゾーン 4 – 制限付きサイト ゾーン</span><span class="sxs-lookup"><span data-stu-id="eb617-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="eb617-169">要件</span><span class="sxs-lookup"><span data-stu-id="eb617-169">Requirements</span></span>

<span data-ttu-id="eb617-170">信頼済みサイトごとにイントラネットまたはインターネット サイトの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb617-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="eb617-171">信頼できるサイトのカスタマイズと展開</span><span class="sxs-lookup"><span data-stu-id="eb617-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="eb617-172">**信頼できるサイトを追加するには**</span><span class="sxs-lookup"><span data-stu-id="eb617-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="eb617-173">Microsoft Endpoint Manager に [サインインし、[](https://endpoint.microsoft.com/) デバイス] メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb617-173">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="eb617-174">[Microsoft Managed Desktop] セクションを探し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-174">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="eb617-175">[設定 **] ワークスペース** で、[信頼済 **みサイト] を** 選択し、[信頼できるサイトの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-175">In **Settings** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="eb617-176">[ **信頼済みサイトの追加**] で、URL を入力し、セキュリティ ゾーンを選択し、[信頼済みサイトの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="eb617-177">追加する信頼済みサイトごとに手順 1 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb617-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="eb617-178">[ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb617-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="eb617-179">**信頼できるサイトを削除するには**</span><span class="sxs-lookup"><span data-stu-id="eb617-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="eb617-180">Microsoft Endpoint Manager に [サインインし、[](https://endpoint.microsoft.com/) デバイス] メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb617-180">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="eb617-181">[Microsoft Managed Desktop] セクションを探し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-181">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="eb617-182">[設定 **] ワークスペースで** 、[信頼済み **サイト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-182">In **Settings** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="eb617-183">削除するサイトを選択し、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="eb617-184">削除する信頼済みサイトごとに手順 1 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb617-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="eb617-185">[ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb617-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="eb617-186">プロキシ</span><span class="sxs-lookup"><span data-stu-id="eb617-186">Proxy</span></span>
<span data-ttu-id="eb617-187">組織のネットワーク プロキシ設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="eb617-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="eb617-188">プロキシ サーバーとポート番号を追加し、プロキシ サイトの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="eb617-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="eb617-189">Microsoft Managed Desktop には、サービスを動作するために必要な一連の既定のプロキシ例外が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb617-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="eb617-190">既定の除外リストは、Microsoft Managed Desktop サービスによってのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="eb617-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="eb617-191">詳細については [、「Microsoft Managed Desktop のネットワーク構成」を参照してください](../get-ready/network.md)。</span><span class="sxs-lookup"><span data-stu-id="eb617-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="eb617-192">Microsoft Managed Desktop ポータルに追加するプロキシ サイトの例外は、Microsoft Managed Desktop サービスに含まれる既定のプロキシ例外に追加されます。</span><span class="sxs-lookup"><span data-stu-id="eb617-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="eb617-193">既定のプロキシ例外リストの更新は、常に顧客の展開よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="eb617-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="eb617-194">つまり、既定のプロキシ例外リストの展開がある場合、ステージ展開は一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="eb617-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="eb617-195">要件</span><span class="sxs-lookup"><span data-stu-id="eb617-195">Requirements</span></span>

<span data-ttu-id="eb617-196">プロキシ サーバーとプロキシ サイトの例外に対して、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb617-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="eb617-197">有効なサーバー アドレスとポート番号である必要があります</span><span class="sxs-lookup"><span data-stu-id="eb617-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="eb617-198">URL は有効な http サイトである必要があります</span><span class="sxs-lookup"><span data-stu-id="eb617-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="eb617-199">プロキシのカスタマイズと展開</span><span class="sxs-lookup"><span data-stu-id="eb617-199">Customize and deploy proxies</span></span>

<span data-ttu-id="eb617-200">**個々のプロキシ サイトの例外を追加するには**</span><span class="sxs-lookup"><span data-stu-id="eb617-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="eb617-201">Microsoft Endpoint Manager に [サインインし、[](https://endpoint.microsoft.com/) デバイス] メニュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="eb617-201">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="eb617-202">[Microsoft Managed Desktop] セクションを探し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-202">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="eb617-203">[設定 **] ワークスペースで** 、[プロキシ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-203">In **Settings** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="eb617-204">プロキシ サーバー **のアドレス** と **ポート番号** を入力し、[プロキシ例外の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="eb617-205">有効な http サイトの URL を入力し、[プロキシ例外の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb617-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="eb617-206">追加する信頼済みサイトごとに手順 1 ~ 5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb617-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="eb617-207">[ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb617-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eb617-208">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="eb617-208">Additional resources</span></span>
- [<span data-ttu-id="eb617-209">構成可能な設定の概要</span><span class="sxs-lookup"><span data-stu-id="eb617-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="eb617-210">構成可能な設定を展開する</span><span class="sxs-lookup"><span data-stu-id="eb617-210">Deploy configurable settings</span></span>](config-setting-deploy.md)