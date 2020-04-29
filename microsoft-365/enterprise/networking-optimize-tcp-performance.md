---
title: '手順 5: クライアントと Microsoft 365 サービスのパフォーマンスを最適化する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パフォーマンス向上のために TCP 設定と Microsoft 365 サービスを構成します。
ms.openlocfilehash: 2db35f67ff19998b8a70742ec8fa24cb8d517c5d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631467"
---
# <a name="step-5-optimize-client-and-microsoft-365-service-performance"></a><span data-ttu-id="2b3b5-103">手順 5: クライアントと Microsoft 365 サービスのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="2b3b5-103">Step 5: Optimize client and Microsoft 365 service performance</span></span>

<span data-ttu-id="2b3b5-104">*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="2b3b5-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 1 - ネットワーキング](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="2b3b5-106">クライアント デバイスと Microsoft 365 サービスとの間の伝送制御プロトコル (TCP) の動作を細かく調整することで、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="2b3b5-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Microsoft 365 services.</span></span>

<span data-ttu-id="2b3b5-107">クライアント デバイスでは、TCP パフォーマンスを最適化するため次の TCP 設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b3b5-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="2b3b5-108">[TCP ウィンドウ スケーリング](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/): 受信確認が必要となるまでに、クライアント デバイスがより多くのデータを送信できます</span><span class="sxs-lookup"><span data-stu-id="2b3b5-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="2b3b5-109">[TCP アイドル時間](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/): クライアント デバイスがオープン接続をより効率的に処理できます</span><span class="sxs-lookup"><span data-stu-id="2b3b5-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="2b3b5-110">[TCP 最大セグメント サイズ](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/): クライアント デバイスが 1 つのパケットで最大データ ブロックを送信できます</span><span class="sxs-lookup"><span data-stu-id="2b3b5-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="2b3b5-111">[TCP 選択的確認応答](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/): クライアント デバイスが、受信データの確認応答をより効率的に実行できます</span><span class="sxs-lookup"><span data-stu-id="2b3b5-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="2b3b5-112">Microsoft 365 サービスの場合は、パフォーマンスの最適化については次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b3b5-112">For Microsoft 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="2b3b5-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b3b5-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="2b3b5-114">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2b3b5-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="2b3b5-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b3b5-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="2b3b5-116">Project Online の Project Web App</span><span class="sxs-lookup"><span data-stu-id="2b3b5-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="2b3b5-117">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step5)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2b3b5-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b3b5-118">次の手順</span><span class="sxs-lookup"><span data-stu-id="2b3b5-118">Next step</span></span>

[<span data-ttu-id="2b3b5-119">ネットワーク インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="2b3b5-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
