---
title: 高度な電子情報開示でユーザーとケースをセットアップする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '高度な電子情報開示でユーザーの役割を構成し、ケースを作成し、ユーザーをケースに割り当てる方法について説明します。  '
ms.openlocfilehash: 5c82ad8b630974d3afeb1928f8dd229ffb0dc36a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636071"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>上級電子情報開示でユーザーおよびケースをセットアップする (クラシック)

このトピックでは、上級電子情報開示 (クラシック) のユーザーとケースをセットアップする方法について説明します。
  
> [!IMPORTANT]
> 高度な電子情報開示の新バージョンへの投資を継続するうちに、microsoft は advanced ediscovery *(classic)* または*advanced ediscovery v 1.0*とも呼ばれる、高度な電子情報開示の廃止をアナウンスしています。 まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。 Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。 Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。 
  
## <a name="prerequisites"></a>前提条件

Advanced eDiscovery でケースとユーザーを設定する前に、次のものが必要です。
  
- Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office365 E5 ライセンスが割り当てられている必要があります。または、Office365 E1 または E3 ライセンスを持つユーザーに Advanced eDiscovery 単体のライセンスを割り当てることもできます。ケースに割り当てられ、Advanced eDiscovery を使用してデータを分析する管理者および法令遵守責任者には E5 ライセンスは不要です。 
    
- 電子情報開示ケースを作成してメンバーを追加するには、 &amp;セキュリティコンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 セキュリティ&amp; /コンプライアンスセンターの電子情報開示マネージャーの役割グループに自分を追加するには、組織の全体管理者である必要があります。 全体管理者ではない場合は、電子情報開示マネージャーの役割グループに追加するように全体管理者に依頼する必要があります。 詳細については、以下を参照してください。
    
  - [Microsoft 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](~/security/office-365-security/protect-against-threats.md)
    
  - [Microsoft 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>手順 1: ユーザーに電子情報開示のアクセス許可を割り当てる

最初の手順は、ユーザーが電子情報開示ケースのメンバー &amp;として追加できるように、セキュリティコンプライアンスセンターで必要なアクセス許可をユーザーに割り当てることです。 セキュリティ&amp; /コンプライアンスセンターでユーザーをケースのメンバーとして追加すると、上級電子情報開示のケースにアクセスできるようになります。
  
電子情報開示ケースのメンバーとして追加できるように、必要なアクセス許可をユーザーに割り当てるには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報開示のケース](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)」のステップ1を参照してください。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>手順 2: 電子情報開示ケースを作成し、メンバーを追加する

次の手順では、セキュリティ&amp;コンプライアンスセンターで新しい電子情報開示ケースを作成し、メンバーを追加します。 そのケースのメンバーは、高度な電子情報開示のケースにアクセスできるようになります。
  
1. 新しい電子情報開示ケースを作成するには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報](ediscovery-cases.md#step-2-create-a-new-case)開示のケース」のステップ2を参照してください。
    
2. 電子情報開示ケースにメンバーを追加するには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報開示ケース](ediscovery-cases.md#step-3-add-members-to-a-case)のステップ3」を参照してください。
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>手順 3: 高度な電子情報開示でケースを進める

電子情報開示ケースを作成してメンバーを追加すると、そのユーザー (またはケースのメンバー) は、高度な電子情報開示で対応するケースにアクセスできるようになります。 高度な電子情報開示のケースにアクセスするには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)開示のケース」の手順8を参照してください。
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[データの準備](prepare-data-for-advanced-ediscovery.md)
 
