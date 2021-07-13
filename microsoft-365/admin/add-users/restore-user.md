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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: ユーザー アカウントを削除した後 30 日以内に、アカウントとすべてのデータを復元し、ユーザーは同じアカウントでサインインできます。
ms.openlocfilehash: e37f913bcc6a54bdcc1e0f52168fe1aab0c8afdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394269"
---
# <a name="restore-a-user"></a>ユーザーを復元する
   
ユーザー アカウントを削除してから 30 日以内に復元すると、そのアカウントと関連するすべてのデータが復元されます。ユーザーは同じ職場や学校のアカウントでサインインできます。ユーザーのメールボックスは完全に復元されます。特定のユーザー アカウントを復元できなくなるまでの残り時間を知るには、[サポートにお問い合わせください](../../business-video/get-help-support.md)。
  
いくつかのヒントをご紹介します。
  
- アカウントに割り当て可能なライセンスを確認します。
    
- ビジネスで Active Directory を使用している場合、ユーザー アカウントの復元に関するインストルトションについては、「How to troubleshoot deleted user account in Office 365 」[を参照してください](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)。 
    
## <a name="restore-one-or-more-user-accounts"></a>1 つ以上のユーザー アカウントを復元する

これらの手順を実行するにはMicrosoft 365管理者またはユーザー管理管理者である必要があります。 

1. 管理センターで、[ユーザーの削除済 **み** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">ユーザー] ページに移動</a> します。

2. [削除 **されたユーザー] ページ** で、復元するユーザーの名前を選択し、[復元] を **選択します**。
    
3. プロンプトに従ってパスワードを設定し、[復元] を **選択します**。
    
4. ユーザーが正常に復元された場合は、[電子メールを送信して **閉じる] を選択します**。 名前の競合またはプロキシ アドレスの競合が発生した場合は、これらのアカウントの復元方法については、以下の手順を参照してください。
    
ユーザーを復元した後で、パスワードが変更されたと通知し、そのユーザーをフォローアップしてください。
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>ユーザー名が競合するユーザーを復元する

ユーザー アカウントを削除し、同じユーザー名で (同じユーザーの、または名前が似ている別のユーザーの) ユーザー アカウントを新しく作成した後、削除したアカウントを復元しようとすると、ユーザー名の競合が発生します。
  
この問題を修正するには、アクティブなユーザー アカウントを復元しているアカウントに置き換えます。または、復元しているアカウントに別のユーザー名を割り当てて、同じユーザー名で複数のアカウントが存在しないようにします。次のように行います。

1. 管理センターで、[ユーザーの削除済 **み** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">ユーザー] ページに移動</a> します。
  
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
  
この操作を行[うには、Microsoft 365](about-admin-roles.md)アクセス許可が必要です。 

1. 管理センターで、[ユーザーの削除済 **み** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">ユーザー] ページに移動</a> します。

2. [ **削除済みのユーザー**] ページで、復元するユーザーを選択して、[ **復元**] を選択します。 
    
3. [復元] **ページで** 、指示に従ってパスワードを設定し、[復元] を **選択します**。 競合しているプロキシ アドレスは、復元したユーザーから自動的に削除されます。
    
4. 結果を確認し、[ **閉じる**] を選びます。

## <a name="related-content"></a>関連コンテンツ

[ユーザーを削除](delete-a-user.md) する (記事)\
[管理者ロールの割り当](assign-admin-roles.md) て (ビデオ)\
[ユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md) (記事)
