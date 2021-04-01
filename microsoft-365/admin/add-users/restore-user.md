---
title: ユーザーを復元する
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
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 削除されたユーザー アカウントと関連付けられているすべてのデータを復元する方法について学習します。
ms.openlocfilehash: 75e664c68dec13b857e4bd308d49e5b58d5edfc8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471015"
---
# <a name="restore-a-user"></a>ユーザーを復元する
   
ユーザー アカウントを削除してから 30 日以内に復元すると、そのアカウントと関連するすべてのデータが復元されます。ユーザーは同じ職場や学校のアカウントでサインインできます。ユーザーのメールボックスは完全に復元されます。特定のユーザー アカウントを復元できなくなるまでの残り時間を知るには、[サポートにお問い合わせください](../contact-support-for-business-products.md)。
  
いくつかのヒントをご紹介します。
  
- アカウントに割り当て可能なライセンスを確認します。
    
- Active Directory を使用している場合、ユーザー アカウントを復元する手順については、「[Office 365、Azure、Intune で削除済みのユーザー アカウントをトラブルシューティングする方法](https://support.microsoft.com/kb/2619308)」を参照してください。 
    
## <a name="restore-one-or-more-user-accounts"></a>1 つ以上のユーザー アカウントを復元する

これらの手順を実行するには、Microsoft 365 のグローバル管理者またはユーザー管理管理者である必要があります。 
  
 
::: moniker range="o365-worldwide"

1. 管理センターで、[ユーザーの削除済 **み** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">ユーザー] ページに移動</a> します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターに移動 [し、[](https://go.microsoft.com/fwlink/p/?linkid=848041)ユーザーの削除済 **みユーザー]** \> **を選択します**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターに移動 [し、[](https://go.microsoft.com/fwlink/p/?linkid=850627)ユーザーの削除済 **みユーザー]** \> **を選択します**。

::: moniker-end

2. [削除 **されたユーザー] ページ** で、復元するユーザーの名前を選択し、[復元] を **選択します**。
    
 
3. プロンプトに従ってパスワードを設定し、[復元] を **選択します**。
    
4. ユーザーが正常に復元された場合は、[電子メールを送信して **閉じる] を選択します**。 名前の競合またはプロキシ アドレスの競合が発生した場合は、これらのアカウントの復元方法については、以下の手順を参照してください。
    
ユーザーを復元した後で、パスワードが変更されたと通知し、そのユーザーをフォローアップしてください。
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>ユーザー名が競合するユーザーを復元する
<a name="RestoreUserNameConflict"> </a>

ユーザー アカウントを削除し、同じユーザー名で (同じユーザーの、または名前が似ている別のユーザーの) ユーザー アカウントを新しく作成した後、削除したアカウントを復元しようとすると、ユーザー名の競合が発生します。
  
この問題を修正するには、アクティブなユーザー アカウントを復元しているアカウントに置き換えます。または、復元しているアカウントに別のユーザー名を割り当てて、同じユーザー名で複数のアカウントが存在しないようにします。次のように行います。
  

::: moniker range="o365-worldwide"

1. 管理センターで、[ユーザーの削除済 **み** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">ユーザー] ページに移動</a> します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターに移動 [し、[](https://go.microsoft.com/fwlink/p/?linkid=848041)ユーザーの削除済 **みユーザー]** \> **を選択します**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターに移動 [し、[](https://go.microsoft.com/fwlink/p/?linkid=850627)ユーザーの削除済 **みユーザー]** \> **を選択します**。

::: moniker-end

  
2. [削除 **されたユーザー] ページ** で、復元するユーザーの名前を選択し、[復元] を **選択します**。
    
    > [!NOTE]
    > 2 人以上のユーザーの復元が失敗した場合、エラー メッセージで一部のユーザーの復元操作が失敗したことが示されます。ログを見て復元されなかったユーザーを確認し、失敗したアカウントを 1 つずつ復元します。 
  
3. プロンプトに従ってパスワードを設定し、[復元] を **選択します**。
    
4. アカウントの復元に問題があったことを示すメッセージが表示されます。次のいずれかの操作を行います。
    
  - 復元をキャンセルし、現在のアクティブなユーザーの名前を変更します。もう一度復元を試みます。
    
  - または、ユーザーの新しいプライマリ メール アドレスを入力し、[復元] を **選択します**。
    
5. 結果を確認し、[ **閉じる**] を選びます。
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>プロキシ アドレスが競合するユーザーを復元する

プロキシ アドレスを含むユーザー アカウントを削除し、同じプロキシ アドレスを別のアカウントに割り当てた後、削除したアカウントを復元しようとすると、プロキシ アドレスの競合が発生します。この問題を解決するには、次の手順に従ってください。
  
これを行うには [、Microsoft](about-admin-roles.md) 365 の管理者権限が必要です。 
  

::: moniker range="o365-worldwide"

1. 管理センターで、[ユーザーの削除済 **み** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">ユーザー] ページに移動</a> します。

::: moniker-end

::: moniker range="o365-germany"

管理センターに移動 [し、[](https://go.microsoft.com/fwlink/p/?linkid=848041)ユーザーの削除済 **みユーザー]** \> **を選択します**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターに移動 [し、[](https://go.microsoft.com/fwlink/p/?linkid=850627)ユーザーの削除済 **みユーザー]** \> **を選択します**。

::: moniker-end

2. [ **削除済みのユーザー**] ページで、復元するユーザーを選択して、[ **復元**] を選択します。 
    
3. [復元] **ページで** 、指示に従ってパスワードを設定し、[復元] を **選択します**。 競合しているプロキシ アドレスは、復元したユーザーから自動的に削除されます。
    
4. 結果を確認し、[ **閉じる**] を選びます。

## <a name="related-articles"></a>関連記事

[ユーザーの削除](delete-a-user.md)
