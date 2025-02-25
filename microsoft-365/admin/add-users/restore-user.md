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
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: ユーザー アカウントを削除してから 30 日以内は、アカウントとすべてのデータを復元でき、ユーザーは同じアカウントでサインインできます。
ms.openlocfilehash: 2f9a28e5000c1ba826b5458916f30c3e8a438253
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65436209"
---
# <a name="restore-a-user-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでユーザーを復元する
   
ユーザー アカウントを削除してから 30 日以内に復元すると、そのアカウントと関連するすべてのデータが復元されます。ユーザーは同じ職場や学校のアカウントでサインインできます。ユーザーのメールボックスは完全に復元されます。特定のユーザー アカウントを復元できなくなるまでの残り時間を知るには、[サポートにお問い合わせください](../../business-video/get-help-support.md)。
  
いくつかのヒントをご紹介します。
  
- アカウントへの割り当てに利用可能なライセンスがあることを確認します。
    
- Active Directory を使用している場合、ユーザー アカウントを復元する手順については、「[Office 365 で削除済みのユーザー アカウントをトラブルシューティングする方法](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)」を参照してください。 
    
## <a name="restore-one-or-more-user-accounts"></a>1 つ以上のユーザー アカウントを復元する

これらの手順を実行するには、Microsoft 365 グローバル管理者またはユーザー管理の管理者である必要があります。 

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">削除済みのユーザー</a>] ページの順に移動します。

2. [**削除済みのユーザー**] ページで、復元するユーザーの名前を選び、[**ユーザーの復元**] を選びます。
    
3. 画面の指示に従ってパスワードを設定し、[**復元**] を選びます。
    
4. ユーザーの復元が正常に完了したら、[**メールを送信して閉じる**] を選択します。名前の競合またはプロキシ アドレスの競合が発生した場合は、これらのアカウントの復元方法については、以下の手順を参照してください。
    
ユーザーを復元した後は、パスワードが変更されたことをユーザーに通知し、ユーザーをフォローアップします。
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>ユーザー名が競合するユーザーを復元する

ユーザー アカウントを削除し、同じユーザー名で (同じユーザーの、または名前が似ている別のユーザーの) ユーザー アカウントを新しく作成した後、削除したアカウントを復元しようとすると、ユーザー名の競合が発生します。
  
この問題を修正するには、アクティブなユーザー アカウントを復元しているアカウントに置き換えます。または、復元しているアカウントに別のユーザー名を割り当てて、同じユーザー名で複数のアカウントが存在しないようにします。次のように行います。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">削除済みのユーザー</a>] ページの順に移動します。
  
2. [**削除済みのユーザー**] ページで、復元するユーザーの名前を選び、[**復元**] を選びます。
    
    > [!NOTE]
    > 2 人以上のユーザーの復元が失敗した場合、エラー メッセージで一部のユーザーの復元操作が失敗したことが示されます。ログを見て復元されなかったユーザーを確認し、失敗したアカウントを 1 つずつ復元します。 
  
3. 画面の指示に従ってパスワードを設定し、[**復元**] を選びます。
    
4. アカウントの復元に問題があったことを示すメッセージが表示されます。次のいずれかの操作を行います。
    
     - 復元をキャンセルし、現在のアクティブなユーザーの名前を変更します。もう一度復元を試みます。
    
     - または、ユーザー用に新規のプライマリ メール アドレスを入力して、[**復元**] を選びます。
    
5. 結果を確認し、[ **閉じる**] を選びます。
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>プロキシ アドレスが競合するユーザーを復元する

プロキシ アドレスを含むユーザー アカウントを削除し、同じプロキシ アドレスを別のアカウントに割り当てた後、削除したアカウントを復元しようとすると、プロキシ アドレスの競合が発生します。この問題を解決するには、次の手順に従ってください。
  
Microsoft 365 でこれを行うには、[管理者権限](about-admin-roles.md)が必要です。 

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">削除済みのユーザー</a>] ページの順に移動します。

2. [ **削除済みのユーザー**] ページで、復元するユーザーを選択して、[ **復元**] を選択します。 
    
3. [**復元**] ページで、指示に従ってパスワードを設定し、[**復元**] を選びます。 競合しているプロキシ アドレスは、復元したユーザーから自動的に削除されます。
    
4. 結果を確認し、[ **閉じる**] を選びます。

## <a name="related-content"></a>関連コンテンツ

[ユーザーを削除する](delete-a-user.md) (記事)\
[管理者の役割を割り当てる](assign-admin-roles.md) (ビデオ)\
[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md) (記事)
