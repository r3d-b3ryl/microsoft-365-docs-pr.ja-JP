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
description: この記事では、Microsoft 365 接続を監視および保守するために使用できるツールと手法について説明します。
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920778"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="38b0c-103">Microsoft 365 の接続を監視する</span><span class="sxs-lookup"><span data-stu-id="38b0c-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="38b0c-104">Microsoft 365 を展開したら、以下のツールと手法の一部を使用して Microsoft 365 接続を維持できます。</span><span class="sxs-lookup"><span data-stu-id="38b0c-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="38b0c-105">サービスの正常性と継続性に関[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)する公式ガイドラインと、低速ネットワークで Microsoft [365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)を使用するためのベスト プラクティスを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b0c-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="38b0c-106">また[、Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)管理アプリを利用し[、Microsoft 365 for business のブックマークを作成する必要があります。](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="38b0c-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="38b0c-107">Microsoft 365 Connectivity の監視</span><span class="sxs-lookup"><span data-stu-id="38b0c-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="38b0c-108">**新しい Microsoft 365 エンドポイントの通知を受け取る**</span><span class="sxs-lookup"><span data-stu-id="38b0c-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="38b0c-109">[Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)エンドポイントを管理している場合は、新しいエンドポイントを発行するときに通知を受け取る必要があります。お気に入りの RSS リーダーを使用して RSS フィードを購読できます。</span><span class="sxs-lookup"><span data-stu-id="38b0c-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="38b0c-110">Outlook を介して [購読する方法、または](https://go.microsoft.com/fwlink/p/?LinkId=532416) RSS フィードの更新プログラムを電子メール [で送信する方法を次に示します](https://go.microsoft.com/fwlink/p/?LinkId=532417)。</span><span class="sxs-lookup"><span data-stu-id="38b0c-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="38b0c-111">**システム センターを使用して Microsoft 365 を監視する**</span><span class="sxs-lookup"><span data-stu-id="38b0c-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="38b0c-112">Microsoft System Center を使用している場合は、System Center Management [Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) をダウンロードして、Microsoft 365 の今日の監視を開始できます。</span><span class="sxs-lookup"><span data-stu-id="38b0c-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="38b0c-113">詳細なガイダンスについては、「管理パックの運用ガイド」または「System Centre Operations Manager を使用した [Office365 監視」のブログを参照してください。](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="38b0c-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="38b0c-114">**Azure ExpressRoute の正常性の監視**</span><span class="sxs-lookup"><span data-stu-id="38b0c-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="38b0c-115">Azure ExpressRoute for Microsoft 365 を使用して Microsoft 365 に接続する場合は、Microsoft 365 サービス正常性ダッシュボードと Azure リソースの正常性に関するトラブルシューティング時間の短縮の両方を使用している必要[があります](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)。</span><span class="sxs-lookup"><span data-stu-id="38b0c-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="38b0c-116">**AD FS を使って Azure AD Connect Health を使用する**</span><span class="sxs-lookup"><span data-stu-id="38b0c-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="38b0c-117">Microsoft 365 で AD FS for Single Sign-On を使用している場合は [、Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-adfs)の使用を開始して、AD FS インフラストラクチャを監視します。</span><span class="sxs-lookup"><span data-stu-id="38b0c-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="38b0c-118">**Microsoft 365 をプログラムで監視する**</span><span class="sxs-lookup"><span data-stu-id="38b0c-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="38b0c-119">[Microsoft 365 管理 API に関するガイダンスを参照してください](/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="38b0c-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="38b0c-120">ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="38b0c-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="38b0c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="38b0c-121">Related topics</span></span>

[<span data-ttu-id="38b0c-122">Microsoft 365 Enterprise サービスとアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="38b0c-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="38b0c-123">Microsoft 365 Enterprise の組織の準備をする</span><span class="sxs-lookup"><span data-stu-id="38b0c-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="38b0c-124">Microsoft 365 のネットワーク計画とパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="38b0c-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="38b0c-125">Microsoft 365 とオンプレミス環境との統合</span><span class="sxs-lookup"><span data-stu-id="38b0c-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="38b0c-126">Microsoft 365 エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="38b0c-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)