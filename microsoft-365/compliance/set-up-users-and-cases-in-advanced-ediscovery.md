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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6cfc8e313816c0c01512dd0d4b71f1dbbd6e6505
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819177"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>上級電子情報開示でユーザーおよびケースをセットアップする (クラシック)

このトピックでは、上級電子情報開示 (クラシック) のユーザーとケースをセットアップする方法について説明します。
  
> [!IMPORTANT]
> 新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。 まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。 Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。 Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。 
  
## <a name="requirements-to-set-up-users-and-cases"></a>ユーザーおよびケースをセットアップするための要件

Advanced eDiscovery でケースとユーザーを設定する前に、次のものが必要です。
  
- To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license. 
    
- &amp;電子情報開示ケースを作成してメンバーを追加するには、セキュリティコンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 セキュリティ/コンプライアンスセンターの電子情報開示マネージャーの役割グループに自分を追加するには &amp; 、組織の全体管理者である必要があります。 全体管理者ではない場合は、電子情報開示マネージャーの役割グループに追加するように全体管理者に依頼する必要があります。 詳細については、以下を参照してください。
    
  - [Microsoft 365 セキュリティコンプライアンスセンターのアクセス許可 &amp;](~/security/office-365-security/protect-against-threats.md)
    
  - [Microsoft 365 セキュリティコンプライアンスセンターで電子情報開示のアクセス許可を割り当てる &amp;](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>手順 1: ユーザーに電子情報開示のアクセス許可を割り当てる

最初の手順は、ユーザー &amp; が電子情報開示ケースのメンバーとして追加できるように、セキュリティコンプライアンスセンターで必要なアクセス許可をユーザーに割り当てることです。 セキュリティ/コンプライアンスセンターでユーザーをケースのメンバーとして追加すると、 &amp; 上級電子情報開示のケースにアクセスできるようになります。
  
電子情報開示ケースのメンバーとして追加できるように、必要なアクセス許可をユーザーに割り当てるには、 [Microsoft 365 セキュリティ &amp; コンプライアンスセンターの「電子情報開示のケース](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)」のステップ1を参照してください。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>手順 2: 電子情報開示ケースを作成し、メンバーを追加する

次の手順では、セキュリティ & コンプライアンスセンターで新しい電子情報開示ケースを作成し、メンバーを追加します。 そのケースのメンバーは、高度な電子情報開示のケースにアクセスできるようになります。
  
1. 新しい電子情報開示ケースを作成するには、「 [Core ediscovery の概要](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)」のステップ3を参照してください。

2. 電子情報開示ケースにメンバーを追加するには、「 [Core ediscovery の概要](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)」のステップ4を参照してください。

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>手順 3: 高度な電子情報開示でケースを進める

電子情報開示ケースを作成してメンバーを追加すると、そのユーザー (またはケースのメンバー) は、高度な電子情報開示で対応するケースにアクセスできるようになります。 上級電子情報開示のケースにアクセスするには、「 [Advanced ediscovery でのケース](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery)へのアクセス」を参照してください。
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[高度な電子情報開示のためのデータの準備 (クラシック)](prepare-data-for-advanced-ediscovery.md)
 