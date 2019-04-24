---
title: '手順 4: URL と IP アドレスの変更を計画する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291326"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="5f4be-102">手順 4: URL と IP アドレスの変更を計画する</span><span class="sxs-lookup"><span data-stu-id="5f4be-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="5f4be-103">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="5f4be-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="5f4be-p101">この手順を実行するには[手順 3](networking-configure-proxies-firewalls.md) を実行している必要があります。手順 3 を実行していない場合は、[手順 5](networking-optimize-tcp-performance.md) に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="5f4be-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="5f4be-p102">Microsoft 365 グローバル ネットワークで使用される URL と IP アドレスは、時間の経過とともに変化します。このため、これらのエンドポイントの更新を計画することが重要です。たとえば、次の情報を使用してセキュリティ境界デバイスを再構成することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f4be-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="5f4be-108">制限のない処理を必要とする新しいサービスの新しい URL</span><span class="sxs-lookup"><span data-stu-id="5f4be-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="5f4be-109">廃止となったサービスの削除済み URL</span><span class="sxs-lookup"><span data-stu-id="5f4be-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="5f4be-110">インターネット上の新しい Microsoft ネットワークの場所とサーバーの新しい IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="5f4be-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="5f4be-111">各種サービスの IP アドレス範囲の変更</span><span class="sxs-lookup"><span data-stu-id="5f4be-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="5f4be-112">エンドポイントの変更の実装計画 (変更の通知を含む) の策定に関する詳細については、「[Office 365 エンドポイントを管理する - 統合](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration)」および「[Office 365 エンドポイントを管理する - プロキシ](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f4be-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="5f4be-113">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step4)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5f4be-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5f4be-114">次の手順</span><span class="sxs-lookup"><span data-stu-id="5f4be-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="5f4be-115">クライアントと Office 365 サービスのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="5f4be-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
