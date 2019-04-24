---
title: '手順 5: クライアントと Office 365 サービスのパフォーマンスを最適化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パフォーマンス向上のために TCP 設定と Office 365 サービスを構成します。
ms.openlocfilehash: cf172bcaa87b7c69d33d349d18c449efff30a1d9
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290884"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="5c147-103">手順 5: クライアントと Office 365 サービスのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="5c147-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="5c147-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="5c147-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="5c147-105">クライアント デバイスと Office 365 の間での伝送制御プロトコル (TCP) の動作を細かく調整することで、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="5c147-105">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="5c147-106">クライアント デバイスでは、TCP パフォーマンスを最適化するため次の TCP 設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5c147-106">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="5c147-107">[TCP ウィンドウ スケーリング](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/): 受信確認が必要となるまでに、クライアント デバイスがより多くのデータを送信できます</span><span class="sxs-lookup"><span data-stu-id="5c147-107">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="5c147-108">[TCP アイドル時間](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/): クライアント デバイスがオープン接続をより効率的に処理できます</span><span class="sxs-lookup"><span data-stu-id="5c147-108">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="5c147-109">[TCP 最大セグメント サイズ](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/): クライアント デバイスが 1 つのパケットで最大データ ブロックを送信できます</span><span class="sxs-lookup"><span data-stu-id="5c147-109">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="5c147-110">[TCP 選択的確認応答](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/): クライアント デバイスが、受信データの確認応答をより効率的に実行できます</span><span class="sxs-lookup"><span data-stu-id="5c147-110">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="5c147-111">Office 365 サービスの場合は、パフォーマンスの最適化については次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c147-111">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="5c147-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5c147-112">Exchange Online</span></span>](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [<span data-ttu-id="5c147-113">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5c147-113">Skype for Business Online</span></span>](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [<span data-ttu-id="5c147-114">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5c147-114">SharePoint Online</span></span>](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [<span data-ttu-id="5c147-115">Project Online</span><span class="sxs-lookup"><span data-stu-id="5c147-115">Project Online</span></span>](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

<span data-ttu-id="5c147-116">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step5)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c147-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c147-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="5c147-117">Next step</span></span>

[<span data-ttu-id="5c147-118">ネットワーク インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="5c147-118">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
