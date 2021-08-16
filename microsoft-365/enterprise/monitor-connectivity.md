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
ms.openlocfilehash: 5013ef1129e230ea9a3cd31e5a75dbf367c4e5c01c63b37768e7f73098bcfacc
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899201"
---
# <a name="monitor-microsoft-365-connectivity"></a>Microsoft 365 の接続を監視する

サーバーを展開したらMicrosoft 365、以下のツールMicrosoft 365を使用して、接続を維持できます。 サービス正常性と継続性に関する[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)公式ガイドラインと、低速ネットワークでサービス を使用するためのベスト プラクティスMicrosoft 365[理解する必要があります](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。 また、管理者アプリを使ってMicrosoft 365[し、Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)[ヘルプをブックマーク](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)することもできます。
  
## <a name="monitoring-microsoft-365-connectivity"></a>監視Microsoft 365接続

|監視の種類 |Description |
|:-----|:-----|
|**新しいエンドポイントの通知Microsoft 365する** <br/> |[Microsoft 365 エンドポイント[](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)を管理している場合は、新しいエンドポイントを発行するときに通知を受信する必要があります。お気に入りの RSS リーダーを使用して RSS フィードを購読できます。 以下に、RSS フィード[の更新](https://go.microsoft.com/fwlink/p/?LinkId=532416)Outlookメールで送信する方法[を示します](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**[監視System Centerを使用Microsoft 365** <br/> |Microsoft System Centerを使用している場合は、System Center管理パックをダウンロード[して](https://www.microsoft.com/download/details.aspx?id=43708)、Office 365をMicrosoft 365できます。 詳細なガイダンスについては、管理パックの運用ガイドを参照してください。 <br/> |
|**Azure ExpressRoute の正常性の監視** <br/> |Microsoft 365 用の Azure ExpressRoute を使用して Microsoft 365 に接続する場合は、Microsoft 365 サービス正常性ダッシュボードと Azure Resource 正常性のトラブルシューティング時間の短縮の両方を使用している必要[があります](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)。 <br/> |
|**AD FS を使って Azure AD Connect Health を使用する** <br/> |AD FS for Single Sign-On を Microsoft 365 で使用している場合は[、Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-adfs)を使用して FS インフラストラクチャをADする必要があります。  <br/> |
|**プログラムを使用してMicrosoft 365** <br/> |管理 API に関するガイダンス[Microsoft 365参照してください](/office/office-365-management-api/office-365-management-apis-overview)。  <br/> |

ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>関連トピック

[サービスMicrosoft 365 Enterpriseアプリケーションを構成する](configure-services-and-applications.md)
  
[組織の準備を整Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](network-planning-and-performance.md)
  
[Microsoft 365環境との統合](microsoft-365-integration.md)
  
[エンドポイントMicrosoft 365管理](managing-office-365-endpoints.md)
