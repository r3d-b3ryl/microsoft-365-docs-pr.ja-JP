---
title: Exchange Online のパフォーマンスをチューニングする
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: この記事には、パフォーマンスを向上させる方法を示す一般的なヒントと他のリソースへのリンクExchange Online。
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909444"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="6a4f9-103">Exchange Online のパフォーマンスをチューニングする</span><span class="sxs-lookup"><span data-stu-id="6a4f9-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="6a4f9-104">この記事には、移行の前に特に、Exchange Onlineのパフォーマンスを向上させる方法を示す一般的なヒントと他のリソースへのリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="6a4f9-105">この記事は、プロジェクトのネットワーク[計画とパフォーマンスの調整Office 365](./network-planning-and-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="6a4f9-106">パフォーマンスを向上させるために考慮Exchange Online点</span><span class="sxs-lookup"><span data-stu-id="6a4f9-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="6a4f9-107">移行の速度を向上し、組織の帯域幅の制約を軽減するには、次Exchange Online検討してください。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="6a4f9-108">**メールボックスのサイズを小さくする。**</span><span class="sxs-lookup"><span data-stu-id="6a4f9-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="6a4f9-109">メールボックスのサイズを小さくすると、移行速度が向上します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="6a4f9-110">**ハイブリッド展開でメールボックスの移動機能Exchange使用します。**</span><span class="sxs-lookup"><span data-stu-id="6a4f9-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="6a4f9-111">ハイブリッド展開Exchangeオフライン メール (.OST ファイル) に移行するときに再ダウンロードは必要Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="6a4f9-112">これにより、ダウンロード帯域幅の要件が大幅に削減されます。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="6a4f9-113">**インターネット トラフィックが低く、オンプレミスでの使用が少ない期間中にメールボックスの移動をExchangeします。**</span><span class="sxs-lookup"><span data-stu-id="6a4f9-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="6a4f9-114">移動をスケジュールする場合、移行要求はメールボックス レプリケーション プロキシに送信され、すぐには実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="6a4f9-115">**Web 上のユーザーにOutlookポップアウトを使用します。**</span><span class="sxs-lookup"><span data-stu-id="6a4f9-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="6a4f9-116">リーン ポップアウトは、Microsoft Edge または Internet Explorer で一部のコンポーネントをレンダリングすることにより、Microsoft Edge または Internet Explorer の特定の電子メール メッセージのメモリ負荷の小さいバージョンを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="6a4f9-117">詳細については、「無駄のないポップアウトを使用して、メール メッセージを読み取る際に [使用されるメモリを減らす」を参照してください](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="6a4f9-118">一般的なアドバイス</span><span class="sxs-lookup"><span data-stu-id="6a4f9-118">General advice</span></span>

- <span data-ttu-id="6a4f9-119">ユーザーの DNS 参照が、outlook.office.com の論理的なエントリの場所に MS データセンターを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="6a4f9-120">メールボックスキャッシュを調査し、適切なオプションを選択します (再.</span><span class="sxs-lookup"><span data-stu-id="6a4f9-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="6a4f9-121">キャッシュ期間、共有メールボックス キャッシュ、et cetera)。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="6a4f9-122">インターネットをOutlookする前に、VPN 接続を (中央オフィスに) 転送するデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="6a4f9-123">メールボックス データがフォルダー、およびアイテムの量に関する制限に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="6a4f9-124">移行パフォーマンスの詳細については、「Exchangeパフォーマンスとベスト プラクティスOffice 365[を参照してください](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
