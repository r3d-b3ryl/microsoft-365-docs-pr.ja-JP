---
title: '手順 4: トラフィック バイパスを構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Office 365 が稼働している信頼できる場所にトラフィックをバイパスするのに必要となる Web ブラウザーとエッジ デバイスについて理解し、構成します。
ms.openlocfilehash: 8486b5c0da9e44ed0b9ee42feb7acbfd21445010
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291590"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="1f30b-103">手順 4: トラフィック バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="1f30b-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="1f30b-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="1f30b-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="1f30b-p101">一般的なインターネット トラフィックにはリスクがあるため、組織のネットワークでは、通常、プロキシ サーバー、SSL 中断/検査、パケット検査デバイス、およびデータ損失防止システムのようなエッジ デバイスを使用して、セキュリティを適用します。ネットワーク傍受デバイスに関する問題については、「Office 365 トラフィックにサードパーティのネットワーク デバイスまたはソリューションを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="1f30b-p102">ただし、Microsoft 365 のクラウドベース サービスで使用する DNS ドメイン名と IP アドレスはよく知られている上に、トラフィックとサービスは多くのセキュリティ機能で保護されています。この種のセキュリティと保護は既に適用されているので、エッジ デバイスで同じことを行う必要はありません。Microsoft 365 のトラフィックが、中間地点や重複するセキュリティ処理を経由する設定では、パフォーマンスが大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="1f30b-p103">中間地点や重複するセキュリティ処理を排除する最初の手順として、Microsoft 365 のトラフィックを識別します。Microsoft では、次の種類の DNS ドメイン名と IP アドレス範囲 (エンドポイントと呼ばれる) を定義しています。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="1f30b-113">**最適化**: すべての Office 365 サービスへの接続に必須で、Microsoft 365 の帯域幅、接続、データ量の 75% 以上に相当します。</span><span class="sxs-lookup"><span data-stu-id="1f30b-113">Optimize - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span> <span data-ttu-id="1f30b-114">これらのエンドポイントは、ネットワーク パフォーマンス、待機時間、可用性の影響を最も受けやすい Microsoft 365 シナリオに該当します。</span><span class="sxs-lookup"><span data-stu-id="1f30b-114">Optimize - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="1f30b-115">**許可**: 特定の Microsoft 365 サービスや機能への接続に必須ですが、ネットワーク パフォーマンスや待機時間の影響は、最適化カテゴリのエンドポイントほど大きくありません。</span><span class="sxs-lookup"><span data-stu-id="1f30b-115">Allow - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="1f30b-116">**既定**: 最適化を必要としない Microsoft 365 サービスや依存関係を表します。</span><span class="sxs-lookup"><span data-stu-id="1f30b-116">Default - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span> <span data-ttu-id="1f30b-117">標準カテゴリのエンドポイントは、通常のインターネット トラフィックとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f30b-117">Default - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="1f30b-118">DNS ドメイン名と IP アドレスの範囲については、「[https://aka.ms/o365endpoints](https://aka.ms/o365endpoints)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f30b-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="1f30b-119">Microsoft では、次の方法を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="1f30b-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="1f30b-p106">オンプレミスで使用するコンピューターのインターネット ブラウザー上で、プロキシ自動構成 (PAC) スクリプトを使用して、Microsoft 365 クラウドベース サービスの DNS ドメイン名用プロキシ サーバーをバイパスします。最新の Microsoft 365 PAC スクリプトについては、「Get-Pacfile PowerShell スクリプト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- <span data-ttu-id="1f30b-p107">エッジ デバイスを分析して重複する処理を特定したら、それらのエッジ デバイスが "最適化" および "許可" エンドポイントにトラフィックを処理せずに転送するように構成します。これは、トラフィック バイパスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="1f30b-p108">エッジ デバイスには、ファイアウォール、SSL 中断/検査、パケット検査デバイス、およびデータ損失防止システムが含まれます。エッジ デバイスの構成と更新には、スクリプトや REST 呼び出しを使用して、Office 365 エンドポイント Web サービスから構造化されたエンドポイントのリストを使用できます。詳細については、「[Office 365 IP アドレスと URL の Web サービス](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="1f30b-p109">なお、バイパスするのは、Microsoft 365 で "最適化" および "許可" カテゴリに含まれるエンドポイントに対するトラフィックのための通常のプロキシとネットワーク セキュリティ処理のみです。他のすべての一般的なインターネット トラフィックは、プロキシ処理され、既存のネットワーク セキュリティ処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="1f30b-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="1f30b-129">中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step4)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f30b-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1f30b-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="1f30b-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="1f30b-131">クライアントと Office 365 サービスのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="1f30b-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



