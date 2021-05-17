---
title: Office 365ビデオ ネットワークに関するよく寄せられる質問
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 帯域幅の計画、暗号化、サービスによるコンテンツ配信ネットワーク (CDN) の活用方法に関する最も&質問に対する回答を見つける。
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921572"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a><span data-ttu-id="12e81-103">Office 365ビデオ ネットワークに関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="12e81-103">Office 365 Video networking Frequently Asked Questions</span></span>

<span data-ttu-id="12e81-104">ビデオ Office 365ストリーミング サービスを使用すると、組織内でのビデオの保存とストリーミングが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="12e81-104">The Office 365 Video repository and streaming services make storing and streaming videos within your organization simple.</span></span> <span data-ttu-id="12e81-105">ビデオに関する多[くのOffice 365があります](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)。このネットワークに関する FAQ は、帯域幅の計画、暗号化、およびサービスがコンテンツ配信ネットワーク[](content-delivery-networks.md) (CDN) を活用する方法に関する最も一般的な質問に答える目的で設計されています。</span><span class="sxs-lookup"><span data-stu-id="12e81-105">There's a lot of great [information about Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); this networking FAQ is designed to answer the most common questions around bandwidth planning, encryption, and how the service leverages [Content Delivery Networks](content-delivery-networks.md) (CDNs).</span></span>
  
