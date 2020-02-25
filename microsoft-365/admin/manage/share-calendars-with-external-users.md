---
title: 予定表を外部ユーザーと共有する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'ユーザーが会議や予定の外部ユーザーと予定表を共有する方法について説明します。 '
ms.openlocfilehash: 42bce53c3963c41684644d02dab18210f9ed828a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254829"
---
# <a name="share-calendars-with-external-users"></a>予定表を外部ユーザーと共有する

多くの場合、組織外のユーザーとの会議をスケジュールする必要があります。 互いに合意できる会議時間を見つけるプロセスを簡単にするために、Office 365 では "外部ユーザー" が予定表を表示できるようにすることができます。この外部ユーザーとは、空き時間情報を確認する必要があるが、Office 365 環境のユーザー アカウントを持っていないユーザーのことです。
  
予定表の共有はグローバル設定なので、管理者がテナント内のすべてのユーザーに対して有効にすることができます。 共有が有効になると、ユーザーは Outlook Web App を使用して、組織内または組織外のユーザーと予定表を共有できます。 組織内のユーザーは、自分とは別に、共有の予定表を並べて表示することができます。 組織外のユーザーには、予定表の表示に使用できる URL が送信されます。 ユーザーは、いつ共有するか、どの程度共有するか、どのような場合に自分の予定表を非公開にするかを決定します。
  
> [!NOTE]
> Exchange Server 2013 (オンプレミスのソリューション) を使用する組織と予定表を共有する場合は、Exchange 管理者がクラウドとの認証リレーションシップをセットアップする必要があります。これは "フェデレーション" と呼ばれるもので、ソフトウェアの最小要件を満たす必要があります。詳細については、「[共有](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)」を参照してください。 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して予定表の共有を有効にする

1. 管理センターで、 [**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービスとアドイン</a>] ページの順に移動します。 
    
  
2. [**サービス&amp;アドイン**] ページで、[**予定表**] を選択します。
  
3. 開いた [**予定表**] ページで、Office 365 または Exchange を使用している組織外のユーザーと予定表を共有するかどうかを選択します。
    
4. 匿名ユーザー (ログオン資格情報を持たないユーザー) が電子メール招待状を使用して予定表にアクセスできるようにするかどうかを選択します。

5. ユーザーが利用できるようにする予定表の情報の種類を選択します。 すべての情報を許可することも、時間、件名、場所のみに制限することもできます。

    
## <a name="invite-people-to-access-calendars"></a>予定表にアクセスできるようにユーザーを招待する

テナントで共有が有効になると、予定表の所有者は特定のユーザーを招待できます。手順については、「[予定表を共有する](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx)」を参照してください。 
  

