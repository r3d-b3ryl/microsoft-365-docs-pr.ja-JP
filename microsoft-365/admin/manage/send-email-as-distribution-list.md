---
title: Office 365 で配布リストとしてメールを送信する
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Office 365 で配布リストとしてメールを送信する 方法の詳細をご確認ください。
ms.openlocfilehash: f165279cf6cfbedda4f122f453c2321c16f412d3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254852"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a>Office 365 で配布リストとしてメールを送信する

Office 365 では、ユーザーが配布リストとしてメールを送信できます。配布リストのメンバーであるユーザーが配布リストに送信されたメッセージに返信すると、メールは個別のユーザーからではなく、配布リストからであることが表示されます。このトピックでは、この操作を行う方法を示します。
  
## <a name="send-email-as-a-distribution-list"></a>配布リストとしてメールを送信する

これらの手順を実行する前に、Office 365 配布リストにが追加されており、それに対して送信者アクセス許可が付与されていることを確認してください。
  
 **管理者**: 「 [office 365 ユーザーまたは連絡先をリストに追加](../email/add-user-or-contact-to-distribution-list.md)し、[メンバーが office 365 グループのトピックとして電子メールを送信できるように](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)し、配布リストに正しいユーザーを追加することを許可する」の手順に従っていることを確認してください。
  
1. Outlook on the web を開き、受信トレイに移動します。 
    
2. 配布リストに送信されたメッセージを開きます。 
    
3. [**返信**] を選択します。 
    
4. メッセージの下部で、[**その他** \> **の表示元**] を選択します。<br/> ![[詳細] を選択し、[表示] を選択します。](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. `Ina@weewalter.me` -などの差出人のアドレスを右クリックして、[**削除**] を選択します。<br/> ![FROM エイリアスを削除する](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 次に、support@contoso.com などの配布リストを入力して、メッセージを送信します。 次回、配布リストから返信するときに、そのアドレスが [**差出人**] リストにオプションとして表示されます。<br/>![共有メールボックスのエイリアスが表示されます。](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)
  

