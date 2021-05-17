---
title: Microsoft 365 の接続を監視する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: この記事では、ネットワーク接続の監視と維持に使用できるツールとMicrosoft 365します。
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920778"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="2ffb7-103">Microsoft 365 の接続を監視する</span><span class="sxs-lookup"><span data-stu-id="2ffb7-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="2ffb7-104">サーバーを展開したらMicrosoft 365、以下のツールMicrosoft 365を使用して、接続を維持できます。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="2ffb7-105">サービス正常性と継続性に関する[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)公式ガイドラインと、低速ネットワークでサービス を使用するためのベスト プラクティスMicrosoft 365[理解する必要があります](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="2ffb7-106">また、管理者アプリを使ってMicrosoft 365[し、Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)[ヘルプをブックマーク](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="2ffb7-107">監視Microsoft 365接続</span><span class="sxs-lookup"><span data-stu-id="2ffb7-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2ffb7-108">**新しいエンドポイントの通知Microsoft 365する**</span><span class="sxs-lookup"><span data-stu-id="2ffb7-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="2ffb7-109">[Microsoft 365 エンドポイント[](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)を管理している場合は、新しいエンドポイントを発行するときに通知を受信する必要があります。お気に入りの RSS リーダーを使用して RSS フィードを購読できます。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="2ffb7-110">以下に、RSS フィード[の更新](https://go.microsoft.com/fwlink/p/?LinkId=532416)Outlookメールで送信する方法[を示します](https://go.microsoft.com/fwlink/p/?LinkId=532417)。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="2ffb7-111">**[監視System Centerを使用Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="2ffb7-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="2ffb7-112">Microsoft System Centerを使用している場合は、System Center管理パックをダウンロード[して](https://www.microsoft.com/download/details.aspx?id=43708)、Office 365をMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="2ffb7-113">詳細なガイダンスについては、「管理パックの運用ガイド」または「System Centre Operations Manager を使用した [Office365 監視」のブログを参照してください。](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ffb7-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="2ffb7-114">**Azure ExpressRoute の正常性の監視**</span><span class="sxs-lookup"><span data-stu-id="2ffb7-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="2ffb7-115">Microsoft 365 用の Azure ExpressRoute を使用して Microsoft 365 に接続する場合は、Microsoft 365 サービス正常性ダッシュボードと Azure Resource 正常性のトラブルシューティング時間の短縮の両方を使用している必要[があります](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="2ffb7-116">**AD FS を使って Azure AD Connect Health を使用する**</span><span class="sxs-lookup"><span data-stu-id="2ffb7-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="2ffb7-117">AD FS for Single Sign-On を Microsoft 365 で使用している場合は[、Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-adfs)を使用して FS インフラストラクチャをADする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="2ffb7-118">**プログラムを使用してMicrosoft 365**</span><span class="sxs-lookup"><span data-stu-id="2ffb7-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="2ffb7-119">管理 API に関するガイダンス[Microsoft 365参照してください](/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="2ffb7-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="2ffb7-120">ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="2ffb7-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2ffb7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ffb7-121">Related topics</span></span>

[<span data-ttu-id="2ffb7-122">サービスMicrosoft 365 Enterpriseアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="2ffb7-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="2ffb7-123">組織の準備を整Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2ffb7-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="2ffb7-124">Microsoft 365 のネットワーク計画とパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="2ffb7-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="2ffb7-125">Microsoft 365環境との統合</span><span class="sxs-lookup"><span data-stu-id="2ffb7-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="2ffb7-126">エンドポイントMicrosoft 365管理</span><span class="sxs-lookup"><span data-stu-id="2ffb7-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)