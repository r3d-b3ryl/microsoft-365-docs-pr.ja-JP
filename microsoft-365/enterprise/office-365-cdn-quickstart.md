---
title: Office 365 コンテンツ配信ネットワーク (CDN) クイック スタート
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 コンテンツ配信ネットワーク (CDN) クイック スタート
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921596"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="e1830-103">Office 365 コンテンツ配信ネットワーク (CDN) クイック スタート</span><span class="sxs-lookup"><span data-stu-id="e1830-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="e1830-104">組み込みの Office **365** コンテンツ配信ネットワーク (CDN) を使用して静的アセット (イメージ、JavaScript、スタイルシート、WOFF ファイル) をホストし、SharePoint Online ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e1830-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="e1830-105">Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="e1830-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="e1830-106">また、365 CDN Officeは、圧縮と HTTP パイプライン処理を強化するために HTTP/2 プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1830-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="e1830-107">Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1830-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="e1830-108">詳細な情報ガイダンスについては [、「Use the Office 365 Content Delivery Network (CDN) with SharePoint Online 」を参照してください](use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="e1830-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="e1830-109">このOffice 365 CDN は、実稼働 (世界規模) クラウドのテナントでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="e1830-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="e1830-110">米国政府、中国、ドイツのクラウドのテナントは、現在、365 CDN Officeサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e1830-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="e1830-111">SharePoint のページ診断ツールを使用して CDN 内に含めてないアイテムを識別する</span><span class="sxs-lookup"><span data-stu-id="e1830-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="e1830-112">**SharePoint** ツール ブラウザー拡張機能のページ診断を使用すると、CDN 配信元に追加できる SharePoint Online ページのアセットを簡単に一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1830-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="e1830-113">**SharePoint のページ診断** ツールは、新しい Microsoft Edge (および SharePoint Online モダン ポータルと従来の発行サイト ページの両方を分析する Chrome ブラウザー) のブラウザー https://www.microsoft.com/edge) 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="e1830-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="e1830-114">このツールでは、定義されている一連のパフォーマンス条件に対するページのパフォーマンスを示す分析済みの各ページのレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1830-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="e1830-115">SharePoint 用ページ診断ツールのインストール方法と詳細については、「[SharePoint Online 用ページ診断ツールを使用する](./page-diagnostics-for-spo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1830-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="e1830-116">SharePoint Online ページで SharePoint 用ページ診断ツールを実行すると、[診断テスト]タブをクリックすると、CDN によってホストされていないアセットの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1830-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="e1830-117">これらのアセットは、下のスクリーンショットに示すように、コンテンツ配信 **ネットワーク (CDN) チェック** という見出しの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1830-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![ページ診断](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="e1830-119">ページ診断ツールは SharePoint Online でのみ機能し、SharePoint システム ページでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e1830-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="e1830-120">CDN の概要</span><span class="sxs-lookup"><span data-stu-id="e1830-120">CDN Overview</span></span>

<span data-ttu-id="e1830-121">Office 365 CDN は、画像や javascript ファイルなどの頻繁にアクセスするオブジェクトを高速グローバル ネットワーク上に分散し、ページの読み込み時間を短縮し、ホストされたオブジェクトへのアクセスをユーザーに可能な限り近く提供することで、ユーザーのパフォーマンスを最適化するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e1830-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="e1830-122">CDN は、配信元と呼ばれる場所からアセットをフェッチ _します_。</span><span class="sxs-lookup"><span data-stu-id="e1830-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="e1830-123">オリジンには、URL からアクセスできる SharePoint サイト、ドキュメント ライブラリ、またはフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1830-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="e1830-124">365 cdn Officeは、次の 2 つの基本的な種類に分かされています。</span><span class="sxs-lookup"><span data-stu-id="e1830-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="e1830-125">**パブリック CDN** は、JS (JavaScript)、CSS (StyleSheets)、Web フォント ファイル (WOFF、WOFF2)、会社のロゴなどの非専有画像に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e1830-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="e1830-126">**プライベート CDN** は、画像 (PNG、JPG、JPEG など) に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e1830-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="e1830-127">組織のパブリックオリジンとプライベートオリジンの両方を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1830-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="e1830-128">ほとんどの組織では、2 つの組み合わせを実装します。</span><span class="sxs-lookup"><span data-stu-id="e1830-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="e1830-129">パブリック オプションとプライベート オプションの両方が同様のパフォーマンス向上を実現しますが、それぞれに固有の属性と利点があります。</span><span class="sxs-lookup"><span data-stu-id="e1830-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="e1830-130">パブリック CDN とプライベート CDN の配信元の詳細については、「各配信元をパブリックまたはプライベートにするかどうかを選択する [」を参照してください](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。</span><span class="sxs-lookup"><span data-stu-id="e1830-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="e1830-131">既定の構成でパブリック CDN とプライベート CDN を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="e1830-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="e1830-132">テナント CDN 設定を変更する前に、組織のコンプライアンス、セキュリティ、およびプライバシー ポリシーを満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1830-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="e1830-133">詳細な構成設定については、または既に CDN を有効にし、追加の場所 (配信元) を追加する場合は、「SharePoint Online 管理シェルを使用して[Office 365 CDN](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)を設定して構成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1830-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="e1830-134">SharePoint Online 管理シェルを使用してテナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="e1830-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="e1830-135">組織でパブリックオリジンとプライベート オリジンの両方を既定の構成で使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e1830-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="e1830-136">これらのコマンドレットの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e1830-136">Output of these cmdlets should look like the following:</span></span>

![データの出力Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="e1830-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1830-138">See also</span></span>

[<span data-ttu-id="e1830-139">SharePoint Online のページ診断ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="e1830-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="e1830-140">SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用</span><span class="sxs-lookup"><span data-stu-id="e1830-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="e1830-141">Content Delivery Network</span><span class="sxs-lookup"><span data-stu-id="e1830-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="e1830-142">Office 365 のネットワーク計画とパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="e1830-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="e1830-143">SharePoint Performance Series - Office 365 CDN ビデオ シリーズ</span><span class="sxs-lookup"><span data-stu-id="e1830-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)