<span data-ttu-id="12e81-106">ビデオがアップロードまたは再生された場合に何が起こるかについて十分に理解していない場合は、このビデオを一緒に見てみましょう。Office 365 ビデオにアップロードするとビデオ[ファイルに何が](https://www.youtube.com/watch?v=HXSZ0jYBKlM)起こるか。</span><span class="sxs-lookup"><span data-stu-id="12e81-106">If you don't already have a thorough understanding of what happens when a video is uploaded or played back, have a look at this video we put together, [What happens to a video file when uploaded to Office 365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).</span></span>
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a><span data-ttu-id="12e81-107">ビデオ帯域幅の要件Office 365は何ですか?</span><span class="sxs-lookup"><span data-stu-id="12e81-107">What are the Office 365 Video bandwidth requirements?</span></span>

<span data-ttu-id="12e81-108">サポートされている多数[のビデオ形式は](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817)、ユーザーにアップロードOffice 365。</span><span class="sxs-lookup"><span data-stu-id="12e81-108">There are a numerous [supported video formats](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) that can be uploaded to Office 365.</span></span> <span data-ttu-id="12e81-109">その後、各ビデオ ファイルは、再生用にいくつかの異なるビデオ品質を持つ標準形式にエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="12e81-109">Each video file is then encoded to a standard format with several different video qualities for playback.</span></span> <span data-ttu-id="12e81-110">Office 365ビデオでは、アダプティブ ビットレート ストリーミングを使用して、利用可能なネットワーク帯域幅とビデオ プレーヤーのサイズに基づいて最適なビデオ再生品質を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e81-110">Office 365 Video uses adaptive bitrate streaming to select the best video playback quality based on the available network bandwidth and size of the video player.</span></span> <span data-ttu-id="12e81-111">これを行うには、プレイヤーは最初に最も低い再生品質を要求します。</span><span class="sxs-lookup"><span data-stu-id="12e81-111">To do this, the player initially requests the lowest playback quality.</span></span> <span data-ttu-id="12e81-112">その後、サービスはビデオ プレーヤーに 2 秒間のビデオ セグメントの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="12e81-112">The service then begins sending 2-second video segments to the video player.</span></span> <span data-ttu-id="12e81-113">プレイヤーは、各セグメントの配信速度に基づいて、より高い再生品質または低い再生品質を要求できます。</span><span class="sxs-lookup"><span data-stu-id="12e81-113">The player can then request higher or lower playback quality based on how quickly each segment is delivered.</span></span>
  
<span data-ttu-id="12e81-114">アダプティブ ビットレート ストリーミングは、ビデオが中断やバッファー処理の最小量で再生されている間、バックグラウンドでこのすべての処理を行います。</span><span class="sxs-lookup"><span data-stu-id="12e81-114">The adaptive bitrate streaming does all this in the background while the video plays with the least amount of disruption or buffering.</span></span> <span data-ttu-id="12e81-115">ビデオ再生中に、ビデオ プレーヤーは、ビューアーが手動で自動再生品質を上書きして、特定のビデオ再生品質を選択できます。</span><span class="sxs-lookup"><span data-stu-id="12e81-115">During video playback, the video player allows the viewer to manually override the automatic playback quality, to select a specific video playback quality.</span></span>
  
<span data-ttu-id="12e81-116">ビデオ再生の各品質のネットワーク要件の概要を示す簡単な表を次に示します。</span><span class="sxs-lookup"><span data-stu-id="12e81-116">Here's a quick table that outlines the network requirements for each of the video playback qualities.</span></span> <span data-ttu-id="12e81-117">ビデオの再生に必要な 1 人あたりの最小帯域幅は 802Kbps です。</span><span class="sxs-lookup"><span data-stu-id="12e81-117">The minimum bandwidth per person needed to play a video is 802Kbps.</span></span>
  
| <span data-ttu-id="12e81-118">再生品質</span><span class="sxs-lookup"><span data-stu-id="12e81-118">Playback Quality</span></span> | <span data-ttu-id="12e81-119">ネットワーク速度</span><span class="sxs-lookup"><span data-stu-id="12e81-119">Network Speed</span></span> |
|:-----|:-----|
|<span data-ttu-id="12e81-120">288p</span><span class="sxs-lookup"><span data-stu-id="12e81-120">288p</span></span>  <br/> |<span data-ttu-id="12e81-121">802Kbps</span><span class="sxs-lookup"><span data-stu-id="12e81-121">802Kbps</span></span>  <br/> |
|<span data-ttu-id="12e81-122">360p</span><span class="sxs-lookup"><span data-stu-id="12e81-122">360p</span></span>  <br/> |<span data-ttu-id="12e81-123">1.2 Mbps</span><span class="sxs-lookup"><span data-stu-id="12e81-123">1.2 Mbps</span></span>  <br/> |
|<span data-ttu-id="12e81-124">576p</span><span class="sxs-lookup"><span data-stu-id="12e81-124">576p</span></span>  <br/> |<span data-ttu-id="12e81-125">2.5 Mbps</span><span class="sxs-lookup"><span data-stu-id="12e81-125">2.5 Mbps</span></span>  <br/> |
|<span data-ttu-id="12e81-126">720p</span><span class="sxs-lookup"><span data-stu-id="12e81-126">720p</span></span>  <br/> |<span data-ttu-id="12e81-127">3.8 Mbps</span><span class="sxs-lookup"><span data-stu-id="12e81-127">3.8 Mbps</span></span>  <br/> |

<span data-ttu-id="12e81-128">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-128">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a><span data-ttu-id="12e81-129">コンテンツ配信ネットワーク (CDN) はビデオの再生にどう役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="12e81-129">How do Content Delivery Networks (CDNs) help video playback?</span></span>

<span data-ttu-id="12e81-130">同じ地理的な場所内の同じ組織の複数のユーザーが同じビデオをストリーミングしている場合、CDN は、これらのビデオのコピーをその地理的地域に近い場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="12e81-130">If several people from the same organization within the same geographic location are streaming the same video(s), CDNs will store a copy of these videos in a location closer to that geographic region.</span></span> <span data-ttu-id="12e81-131">ビデオを保存するか、最も近い場所にキャッシュすると、各ユーザーは、遠く離れた場所ではなく、最も近い場所からビデオをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="12e81-131">With the video stored, or cached at the closest location, each person streams the video from the location closest to them instead of a location further away.</span></span> <span data-ttu-id="12e81-132">Office 365ビデオでは、Azure Media Servicesを使用して、Azure CDN にキャッシュされるコンテンツと、その期間を管理します。</span><span class="sxs-lookup"><span data-stu-id="12e81-132">Office 365 Video uses Azure Media Services to manage what is cached in the Azure CDNs, and for how long.</span></span> <span data-ttu-id="12e81-133">Azure Media Services任意の場所をAzure CDN、数日間[](/azure/cdn/cdn-pop-locations)ビデオ フラグメントとマニフェストをキャッシュできます。</span><span class="sxs-lookup"><span data-stu-id="12e81-133">Azure Media Services can use any of the [Azure CDN locations](/azure/cdn/cdn-pop-locations) to cache video fragments and manifests for a few days.</span></span> <span data-ttu-id="12e81-134">組織内のユーザーがキャッシュされたビデオを引き続き視聴する場合、キャッシュに残されます。</span><span class="sxs-lookup"><span data-stu-id="12e81-134">If people in your organization continue to watch the cached videos they'll stay in the cache.</span></span> <span data-ttu-id="12e81-135">数日間ビデオにアクセスするユーザーがいない場合、ビデオは最終的にキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="12e81-135">If no one accesses the video for several days, the video will eventually drop be dropped from the cache.</span></span> <span data-ttu-id="12e81-136">次回、誰かがビデオを視聴しようとすると、最も近い場所に再びCDNされます。</span><span class="sxs-lookup"><span data-stu-id="12e81-136">The next time someone attempts to watch the video it's once again cached at the nearest CDN location.</span></span>
  
<span data-ttu-id="12e81-137">コンテンツが近くの CDN でキャッシュされている間にビデオを視聴しようとするすべてのユーザーは、ビデオが近く、ほとんどの場合ホップが少なく、離れて行くメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="12e81-137">Everyone who attempts to watch the video while the content is cached at a nearby CDN benefits from the video being closer, and in most cases less hops, away.</span></span> <span data-ttu-id="12e81-138">これにより、ビデオの再生速度が向上します。ただし、ビデオを再生するネットワーク要件は変更されません。</span><span class="sxs-lookup"><span data-stu-id="12e81-138">This improves video playback speed; however, it doesn't change the network requirement to play the video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12e81-139">容量制限に達した場合など、3 日前にビデオが削除される場合があります。</span><span class="sxs-lookup"><span data-stu-id="12e81-139">There are some circumstances, such as our capacity limit being reached, where the video may be removed before the three days has been reached.</span></span>
  
<span data-ttu-id="12e81-140">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-140">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a><span data-ttu-id="12e81-141">高速再生のためにビデオをローカルにキャッシュできますか?</span><span class="sxs-lookup"><span data-stu-id="12e81-141">Can I cache the videos locally for faster playback?</span></span>

<span data-ttu-id="12e81-142">はい。</span><span class="sxs-lookup"><span data-stu-id="12e81-142">Yes.</span></span> <span data-ttu-id="12e81-143">Office 365、ローカル CDN またはキャッシュ プロキシを使用して、ビデオや他の Office 365 コンテンツをローカル ネットワークに持ち込み、アクセスを高速化できます。</span><span class="sxs-lookup"><span data-stu-id="12e81-143">Office 365 won't prevent you from using a local CDN or a caching proxy to bring video or other Office 365 content into your local network for faster access.</span></span> <span data-ttu-id="12e81-144">ネットワークにローカル キャッシュ ソリューションを実装するにはいくつかの方法があります。最も一般的な方法は、コンテンツをローカルにキャッシュするプロキシ ソリューションを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="12e81-144">There are several ways to implement a local caching solution on your network, the most common method is to use a proxy solution that caches content locally.</span></span> <span data-ttu-id="12e81-145">プロキシまたはプライベート CDN がビデオ フラグメントとマニフェストをキャッシュすると、プロキシまたはプライベート CDN を経由するファイルに対する今後の要求はローカル キャッシュから引き出され、インターネットの場所から引き出されません。</span><span class="sxs-lookup"><span data-stu-id="12e81-145">Once a proxy or private CDN has cached the video fragments and manifests, future requests for those files that route through the proxy or private CDN are pulled from the local cache and not pulled from an internet location.</span></span> <span data-ttu-id="12e81-146">このようなソリューションの計画中に、ネットワーク帯域幅、容量、ビデオ再生の同時実行を検討します。</span><span class="sxs-lookup"><span data-stu-id="12e81-146">Consider network bandwidth, capacity, and video playback concurrency during the planning of a solution like this.</span></span>
  
<span data-ttu-id="12e81-147">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-147">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-videos-are-encrypted-and-secured"></a><span data-ttu-id="12e81-148">ビデオの暗号化とセキュリティ保護の方法</span><span class="sxs-lookup"><span data-stu-id="12e81-148">How videos are encrypted and secured?</span></span>

<span data-ttu-id="12e81-149">Office 365ビデオでは、データを安全かつプライベートに保つ必要がある点が分かっています。</span><span class="sxs-lookup"><span data-stu-id="12e81-149">Office 365 Video knows how important it is to keep your data secure and private.</span></span> <span data-ttu-id="12e81-150">[Microsoft Trust Center では](https://products.office.com/business/office-365-trust-center-welcome) 、コンテンツのプライバシーとセキュリティに対する取り組みについて説明します。</span><span class="sxs-lookup"><span data-stu-id="12e81-150">[Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) describes our commitment to the privacy and security of your content.</span></span> <span data-ttu-id="12e81-151">ビデオの再生では、優れたエクスペリエンスを実現するには速度が重要です。ただし、速度と引き換えにセキュリティやプライバシーは侵害しません。</span><span class="sxs-lookup"><span data-stu-id="12e81-151">With video playback, speed is important for a good experience; however, we don't compromise your security or privacy in exchange for speed.</span></span> <span data-ttu-id="12e81-152">速度、セキュリティ、プライバシーに対応する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="12e81-152">Here's how we accommodate speed, security and privacy.</span></span>
  
<span data-ttu-id="12e81-153">組織内のユーザーが新しいビデオをアップロードすると、そのビデオはトランスコードされ、AES-128 暗号化で暗号化され、Azure Media Services に保存されます。</span><span class="sxs-lookup"><span data-stu-id="12e81-153">When you or someone in your organization uploads a new video, that video is transcoded, encrypted with AES-128 encryption, and stored in Azure Media Services.</span></span> <span data-ttu-id="12e81-154">つまり、ビデオは転送中と保存時の両方で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="12e81-154">This means the videos are encrypted both in transit and at rest.</span></span>
  
<span data-ttu-id="12e81-155">組織内のユーザーが新しいビデオを視聴しようとすると、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="12e81-155">When someone in your organization attempts to watch a new video, they follow these steps:</span></span>
  
1. <span data-ttu-id="12e81-156">ビデオSharePointアクセス許可を持っている場合は、オンラインで確認します。</span><span class="sxs-lookup"><span data-stu-id="12e81-156">Ask SharePoint Online if they have permission to view the video.</span></span>

2. <span data-ttu-id="12e81-157">SharePointオンラインでは、ファイルのアクセス許可を使用して、ユーザーがビデオを視聴できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="12e81-157">SharePoint Online uses the file permissions to determine if the person can watch the video.</span></span>

3. <span data-ttu-id="12e81-158">許可されている場合、SharePointオンラインは Azure からトークンを取得してビデオ プレーヤーに渡します。</span><span class="sxs-lookup"><span data-stu-id="12e81-158">If they're allowed, SharePoint Online retrieves a token from Azure to give to the video player.</span></span>

4. <span data-ttu-id="12e81-159">その後、ビデオ プレーヤーはトークンを使用して Azure から復号化キーを要求します。</span><span class="sxs-lookup"><span data-stu-id="12e81-159">The video player then uses the token to request the decryption key from Azure.</span></span>

5. <span data-ttu-id="12e81-160">復号化キーを手にして、ビデオ プレーヤーはビデオをストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="12e81-160">With the decryption key in hand, the video player is able to stream the video.</span></span>

![O365 ビデオ再生](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
<span data-ttu-id="12e81-162">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-162">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a><span data-ttu-id="12e81-163">ビデオを再生する場合のOffice 365ですか?</span><span class="sxs-lookup"><span data-stu-id="12e81-163">What are the requirements to playback Office 365 Video?</span></span>

<span data-ttu-id="12e81-164">Office 365ビデオでサポートされるオペレーティング システムと Web ブラウザーは、システム要件にSharePointオンライン要件Office 365[同じです](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)。</span><span class="sxs-lookup"><span data-stu-id="12e81-164">Office 365 Video supported operating systems and web browsers are the same as the SharePoint Online requirements in [Office 365 system requirements](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45).</span></span> <span data-ttu-id="12e81-165">どのオペレーティング システムと Web ブラウザーの構成に応じて、ビデオ プレーヤーの特定のニーズが決定されます。</span><span class="sxs-lookup"><span data-stu-id="12e81-165">Depending on which operating system and web browser configuration you have will determine the specific needs of the video player.</span></span> <span data-ttu-id="12e81-166">ビデオ再生の要件の [詳細については、次の情報を参照してください](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)。</span><span class="sxs-lookup"><span data-stu-id="12e81-166">Here's more information on [video playback requirements](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).</span></span>
  
<span data-ttu-id="12e81-167">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-167">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a><span data-ttu-id="12e81-168">ビデオを動作Office 365できない場合は、どこから始める必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="12e81-168">I can't get Office 365 video to work, where should I start?</span></span>

<span data-ttu-id="12e81-169">ビデオへの接続Office 365トラブルシューティングには、ネットワーク、ISP、およびデバイスの構成のトラブルシューティングがOffice 365。</span><span class="sxs-lookup"><span data-stu-id="12e81-169">Troubleshooting connectivity to Office 365 Video involves troubleshooting your network, your ISP(s), and your configuration of Office 365.</span></span> <span data-ttu-id="12e81-170">最初に開始する場所は、サービス正常性ダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="12e81-170">The first place to start is the service health dashboard.</span></span> <span data-ttu-id="12e81-171">これにより、ビデオに問題Office 365問題が発生している可能性が示されます。</span><span class="sxs-lookup"><span data-stu-id="12e81-171">This will tell you of Office 365 Video is having a problem or not.</span></span> <span data-ttu-id="12e81-172">すべてが見栄えの良い場合は、役立つ追加のリソースを次に示します。</span><span class="sxs-lookup"><span data-stu-id="12e81-172">If everything looks great there, here's some additional resources to help you.</span></span>
  
- <span data-ttu-id="12e81-173">ビデオに必要なネットワーク エンドポイントに接続[Office 365します](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="12e81-173">Make sure you can connect to the [network endpoints required for Office 365 Video](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

- <span data-ttu-id="12e81-174">ネットワークのトラブルシューティング ガイドを使用して[、ネットワークOffice 365を確認します](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。</span><span class="sxs-lookup"><span data-stu-id="12e81-174">Check your network connectivity using our [Office 365 network troubleshooting guide](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).</span></span>

- <span data-ttu-id="12e81-175">低速の[ネットワークでネットワークを使用するためのベスト Office 365を参照してください](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="12e81-175">See our [best practices for using Office 365 on a slow network](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span>

- <span data-ttu-id="12e81-176">[ビデオ構成に関するOffice 365を確認します](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)。</span><span class="sxs-lookup"><span data-stu-id="12e81-176">[Find help about Office 365 Video configuration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).</span></span>

<span data-ttu-id="12e81-177">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-177">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="office-365-video-resources"></a><span data-ttu-id="12e81-178">Office 365ビデオ リソース</span><span class="sxs-lookup"><span data-stu-id="12e81-178">Office 365 Video resources</span></span>

<span data-ttu-id="12e81-179">ビデオの展開と使用を正常に行うのに役立つその他のOffice 365示します。</span><span class="sxs-lookup"><span data-stu-id="12e81-179">Here's a few other resources to help you successfully deploy and use Office 365 Video:</span></span>
  
[<span data-ttu-id="12e81-180">ビデオ構成に関するOffice 365検索</span><span class="sxs-lookup"><span data-stu-id="12e81-180">Find help about Office 365 Video configuration</span></span>](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[<span data-ttu-id="12e81-181">Office 365 ビデオを利用する</span><span class="sxs-lookup"><span data-stu-id="12e81-181">Meet Office 365 Video</span></span>](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[<span data-ttu-id="12e81-182">ビデオでチャネルを作成およびOffice 365する</span><span class="sxs-lookup"><span data-stu-id="12e81-182">Create and manage a channel in Office 365 Video</span></span>](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[<span data-ttu-id="12e81-183">Office 365 ビデオ ポータルを管理する</span><span class="sxs-lookup"><span data-stu-id="12e81-183">Manage your Office 365 Video portal</span></span>](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[<span data-ttu-id="12e81-184">ビデオで動作するビデオ形式Office 365ビデオ</span><span class="sxs-lookup"><span data-stu-id="12e81-184">Video formats that work in Office 365 Video</span></span>](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
<span data-ttu-id="12e81-185">([トップに戻る](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="12e81-185">([Back to top](office-365-video-networking-faq.md))</span></span>
  
<span data-ttu-id="12e81-186">ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/video365networkfaq]()</span><span class="sxs-lookup"><span data-stu-id="12e81-186">Here's a short link you can use to come back: [https://aka.ms/video365networkfaq]()</span></span>