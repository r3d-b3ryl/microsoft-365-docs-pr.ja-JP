---
title: 予定表を外部ユーザーと共有する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: ユーザーが会議や予定の予定表を外部ユーザーと共有する方法について学習します。
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760056"
---
# <a name="share-calendars-with-external-users"></a>予定表を外部ユーザーと共有する

ユーザーが組織外のユーザーとの会議をスケジュールする必要がある場合があります。 一般的な会議時間を見つけるプロセスを簡素化するために、Microsoft 365 を使用すると、これらのユーザーが予定表を使用できます。 これらは、組織内のユーザーの空き時間情報を表示する必要があるが、Microsoft 365 組織のユーザー アカウントを持っている必要があるユーザーです。

Microsoft 365 管理センターでは、組織内のすべてのユーザーに対して予定表の共有を有効にできます。 共有を有効にすると、ユーザーは Outlook Web App を使用して組織内外のユーザーと予定表を共有できます。 組織内のユーザーは、自分の予定表と一緒に共有の予定表を表示できます。 組織外のユーザーには、予定表の表示に使用できる URL が送信されます。 組織内のユーザーは、共有する時間と共有する量を決定します。

> [!NOTE]
> Exchange Server 2013 (オンプレミスのソリューション) を使用する組織と予定表を共有する場合は、Exchange 管理者がクラウドとの認証リレーションシップをセットアップする必要があります。 これはフェデレーションと呼ばれるので、ソフトウェアの最小要件を満たす必要があります。 詳細については、「[共有](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)」を参照してください。
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して予定表の共有を有効にする

1. 管理センターで、[設定組織の設定 **]** \> **に移動します**。

2. [サービス] **タブで** 、[予定表] を **選択します**。
  
3. [予定表 **] ページ** で、Microsoft 365 または Exchange を持つ組織外のユーザーと予定表を共有するかどうかを選択します。 匿名ユーザー (資格情報のないユーザー) が電子メールの招待状を介して予定表にアクセスできるかどうかを選択します。

4. ユーザーが利用できる予定表情報の種類を選択します。 すべての情報を許可するか、時間のみ、または時間、件名、場所にのみ制限できます。

## <a name="invite-people-to-access-calendars"></a>予定表にアクセスできるようにユーザーを招待する

共有を有効にすると、予定表の所有者は特定のユーザーに招待を拡張できます。 手順については、「[予定表を共有する](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)」を参照してください。