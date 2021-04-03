---
title: SharePoint Online Office 365 コンテンツ配信ネットワーク (CDN) を使用する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: SharePoint Online アセットの配信を高速化Office 365 コンテンツ配信ネットワーク (CDN) を使用する方法について説明します。
ms.openlocfilehash: 6819f627d3590cd2739b36cb1bc303f197d6aaa5
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570407"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="f9873-103">SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用</span><span class="sxs-lookup"><span data-stu-id="f9873-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="f9873-104">組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的資産をホストすることで、SharePoint Online ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f9873-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="f9873-105">Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="f9873-106">また、Office 365 CDN は、圧縮と HTTP パイプライン処理を強化するために [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="f9873-107">Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9873-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-108">このOffice 365 CDN は、Production **(ワールド** ワイド) クラウドのテナントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="f9873-109">米国政府、中国、ドイツのクラウドのテナントは、現在、365 CDN Officeサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f9873-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="f9873-110">Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。</span><span class="sxs-lookup"><span data-stu-id="f9873-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="f9873-111">Office 365 CDN でホストするコンテンツの種類に応じて、**公開**、**非公開**、またはその両方の元の場所を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="f9873-112">パブリック [オリジンとプライベートオリジン](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) の違いの詳細については、「各オリジンをパブリックまたはプライベートにするかどうかを選択する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="f9873-113">![Office 365 CDN の概念図](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN の概念図")</span><span class="sxs-lookup"><span data-stu-id="f9873-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="f9873-114">CDN の動作方法を既に理解している場合は、テナントの 365 CDN を有効にするには、Office手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="f9873-115">このトピックでは、方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9873-115">This topic describes how.</span></span> <span data-ttu-id="f9873-116">静的アセットのホスティングを開始する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="f9873-117">他にも、Office 365 と一緒に使用できる Microsoft ホスト型 CDN は、特殊な使用シナリオで使用できますが、Office 365 CDN の範囲を外れたため、このトピックでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="f9873-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="f9873-118">詳細については、「その他の [Microsoft CDN」を参照してください](content-delivery-networks.md#other-microsoft-cdns)。</span><span class="sxs-lookup"><span data-stu-id="f9873-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="f9873-119">**[365 のネットワーク計画と](./network-planning-and-performance.md)パフォーマンスの調整に戻Officeします。**</span><span class="sxs-lookup"><span data-stu-id="f9873-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="f9873-120">SharePoint Online の Office 365 CDN の操作の概要</span><span class="sxs-lookup"><span data-stu-id="f9873-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="f9873-121">組織の 365 CDN Office設定するには、次の基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="f9873-122">365 CDN の展開Office計画する</span><span class="sxs-lookup"><span data-stu-id="f9873-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="f9873-123">[CDN でホストする静的アセットを決定します](use-microsoft-365-cdn-with-spo.md#CDNAssets)。</span><span class="sxs-lookup"><span data-stu-id="f9873-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="f9873-124">[アセットを格納する場所を決定します](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。</span><span class="sxs-lookup"><span data-stu-id="f9873-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="f9873-125">この場所には、SharePoint サイト、ライブラリ、またはフォルダーを指定できます。これは原点と呼 _ばれる場所です_。</span><span class="sxs-lookup"><span data-stu-id="f9873-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="f9873-126">[各オリジンをパブリックまたはプライベートにするかどうかを選択します](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。</span><span class="sxs-lookup"><span data-stu-id="f9873-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="f9873-127">パブリック型とプライベート型の両方の複数のオリジンを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="f9873-128">PowerShell または SharePoint Online CLI を使用して CDN を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="f9873-129">SharePoint Online 管理シェルを使用して CDN を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="f9873-130">PnP PowerShell を使用して CDN を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="f9873-131">365 CLI を使用して CDN を設定Office構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="f9873-132">この手順を完了すると、次の機能が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="f9873-133">組織の CDN を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="f9873-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="f9873-134">各オリジンをパブリックまたはプライベートとして識別するオリジンを追加しました。</span><span class="sxs-lookup"><span data-stu-id="f9873-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="f9873-135">セットアップが完了したら、次の方法で [365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) Officeを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="f9873-136">アセットの追加、更新、および削除</span><span class="sxs-lookup"><span data-stu-id="f9873-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="f9873-137">原点の追加と削除</span><span class="sxs-lookup"><span data-stu-id="f9873-137">Adding and removing origins</span></span>
+ <span data-ttu-id="f9873-138">CDN ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="f9873-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="f9873-139">必要に応じて、CDN を無効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="f9873-140">最後に [、「CDN アセットを使用して](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) パブリックとプライベートの両方の配信元から CDN アセットにアクセスする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="f9873-141">一 [般的な問題の解決Officeについては、「365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) のトラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="f9873-142">365 CDN の展開Office計画する</span><span class="sxs-lookup"><span data-stu-id="f9873-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="f9873-143">Office 365 テナントに Office 365 CDN を展開する前に、計画プロセスの一環として次の要素を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="f9873-144">CDN でホストする静的アセットを決定する</span><span class="sxs-lookup"><span data-stu-id="f9873-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="f9873-145">アセットの保存場所を決定する</span><span class="sxs-lookup"><span data-stu-id="f9873-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="f9873-146">各オリジンをパブリックまたはプライベートにするかどうかを選択する</span><span class="sxs-lookup"><span data-stu-id="f9873-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="f9873-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="f9873-148">CDN でホストする静的アセットを決定する</span><span class="sxs-lookup"><span data-stu-id="f9873-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="f9873-149">一般に、CDN は静的アセット、またはあまり頻繁に変更しないアセットをホストする場合に最も効果的です。</span><span class="sxs-lookup"><span data-stu-id="f9873-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="f9873-150">経験則として、次の条件の一部またはすべてが満たされているファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="f9873-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="f9873-151">ページに埋め込まれた静的ファイル (スクリプトや画像など) で、ページの読み込み時間に大きな増分影響を与える可能性がある</span><span class="sxs-lookup"><span data-stu-id="f9873-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="f9873-152">実行可能ファイルやインストール ファイルのような大きなファイル</span><span class="sxs-lookup"><span data-stu-id="f9873-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="f9873-153">クライアント側コードをサポートするリソース ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f9873-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="f9873-154">たとえば、サイト イメージやスクリプトのように繰り返し要求される小さなファイルは、サイトレンダリングのパフォーマンスを大幅に向上し、CDN 配信元に追加するときに SharePoint Online サイトの負荷を徐々に軽減できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="f9873-155">インストール実行可能ファイルなどの大きなファイルを CDN からダウンロードして、パフォーマンスにプラスの影響を与え、SharePoint Online サイトへの負荷を軽減できます。たとえアクセス頻度が高くなくてもです。</span><span class="sxs-lookup"><span data-stu-id="f9873-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="f9873-156">ファイル単位でのパフォーマンスの向上は、クライアントが最も近い CDN エンドポイントへの近接性、ローカル ネットワーク上の一時的な状態など、多くの要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="f9873-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="f9873-157">多くの静的ファイルは非常に小さく、1 秒Office 365 からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="f9873-158">ただし、Web ページには、累積ダウンロード時間が数秒の埋め込みファイルが多数含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="f9873-159">CDN からこれらのファイルを提供すると、ページ全体の読み込み時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="f9873-160">例 [については、「CDN が提供するパフォーマンスの向上](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9873-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="f9873-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="f9873-162">アセットの保存場所を決定する</span><span class="sxs-lookup"><span data-stu-id="f9873-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="f9873-163">CDN は、配信元と呼ばれる場所からアセットをフェッチ _します_。</span><span class="sxs-lookup"><span data-stu-id="f9873-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="f9873-164">オリジンには、URL からアクセスできる SharePoint サイト、ドキュメント ライブラリ、またはフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="f9873-165">組織の起点を指定する場合、柔軟性が高い。</span><span class="sxs-lookup"><span data-stu-id="f9873-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="f9873-166">たとえば、複数の配信元を指定したり、すべての CDN アセットを置く 1 つの配信元を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="f9873-167">組織のパブリックオリジンとプライベートオリジンの両方を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="f9873-168">ほとんどの組織では、2 つの組み合わせを実装します。</span><span class="sxs-lookup"><span data-stu-id="f9873-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="f9873-169">フォルダーやドキュメント ライブラリなどの配信元の新しいコンテナーを作成し、CDN から使用できるファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="f9873-170">これは、CDN から利用できる特定のアセットセットを持ち、CDN アセットのセットをコンテナー内のファイルにのみ制限する場合に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="f9873-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="f9873-171">また、既存のサイト コレクション、サイト、ライブラリ、またはフォルダーを配信元として構成し、コンテナー内のすべての適格なアセットを CDN から利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="f9873-172">既存のコンテナーをオリジンとして追加する前に、コンテンツとアクセス許可を認識し、不注意でアセットを匿名アクセスや承認されていないユーザーに公開することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f9873-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="f9873-173">CDN ポリシーを _定義して、_ 配信元のコンテンツを CDN から除外できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="f9873-174">CDN ポリシーは、ファイルの種類やサイトの分類などの属性によってパブリックまたはプライベートオリジンのアセットを除外し、ポリシーで指定した CdnType (プライベートまたはパブリック) のすべての配信元に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="f9873-175">たとえば、複数のサブサイトを含むサイトで構成されるプライベート オリジンを追加する場合は、機密としてマークされたサイトを除外するポリシーを定義して、その分類が適用されたサイトのコンテンツが CDN から提供されません。</span><span class="sxs-lookup"><span data-stu-id="f9873-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="f9873-176">ポリシーは、CDN に追加 _した_ すべてのプライベート配信元のコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="f9873-177">配信元の数が多い場合、CDN サービスが要求を処理する時間に与える影響が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="f9873-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="f9873-178">可能な限り原点の数を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9873-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="f9873-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="f9873-180">各オリジンをパブリックまたはプライベートにするかどうかを選択する</span><span class="sxs-lookup"><span data-stu-id="f9873-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="f9873-181">発生元を特定する場合は、公開または非公開に _するかどうかを_ 指定 _します_。</span><span class="sxs-lookup"><span data-stu-id="f9873-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="f9873-182">パブリック 配信元の CDN アセットへのアクセスは匿名であり、プライベート配信元の CDN コンテンツは、セキュリティを強化するために動的に生成されたトークンによってセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="f9873-183">選択したオプションに関係なく、CDN 自体の管理に関しては、Microsoft が重い作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f9873-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="f9873-184">また、CDN を設定して配信元を特定した後で、後で考え方を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="f9873-185">パブリック オプションとプライベート オプションの両方が同様のパフォーマンス向上を実現しますが、それぞれに固有の属性と利点があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="f9873-186">**Office** 365 CDN 内のパブリックオリジンは匿名でアクセス可能であり、ホストされたアセットには、アセットへの URL を持つユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="f9873-187">公開されている元の場所のコンテンツへのアクセスは匿名になるため、アクセスしたコンテンツは、機密データ以外の一般的なコンテンツ (JavaScript ファイル、スクリプト、アイコン、画像など) をキャッシュする場合にのみ使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f9873-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="f9873-188">**Office** 365 CDN 内のプライベートオリジンは、SharePoint Online ドキュメント ライブラリ、サイト、および独自のイメージなどのユーザー コンテンツへのプライベート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f9873-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="f9873-189">プライベート オリジンのコンテンツへのアクセスは、動的に生成されたトークンによって保護され、元のドキュメント ライブラリまたは保存場所へのアクセス許可を持つユーザーだけがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="f9873-190">Office 365 CDN のプライベートオリジンは SharePoint Online コンテンツにのみ使用できます。プライベート配信元のアセットにアクセスできるのは、SharePoint Online テナントからのリダイレクトによってのみです。</span><span class="sxs-lookup"><span data-stu-id="f9873-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="f9873-191">プライベートオリジンのアセットへの CDN アクセスの仕組みについては、「プライベート オリジンでアセットを使用する」 [をご覧ください](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)。</span><span class="sxs-lookup"><span data-stu-id="f9873-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="f9873-192">パブリックオリジンでアセットをホストする属性と利点</span><span class="sxs-lookup"><span data-stu-id="f9873-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="f9873-193">パブリックの配信元で公開されている資産には、すべてのユーザーが匿名でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="f9873-194">ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="f9873-195">パブリックの配信元から資産を削除した場合、その資産は最大 30 日間はキャッシュから引き続き使用できます。ただし、CDN 内の資産へのリンクは 15 分以内に無効になります。</span><span class="sxs-lookup"><span data-stu-id="f9873-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="f9873-196">パブリックの配信元にスタイル シート (CSS ファイル) をホストする場合は、コード内で相対パスと URI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="f9873-197">つまり、背景画像と他のオブジェクトの場所を、呼び出し元の資産の場所からの相対位置で参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f9873-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="f9873-198">パブリック オリジンの URL を作成することもできますが、慎重に進み、ページ コンテキスト プロパティを使用し、そのガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="f9873-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="f9873-199">CDN にアクセスできなくなった場合、SharePoint Online でその URL は自動的に組織に対して解決されず、結果としてリンクが壊れて他のエラーが発生する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="f9873-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="f9873-200">URL も変更される可能性があります。これは、現在の値に対してハードコードされるだけではない理由です。</span><span class="sxs-lookup"><span data-stu-id="f9873-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="f9873-201">パブリックオリジンに含まれる既定のファイルの種類は、.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2 です。</span><span class="sxs-lookup"><span data-stu-id="f9873-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="f9873-202">追加のファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="f9873-203">指定したサイト分類によって識別されたアセットを除外するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="f9873-204">たとえば、許可されているファイルの種類のもので、パブリックの配信元にある資産であっても、"社外秘" または "制限付き" としてマークされている資産はすべて除外する、といったことができます。</span><span class="sxs-lookup"><span data-stu-id="f9873-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="f9873-205">プライベートオリジンでアセットをホストする属性と利点</span><span class="sxs-lookup"><span data-stu-id="f9873-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="f9873-206">プライベートオリジンは、SharePoint Online アセットにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="f9873-207">ユーザーは、コンテナーにアクセスするためのアクセス許可を持っている場合にのみ、プライベートオリジンからアセットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="f9873-208">これらの資産に匿名でアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="f9873-209">プライベートオリジンのアセットは、SharePoint Online テナントから参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="f9873-210">プライベート CDN アセットへの直接アクセスは機能しません。</span><span class="sxs-lookup"><span data-stu-id="f9873-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="f9873-211">プライベートオリジンからアセットを削除した場合、アセットはキャッシュから最大 1 時間引き続き使用できます。ただし、アセットの削除から 15 分以内に CDN 内のアセットへのリンクは無効になります。</span><span class="sxs-lookup"><span data-stu-id="f9873-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="f9873-212">プライベートの配信元用に含まれている既定のファイルの種類は、.gif、.ico、.jpeg、.jpg、.js、.png です。</span><span class="sxs-lookup"><span data-stu-id="f9873-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="f9873-213">追加のファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="f9873-214">パブリックオリジンと同様に、ワイルドカードを使用してフォルダーまたはドキュメント ライブラリ内のすべてのアセットを含める場合でも、指定したサイト分類によって識別されたアセットを除外するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="f9873-215">Office 365 CDN、一般的な CDN 概念、および Office 365 テナントで使用できるその他の Microsoft CDN を使用する理由の詳細については、「Content [Delivery Networks」](content-delivery-networks.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="f9873-216">既定の CDN 配信元</span><span class="sxs-lookup"><span data-stu-id="f9873-216">Default CDN origins</span></span>

<span data-ttu-id="f9873-217">特に指定しない限り、Office 365 では、365 CDN を有効にするときに既定の配信元Office設定します。</span><span class="sxs-lookup"><span data-stu-id="f9873-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="f9873-218">最初にプロビジョニングしない場合は、セットアップの完了後にこれらのオリジンを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="f9873-219">既定の配信元のセットアップをスキップした結果を理解し、その理由が特定の理由がない限り、CDN を有効にするときに作成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="f9873-220">既定のプライベート CDN 配信元:</span><span class="sxs-lookup"><span data-stu-id="f9873-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="f9873-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="f9873-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="f9873-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="f9873-222">\*/siteassets</span></span>

<span data-ttu-id="f9873-223">既定のパブリック CDN の配信元:</span><span class="sxs-lookup"><span data-stu-id="f9873-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="f9873-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="f9873-224">\*/masterpage</span></span>
+ <span data-ttu-id="f9873-225">\*/style ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f9873-225">\*/style library</span></span>
+ <span data-ttu-id="f9873-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="f9873-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-227">_clientsideassets は_ 、2017 年 12 月に Office 365 CDN サービスに追加された既定のパブリック 配信元です。</span><span class="sxs-lookup"><span data-stu-id="f9873-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="f9873-228">CDN の SharePoint Framework ソリューションが機能するには、このオリジンが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="f9873-229">2017 年 12 月より前に Office 365 CDN を有効にした場合、または CDN を有効にするときに既定の配信元のセットアップをスキップした場合は、手動でこの配信元を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="f9873-230">詳細については [、「My client-side Web パーツまたは SharePoint Framework ソリューションが機能しない」を参照してください](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。</span><span class="sxs-lookup"><span data-stu-id="f9873-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="f9873-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="f9873-232">SharePoint Online 管理シェルを使用Office 365 CDN のセットアップと構成</span><span class="sxs-lookup"><span data-stu-id="f9873-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="f9873-233">このセクションの手順では、SharePoint Online 管理シェルを使用して SharePoint Online に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="f9873-234">手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="f9873-235">SharePoint Online 管理シェルを使用して SharePoint Online でアセットをホストする CDN を設定および構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="f9873-236">クリックして展開</span><span class="sxs-lookup"><span data-stu-id="f9873-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="f9873-237">組織が 365 CDN Officeを有効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="f9873-238">テナント CDN 設定を変更する前に、365 テナントのプライベート CDN 構成の現在Officeする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="f9873-239">SharePoint Online 管理シェルを使用してテナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="f9873-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="f9873-240">**Get-SPOTenantCdnEnabled** コマンドレットを使用して、テナントから CDN 状態設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="f9873-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="f9873-241">指定した CdnType の CDN の状態が画面に出力されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="f9873-242">**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織が 365 CDN Office使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="f9873-243">組織でパブリックオリジン、プライベートオリジン、または両方を一度に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="f9873-244">また、CDN を有効にするときに既定の配信元のセットアップをスキップする構成もできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="f9873-245">このトピックの説明に従って、これらの原点は後でいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="f9873-246">SharePoint online Windows PowerShellで、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="f9873-247">たとえば、組織でパブリックオリジンとプライベート オリジンの両方を使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="f9873-248">組織でパブリックオリジンとプライベート オリジンの両方を使用できますが、既定のオリジンの設定をスキップするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="f9873-249">Office 365 CDN を有効にした場合に既定でプロビジョニングされる配信元と、既定の配信元のセットアップをスキップした場合の潜在的な影響については、「Default [CDN origins」](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="f9873-250">組織でパブリックオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="f9873-251">組織でプライベートオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="f9873-252">このコマンドレットの詳細については [、「Set-SPOTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="f9873-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="f9873-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="f9873-254">365 CDN に含めるファイルの種類Office変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="f9873-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="f9873-255">**Set-SPOTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9873-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="f9873-256">リストに追加のファイルの種類を追加する場合は、まずコマンドレットを使用して、既に許可されているファイルの種類を確認し、新しいファイルの種類と一緒にリストに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="f9873-257">**Set-SPOTenantCdnPolicy** コマンドレットを使用して、CDN のパブリックオリジンとプライベート オリジンでホストできる静的ファイルの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="f9873-258">既定では、.css、.gif、.jpg、.js など、一般的なアセットの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="f9873-259">SharePoint online Windows PowerShellで、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="f9873-260">たとえば、CDN で .css ファイルと .png ファイルをホストするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="f9873-261">CDN で現在許可されているファイルの種類を確認するには **、Get-SPOTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f9873-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="f9873-262">これらのコマンドレットの詳細については [、「Set-SPOTenantCdnPolicy」](/powershell/module/sharepoint-online/) および [「Get-SPOTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="f9873-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="f9873-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="f9873-264">365 CDN から除外するサイト分類のOffice変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="f9873-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="f9873-265">**Set-SPOTenantCdnPolicy** コマンドレットを使用してサイトの分類を除外すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9873-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="f9873-266">追加のサイト分類を除外する場合は、まずコマンドレットを使用して、既に除外されている分類を確認し、新しい分類と共に追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="f9873-267">
  \*\*Set-SPOTenantCdnPolicy\*\* コマンドレットを使用して、CDN で利用できるようにしないサイトの分類を除外します。</span><span class="sxs-lookup"><span data-stu-id="f9873-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="f9873-268">既定で除外されるサイトの分類はありません。</span><span class="sxs-lookup"><span data-stu-id="f9873-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="f9873-269">SharePoint online Windows PowerShellで、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="f9873-270">現在制限されているサイト分類を確認するには **、Get-SPOTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f9873-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="f9873-271">返されるプロパティは IncludeFileExtensions、ExcludeRestrictedSiteClassifications、ExcludeIfNoScriptDisabled _です_。  </span><span class="sxs-lookup"><span data-stu-id="f9873-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="f9873-272">_IncludeFileExtensions_ プロパティには、CDN から提供されるファイル拡張子の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9873-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-273">既定のファイル拡張子は、パブリックとプライベートの間で異なります。</span><span class="sxs-lookup"><span data-stu-id="f9873-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="f9873-274">_ExcludeRestrictedSiteClassifications_ プロパティには、CDN から除外するサイト分類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9873-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="f9873-275">たとえば、機密としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツが CDN から提供されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="f9873-276">_ExcludeIfNoScriptDisabled プロパティは_、サイト レベルの _NoScript_ 属性設定に基づいて CDN からコンテンツを除外します。</span><span class="sxs-lookup"><span data-stu-id="f9873-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="f9873-277">既定では _、NoScript_ 属性は [モダンサイトに対して有効] および [クラシック サイト **では無効]** _に設定_ されています。</span><span class="sxs-lookup"><span data-stu-id="f9873-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="f9873-278">これは、テナントの設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f9873-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="f9873-279">これらのコマンドレットの詳細については [、「Set-SPOTenantCdnPolicy」](/powershell/module/sharepoint-online/) および [「Get-SPOTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="f9873-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="f9873-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="f9873-281">アセットのオリジンを追加する</span><span class="sxs-lookup"><span data-stu-id="f9873-281">Add an origin for your assets</span></span>

<span data-ttu-id="f9873-282">発生元 **を定義するには、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="f9873-283">複数の配信元を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-283">You can define multiple origins.</span></span> <span data-ttu-id="f9873-284">配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。</span><span class="sxs-lookup"><span data-stu-id="f9873-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f9873-285">ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="f9873-286">path の値 _は_ 、アセットを含むライブラリまたはフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="f9873-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="f9873-287">相対パスに加え、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="f9873-288">Origins は、URL の先頭に付加されたワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f9873-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="f9873-289">これにより、複数のサイトにまたがるオリジンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="f9873-290">たとえば、すべてのサイトの masterpages フォルダー内のすべてのアセットを CDN 内のパブリック オリジンとして含めるには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="f9873-291">ワイルドカード修飾子 \* は、パスの先頭でのみ使用できます。指定した URL の下のすべての URL セグメント **/** と一致します。</span><span class="sxs-lookup"><span data-stu-id="f9873-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="f9873-292">パスは、ドキュメント ライブラリ、フォルダー、またはサイトを指します。</span><span class="sxs-lookup"><span data-stu-id="f9873-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="f9873-293">たとえば、パス _\*/site1 は_ 、サイトの下のすべてのドキュメント ライブラリと一致します。</span><span class="sxs-lookup"><span data-stu-id="f9873-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="f9873-294">特定の相対パスを持つ原点を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="f9873-295">完全パスを使用して原点を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="f9873-296">次の使用例は、サイトアセッツ ライブラリのプライベートオリジンを特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="f9873-297">次の使用例は、サイト コレクションのサイト アセット ライブラリに _folder1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="f9873-298">パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換える方法があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="f9873-299">次の例では、サイト コレクションのサイト アセット ライブラリにフォルダー _1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="f9873-300">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-301">プライベートオリジンでは、配信元から共有されているアセットに、CDN からアクセスする前にメジャー バージョンが発行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="f9873-302">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-303">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="f9873-305">例: SharePoint Online のマスター ページとスタイル ライブラリのパブリックオリジンを構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="f9873-306">通常、これらの配信元は、既定で 365 CDN を有効Office設定されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="f9873-307">ただし、手動で有効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="f9873-308">スタイル ライブラリをパブリックオリジンとして定義するには **、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="f9873-309">マスター ページをパブリックオリジンとして定義するには **、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="f9873-310">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="f9873-311">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-312">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="f9873-314">例: SharePoint Online のサイトアセット、サイト ページ、および発行イメージのプライベートオリジンを構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="f9873-315">**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイトアセット フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="f9873-316">**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="f9873-317">発行イメージ **フォルダーをプライベートオリジンとして定義するには、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="f9873-318">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="f9873-319">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-320">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="f9873-322">例: SharePoint Online のサイト コレクションのプライベートオリジンを構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="f9873-323">**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="f9873-324">例:</span><span class="sxs-lookup"><span data-stu-id="f9873-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="f9873-325">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="f9873-326">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-327">SharePoint Online テナント _が_ CDN サービスに接続すると予想される構成保留中のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9873-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="f9873-328">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="f9873-330">365 CDN Office管理する</span><span class="sxs-lookup"><span data-stu-id="f9873-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="f9873-331">CDN の設定が完了したら、このセクションで説明するように、コンテンツの更新やニーズの変更に応じて構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="f9873-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="f9873-333">365 CDN のアセットを追加、更新Office削除する</span><span class="sxs-lookup"><span data-stu-id="f9873-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="f9873-334">セットアップ手順が完了したら、新しいアセットを追加し、必要に従って既存のアセットを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="f9873-335">作成元として識別したフォルダーまたは SharePoint ライブラリ内のアセットに変更を加えるだけ。</span><span class="sxs-lookup"><span data-stu-id="f9873-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="f9873-336">新しいアセットを追加すると、すぐに CDN 経由で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="f9873-337">ただし、アセットを更新すると、新しいコピーが伝達され CDN で使用可能になるには、最大 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="f9873-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="f9873-338">オリジンの場所を取得する必要がある場合は **、Get-SPOTenantCdnOrigins コマンドレットを使用** できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="f9873-339">このコマンドレットの使用方法については [、「Get-SPOTenantCdnOrigins」を参照してください](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。</span><span class="sxs-lookup"><span data-stu-id="f9873-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="f9873-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="f9873-341">365 CDN から配信元をOfficeする</span><span class="sxs-lookup"><span data-stu-id="f9873-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="f9873-342">作成元として識別したフォルダーまたは SharePoint ライブラリへのアクセスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="f9873-343">これを行うには **、Remove-SPOTenantCdnOrigin コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f9873-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="f9873-344">このコマンドレットの使用方法については [、「Remove-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="f9873-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="f9873-346">365 CDN で配信Office変更する</span><span class="sxs-lookup"><span data-stu-id="f9873-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="f9873-347">作成した原点は変更できません。</span><span class="sxs-lookup"><span data-stu-id="f9873-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="f9873-348">代わりに、原点を削除し、新しい原点を追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="f9873-349">詳細については [、「365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) から配信元を削除するには」Officeアセットの配信元を追加 [するには」を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。</span><span class="sxs-lookup"><span data-stu-id="f9873-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="f9873-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="f9873-351">365 CDN Officeを無効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="f9873-352">**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織の CDN を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f9873-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="f9873-353">CDN でパブリックオリジンとプライベート オリジンの両方が有効になっている場合は、次の例に示すように、コマンドレットを 2 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="f9873-354">CDN でのパブリックオリジンの使用を無効にするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="f9873-355">CDN でのプライベートオリジンの使用を無効にするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="f9873-356">このコマンドレットの詳細については [、「Set-SPOTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="f9873-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="f9873-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="f9873-358">PnP PowerShell を使用してOffice 365 CDN を設定および構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="f9873-359">このセクションの手順では、PnP PowerShell を使用して SharePoint Online に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="f9873-360">手順については [、「PnP PowerShell の使用を開始する」を参照してください](https://github.com/SharePoint/PnP-PowerShell#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="f9873-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="f9873-361">PnP PowerShell を使用して SharePoint Online でアセットをホストする CDN を設定および構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="f9873-362">クリックして展開</span><span class="sxs-lookup"><span data-stu-id="f9873-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="f9873-363">組織が 365 CDN Officeを有効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="f9873-364">テナント CDN 設定を変更する前に、365 テナントのプライベート CDN 構成の現在Officeする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="f9873-365">PnP PowerShell を使用してテナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="f9873-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="f9873-366">**Get-PnPTenantCdnEnabled** コマンドレットを使用して、テナントから CDN 状態設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="f9873-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="f9873-367">指定した CdnType の CDN の状態が画面に出力されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="f9873-368">**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織が 365 CDN Office使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="f9873-369">組織でパブリックオリジン、プライベートオリジン、または両方を同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="f9873-370">また、CDN を有効にするときに既定の配信元のセットアップをスキップする構成もできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="f9873-371">このトピックの説明に従って、これらの原点は後でいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="f9873-372">PnP PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="f9873-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="f9873-373">たとえば、組織でパブリックオリジンとプライベート オリジンの両方を使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="f9873-374">組織でパブリックオリジンとプライベート オリジンの両方を使用できますが、既定のオリジンの設定をスキップするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="f9873-375">Office 365 CDN を有効にした場合に既定でプロビジョニングされる配信元と、既定の配信元のセットアップをスキップした場合の潜在的な影響については、「Default [CDN origins」](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="f9873-376">組織でパブリックオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="f9873-377">組織でプライベートオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="f9873-378">このコマンドレットの詳細については [、「Set-PnPTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="f9873-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="f9873-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="f9873-380">365 CDN に含めるファイルの種類Office変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="f9873-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="f9873-381">**Set-PnPTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9873-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="f9873-382">リストに追加のファイルの種類を追加する場合は、まずコマンドレットを使用して、既に許可されているファイルの種類を確認し、新しいファイルの種類と一緒にリストに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="f9873-383">**Set-PnPTenantCdnPolicy** コマンドレットを使用して、CDN のパブリックオリジンとプライベート オリジンでホストできる静的ファイルの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="f9873-384">既定では、.css、.gif、.jpg、.js など、一般的なアセットの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="f9873-385">PnP PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="f9873-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="f9873-386">たとえば、CDN で .css ファイルと .png ファイルをホストするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="f9873-387">CDN で現在許可されているファイルの種類を確認するには **、Get-PnPTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f9873-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="f9873-388">これらのコマンドレットの詳細については [、「Set-PnPTenantCdnPolicy」](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) および [「Get-PnPTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。</span><span class="sxs-lookup"><span data-stu-id="f9873-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="f9873-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="f9873-390">365 CDN から除外するサイト分類のOffice変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="f9873-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="f9873-391">**Set-PnPTenantCdnPolicy** コマンドレットを使用してサイトの分類を除外すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9873-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="f9873-392">追加のサイト分類を除外する場合は、まずコマンドレットを使用して、既に除外されている分類を確認し、新しい分類と共に追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="f9873-393">**Set-PnPTenantCdnPolicy** コマンドレットを使用して、CDN で使用できないサイト分類を除外します。</span><span class="sxs-lookup"><span data-stu-id="f9873-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="f9873-394">既定で除外されるサイトの分類はありません。</span><span class="sxs-lookup"><span data-stu-id="f9873-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="f9873-395">PnP PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="f9873-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="f9873-396">現在制限されているサイト分類を確認するには **、Get-PnPTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f9873-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="f9873-397">返されるプロパティは IncludeFileExtensions、ExcludeRestrictedSiteClassifications、ExcludeIfNoScriptDisabled _です_。  </span><span class="sxs-lookup"><span data-stu-id="f9873-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="f9873-398">_IncludeFileExtensions_ プロパティには、CDN から提供されるファイル拡張子の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9873-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-399">既定のファイル拡張子は、パブリックとプライベートの間で異なります。</span><span class="sxs-lookup"><span data-stu-id="f9873-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="f9873-400">_ExcludeRestrictedSiteClassifications_ プロパティには、CDN から除外するサイト分類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9873-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="f9873-401">たとえば、機密としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツが CDN から提供されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="f9873-402">_ExcludeIfNoScriptDisabled プロパティは_、サイト レベルの _NoScript_ 属性設定に基づいて CDN からコンテンツを除外します。</span><span class="sxs-lookup"><span data-stu-id="f9873-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="f9873-403">既定では _、NoScript_ 属性は [モダンサイトに対して有効] および [クラシック サイト **では無効]** _に設定_ されています。</span><span class="sxs-lookup"><span data-stu-id="f9873-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="f9873-404">これは、テナントの設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f9873-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="f9873-405">これらのコマンドレットの詳細については [、「Set-PnPTenantCdnPolicy」](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) および [「Get-PnPTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。</span><span class="sxs-lookup"><span data-stu-id="f9873-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="f9873-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="f9873-407">アセットのオリジンを追加する</span><span class="sxs-lookup"><span data-stu-id="f9873-407">Add an origin for your assets</span></span>

<span data-ttu-id="f9873-408">発生元 **を定義するには、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="f9873-409">複数の配信元を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-409">You can define multiple origins.</span></span> <span data-ttu-id="f9873-410">配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。</span><span class="sxs-lookup"><span data-stu-id="f9873-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f9873-411">ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="f9873-412">path の値 _は_ 、アセットを含むライブラリまたはフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="f9873-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="f9873-413">相対パスに加え、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="f9873-414">Origins は、URL の先頭に付加されたワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f9873-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="f9873-415">これにより、複数のサイトにまたがるオリジンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="f9873-416">たとえば、すべてのサイトの masterpages フォルダー内のすべてのアセットを CDN 内のパブリック オリジンとして含めるには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="f9873-417">ワイルドカード修飾子 \* は、パスの先頭でのみ使用できます。指定した URL の下のすべての URL セグメント **/** と一致します。</span><span class="sxs-lookup"><span data-stu-id="f9873-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="f9873-418">パスは、ドキュメント ライブラリ、フォルダー、またはサイトを指します。</span><span class="sxs-lookup"><span data-stu-id="f9873-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="f9873-419">たとえば、パス _\*/site1 は_ 、サイトの下のすべてのドキュメント ライブラリと一致します。</span><span class="sxs-lookup"><span data-stu-id="f9873-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="f9873-420">特定の相対パスを持つ原点を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="f9873-421">完全パスを使用して原点を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="f9873-422">次の使用例は、サイトアセット ライブラリのプライベートオリジンを特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="f9873-423">次の使用例は、サイト コレクションのサイト アセット ライブラリに _folder1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="f9873-424">パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換える方法があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="f9873-425">次の例では、サイト コレクションのサイト アセット ライブラリにフォルダー _1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="f9873-426">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-427">プライベートオリジンでは、配信元から共有されているアセットに、CDN からアクセスする前にメジャー バージョンが発行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="f9873-428">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-429">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="f9873-431">例: SharePoint Online のマスター ページとスタイル ライブラリのパブリックオリジンを構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="f9873-432">通常、これらの配信元は、既定で 365 CDN を有効Office設定されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="f9873-433">ただし、手動で有効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="f9873-434">スタイル ライブラリをパブリックオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="f9873-435">マスター ページをパブリックオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="f9873-436">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="f9873-437">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-438">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="f9873-440">例: SharePoint Online のサイトアセット、サイト ページ、および発行イメージのプライベートオリジンを構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="f9873-441">**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイトアセット フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="f9873-442">**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="f9873-443">発行イメージ フォルダーをプライベートオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="f9873-444">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="f9873-445">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-446">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="f9873-448">例: SharePoint Online のサイト コレクションのプライベートオリジンを構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="f9873-449">**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="f9873-450">例:</span><span class="sxs-lookup"><span data-stu-id="f9873-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="f9873-451">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="f9873-452">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="f9873-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="f9873-453">SharePoint Online テナント _が_ CDN サービスに接続すると予想される構成保留中のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9873-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="f9873-454">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="f9873-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="f9873-456">365 CDN Office管理する</span><span class="sxs-lookup"><span data-stu-id="f9873-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="f9873-457">CDN の設定が完了したら、このセクションで説明するように、コンテンツの更新やニーズの変更に応じて構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="f9873-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="f9873-459">365 CDN のアセットを追加、更新Office削除する</span><span class="sxs-lookup"><span data-stu-id="f9873-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="f9873-460">セットアップ手順が完了したら、新しいアセットを追加し、必要に従って既存のアセットを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="f9873-461">作成元として識別したフォルダーまたは SharePoint ライブラリ内のアセットに変更を加えるだけ。</span><span class="sxs-lookup"><span data-stu-id="f9873-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="f9873-462">新しいアセットを追加すると、すぐに CDN 経由で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="f9873-463">ただし、アセットを更新すると、新しいコピーが伝達され CDN で使用可能になるには、最大 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="f9873-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="f9873-464">オリジンの場所を取得する必要がある場合は **、Get-PnPTenantCdnOrigin コマンドレットを使用** できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="f9873-465">このコマンドレットの使用方法については [、「Get-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="f9873-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="f9873-467">365 CDN から配信元をOfficeする</span><span class="sxs-lookup"><span data-stu-id="f9873-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="f9873-468">作成元として識別したフォルダーまたは SharePoint ライブラリへのアクセスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="f9873-469">これを行うには **、Remove-PnPTenantCdnOrigin コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="f9873-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="f9873-470">このコマンドレットの使用方法については [、「Remove-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="f9873-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="f9873-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="f9873-472">365 CDN で配信Office変更する</span><span class="sxs-lookup"><span data-stu-id="f9873-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="f9873-473">作成した原点は変更できません。</span><span class="sxs-lookup"><span data-stu-id="f9873-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="f9873-474">代わりに、原点を削除し、新しい原点を追加します。</span><span class="sxs-lookup"><span data-stu-id="f9873-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="f9873-475">詳細については [、「365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) から配信元を削除するには」Officeアセットの配信元を追加 [するには」を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。</span><span class="sxs-lookup"><span data-stu-id="f9873-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="f9873-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="f9873-477">365 CDN Officeを無効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="f9873-478">**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織の CDN を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f9873-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="f9873-479">CDN でパブリックオリジンとプライベート オリジンの両方が有効になっている場合は、次の例に示すように、コマンドレットを 2 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="f9873-480">CDN でのパブリックオリジンの使用を無効にするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="f9873-481">CDN でのプライベートオリジンの使用を無効にするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9873-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="f9873-482">このコマンドレットの詳細については [、「Set-PnPTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="f9873-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="f9873-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="f9873-484">Office 365 CLI を使用して Office 365 CDN をセットアップおよび構成する</span><span class="sxs-lookup"><span data-stu-id="f9873-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="f9873-485">このセクションの手順では [、365 CLI](https://aka.ms/o365cli)をインストールOffice必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="f9873-486">次に、login コマンドOffice 365 テナントに [接続](https://pnp.github.io/office365-cli/cmd/login/) します。</span><span class="sxs-lookup"><span data-stu-id="f9873-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="f9873-487">次の手順を実行して、SHAREPoint Online で 365 CLI を使用してアセットをホストする CDN をOfficeします。</span><span class="sxs-lookup"><span data-stu-id="f9873-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="f9873-488">クリックして展開</span><span class="sxs-lookup"><span data-stu-id="f9873-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="f9873-489">365 CDN Officeを有効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="f9873-490">テナントの Office 365 CDN の状態は [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) コマンドを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="f9873-491">テナントで Office 365 パブリック CDN を有効にするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="f9873-492">365 SharePoint CDN Office有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="f9873-493">Office 365 CDN の現在の状況を確認する</span><span class="sxs-lookup"><span data-stu-id="f9873-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="f9873-494">365 CDN の特定の種類Officeが有効または無効になっているか確認するには [、spo cdn get コマンドを使用](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) します。</span><span class="sxs-lookup"><span data-stu-id="f9873-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="f9873-495">Office 365 パブリック CDN が有効かどうかを確認するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="f9873-496">365 CDN Officeを表示する</span><span class="sxs-lookup"><span data-stu-id="f9873-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="f9873-497">現在構成されている Office 365 パブリック CDN の配信元を確認するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="f9873-498">365 CDN を有効にするときに既定でプロビジョニングされる配信元の詳細については、「既定の [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 配信元Office参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="f9873-499">365 CDN Officeを追加する</span><span class="sxs-lookup"><span data-stu-id="f9873-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9873-500">パブリック オリジンとして構成された SharePoint ドキュメント ライブラリには、組織に対して機密性が高いと見なされるリソースを配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f9873-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="f9873-501">[spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) コマンドを使用して CDN の配信元を定義します。</span><span class="sxs-lookup"><span data-stu-id="f9873-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="f9873-502">複数の配信元を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-502">You can define multiple origins.</span></span> <span data-ttu-id="f9873-503">配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。</span><span class="sxs-lookup"><span data-stu-id="f9873-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="f9873-504">ここで `path` 、アセットを含むフォルダーへの相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9873-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="f9873-505">相対パスに加え、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="f9873-506">すべてのサイトのマスター ページギャラリーのすべてのアセットを公開元として含めるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="f9873-507">特定のサイト コレクションのプライベートの配信元を構成するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="f9873-508">CDN の配信元の追加後、CDN サービス経由でファイルを取得できるようになるまで最大 15 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9873-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="f9873-509">特定の配信元が既に有効かどうかは、[spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) コマンドを使用して検証できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="f9873-510">365 CDN Officeを削除する</span><span class="sxs-lookup"><span data-stu-id="f9873-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="f9873-511">[spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) コマンドを使用して、指定した種類の CDN の配信元を削除します。</span><span class="sxs-lookup"><span data-stu-id="f9873-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="f9873-512">CDN 構成からパブリックオリジンを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="f9873-513">CDN 配信元を削除しても、その配信元と一致するドキュメント ライブラリに格納されているファイルには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="f9873-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="f9873-514">これらのアセットが SharePoint URL を使用して参照されている場合、SharePoint はドキュメント ライブラリを指す元の URL に自動的に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f9873-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="f9873-515">ただし、アセットがパブリック CDN URL を使用して参照されている場合、配信元を削除するとリンクが壊れ、手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="f9873-516">365 CDN Officeを変更する</span><span class="sxs-lookup"><span data-stu-id="f9873-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="f9873-517">既存の CDN の配信元を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="f9873-518">代わりに、`spo cdn origin remove` コマンドを使用して定義済みの CDN の配信元を削除して、`spo cdn origin add` コマンドで新しい配信元を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="f9873-519">365 CDN に含めるファイルのOffice変更する</span><span class="sxs-lookup"><span data-stu-id="f9873-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="f9873-520">既定では _、.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2_ のファイルの種類が CDN に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9873-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="f9873-521">CDN に他の種類のファイルを含める必要がある場合、[spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して CDN 構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-522">ファイルの種類のリストを変更する場合、現在定義されているリストを上書きします。</span><span class="sxs-lookup"><span data-stu-id="f9873-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="f9873-523">他のファイルの種類を追加する場合は、[spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) コマンドを最初に使用して現在構成されているファイルの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="f9873-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="f9873-524">JSON ファイルの種類 _をパブリック CDN_ に含まれるファイルの既定の一覧に追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="f9873-525">Office 365 CDN から除外するサイトの分類のリストを変更する</span><span class="sxs-lookup"><span data-stu-id="f9873-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="f9873-526">[spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して、CDN で利用できるようにしないサイトの分類を除外します。</span><span class="sxs-lookup"><span data-stu-id="f9873-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="f9873-527">既定で除外されるサイトの分類はありません。</span><span class="sxs-lookup"><span data-stu-id="f9873-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-528">除外するサイトの分類のリストを変更する場合、現在定義されているリストを上書きします。</span><span class="sxs-lookup"><span data-stu-id="f9873-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="f9873-529">他の分類を除外する場合は、[spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) コマンドを最初に使用して現在構成されている分類を確認します。</span><span class="sxs-lookup"><span data-stu-id="f9873-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="f9873-530">HBI として分類された _サイトをパブリック_ CDN から除外するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="f9873-531">365 CDN Officeを無効にする</span><span class="sxs-lookup"><span data-stu-id="f9873-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="f9873-532">Office 365 CDN を無効にするには、`spo cdn set` コマンドを使用します。たとえば、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="f9873-533">CDN アセットの使用</span><span class="sxs-lookup"><span data-stu-id="f9873-533">Using your CDN assets</span></span>

<span data-ttu-id="f9873-534">CDN を有効にし、配信元とポリシーを構成したので、CDN アセットの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="f9873-535">このセクションでは、SharePoint ページとコンテンツで CDN URL を使用して、SharePoint がパブリックオリジンとプライベート オリジンの両方のアセットの要求を CDN にリダイレクトする方法を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f9873-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="f9873-536">CDN アセットへのリンクの更新</span><span class="sxs-lookup"><span data-stu-id="f9873-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="f9873-537">パブリックオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="f9873-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="f9873-538">プライベートオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="f9873-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="f9873-539">クライアント側 Web パーツをホストするために CDN を使用する方法については [、「Office 365 CDN](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)からクライアント側 Web パーツをホストする (Hello World Part 4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-540">_ClientSideAssets_ フォルダーをプライベート **CDN** 配信元リストに追加すると、CDN ホスト型カスタム Web パーツはレンダリングに失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9873-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="f9873-541">SPFX Web パーツで使用されるファイルはパブリック CDN のみを使用し、ClientSideAssets フォルダーはパブリック CDN の既定の配信元です。</span><span class="sxs-lookup"><span data-stu-id="f9873-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="f9873-542">CDN アセットへのリンクの更新</span><span class="sxs-lookup"><span data-stu-id="f9873-542">Updating links to CDN assets</span></span>

<span data-ttu-id="f9873-543">オリジンに追加したアセットを使用するには、元のファイルへのリンクを元のファイルへのパスで更新します。</span><span class="sxs-lookup"><span data-stu-id="f9873-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="f9873-544">オリジンに追加したアセットへのリンクを含むページまたはコンテンツを編集します。</span><span class="sxs-lookup"><span data-stu-id="f9873-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="f9873-545">また、表示される任意の場所で特定のアセットへのリンクを更新する場合は、いくつかの方法のいずれかを使用して、入力サイトまたはサイト コレクション全体のリンクをグローバルに検索および置換できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="f9873-546">配信元のアセットへのリンクごとに、パスを CDN 配信元のファイルへのパスに置き換える。</span><span class="sxs-lookup"><span data-stu-id="f9873-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="f9873-547">相対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-547">You can use relative paths.</span></span>
+ <span data-ttu-id="f9873-548">ページまたはコンテンツを保存します。</span><span class="sxs-lookup"><span data-stu-id="f9873-548">Save the page or content.</span></span>

<span data-ttu-id="f9873-549">たとえば、ドキュメント ライブラリ フォルダー _/site/CDN_origins/public/ にコピーしたイメージ /site/SiteAssets/images/image.png_ を _検討します_。</span><span class="sxs-lookup"><span data-stu-id="f9873-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="f9873-550">CDN アセットを使用するには、イメージ ファイルの場所への元のパスを原点へのパスに置き換え、新しい URL _/site/CDN_origins/public/image.pngを作成します_。</span><span class="sxs-lookup"><span data-stu-id="f9873-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="f9873-551">相対パスではなくアセットの完全な URL を使用する場合は、次のようにリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9873-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="f9873-552">一般に、CDN 内のアセットに URL を直接ハードコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="f9873-553">ただし、必要に応じて、パブリック オリジンのアセットの URL を手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="f9873-554">詳細については [、「Hardcoding CDN URL for public assets」を参照してください](use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="f9873-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md).</span></span>

<span data-ttu-id="f9873-555">CDN からアセットが提供されているのを確認する方法については、「Office [](use-microsoft-365-cdn-with-spo.md#CDNConfirm) [365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)のトラブルシューティング」の「CDN によってアセットが提供されているのを確認する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="f9873-556">パブリックオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="f9873-556">Using assets in public origins</span></span>

<span data-ttu-id="f9873-557">SharePoint Online **の** 発行機能は、パブリック オリジンに格納されているアセットの URL を CDN 相当の URL に自動的に書き換え、SharePoint ではなく CDN サービスからアセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="f9873-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="f9873-558">発行元が発行機能が有効なサイトで、CDN にオフロードするアセットが次のいずれかのカテゴリにある場合、アセットが CDN ポリシーによって除外されていない場合、SharePoint は配信元のアセットの URL を自動的に書き換える。</span><span class="sxs-lookup"><span data-stu-id="f9873-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="f9873-559">SharePoint 発行機能によって自動的に書き換えられるのは次のようなリンクです。</span><span class="sxs-lookup"><span data-stu-id="f9873-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="f9873-560">従来の発行ページの HTML 応答の IMG/LINK/CSS URL</span><span class="sxs-lookup"><span data-stu-id="f9873-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="f9873-561">これには、ページの HTML コンテンツ内に作成者によって追加された画像が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9873-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="f9873-562">画像ライブラリ スライドショー Web パーツの画像 URL</span><span class="sxs-lookup"><span data-stu-id="f9873-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="f9873-563">SPList REST API (RenderListDataAsStream) 結果の画像フィールド</span><span class="sxs-lookup"><span data-stu-id="f9873-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="f9873-564">フィールドのコンマ区切りリストを指定するには、新しいプロパティ _ImageFieldsToTryRewriteToCdnUrls_ を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9873-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="f9873-565">ハイパーリンク フィールドと PublishingImage フィールドをサポート</span><span class="sxs-lookup"><span data-stu-id="f9873-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="f9873-566">SharePoint イメージの表示</span><span class="sxs-lookup"><span data-stu-id="f9873-566">SharePoint image renditions</span></span>

<span data-ttu-id="f9873-567">次の図は、SharePoint がパブリックオリジンからアセットを含むページの要求を受け取るワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9873-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="f9873-568">![ワークフロー図: パブリック Officeから 365 CDN アセットを取得する](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "ワークフロー: パブリック Officeから 365 CDN アセットを取得する")</span><span class="sxs-lookup"><span data-stu-id="f9873-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="f9873-569">ページ上の特定の URL の自動書き換えを無効にする場合は、ページをチェックアウトしてクエリ文字列パラメーターを **追加できます。無効にする各リンクの末尾に NoAutoReWrites=true** を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9873-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="f9873-570">パブリック アセットの CDN URL の作成</span><span class="sxs-lookup"><span data-stu-id="f9873-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="f9873-571">公開機能がパブリック 配信元で有効になっていない場合、またはアセットが CDN サービスの自動書き換え機能でサポートされているリンクの種類の 1 つではない場合は、アセットの CDN の場所に URL を手動で作成し、コンテンツでこれらの URL を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-572">リソースが要求された時点で URL の最後のセクションを形成する必要なアクセス トークンが生成されるので、プライベート 配信元のアセットに CDN URL をハードコードまたは構築することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="f9873-573">パブリック CDN の URL を作成できます。変更される可能性がある URL はハード コードされません。</span><span class="sxs-lookup"><span data-stu-id="f9873-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="f9873-574">パブリック CDN アセットの場合、URL 形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f9873-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="f9873-575">**TenantHostName をテナント** 名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="f9873-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="f9873-576">例:</span><span class="sxs-lookup"><span data-stu-id="f9873-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="f9873-577">ページ コンテキスト プロパティを使用して、ハード コーディング " " ではなくプレフィックスを作成する必要 https://publiccdn.sharepointonline.com があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="f9873-578">URL は変更される可能性があります。ハード コード化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f9873-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="f9873-579">クラシック SharePoint Online で表示テンプレートを使用している場合は、URL のプレフィックスとして表示テンプレートのプロパティ "window._spPageContextInfo.publicCdnBaseUrl" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="f9873-580">モダンおよびクラシック SharePoint 用の SPFx Web パーツの場合は、プロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="f9873-581">これにより、プレフィックスが提供され、変更された場合に実装が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="f9873-582">SPFx の例として、URL はプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" を使用して構築できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="f9873-583">シーズン 1 [パフォーマンス シリーズの一部であるクライアント](https://youtu.be/IH1RbQlbhIA) 側コードでの CDN の使用 [を参照してください。](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="f9873-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="f9873-584">プライベートオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="f9873-584">Using assets in private origins</span></span>

<span data-ttu-id="f9873-585">プライベートオリジンでアセットを使用するには、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f9873-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="f9873-586">SharePoint Online は、プライベート配信元のアセットの URL を自動的に書き換えるので、それらのアセットの要求は常に CDN から提供されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="f9873-587">これらの URL には、アセットが要求された時点で SharePoint Online によって自動生成する必要があるトークンが含まれているため、プライベート配信元の CDN アセットに対して URL を手動でビルドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="f9873-588">プライベートオリジンのアセットへのアクセスは、オリジンに対するユーザーのアクセス許可に基づいて動的に生成されたトークンによって保護されます。以下のセクションで説明する注意点があります。</span><span class="sxs-lookup"><span data-stu-id="f9873-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="f9873-589">CDN がコンテンツをレンダリングするには、少なくとも配信元への読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="f9873-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="f9873-590">次の図は、SharePoint がプライベートオリジンからアセットを含むページの要求を受け取るワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9873-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="f9873-591">![ワークフロー図: プライベート Officeから 365 CDN アセットを取得する](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "ワークフロー: プライベート Officeから 365 CDN アセットを取得する")</span><span class="sxs-lookup"><span data-stu-id="f9873-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="f9873-592">プライベートオリジンでのトークンベースの承認</span><span class="sxs-lookup"><span data-stu-id="f9873-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="f9873-593">SharePoint Online によって生成されたトークンによって、Office 365 CDN のプライベート オリジンのアセットへのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="f9873-594">作成元によって指定されたフォルダーまたはライブラリへのアクセス許可を既に持っているユーザーには、アクセス許可レベルに基づいてユーザーがファイルにアクセスできるトークンが自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="f9873-595">これらのアクセス トークンは、トークン再生攻撃を防止するために生成された後、30 ~ 90 分間有効です。</span><span class="sxs-lookup"><span data-stu-id="f9873-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="f9873-596">アクセス トークンが生成されると、SharePoint Online は、2 つの承認パラメーターを含むカスタム URI _をクライアント_ に返します (エッジ承認トークン) と _oat_ (起点承認トークン)。</span><span class="sxs-lookup"><span data-stu-id="f9873-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="f9873-597">各トークンの構造は _、epoch<_ のセキュリティで保護された署名の>__<の有効期限>。</span><span class="sxs-lookup"><span data-stu-id="f9873-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="f9873-598">例:</span><span class="sxs-lookup"><span data-stu-id="f9873-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="f9873-599">トークンを所有しているユーザーは、CDN 内のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="f9873-600">ただし、これらのアクセス トークンを含む URL は HTTPS 経由でのみ共有されます。そのため、トークンの有効期限が切れる前にエンド ユーザーが URL を明示的に共有しない限り、承認されていないユーザーはアセットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="f9873-601">アイテム レベルのアクセス許可は、プライベートオリジンのアセットではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f9873-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="f9873-602">SharePoint Online は、プライベート オリジンのアセットに対するアイテム レベルのアクセス許可をサポートしていない点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f9873-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="f9873-603">たとえば、場所にあるファイルの場合、ユーザーは次の条件に従って `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` ファイルに効果的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="f9873-604">User</span><span class="sxs-lookup"><span data-stu-id="f9873-604">User</span></span>  |<span data-ttu-id="f9873-605">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f9873-605">Permissions</span></span>  |<span data-ttu-id="f9873-606">有効なアクセス</span><span class="sxs-lookup"><span data-stu-id="f9873-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f9873-607">ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="f9873-607">User 1</span></span>     |<span data-ttu-id="f9873-608">フォルダー 1 へのアクセス権を持つ</span><span class="sxs-lookup"><span data-stu-id="f9873-608">Has access to folder1</span></span>         |<span data-ttu-id="f9873-609">CDN からimage1.jpgアクセスできる</span><span class="sxs-lookup"><span data-stu-id="f9873-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="f9873-610">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="f9873-610">User 2</span></span>     |<span data-ttu-id="f9873-611">folder1 にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="f9873-611">Does not have access to folder1</span></span>         |<span data-ttu-id="f9873-612">CDN からimage1.jpgにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="f9873-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="f9873-613">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="f9873-613">User 3</span></span>     |<span data-ttu-id="f9873-614">folder1 へのアクセス権は付与されませんが、SharePoint Online 内のユーザーにアクセスするためのimage1.jpgアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="f9873-615">SharePoint Online から直接image1.jpgアクセスできますが、CDN からアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="f9873-616">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="f9873-616">User 4</span></span>     |<span data-ttu-id="f9873-617">フォルダー 1 へのアクセス権を持っていますが、SharePoint Online でフォルダーへのアクセスimage1.jpg明示的に拒否されています</span><span class="sxs-lookup"><span data-stu-id="f9873-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="f9873-618">SharePoint Online からアセットにアクセスすることはできませんが、SharePoint Online でファイルへのアクセスが拒否されているにもかかわらず CDN からアセットにアクセスできます</span><span class="sxs-lookup"><span data-stu-id="f9873-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="f9873-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="f9873-620">365 CDN Officeトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f9873-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="f9873-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="f9873-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="f9873-622">CDN によってアセットが提供されているのを確認する方法</span><span class="sxs-lookup"><span data-stu-id="f9873-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="f9873-623">CDN アセットへのリンクをページに追加したら、そのアセットが CDN から提供されているのを確認するには、ページを参照し、レンダリング後にイメージを右クリックし、イメージの URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="f9873-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="f9873-624">ブラウザーの開発者ツールを使用して、ページ上の各アセットの URL を表示したり、サードパーティのネットワーク トレース ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9873-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="f9873-625">Fiddler などのネットワーク ツールを使用して SharePoint ページからアセットをレンダリングする外部でアセットをテストする場合は、URL が SharePoint Online テナントのルート URL である GET 要求に、参照先ヘッダー "Referer:" を手動で追加する必要があります。 `https://yourdomain.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="f9873-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="f9873-626">SharePoint Online からの参照者が必要なので、WEB ブラウザーで CDN URL を直接テストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9873-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="f9873-627">ただし、CDN アセット URL を SharePoint ページに追加し、ブラウザーでページを開いた場合は、CDN アセットがページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9873-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="f9873-628">Microsoft Edge ブラウザーでの開発者ツールの使用の詳細については [、「Microsoft Edge Developer Tools」を参照してください](/microsoft-edge/devtools-guide)。</span><span class="sxs-lookup"><span data-stu-id="f9873-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="f9873-629">SharePoint Developer Patterns and [Practices YouTube](https://aka.ms/sppnp-videos) チャネルでホストされている短いビデオを見て、CDN が動作しているのを確認する方法を説明するには [、「CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)の使用状況を確認し、最適なネットワーク接続を確保する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9873-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="f9873-630">新しいオリジンのアセットが使用できない理由</span><span class="sxs-lookup"><span data-stu-id="f9873-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="f9873-631">新しい配信元のアセットは、登録が CDN 経由で伝達され、アセットが配信元から CDN ストレージにアップロードされるのに時間がかかるので、すぐには使用できません。</span><span class="sxs-lookup"><span data-stu-id="f9873-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="f9873-632">CDN でアセットを利用するために必要な時間は、アセットの数とファイル サイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f9873-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="f9873-633">クライアント側 Web パーツまたは SharePoint Framework ソリューションが機能しない</span><span class="sxs-lookup"><span data-stu-id="f9873-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="f9873-634">パブリック配信元に対Office 365 CDN を有効にした場合、CDN サービスは次の既定の配信元を自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="f9873-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="f9873-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="f9873-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="f9873-636">\*/STYLE ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f9873-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="f9873-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="f9873-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="f9873-638">\*/clientsideassets の生成元が見つからない場合、SharePoint Framework ソリューションは失敗し、警告メッセージやエラー メッセージは生成されません。</span><span class="sxs-lookup"><span data-stu-id="f9873-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="f9873-639">このオリジンは _、-NoDefaultOrigins_ パラメーターが **$true** に設定された CDN が有効になっているか、またはオリジンが手動で削除されたためです。</span><span class="sxs-lookup"><span data-stu-id="f9873-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="f9873-640">次の PowerShell コマンドを使用して、どの原点が存在するのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="f9873-641">または、次の 365 CLI Office確認できます。</span><span class="sxs-lookup"><span data-stu-id="f9873-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="f9873-642">PowerShell で原点を追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="f9873-643">365 CLI で原点をOfficeするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9873-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="f9873-644">PowerShell モジュールと CLI シェルは、365 CDN のOffice必要ですか?</span><span class="sxs-lookup"><span data-stu-id="f9873-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="f9873-645">**SharePoint Online** 管理シェル PowerShell モジュールまたは 365 CLI を使用して、Office **365 CDN をOfficeできます**。</span><span class="sxs-lookup"><span data-stu-id="f9873-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="f9873-646">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="f9873-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="f9873-647">Office 365 CLI のインストール</span><span class="sxs-lookup"><span data-stu-id="f9873-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="f9873-648">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9873-648">See also</span></span>

[<span data-ttu-id="f9873-649">Content Delivery Network</span><span class="sxs-lookup"><span data-stu-id="f9873-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="f9873-650">Office 365 のネットワーク計画とパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="f9873-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="f9873-651">SharePoint Performance Series - Office 365 CDN ビデオ シリーズ</span><span class="sxs-lookup"><span data-stu-id="f9873-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)