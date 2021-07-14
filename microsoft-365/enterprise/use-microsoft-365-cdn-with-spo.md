---
title: オンラインでOffice 365 Content Delivery Network (CDN) をSharePointする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/13/2021
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
description: オンライン アセットの配信をOffice 365 Content Delivery Network (CDN) を使用する方法SharePointします。
ms.openlocfilehash: 24b86f059e5a59d3b6dadf989bef0ab38ad8e010
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419564"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="b8c0c-103">SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用</span><span class="sxs-lookup"><span data-stu-id="b8c0c-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="b8c0c-104">組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的資産をホストすることで、SharePoint Online ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="b8c0c-105">Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="b8c0c-106">また、このOffice 365 CDN [HTTP/2 プロトコル](https://en.wikipedia.org/wiki/HTTP/2)を使用して、圧縮と HTTP パイプライン処理を強化します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="b8c0c-107">Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-108">Office 365 CDN は、**本番** (ワールドワイド) クラウドのテナントのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="b8c0c-109">現在、米国政府、中国、ドイツのクラウドのテナントは Office 365 CDN をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="b8c0c-110">Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="b8c0c-111">Office 365 CDN でホストするコンテンツの種類に応じて、**公開**、**非公開**、またはその両方の元の場所を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="b8c0c-112">パブリック [オリジンとプライベートオリジン](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) の違いの詳細については、「各オリジンをパブリックまたはプライベートにするかどうかを選択する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="b8c0c-113">![Office 365 CDN の概念図](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN の概念図")</span><span class="sxs-lookup"><span data-stu-id="b8c0c-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="b8c0c-114">既に CDN の動作方法に精通している場合は、テナントに対してユーザー設定を有効にするには、いくつかの手順Office 365 CDN必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="b8c0c-115">このトピックでは、方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-115">This topic describes how.</span></span> <span data-ttu-id="b8c0c-116">静的アセットのホスティングを開始する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="b8c0c-117">Office 365 と一緒に使用できる Microsoft ホスト型 CDN は、特殊な使用シナリオに使用できますが、Office 365 CDN の範囲を外れたため、このトピックでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="b8c0c-118">詳細については、「その他の [Microsoft CDN」を参照してください](content-delivery-networks.md#other-microsoft-cdns)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="b8c0c-119">**[ネットワークの計画 [とパフォーマンスの](./network-planning-and-performance.md)調整] に戻Office 365。**</span><span class="sxs-lookup"><span data-stu-id="b8c0c-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="b8c0c-120">オンラインでのユーザーの操作Office 365 CDNのSharePoint概要</span><span class="sxs-lookup"><span data-stu-id="b8c0c-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="b8c0c-121">組織のOffice 365 CDNを設定するには、次の基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="b8c0c-122">アプリケーションの展開を計画Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="b8c0c-123">[サーバーでホストする静的アセットを決定CDN。](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="b8c0c-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="b8c0c-124">[アセットを格納する場所を決定します](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="b8c0c-125">この場所は、サイト、SharePoint、またはフォルダーの 1 つであり、原点と呼 _ばれる場所です_。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="b8c0c-126">[各オリジンをパブリックまたはプライベートにするかどうかを選択します](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="b8c0c-127">パブリック型とプライベート型の両方の複数のオリジンを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="b8c0c-128">PowerShell またはオンライン CLI CDNを使用して、サーバーサーバーをSharePoint構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="b8c0c-129">オンライン管理シェルを使用してCDNを設定SharePoint構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="b8c0c-130">PnP PowerShell を使用してCDN設定および構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="b8c0c-131">CLI を使用してCDN設定および構成Office 365します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="b8c0c-132">この手順を完了すると、次の機能が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="b8c0c-133">組織のCDNを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="b8c0c-134">各オリジンをパブリックまたはプライベートとして識別するオリジンを追加しました。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="b8c0c-135">セットアップが完了したら、次の方法で時間の[Office 365 CDNを管理](use-microsoft-365-cdn-with-spo.md#CDNManage)できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>

+ <span data-ttu-id="b8c0c-136">アセットの追加、更新、および削除</span><span class="sxs-lookup"><span data-stu-id="b8c0c-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="b8c0c-137">原点の追加と削除</span><span class="sxs-lookup"><span data-stu-id="b8c0c-137">Adding and removing origins</span></span>
+ <span data-ttu-id="b8c0c-138">ポリシー CDN構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="b8c0c-139">必要に応じて、サーバーを無効CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="b8c0c-140">最後に[、「リソース](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)アセットCDN使用して、パブリックとプライベートの両方のCDNアセットにアクセスする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="b8c0c-141">一[般的な問題の解決Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)については、「トラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="b8c0c-142">アプリケーションの展開を計画Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-143">テナントのOffice 365 CDNをOffice 365前に、計画プロセスの一部として次の要素を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="b8c0c-144">サーバーでホストする静的アセットを決定CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="b8c0c-145">アセットの保存場所を決定する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="b8c0c-146">各オリジンをパブリックまたはプライベートにするかどうかを選択する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="b8c0c-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="b8c0c-148">サーバーでホストする静的アセットを決定CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="b8c0c-149">一般に、CDN は静的アセット、またはあまり頻繁に変更しないアセットをホストする場合に最も効果的です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="b8c0c-150">経験則として、次の条件の一部またはすべてが満たされているファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="b8c0c-151">ページに埋め込まれた静的ファイル (スクリプトや画像など) で、ページの読み込み時間に大きな増分影響を与える可能性がある</span><span class="sxs-lookup"><span data-stu-id="b8c0c-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="b8c0c-152">実行可能ファイルやインストール ファイルのような大きなファイル</span><span class="sxs-lookup"><span data-stu-id="b8c0c-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="b8c0c-153">クライアント側コードをサポートするリソース ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b8c0c-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="b8c0c-154">たとえば、サイト イメージやスクリプトのように繰り返し要求される小さなファイルは、サイトレンダリングのパフォーマンスを大幅に向上し、CDN オリジンに追加すると、SharePoint Online サイトの負荷を徐々に軽減できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="b8c0c-155">インストール実行可能ファイルなどの大きなファイルは、CDN からダウンロードして、パフォーマンスにプラスの影響を与え、SharePoint Online サイトへの負荷を軽減できます。たとえアクセス頻度が高くなくてもです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="b8c0c-156">ファイル単位でのパフォーマンスの向上は、クライアントが最も近い CDN エンドポイントへの近接性、ローカル ネットワーク上の一時的な状態など、多くの要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="b8c0c-157">多くの静的ファイルは非常に小さく、1 秒Office 365からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="b8c0c-158">ただし、Web ページには、累積ダウンロード時間が数秒の埋め込みファイルが多数含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="b8c0c-159">これらのファイルをサーバーから提供CDNページの読み込み時間を大幅に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="b8c0c-160">例[については、「ユーザーが提供するパフォーマンスCDN」](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="b8c0c-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="b8c0c-162">アセットの保存場所を決定する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="b8c0c-163">このCDN元と呼ばれる場所からアセットをフェッチ _します_。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="b8c0c-164">オリジンには、URL SharePointアクセスできるサイト、ドキュメント ライブラリ、またはフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="b8c0c-165">組織の起点を指定する場合、柔軟性が高い。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="b8c0c-166">たとえば、複数の原点または 1 つの原点を指定して、すべてのアセットをCDNできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="b8c0c-167">組織のパブリックオリジンとプライベートオリジンの両方を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="b8c0c-168">ほとんどの組織では、2 つの組み合わせを実装します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="b8c0c-169">フォルダーやドキュメント ライブラリなど、オリジン用の新しいコンテナーを作成し、新しいフォルダーから使用できるファイルを追加CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="b8c0c-170">これは、CDN から利用できるアセットの特定のセットを持ち、CDN アセットのセットをコンテナー内のファイルにのみ制限する場合に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="b8c0c-171">また、既存のサイト コレクション、サイト、ライブラリ、またはフォルダーを起点として構成することもできます。コンテナー内のすべての適格なアセットは、CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="b8c0c-172">既存のコンテナーをオリジンとして追加する前に、コンテンツとアクセス許可を認識し、不注意でアセットを匿名アクセスや承認されていないユーザーに公開することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="b8c0c-173">作成元の _CDNコンテンツ_ を除外するポリシーを定義CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="b8c0c-174">CDNポリシーは、ファイルの種類やサイト分類などの属性によってパブリックまたはプライベートオリジンのアセットを除外し、ポリシーで指定した CdnType (プライベートまたはパブリック) のすべての配信元に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="b8c0c-175">たとえば、複数のサブサイトを含むサイトで構成されるプライベート オリジンを追加する場合は、機密としてマークされたサイトを除外するポリシーを定義して、その分類が適用されたサイトのコンテンツが CDN から提供されません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="b8c0c-176">ポリシーは、ユーザーに追加 _した_ すべてのプライベートオリジンのコンテンツに適用CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>

<span data-ttu-id="b8c0c-177">発生元の数が多い場合、要求の処理に必要なサービスの時間に与える影響が大CDN念頭に置いておきます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="b8c0c-178">可能な限り原点の数を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-178">We recommend that you limit the number of origins as much as possible.</span></span>

<span data-ttu-id="b8c0c-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="b8c0c-180">各オリジンをパブリックまたはプライベートにするかどうかを選択する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="b8c0c-181">発生元を特定する場合は、公開または非公開に _するかどうかを_ 指定 _します_。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="b8c0c-182">パブリックオリジンCDNアセットへのアクセスは匿名であり、プライベートオリジンCDNコンテンツは動的に生成されたトークンによって保護され、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="b8c0c-183">選択したオプションに関係なく、Microsoft は、ユーザー自身の管理に関して、すべての重いCDNします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="b8c0c-184">また、後で、サイトをセットアップして原点を特定した後CDN変更できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="b8c0c-185">パブリック オプションとプライベート オプションの両方が同様のパフォーマンス向上を実現しますが、それぞれに固有の属性と利点があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="b8c0c-186">**サイト** 内の公開元Office 365 CDN匿名でアクセス可能であり、ホストされているアセットには、アセットの URL を持つユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="b8c0c-187">公開されている元の場所のコンテンツへのアクセスは匿名になるため、アクセスしたコンテンツは、機密データ以外の一般的なコンテンツ (JavaScript ファイル、スクリプト、アイコン、画像など) をキャッシュする場合にのみ使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="b8c0c-188">Office 365 CDN 内の **非公開** の元の場所は、SharePoint Online ドキュメント ライブラリ、サイト、独自のイメージなど、ユーザー コンテンツへのプライベート アクセスを行う場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="b8c0c-189">プライベート オリジンのコンテンツへのアクセスは、動的に生成されたトークンによって保護され、元のドキュメント ライブラリまたは保存場所へのアクセス許可を持つユーザーだけがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="b8c0c-190">Office 365 CDN のプライベートオリジンは SharePoint Online コンテンツにのみ使用できます。また、SharePoint Online テナントからのリダイレクトによってのみプライベートオリジンのアセットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="b8c0c-191">プライベート オリジンのアセットへのアクセスCDNの詳細については、「プライベート オリジンでアセットを使用する」[を参照してください](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="b8c0c-192">パブリックオリジンでアセットをホストする属性と利点</span><span class="sxs-lookup"><span data-stu-id="b8c0c-192">Attributes and advantages of hosting assets in public origins</span></span>

+ <span data-ttu-id="b8c0c-193">パブリックの配信元で公開されている資産には、すべてのユーザーが匿名でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="b8c0c-194">ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="b8c0c-195">パブリックの配信元から資産を削除した場合、その資産は最大 30 日間はキャッシュから引き続き使用できます。ただし、CDN 内の資産へのリンクは 15 分以内に無効になります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="b8c0c-196">パブリックの配信元にスタイル シート (CSS ファイル) をホストする場合は、コード内で相対パスと URI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="b8c0c-197">つまり、背景画像と他のオブジェクトの場所を、呼び出し元の資産の場所からの相対位置で参照することができます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="b8c0c-198">パブリック オリジンの URL を作成することもできますが、慎重に進み、ページ コンテキスト プロパティを使用し、そのガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="b8c0c-199">CDN にアクセスできなくなった場合、SharePoint Online でその URL は自動的に組織に対して解決されず、結果としてリンクが壊れて他のエラーが発生する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="b8c0c-200">URL も変更される可能性があります。これは、現在の値に対してハードコードされるだけではない理由です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="b8c0c-201">パブリックオリジンに含まれる既定のファイルの種類は、.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2 です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="b8c0c-202">追加のファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="b8c0c-203">指定したサイト分類によって識別されたアセットを除外するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="b8c0c-204">たとえば、許可されているファイルの種類のもので、パブリックの配信元にある資産であっても、"社外秘" または "制限付き" としてマークされている資産はすべて除外する、といったことができます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="b8c0c-205">プライベートオリジンでアセットをホストする属性と利点</span><span class="sxs-lookup"><span data-stu-id="b8c0c-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="b8c0c-206">プライベートオリジンは、オンラインアセットSharePoint使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="b8c0c-207">ユーザーは、コンテナーにアクセスするためのアクセス許可を持っている場合にのみ、プライベートオリジンからアセットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="b8c0c-208">これらの資産に匿名でアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="b8c0c-209">プライベートオリジンのアセットは、オンライン テナントから参照SharePoint必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="b8c0c-210">プライベート アセットへの直接アクセスCDNは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="b8c0c-211">プライベートオリジンからアセットを削除した場合、アセットはキャッシュから最大 1 時間引き続き使用できます。ただし、削除後 15 分以内に、CDNへのリンクは無効になります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="b8c0c-212">プライベートの配信元用に含まれている既定のファイルの種類は、.gif、.ico、.jpeg、.jpg、.js、.png です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="b8c0c-213">追加のファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="b8c0c-214">パブリックオリジンと同様に、ワイルドカードを使用してフォルダーまたはドキュメント ライブラリ内のすべてのアセットを含める場合でも、指定したサイト分類によって識別されたアセットを除外するポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="b8c0c-215">Office 365 CDN テナントで使用できる Office 365 CDN、CDN の一般的な概念、その他の Microsoft CDN を使用する理由の詳細については、「Office 365 Content [Delivery Networks」](content-delivery-networks.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="b8c0c-216">既定CDN原点</span><span class="sxs-lookup"><span data-stu-id="b8c0c-216">Default CDN origins</span></span>

<span data-ttu-id="b8c0c-217">指定しない限り、Office 365を有効にするときに既定の原点を設定Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b8c0c-218">最初にプロビジョニングしない場合は、セットアップの完了後にこれらのオリジンを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="b8c0c-219">既定の原点のセットアップをスキップした結果を理解し、その理由を特定しない限り、CDN を有効にするときに作成を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>

<span data-ttu-id="b8c0c-220">既定のプライベート CDN元:</span><span class="sxs-lookup"><span data-stu-id="b8c0c-220">Default private CDN origins:</span></span>

+ <span data-ttu-id="b8c0c-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="b8c0c-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="b8c0c-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="b8c0c-222">\*/siteassets</span></span>

<span data-ttu-id="b8c0c-223">既定のパブリック CDN元:</span><span class="sxs-lookup"><span data-stu-id="b8c0c-223">Default public CDN origins:</span></span>

+ <span data-ttu-id="b8c0c-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="b8c0c-224">\*/masterpage</span></span>
+ <span data-ttu-id="b8c0c-225">\*/style ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b8c0c-225">\*/style library</span></span>
+ <span data-ttu-id="b8c0c-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="b8c0c-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-227">_clientsideassets は_、2017 年 12 月に Office 365 CDNに追加された既定のパブリック オリジンです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="b8c0c-228">このオリジンは、アプリケーション内のSharePoint Framework機能するためにCDN必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="b8c0c-229">2017 年 12 月より前に Office 365 CDN を有効にした場合、または CDN を有効にするときに既定の原点のセットアップをスキップした場合は、手動でこの原点を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="b8c0c-230">詳細については、「My client-side Web パーツ」または「SharePoint Framework[が機能しない」を参照してください](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="b8c0c-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="b8c0c-232">オンライン管理シェルを使用してOffice 365 CDNを設定SharePoint構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="b8c0c-233">このセクションの手順では、オンライン管理シェルの SharePointを使用してオンラインにSharePointします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="b8c0c-234">手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

<span data-ttu-id="b8c0c-235">次の手順を実行して、CDN管理シェルを使用して SharePoint Online でアセットをホストSharePoint構成します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="b8c0c-236">クリックして展開</span><span class="sxs-lookup"><span data-stu-id="b8c0c-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b8c0c-237">組織が組織でユーザー設定を使用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-238">テナントの設定を変更する前CDN、テナント内のプライベート CDN構成の現在Office 365する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b8c0c-239">Connect管理シェルを使用してテナントSharePointにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="b8c0c-240">**Get-SPOTenantCdnEnabled** コマンドレットを使用して、テナントからCDN状態設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b8c0c-241">指定した CdnType のCDNの状態が画面に出力されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b8c0c-242">**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織でこのコマンドレットを使用Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b8c0c-243">組織でパブリックオリジン、プライベートオリジン、または両方を一度に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="b8c0c-244">また、既定の原点CDN有効にするときに、既定の原点のセットアップをスキップする方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b8c0c-245">このトピックの説明に従って、これらの原点は後でいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-245">You can always add these origins later as described in this topic.</span></span>

<span data-ttu-id="b8c0c-246">[オンラインWindows PowerShellのSharePoint] で、次のSharePoint使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b8c0c-247">たとえば、組織でパブリックオリジンとプライベート オリジンの両方を使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b8c0c-248">組織でパブリックオリジンとプライベート オリジンの両方を使用できますが、既定のオリジンの設定をスキップするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b8c0c-249">Office 365 CDN を有効にした場合に既定でプロビジョニングされる起点と、既定の原点のセットアップをスキップした場合の潜在的な影響については、「Default CDN [origins」](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b8c0c-250">組織でパブリックオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b8c0c-251">組織でプライベートオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b8c0c-252">このコマンドレットの詳細については [、「Set-SPOTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="b8c0c-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b8c0c-254">ファイルに含めるファイルの種類の一覧を変更する (Office 365 CDN)</span><span class="sxs-lookup"><span data-stu-id="b8c0c-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b8c0c-255">**Set-SPOTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b8c0c-256">リストに追加のファイルの種類を追加する場合は、まずコマンドレットを使用して、既に許可されているファイルの種類を確認し、新しいファイルの種類と一緒にリストに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>

<span data-ttu-id="b8c0c-257">**Set-SPOTenantCdnPolicy** コマンドレットを使用して、パブリックオリジンとプライベート オリジンでホストできる静的ファイルの種類を定義CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b8c0c-258">既定では、一般的なアセットの種類 (.css、.gif、.jpg、および.js。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b8c0c-259">[オンラインWindows PowerShellのSharePoint] で、次のSharePoint使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b8c0c-260">たとえば、.css ファイルとCDNファイルをホスト.pngするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b8c0c-261">現在許可されているファイルの種類を確認するには、CDN **Get-SPOTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b8c0c-262">これらのコマンドレットの詳細については [、「Set-SPOTenantCdnPolicy」](/powershell/module/sharepoint-online/) および [「Get-SPOTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b8c0c-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b8c0c-264">サイトから除外するサイト分類の一覧を変更する (Office 365 CDN)</span><span class="sxs-lookup"><span data-stu-id="b8c0c-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b8c0c-265">**Set-SPOTenantCdnPolicy** コマンドレットを使用してサイトの分類を除外すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b8c0c-266">追加のサイト分類を除外する場合は、まずコマンドレットを使用して、既に除外されている分類を確認し、新しい分類と共に追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b8c0c-267">
  \*\*Set-SPOTenantCdnPolicy\*\* コマンドレットを使用して、CDN で利用できるようにしないサイトの分類を除外します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b8c0c-268">既定で除外されるサイトの分類はありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b8c0c-269">[オンラインWindows PowerShellのSharePoint] で、次のSharePoint使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="b8c0c-270">現在制限されているサイト分類を確認するには **、Get-SPOTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b8c0c-271">返されるプロパティは IncludeFileExtensions、ExcludeRestrictedSiteClassifications、ExcludeIfNoScriptDisabled _です_。  </span><span class="sxs-lookup"><span data-stu-id="b8c0c-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b8c0c-272">_IncludeFileExtensions_ プロパティには、アプリケーションから提供されるファイル拡張子の一覧がCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-273">既定のファイル拡張子は、パブリックとプライベートの間で異なります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b8c0c-274">_ExcludeRestrictedSiteClassifications_ プロパティには、サイトから除外するサイトのCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b8c0c-275">たとえば、機密としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツがサイトから提供CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b8c0c-276">_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性CDNに基づいてコンテンツを除外します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b8c0c-277">既定では _、NoScript_ 属性は [モダンサイトに対して有効] および [クラシック サイト **では無効]** _に設定_ されています。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b8c0c-278">これは、テナントの設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="b8c0c-279">これらのコマンドレットの詳細については [、「Set-SPOTenantCdnPolicy」](/powershell/module/sharepoint-online/) および [「Get-SPOTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-online/)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b8c0c-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b8c0c-281">アセットのオリジンを追加する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-281">Add an origin for your assets</span></span>

<span data-ttu-id="b8c0c-282">発生元 **を定義するには、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b8c0c-283">複数の配信元を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-283">You can define multiple origins.</span></span> <span data-ttu-id="b8c0c-284">配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8c0c-285">ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b8c0c-286">path の値 _は_ 、アセットを含むライブラリまたはフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b8c0c-287">相対パスに加え、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b8c0c-288">Origins は、URL の先頭に付加されたワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b8c0c-289">これにより、複数のサイトにまたがるオリジンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b8c0c-290">たとえば、すべてのサイトの masterpages フォルダー内のすべてのアセットを、CDN 内のパブリック オリジンとして含めるには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b8c0c-291">ワイルドカード修飾子 \* は、パスの先頭でのみ使用できます。指定した URL の下のすべての URL セグメント **/** と一致します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b8c0c-292">パスは、ドキュメント ライブラリ、フォルダー、またはサイトを指します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b8c0c-293">たとえば、パス _\*/site1 は_ 、サイトの下のすべてのドキュメント ライブラリと一致します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b8c0c-294">特定の相対パスを持つ原点を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b8c0c-295">完全パスを使用して原点を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b8c0c-296">次の使用例は、サイトアセッツ ライブラリのプライベートオリジンを特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b8c0c-297">次の使用例は、サイト コレクションのサイト アセット ライブラリに _folder1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b8c0c-298">パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換える方法があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b8c0c-299">次の例では、サイト コレクションのサイト アセット ライブラリにフォルダー _1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b8c0c-300">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-301">プライベートオリジンでは、オリジンから共有されているアセットにメジャー バージョンが公開されている必要があります。そのアセットは、そのオリジンからアクセスCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>

<span data-ttu-id="b8c0c-302">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-303">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b8c0c-305">例: マスター ページとオンライン用のスタイル ライブラリの公開元をSharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b8c0c-306">通常、これらの原点は既定で設定されます。既定では、この設定を有効Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b8c0c-307">ただし、手動で有効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-307">However, if you want to enable them manually, follow these steps.</span></span>

+ <span data-ttu-id="b8c0c-308">スタイル ライブラリをパブリックオリジンとして定義するには **、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b8c0c-309">マスター ページをパブリックオリジンとして定義するには **、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b8c0c-310">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b8c0c-311">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-312">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b8c0c-314">例: サイトアセット、サイト ページ、および公開イメージのプライベート オリジンをオンライン用にSharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b8c0c-315">**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイトアセット フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b8c0c-316">**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b8c0c-317">発行イメージ **フォルダーをプライベートオリジンとして定義するには、Add-SPOTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b8c0c-318">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b8c0c-319">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-320">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b8c0c-322">例: オンラインのサイト コレクションのプライベートオリジンをSharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b8c0c-323">**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b8c0c-324">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b8c0c-325">このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b8c0c-326">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-327">構成保留中の _メッセージが_ 表示される場合があります。これは、オンライン テナントが SharePointサービスに接続CDNです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b8c0c-328">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b8c0c-330">サーバーを管理Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-331">このセクションで説明するように、CDNを設定したら、コンテンツを更新したり、必要に応じて変更を加えたりして、構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>

<span data-ttu-id="b8c0c-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b8c0c-333">アセットを追加、更新、または削除Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-334">セットアップ手順が完了したら、新しいアセットを追加し、必要に従って既存のアセットを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b8c0c-335">作成元として識別したフォルダーまたはSharePointアセットに変更を加えるだけ。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b8c0c-336">新しいアセットを追加した場合は、すぐに新しいアセットをCDNできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b8c0c-337">ただし、アセットを更新した場合、新しいコピーが反映され、新しいコピーが使用できるまで最大で 15 分かかりますCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>

<span data-ttu-id="b8c0c-338">オリジンの場所を取得する必要がある場合は **、Get-SPOTenantCdnOrigins コマンドレットを使用** できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="b8c0c-339">このコマンドレットの使用方法については [、「Get-SPOTenantCdnOrigins」を参照してください](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="b8c0c-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b8c0c-341">オブジェクトから原点を削除Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-342">作成元として識別したフォルダーまたはSharePointライブラリへのアクセスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b8c0c-343">これを行うには **、Remove-SPOTenantCdnOrigin コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b8c0c-344">このコマンドレットの使用方法については [、「Remove-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b8c0c-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b8c0c-346">オブジェクトの原点を変更Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-347">作成した原点は変更できません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b8c0c-348">代わりに、原点を削除し、新しい原点を追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b8c0c-349">詳細については、「アセットから原点[を削除](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)するには」および「Office 365 CDNを追加するには」[を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="b8c0c-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b8c0c-351">サーバーを無効Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-352">**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織のCDNを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b8c0c-353">パブリック オリジンとプライベート オリジンの両方が CDNに対して有効になっている場合は、次の例に示すように、コマンドレットを 2 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>

<span data-ttu-id="b8c0c-354">パブリック オリジンの使用を無効にするには、CDNコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b8c0c-355">次のコマンドでプライベートオリジンCDN無効にするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b8c0c-356">このコマンドレットの詳細については [、「Set-SPOTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="b8c0c-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="b8c0c-358">PnP PowerShell を使用してOffice 365 CDN設定および構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="b8c0c-359">このセクションの手順では、PnP PowerShell を使用してオンラインに接続SharePointします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="b8c0c-360">手順については [、「PnP PowerShell の使用を開始する」を参照してください](https://github.com/SharePoint/PnP-PowerShell#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="b8c0c-361">PnP PowerShell を使用して、CDNをオンラインでホストSharePoint構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="b8c0c-362">クリックして展開</span><span class="sxs-lookup"><span data-stu-id="b8c0c-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b8c0c-363">組織が組織でユーザー設定を使用Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-364">テナントの設定を変更する前CDN、テナント内のプライベート CDN構成の現在Office 365する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b8c0c-365">Connect PnP PowerShell を使用してテナントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="b8c0c-366">**Get-PnPTenantCdnEnabled** コマンドレットを使用して、テナントからCDN状態設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b8c0c-367">指定した CdnType のCDNの状態が画面に出力されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b8c0c-368">**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織でこのコマンドレットを使用Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b8c0c-369">組織でパブリックオリジン、プライベートオリジン、または両方を同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="b8c0c-370">また、既定の原点CDN有効にするときに、既定の原点のセットアップをスキップする方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b8c0c-371">このトピックの説明に従って、これらの原点は後でいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-371">You can always add these origins later as described in this topic.</span></span>

<span data-ttu-id="b8c0c-372">PnP PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="b8c0c-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b8c0c-373">たとえば、組織でパブリックオリジンとプライベート オリジンの両方を使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b8c0c-374">組織でパブリックオリジンとプライベート オリジンの両方を使用できますが、既定のオリジンの設定をスキップするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b8c0c-375">Office 365 CDN を有効にした場合に既定でプロビジョニングされる起点と、既定の原点のセットアップをスキップした場合の潜在的な影響については、「Default CDN [origins」](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b8c0c-376">組織でパブリックオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b8c0c-377">組織でプライベートオリジンを使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b8c0c-378">このコマンドレットの詳細については [、「Set-PnPTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="b8c0c-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b8c0c-380">ファイルに含めるファイルの種類の一覧を変更する (Office 365 CDN)</span><span class="sxs-lookup"><span data-stu-id="b8c0c-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b8c0c-381">**Set-PnPTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b8c0c-382">リストに追加のファイルの種類を追加する場合は、まずコマンドレットを使用して、既に許可されているファイルの種類を確認し、新しいファイルの種類と一緒にリストに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>

<span data-ttu-id="b8c0c-383">**Set-PnPTenantCdnPolicy** コマンドレットを使用して、パブリックオリジンとプライベート オリジンでホストできる静的ファイルの種類を定義CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b8c0c-384">既定では、一般的なアセットの種類 (.css、.gif、.jpg、および.js。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b8c0c-385">PnP PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="b8c0c-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b8c0c-386">たとえば、.css ファイルとCDNファイルをホスト.pngするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b8c0c-387">現在許可されているファイルの種類を確認するには、CDN **Get-PnPTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b8c0c-388">これらのコマンドレットの詳細については [、「Set-PnPTenantCdnPolicy」](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) および [「Get-PnPTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b8c0c-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b8c0c-390">サイトから除外するサイト分類の一覧を変更する (Office 365 CDN)</span><span class="sxs-lookup"><span data-stu-id="b8c0c-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b8c0c-391">**Set-PnPTenantCdnPolicy** コマンドレットを使用してサイトの分類を除外すると、現在定義されているリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b8c0c-392">追加のサイト分類を除外する場合は、まずコマンドレットを使用して、既に除外されている分類を確認し、新しい分類と共に追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b8c0c-393">**Set-PnPTenantCdnPolicy** コマンドレットを使用して、サイトの分類を除外します。このコマンドレットを使用CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b8c0c-394">既定で除外されるサイトの分類はありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b8c0c-395">PnP PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="b8c0c-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="b8c0c-396">現在制限されているサイト分類を確認するには **、Get-PnPTenantCdnPolicies コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b8c0c-397">返されるプロパティは IncludeFileExtensions、ExcludeRestrictedSiteClassifications、ExcludeIfNoScriptDisabled _です_。  </span><span class="sxs-lookup"><span data-stu-id="b8c0c-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b8c0c-398">_IncludeFileExtensions_ プロパティには、アプリケーションから提供されるファイル拡張子の一覧がCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-399">既定のファイル拡張子は、パブリックとプライベートの間で異なります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b8c0c-400">_ExcludeRestrictedSiteClassifications_ プロパティには、サイトから除外するサイトのCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b8c0c-401">たとえば、機密としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツがサイトから提供CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b8c0c-402">_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性CDNに基づいてコンテンツを除外します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b8c0c-403">既定では _、NoScript_ 属性は [モダンサイトに対して有効] および [クラシック サイト **では無効]** _に設定_ されています。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b8c0c-404">これは、テナントの設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="b8c0c-405">これらのコマンドレットの詳細については [、「Set-PnPTenantCdnPolicy」](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) および [「Get-PnPTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b8c0c-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b8c0c-407">アセットのオリジンを追加する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-407">Add an origin for your assets</span></span>

<span data-ttu-id="b8c0c-408">発生元 **を定義するには、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b8c0c-409">複数の配信元を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-409">You can define multiple origins.</span></span> <span data-ttu-id="b8c0c-410">配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8c0c-411">ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b8c0c-412">path の値 _は_ 、アセットを含むライブラリまたはフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b8c0c-413">相対パスに加え、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b8c0c-414">Origins は、URL の先頭に付加されたワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b8c0c-415">これにより、複数のサイトにまたがるオリジンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b8c0c-416">たとえば、すべてのサイトの masterpages フォルダー内のすべてのアセットを、CDN 内のパブリック オリジンとして含めるには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b8c0c-417">ワイルドカード修飾子 \* は、パスの先頭でのみ使用できます。指定した URL の下のすべての URL セグメント **/** と一致します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b8c0c-418">パスは、ドキュメント ライブラリ、フォルダー、またはサイトを指します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b8c0c-419">たとえば、パス _\*/site1 は_ 、サイトの下のすべてのドキュメント ライブラリと一致します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b8c0c-420">特定の相対パスを持つ原点を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b8c0c-421">完全パスを使用して原点を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b8c0c-422">次の使用例は、サイトアセット ライブラリのプライベートオリジンを特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b8c0c-423">次の使用例は、サイト コレクションのサイト アセット ライブラリに _folder1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b8c0c-424">パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換える方法があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b8c0c-425">次の例では、サイト コレクションのサイト アセット ライブラリにフォルダー _1_ フォルダーのプライベートオリジンを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b8c0c-426">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-427">プライベートオリジンでは、オリジンから共有されているアセットにメジャー バージョンが公開されている必要があります。そのアセットは、そのオリジンからアクセスCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>

<span data-ttu-id="b8c0c-428">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-429">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b8c0c-431">例: マスター ページとオンライン用のスタイル ライブラリの公開元をSharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b8c0c-432">通常、これらの原点は既定で設定されます。既定では、この設定を有効Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b8c0c-433">ただし、手動で有効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-433">However, if you want to enable them manually, follow these steps.</span></span>

+ <span data-ttu-id="b8c0c-434">スタイル ライブラリをパブリックオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b8c0c-435">マスター ページをパブリックオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b8c0c-436">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b8c0c-437">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-438">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b8c0c-440">例: サイトアセット、サイト ページ、および公開イメージのプライベート オリジンをオンライン用にSharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b8c0c-441">**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイトアセット フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b8c0c-442">**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b8c0c-443">発行イメージ フォルダーをプライベートオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b8c0c-444">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b8c0c-445">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-446">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b8c0c-448">例: オンラインのサイト コレクションのプライベートオリジンをSharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b8c0c-449">**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b8c0c-450">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b8c0c-451">このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b8c0c-452">コマンドを実行すると、システムはデータセンター全体で構成を同期します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b8c0c-453">構成保留中の _メッセージが_ 表示される場合があります。これは、オンライン テナントが SharePointサービスに接続CDNです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b8c0c-454">これには最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b8c0c-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b8c0c-456">サーバーを管理Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-457">このセクションで説明するように、CDNを設定したら、コンテンツを更新したり、必要に応じて変更を加えたりして、構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>

<span data-ttu-id="b8c0c-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b8c0c-459">アセットを追加、更新、または削除Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-460">セットアップ手順が完了したら、新しいアセットを追加し、必要に従って既存のアセットを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b8c0c-461">作成元として識別したフォルダーまたはSharePointアセットに変更を加えるだけ。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b8c0c-462">新しいアセットを追加した場合は、すぐに新しいアセットをCDNできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b8c0c-463">ただし、アセットを更新した場合、新しいコピーが反映され、新しいコピーが使用できるまで最大で 15 分かかりますCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>

<span data-ttu-id="b8c0c-464">オリジンの場所を取得する必要がある場合は **、Get-PnPTenantCdnOrigin コマンドレットを使用** できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="b8c0c-465">このコマンドレットの使用方法については [、「Get-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b8c0c-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b8c0c-467">オブジェクトから原点を削除Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-468">作成元として識別したフォルダーまたはSharePointライブラリへのアクセスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b8c0c-469">これを行うには **、Remove-PnPTenantCdnOrigin コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b8c0c-470">このコマンドレットの使用方法については [、「Remove-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b8c0c-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b8c0c-472">オブジェクトの原点を変更Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-473">作成した原点は変更できません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b8c0c-474">代わりに、原点を削除し、新しい原点を追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b8c0c-475">詳細については、「アセットから原点[を削除](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)するには」および「Office 365 CDNを追加するには」[を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="b8c0c-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b8c0c-477">サーバーを無効Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-478">**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織のCDNを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b8c0c-479">パブリック オリジンとプライベート オリジンの両方が CDNに対して有効になっている場合は、次の例に示すように、コマンドレットを 2 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>

<span data-ttu-id="b8c0c-480">パブリック オリジンの使用を無効にするには、CDNコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b8c0c-481">次のコマンドでプライベートオリジンCDN無効にするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b8c0c-482">このコマンドレットの詳細については [、「Set-PnPTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="b8c0c-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="b8c0c-484">Office 365 CLI を使用して Office 365 CDN をセットアップおよび構成する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="b8c0c-485">このセクションの手順では、CLI をインストールしている必要Office 365[です](https://aka.ms/o365cli)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="b8c0c-486">次に、login コマンドをOffice 365テナントに[接続](https://pnp.github.io/office365-cli/cmd/login/)します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="b8c0c-487">次の手順を実行して、CDN CLI を使用して SharePointをホストするOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="b8c0c-488">クリックして展開</span><span class="sxs-lookup"><span data-stu-id="b8c0c-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="b8c0c-489">サーバーを有効Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-490">テナントの Office 365 CDN の状態は [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) コマンドを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="b8c0c-491">テナントで Office 365 パブリック CDN を有効にするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="b8c0c-492">アプリケーションを有効にするにはOffice 365 SharePoint CDN実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="b8c0c-493">Office 365 CDN の現在の状況を確認する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-494">特定の種類のファイルが有効または無効Office 365 CDN確認するには[、spo cdn get コマンドを使用](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="b8c0c-495">Office 365 パブリック CDN が有効かどうかを確認するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="b8c0c-496">原点をOffice 365 CDNする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="b8c0c-497">現在構成されている Office 365 パブリック CDN の配信元を確認するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="b8c0c-498">既定[でCDNを](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)有効にした場合にプロビジョニングされるオリジンの詳細については、「Default Office 365 CDN」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="b8c0c-499">原点をOffice 365 CDNする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8c0c-500">パブリック オリジンとして構成されたドキュメント ライブラリ内に、組織にSharePointと見なされるリソースを配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="b8c0c-501">[spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) コマンドを使用して CDN の配信元を定義します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="b8c0c-502">複数の配信元を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-502">You can define multiple origins.</span></span> <span data-ttu-id="b8c0c-503">配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="b8c0c-504">ここで `path` 、アセットを含むフォルダーへの相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="b8c0c-505">相対パスに加え、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="b8c0c-506">すべてのサイトのマスター ページギャラリーのすべてのアセットを公開元として含めるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="b8c0c-507">特定のサイト コレクションのプライベートの配信元を構成するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="b8c0c-508">CDN の配信元の追加後、CDN サービス経由でファイルを取得できるようになるまで最大 15 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="b8c0c-509">特定の配信元が既に有効かどうかは、[spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) コマンドを使用して検証できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="b8c0c-510">原点をOffice 365 CDNする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="b8c0c-511">[spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) コマンドを使用して、指定した種類の CDN の配信元を削除します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="b8c0c-512">パブリックオリジンを構成から削除するにはCDN実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="b8c0c-513">元のCDN削除しても、その原点に一致するドキュメント ライブラリに格納されているファイルには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="b8c0c-514">これらのアセットが URL を使用して参照されているSharePoint、SharePointドキュメント ライブラリを指す元の URL に自動的に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="b8c0c-515">ただし、アセットがパブリック CDN URL を使用して参照されている場合、原点を削除するとリンクが壊れ、手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="b8c0c-516">原点をOffice 365 CDNする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="b8c0c-517">既存の CDN の配信元を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="b8c0c-518">代わりに、`spo cdn origin remove` コマンドを使用して定義済みの CDN の配信元を削除して、`spo cdn origin add` コマンドで新しい配信元を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="b8c0c-519">ファイルに含めるファイルの種類を変更Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-520">既定では、次のファイルの種類が CDN に含まれています _。.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2_ です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="b8c0c-521">CDN に他の種類のファイルを含める必要がある場合、[spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して CDN 構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-522">ファイルの種類のリストを変更する場合、現在定義されているリストを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="b8c0c-523">他のファイルの種類を追加する場合は、[spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) コマンドを最初に使用して現在構成されているファイルの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="b8c0c-524">JSON ファイルの種類 _を_ パブリック ファイルに含まれるファイルの既定の一覧に追加するには、次CDN実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="b8c0c-525">Office 365 CDN から除外するサイトの分類のリストを変更する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-526">[spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して、CDN で利用できるようにしないサイトの分類を除外します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b8c0c-527">既定で除外されるサイトの分類はありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-528">除外するサイトの分類のリストを変更する場合、現在定義されているリストを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="b8c0c-529">他の分類を除外する場合は、[spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) コマンドを最初に使用して現在構成されている分類を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="b8c0c-530">HBI として分類された _サイトを_ パブリック サイトから除外するには、CDN実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b8c0c-531">サーバーを無効Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-532">Office 365 CDN を無効にするには、`spo cdn set` コマンドを使用します。たとえば、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="b8c0c-533">アセットCDN使用する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-533">Using your CDN assets</span></span>

<span data-ttu-id="b8c0c-534">作成元と構成済みのCDNを有効にしたので、アセットの使用CDNできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="b8c0c-535">このセクションでは、SharePoint ページとコンテンツで CDN URL を使用して、SharePoint がパブリックオリジンとプライベート オリジンの両方のアセットの要求を CDN にリダイレクトする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="b8c0c-536">アセットへのリンクCDNする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="b8c0c-537">パブリックオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="b8c0c-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="b8c0c-538">プライベートオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="b8c0c-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="b8c0c-539">クライアント側 Web パーツをホストするために CDN を使用する方法については、「Office 365 CDN からクライアント側 Web パーツをホストする (Hello World Part [4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-540">_ClientSideAssets_ フォルダーをプライベート CDNリストに追加すると、CDNホストされたカスタム Web パーツはレンダリングに失敗します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="b8c0c-541">SPFX Web パーツで使用されるファイルはパブリック CDN のみを使用し、ClientSideAssets フォルダーはパブリック サーバーの既定のCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span>

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="b8c0c-542">アセットへのリンクCDNする</span><span class="sxs-lookup"><span data-stu-id="b8c0c-542">Updating links to CDN assets</span></span>

<span data-ttu-id="b8c0c-543">オリジンに追加したアセットを使用するには、元のファイルへのリンクを元のファイルへのパスで更新します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="b8c0c-544">オリジンに追加したアセットへのリンクを含むページまたはコンテンツを編集します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="b8c0c-545">また、表示される任意の場所で特定のアセットへのリンクを更新する場合は、いくつかの方法のいずれかを使用して、入力サイトまたはサイト コレクション全体のリンクをグローバルに検索および置換できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="b8c0c-546">オリジン内のアセットへの各リンクについて、パスをコピー元のファイルへのパスCDNします。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="b8c0c-547">相対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-547">You can use relative paths.</span></span>
+ <span data-ttu-id="b8c0c-548">ページまたはコンテンツを保存します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-548">Save the page or content.</span></span>

<span data-ttu-id="b8c0c-549">たとえば、ドキュメント ライブラリ フォルダー _/site/CDN_origins/public/ にコピーしたイメージ /site/SiteAssets/images/image.png_ を _検討します_。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="b8c0c-550">CDN アセットを使用するには、イメージ ファイルの場所への元のパスを原点へのパスに置き換え、新しい URL _/site/CDN_origins/public/image.pngを作成します_。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="b8c0c-551">相対パスではなくアセットの完全な URL を使用する場合は、次のようにリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="b8c0c-552">一般に、URL を直接、ページ内のアセットにハードコードCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="b8c0c-553">ただし、必要に応じて、パブリック オリジンのアセットの URL を手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="b8c0c-554">詳細については[、「Hardcoding CDNの URL」を参照してください](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="b8c0c-555">CDN からアセットが提供されているのを確認する方法については、「CDN でアセットが[](use-microsoft-365-cdn-with-spo.md#CDNConfirm)提供されているのを確認する方法」を参照してください。「Office 365 CDN のトラブルシューティング」を[参照してください](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="b8c0c-556">パブリックオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="b8c0c-556">Using assets in public origins</span></span>

<span data-ttu-id="b8c0c-557">SharePoint  Online の発行機能は、パブリック オリジンに格納されているアセットの URL を自動的に CDN 同等のアセットに書き換え、SharePoint ではなく CDN サービスからアセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="b8c0c-558">発行元が発行機能が有効なサイト内で、CDN にオフロードするアセットが次のいずれかのカテゴリにある場合、SharePoint は、アセットが CDN ポリシーによって除外されていない場合、オリジンのアセットの URL を自動的に書き換える。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="b8c0c-559">SharePoint 発行機能によって自動的に書き換えられるのは次のようなリンクです。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="b8c0c-560">従来の発行ページの HTML 応答の IMG/LINK/CSS URL</span><span class="sxs-lookup"><span data-stu-id="b8c0c-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="b8c0c-561">これには、ページの HTML コンテンツ内に作成者によって追加された画像が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="b8c0c-562">画像ライブラリ スライドショー Web パーツの画像 URL</span><span class="sxs-lookup"><span data-stu-id="b8c0c-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="b8c0c-563">SPList REST API (RenderListDataAsStream) 結果の画像フィールド</span><span class="sxs-lookup"><span data-stu-id="b8c0c-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="b8c0c-564">フィールドのコンマ区切りリストを指定するには、新しいプロパティ _ImageFieldsToTryRewriteToCdnUrls_ を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="b8c0c-565">ハイパーリンク フィールドと PublishingImage フィールドをサポート</span><span class="sxs-lookup"><span data-stu-id="b8c0c-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="b8c0c-566">SharePoint表示</span><span class="sxs-lookup"><span data-stu-id="b8c0c-566">SharePoint image renditions</span></span>

<span data-ttu-id="b8c0c-567">次の図は、公開元SharePointを含むページの要求を受け取るワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="b8c0c-568">![ワークフロー図: 公開元Office 365 CDNアセットを取得する](../media/O365-CDN/o365-cdn-public-steps-transparent.png "ワークフロー: パブリック Office 365 CDNアセットの取得")</span><span class="sxs-lookup"><span data-stu-id="b8c0c-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.png "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="b8c0c-569">ページ上の特定の URL の自動書き換えを無効にする場合は、ページをチェックアウトしてクエリ文字列パラメーターを **追加できます。無効にする各リンクの末尾に NoAutoReWrites=true** を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="b8c0c-570">パブリックアセットCDN URL の作成</span><span class="sxs-lookup"><span data-stu-id="b8c0c-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="b8c0c-571">公開機能がパブリック オリジンで有効になっていない場合、またはアセットが CDN サービスの自動書き換え機能でサポートされているリンクの種類の 1 つではない場合は、アセットの CDN 場所に URL を手動で作成し、コンテンツでこれらの URL を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-572">リソースが要求された時点で URL の最後のセクションを形成する必要なアクセス トークンが生成されるので、プライベート オリジンのアセットに CDN URL をハードコードまたは構築することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="b8c0c-573">パブリック サーバーの URL を作成CDN、変更される可能性がある URL をハード コードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="b8c0c-574">パブリック アセットCDN URL 形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="b8c0c-575">**TenantHostName をテナント** 名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="b8c0c-576">例:</span><span class="sxs-lookup"><span data-stu-id="b8c0c-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="b8c0c-577">ページ コンテキスト プロパティを使用して、ハード コーディング " " ではなくプレフィックスを作成する必要 https://publiccdn.sharepointonline.com があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="b8c0c-578">URL は変更される可能性があります。ハード コード化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="b8c0c-579">クラシック SharePoint Online で表示テンプレートを使用している場合は、URL のプレフィックスとして表示テンプレートのプロパティ "window._spPageContextInfo.publicCdnBaseUrl" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="b8c0c-580">モダンおよびクラシック SPFx Web パーツを使用する場合SharePointプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" を利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="b8c0c-581">これにより、プレフィックスが提供され、変更された場合に実装が更新されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="b8c0c-582">SPFx の例として、URL はプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" を使用して構築できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="b8c0c-583">シーズン 1[のパフォーマンス CDNの一部であるクライアント](https://youtu.be/IH1RbQlbhIA)側コードの 「コードを使用する」[を参照してください。](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="b8c0c-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="b8c0c-584">プライベートオリジンでのアセットの使用</span><span class="sxs-lookup"><span data-stu-id="b8c0c-584">Using assets in private origins</span></span>

<span data-ttu-id="b8c0c-585">プライベートオリジンでアセットを使用するには、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="b8c0c-586">SharePointオンラインでは、プライベートオリジン内のアセットの URL が自動的に書き換わるので、それらのアセットの要求は常にサーバーから提供CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="b8c0c-587">これらの URL には、アセットが要求された時点で SharePoint Online によって自動生成する必要があるトークンが含まれているため、プライベート オリジンの CDN アセットに対して URL を手動でビルドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="b8c0c-588">プライベートオリジンのアセットへのアクセスは、オリジンに対するユーザーのアクセス許可に基づいて動的に生成されたトークンによって保護されます。以下のセクションで説明する注意点があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="b8c0c-589">ユーザーがコンテンツをレンダリングするには **、** 少なくとも原点への読み取りアクセスCDN必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="b8c0c-590">次の図は、プライベートオリジンSharePointを含むページの要求を受け取るワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="b8c0c-591">![ワークフロー図: プライベート Office 365 CDNからアセットを取得する](../media/O365-CDN/o365-cdn-private-steps-transparent.png "ワークフロー: プライベート Office 365 CDNからアセットを取得する")</span><span class="sxs-lookup"><span data-stu-id="b8c0c-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.png "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="b8c0c-592">プライベートオリジンでのトークンベースの承認</span><span class="sxs-lookup"><span data-stu-id="b8c0c-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="b8c0c-593">プライベート オリジン内のアセットへのアクセスは、Office 365 CDN Online によって生成されたトークンSharePointされます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="b8c0c-594">作成元によって指定されたフォルダーまたはライブラリへのアクセス許可を既に持っているユーザーには、アクセス許可レベルに基づいてユーザーがファイルにアクセスできるトークンが自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="b8c0c-595">これらのアクセス トークンは、トークン再生攻撃を防止するために生成された後、30 ~ 90 分間有効です。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="b8c0c-596">アクセス トークンが生成されると、SharePoint Online は、2 つの承認パラメーターを含む _クライアントにカスタム_ URI (エッジ承認トークン) と _oat_ (オリジン認証トークン) を返します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="b8c0c-597">各トークンの構造は _、epoch<_ のセキュリティで保護された署名の>__<の有効期限>。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="b8c0c-598">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="b8c0c-599">トークンを所有しているユーザーは、リソースにアクセスCDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="b8c0c-600">ただし、これらのアクセス トークンを含む URL は HTTPS 経由でのみ共有されます。そのため、トークンの有効期限が切れる前にエンド ユーザーが URL を明示的に共有しない限り、承認されていないユーザーはアセットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="b8c0c-601">アイテム レベルのアクセス許可は、プライベートオリジンのアセットではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="b8c0c-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="b8c0c-602">重要な点は、SharePoint Online がプライベートオリジンのアセットに対するアイテム レベルのアクセス許可をサポートしていない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="b8c0c-603">たとえば、場所にあるファイルの場合、ユーザーは次の条件に従って `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` ファイルに効果的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="b8c0c-604">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b8c0c-604">User</span></span>  |<span data-ttu-id="b8c0c-605">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b8c0c-605">Permissions</span></span>  |<span data-ttu-id="b8c0c-606">有効なアクセス</span><span class="sxs-lookup"><span data-stu-id="b8c0c-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b8c0c-607">ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="b8c0c-607">User 1</span></span>     |<span data-ttu-id="b8c0c-608">フォルダー 1 へのアクセス権を持つ</span><span class="sxs-lookup"><span data-stu-id="b8c0c-608">Has access to folder1</span></span>         |<span data-ttu-id="b8c0c-609">サーバーからimage1.jpgアクセスCDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b8c0c-610">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="b8c0c-610">User 2</span></span>     |<span data-ttu-id="b8c0c-611">folder1 にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="b8c0c-611">Does not have access to folder1</span></span>         |<span data-ttu-id="b8c0c-612">サーバーからimage1.jpgにアクセスCDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b8c0c-613">ユーザー 3</span><span class="sxs-lookup"><span data-stu-id="b8c0c-613">User 3</span></span>     |<span data-ttu-id="b8c0c-614">folder1 へのアクセス権は付与されませんが、オンラインでフォルダーにアクセスするための明示的image1.jpgがSharePointされます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b8c0c-615">オンラインから直接image1.jpgアクセスできますが、SharePointからアクセスCDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="b8c0c-616">ユーザー 4</span><span class="sxs-lookup"><span data-stu-id="b8c0c-616">User 4</span></span>     |<span data-ttu-id="b8c0c-617">folder1 へのアクセス権を持っていますが、オンラインでフォルダーへのアクセスimage1.jpg明示的SharePointされています</span><span class="sxs-lookup"><span data-stu-id="b8c0c-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b8c0c-618">SharePoint Online からアセットにアクセスすることはできませんが、CDN Online でファイルへのアクセスが拒否されているにもかかわらず、CDN からアセットにSharePointできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="b8c0c-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="b8c0c-620">問題のトラブルシューティングOffice 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b8c0c-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="b8c0c-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="b8c0c-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="b8c0c-622">アセットがサービスを受け取っているのを確認CDN。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="b8c0c-623">CDN アセットへのリンクをページに追加したら、CDN からアセットが提供されているのを確認するには、ページを参照し、レンダリング後にイメージを右クリックし、イメージの URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="b8c0c-624">ブラウザーの開発者ツールを使用して、ページ上の各アセットの URL を表示したり、サードパーティのネットワーク トレース ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c0c-625">Fiddler などのネットワーク ツールを使用して、SharePoint ページからのアセットのレンダリング以外でアセットをテストする場合は、url が SharePoint Online テナントのルート URL である GET 要求に、参照先ヘッダー "Referer:" を手動で追加する必要があります。 `https://yourdomain.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="b8c0c-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="b8c0c-626">Web ブラウザーでCDN URL をテストすることはできません。Web ブラウザーから参照者がオンラインSharePointがあります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="b8c0c-627">ただし、CDN アセット URL を SharePoint ページに追加し、ブラウザーでページを開いた場合は、CDN アセットがページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="b8c0c-628">ブラウザーで開発者ツールを使用する方法の詳細については、「Microsoft Edge開発者ツール[」をMicrosoft Edgeしてください](/microsoft-edge/devtools-guide)。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="b8c0c-629">SharePoint Developer Patterns and [Practices YouTube](https://aka.ms/sppnp-videos)チャネルでホストされている短いビデオを見て、CDN が動作しているのを確認する方法を説明するには[、「CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)使用状況の確認と最適なネットワーク接続の確保」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="b8c0c-630">新しいオリジンのアセットが使用できない理由</span><span class="sxs-lookup"><span data-stu-id="b8c0c-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="b8c0c-631">登録が CDN 経由で伝達され、アセットが起点から CDN ストレージにアップロードされるのに時間がかかるので、新しいオリジンのアセットはすぐには使用できません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="b8c0c-632">アセットが利用可能になるのに必要な時間は、CDNの数とファイル サイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="b8c0c-633">クライアント側の Web パーツまたはSharePoint Frameworkソリューションが機能しない</span><span class="sxs-lookup"><span data-stu-id="b8c0c-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="b8c0c-634">パブリックオリジンのOffice 365 CDNを有効にした場合、CDNサービスは次の既定のオリジンを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="b8c0c-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="b8c0c-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="b8c0c-636">\*/STYLE ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b8c0c-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="b8c0c-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="b8c0c-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="b8c0c-638">\*/clientsideassets の生成元が見つからない場合、SharePoint Frameworkソリューションは失敗し、警告メッセージやエラー メッセージは生成されません。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="b8c0c-639">CDN が _-NoDefaultOrigins_ パラメーターを **$true** に設定して有効になっているか、または原点が手動で削除されたため、この原点が見つからない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="b8c0c-640">次の PowerShell コマンドを使用して、どの原点が存在するのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="b8c0c-641">または、次の CLI でOffice 365できます。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="b8c0c-642">PowerShell で原点を追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="b8c0c-643">CLI で原点をOffice 365するには、次のOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="b8c0c-644">どの PowerShell モジュールと CLI シェルを使用して作業する必要Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="b8c0c-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="b8c0c-645">オンライン管理シェル PowerShell モジュールまたは Office 365 CDN CLIを使用して、SharePointを使用Office 365 **できます**。</span><span class="sxs-lookup"><span data-stu-id="b8c0c-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="b8c0c-646">SharePoint Online 管理シェルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b8c0c-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [<span data-ttu-id="b8c0c-647">Office 365 CLI のインストール</span><span class="sxs-lookup"><span data-stu-id="b8c0c-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="b8c0c-648">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8c0c-648">See also</span></span>

[<span data-ttu-id="b8c0c-649">Content Delivery Network</span><span class="sxs-lookup"><span data-stu-id="b8c0c-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="b8c0c-650">Office 365 のネットワーク計画とパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="b8c0c-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="b8c0c-651">SharePointPerformance Series - Office 365 CDN ビデオ シリーズ</span><span class="sxs-lookup"><span data-stu-id="b8c0c-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
