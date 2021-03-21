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
# <a name="monitor-microsoft-365-connectivity"></a>Microsoft 365 の接続を監視する

Microsoft 365 を展開したら、以下のツールと手法の一部を使用して Microsoft 365 接続を維持できます。 サービスの正常性と継続性に関[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)する公式ガイドラインと、低速ネットワークで Microsoft [365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)を使用するためのベスト プラクティスを理解する必要があります。 また[、Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)管理アプリを利用し[、Microsoft 365 for business のブックマークを作成する必要があります。](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Microsoft 365 Connectivity の監視

|||
|:-----|:-----|
|**新しい Microsoft 365 エンドポイントの通知を受け取る** <br/> |[Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)エンドポイントを管理している場合は、新しいエンドポイントを発行するときに通知を受け取る必要があります。お気に入りの RSS リーダーを使用して RSS フィードを購読できます。 Outlook を介して [購読する方法、または](https://go.microsoft.com/fwlink/p/?LinkId=532416) RSS フィードの更新プログラムを電子メール [で送信する方法を次に示します](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**システム センターを使用して Microsoft 365 を監視する** <br/> |Microsoft System Center を使用している場合は、System Center Management [Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) をダウンロードして、Microsoft 365 の今日の監視を開始できます。 詳細なガイダンスについては、「管理パックの運用ガイド」または「System Centre Operations Manager を使用した [Office365 監視」のブログを参照してください。](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Azure ExpressRoute の正常性の監視** <br/> |Azure ExpressRoute for Microsoft 365 を使用して Microsoft 365 に接続する場合は、Microsoft 365 サービス正常性ダッシュボードと Azure リソースの正常性に関するトラブルシューティング時間の短縮の両方を使用している必要[があります](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)。 <br/> |
|**AD FS を使って Azure AD Connect Health を使用する** <br/> |Microsoft 365 で AD FS for Single Sign-On を使用している場合は [、Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-adfs)の使用を開始して、AD FS インフラストラクチャを監視します。  <br/> |
|**Microsoft 365 をプログラムで監視する** <br/> |[Microsoft 365 管理 API に関するガイダンスを参照してください](/office/office-365-management-api/office-365-management-apis-overview)。  <br/> |

ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 Enterprise サービスとアプリケーションを構成する](configure-services-and-applications.md)
  
[Microsoft 365 Enterprise の組織の準備をする](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](network-planning-and-performance.md)
  
[Microsoft 365 とオンプレミス環境との統合](microsoft-365-integration.md)
  
[Microsoft 365 エンドポイントの管理](managing-office-365-endpoints.md)