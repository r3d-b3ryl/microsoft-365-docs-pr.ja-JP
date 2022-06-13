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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: ユーザーが組織内外のユーザーと予定表を共有できるように、Microsoft 365 管理センターで予定表共有を有効にします。
ms.openlocfilehash: b3ca1d4f2a6ef24a6958b4fe805ccf617c0984e7
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043146"
---
# <a name="share-microsoft-365-calendars-with-external-users"></a>外部ユーザーとMicrosoft 365予定表を共有する

ユーザーが組織外のユーザーとの会議をスケジュールすることが必要な場合があります。 一般的な会議の時間を見つけるプロセスを簡略化するために、Microsoft 365これらのユーザーが予定表を利用できるようにします。 これらは、組織内のユーザーの空き時間と繁忙時間を表示する必要があるが、Microsoft 365組織のユーザー アカウントを持っていないユーザーです。

組織内のすべてのユーザーの予定表共有をMicrosoft 365 管理センターで有効にすることができます。 共有を有効にすると、ユーザーはOutlook Web Appを使用して、組織内外のユーザーと予定表を共有できます。 組織内のユーザーは、自分の予定表と共に共有予定表を表示できます。 組織外のユーザーには、予定表の表示に使用できる URL が送信されます。 組織内のユーザーは、共有するタイミングと共有する量を決定します。

> [!NOTE]
> Exchange Server 2013 (オンプレミスのソリューション) を使用する組織と予定表を共有する場合は、Exchange 管理者がクラウドとの認証リレーションシップをセットアップする必要があります。 これはフェデレーションと呼ばれ、最小限のソフトウェア要件を満たす必要があります。 詳細については、「[共有](/exchange/sharing-exchange-2013-help)」を参照してください。
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Office 365 管理センターを使用して予定表の共有を有効にする

1. **グローバル管理者** として管理センターにサインインし、**組織の設定****設定**\>移動し、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**サービス**] タブで [</a>**予定表**] を選択します。
  
3. **[予定表**] ページで、Microsoft 365またはExchangeを持つ組織外のユーザーと予定表をユーザーが共有できるようにするかどうかを選択します。 匿名ユーザー (資格情報のないユーザー) に電子メール招待を使用して予定表へのアクセスを許可するかどうかを選択します。

4. ユーザーが利用できるようにする予定表の情報の種類を選択します。 すべての情報を許可することも、時間のみ、時間、件名、場所のみに制限することもできます。

## <a name="external-sharing-sync-interval"></a>外部共有同期間隔

テナントの外部で共有するためのインスタント同期は、現在サポートされていません。 これらの構成では共有できますが、同期は定期的に行われます。 テナント間共有には、次の 2 種類があります。

1. **別のMicrosoft 365 ユーザーにMicrosoft 365(外部共有が有効になっている場合)**:完全に共有された予定表が作成されますが、同期は約 3 時間ごとに行われます。 この設定では、最終的にインスタント同期が有効になります。

2. **Outlook.com ユーザーに** Microsoft 365: 外部共有が無効になっている場合は、別のMicrosoft 365 ユーザーへの共有もこのグループに分類されます。 ICS URL は共有時に生成され、受信者は任意の予定表サービスに追加するために使用できます。 ICS サブスクリプションでは、受信者の予定表サービスは、ICS サブスクリプションを同期して新しい更新プログラムを受け取るタイミングを選択します。 受信者がOutlook.com またはMicrosoft 365 ユーザーの場合、同期は約 3 時間ごとに行われます。

## <a name="invite-people-to-access-calendars"></a>予定表にアクセスできるようにユーザーを招待する

共有が有効になると、予定表の所有者は特定のユーザーに招待を拡張できます。

1. [Web でOutlookを](https://outlook.office365.com)開きます。

2. ページの上部にあるアプリ起動ツールを選択し、[予定表] を選択 **します**。 既定では、プライマリ 予定表は "予定表" と呼ばれます。 他の予定表を作成した場合は、代わりに共有する予定表のいずれかを選択できます。 他のユーザーが所有する予定表を共有することはできません。

3. 予定表を共有する相手の名前またはメール アドレスを [ **電子メールで共有招待を送信** する] ボックスに入力します。

4. このユーザーに表示する情報の量を選択します。

     - **[自分がビジー状態を表示できる** ] では、ユーザーがいつビジー状態かを確認できますが、イベントの場所などの詳細は含まれません。

     - **タイトルと場所を表示できます** 。ユーザーは、イベントのタイトルと場所だけでなく、忙しいときも確認できます。

     - **すべての詳細を表示できます** 。ユーザーはイベントのすべての詳細を表示できます。

     - **編集可能な** ユーザーは、イベントのすべての詳細を表示し、予定表を編集できます (組織内のユーザーと共有する場合にのみ使用できます)。

5. **共有** を選択します。 

## <a name="related-content"></a>関連コンテンツ

[サイトの外部共有を有効または無効にする](/sharepoint/change-external-sharing-site) (記事)\
[Microsoft 365 管理センターの概要](../admin-overview/admin-center-overview.md) (ビデオ)\
[メールと予定表の管理](/admin) (リンク ページ)

