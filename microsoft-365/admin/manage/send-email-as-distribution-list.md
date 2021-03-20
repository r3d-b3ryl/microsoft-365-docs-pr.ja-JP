---
title: 配布リストとして電子メールを送信する
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
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Microsoft 365 で配布リストとして電子メールを送信する方法について説明します。
ms.openlocfilehash: 379f2471fd38da5098bf8f2ca82f4f76ee82bd8e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915160"
---
# <a name="send-email-as-a-distribution-list"></a>配布リストとして電子メールを送信する

Microsoft 365 では、電子メールを配布リストとして送信できます。 配布リストのメンバーであるユーザーが配布リストに送信されたメッセージに返信すると、メールは個別のユーザーからではなく、配布リストからであることが表示されます。 このトピックでは、この操作を行う方法を示します。
  
## <a name="send-email-as-a-distribution-list"></a>配布リストとして電子メールを送信する

これらの手順を実行する前に、Microsoft 365 配布リストに追加され、そのリストに対するアクセス許可として送信が許可されている必要があります。
  
 **管理者**: [「Microsoft 365](../email/add-user-or-contact-to-distribution-list.md) ユーザーまたは連絡先をリストに追加する」および「メンバーが [Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) グループ トピックとしてメールを送信できる」の手順に従い、配布リストに正しいユーザーを追加していることを確認します。
  
1. Outlook on the web を開き、受信トレイに移動します。 
    
2. 配布リストに送信されたメッセージを開きます。 
    
3. [返信 **] を選択します**。 
    
4. メッセージの下部で、[より多くの表示] **を** \> **選択します**。<br/> ![[詳細] を選択し、[Show From] を選択します。](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. From アドレス (など) を右クリックし、[ `Ina@weewalter.me` 削除] を **選択します**。<br/> ![FROM エイリアスを削除する](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 次に、support@contoso.com などの配布リストを入力して、メッセージを送信します。 次に配布リストから返信すると、そのアドレスが [From] リストにオプションとして **表示** されます。<br/>![共有メールボックスのエイリアスが表示される](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)
