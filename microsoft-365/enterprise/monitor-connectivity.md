---
title: Microsoft 365 の接続を監視する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事では、Microsoft 365接続を監視および維持するために使用できるツールと手法について説明します。
ms.openlocfilehash: 0e7c18a10dc851596af6a652fb80c9c72852ee0d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093309"
---
# <a name="monitor-microsoft-365-connectivity"></a>Microsoft 365 の接続を監視する

Microsoft 365をデプロイしたら、以下のいくつかのツールと手法を使用して、Microsoft 365接続を維持できます。 サービス[の正常性と継続性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)に関する公式ガイドラインと、[低速ネットワークでMicrosoft 365を使用するためのベスト プラクティス](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)を理解する必要があります。 また、[Microsoft 365管理者アプリ](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)を取得し、[ビジネス向けのMicrosoft 365をブックマークすることもできます - 管理者ヘルプ](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)。
  
## <a name="monitoring-microsoft-365-connectivity"></a>Microsoft 365接続の監視

|監視の種類 |説明 |
|:-----|:-----|
|**新しいMicrosoft 365 エンドポイントの通知を受け取る** <br/> |[Microsoft 365 エンドポイントを管理している](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)場合は、新しいエンドポイントを発行するときに通知を受け取りたい場合は、お気に入りの RSS リーダーを使用して RSS フィードをサブスクライブできます。 [ここでは、Outlook経由でサブスクライブ](https://go.microsoft.com/fwlink/p/?LinkId=532416)する方法を示します。[RSS フィードの更新プログラムをメールで送信することもできます](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**System Centerを使用してMicrosoft 365を監視する** <br/> |Microsoft System Centerを使用している場合は、[Microsoft 365用の Microsoft System Center Operations Manager 管理パック](https://www.microsoft.com/download/details.aspx?id=103379)をダウンロードして、現在Microsoft 365監視を開始できます。 詳細なガイダンスについては、管理パック操作ガイドを参照してください。 <br/> |
|**Azure ExpressRoute の正常性の監視** <br/> |azure ExpressRoute for Microsoft 365を使用してMicrosoft 365に接続する場合は、Microsoft 365 Service Health ダッシュボードと Azure [Resource Health でのトラブルシューティング時間の短縮](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)の両方を使用していることを確認する必要があります。 <br/> |
|**AD FS を使って Azure AD Connect Health を使用する** <br/> |Microsoft 365で AD FS for Single Sign-Onを使用している場合は、[Azure AD Connect Health を使用して AD FS インフラストラクチャを監視する必要があります](/azure/active-directory/hybrid/how-to-connect-health-adfs)。  <br/> |
|**プログラムによってMicrosoft 365を監視する** <br/> |[Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview) に関するガイダンスを参照してください。  <br/> |

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 Enterpriseサービスとアプリケーションを構成する](configure-services-and-applications.md)
  
[組織でMicrosoft 365 Enterpriseの準備を整える](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](network-planning-and-performance.md)
  
[オンプレミス環境とのMicrosoft 365統合](microsoft-365-integration.md)
  
[Microsoft 365 エンドポイントの管理](managing-office-365-endpoints.md)
