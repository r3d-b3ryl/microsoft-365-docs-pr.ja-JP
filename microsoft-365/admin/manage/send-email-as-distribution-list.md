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
ms.localizationpriority: medium
ms.collection:
- Adm_O365
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Microsoft 365の配布リストとして電子メールを送信し、メンバーがメッセージに返信したときに、配布リストから送信されているように見えるようにします。
ms.openlocfilehash: dd6e1f906481fe1c04bfa7cd275bd108ab558d59
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65468462"
---
# <a name="send-microsoft-365-email-as-a-distribution-list"></a>Microsoft 365電子メールを配布リストとして送信する

Microsoft 365では、配布リストとして電子メールを送信できます。 配布リストのメンバーであるユーザーが配布リストに送信されたメッセージに返信すると、メールは個別のユーザーからではなく、配布リストからであることが表示されます。 このトピックでは、この操作を行う方法を示します。
  
## <a name="before-you-begin"></a>はじめに

これらの手順を実行する前に、Microsoft 365配布リストに追加され、その配布リストに対するアクセス許可として送信が付与されていることを確認します。
  
 **管理者**: [Microsoft 365 ユーザーまたは連絡先をリストに追加](../email/add-user-or-contact-to-distribution-list.md)するおよびメンバーにMicrosoft 365 [グループとして電子メールを送信することを許可する](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)トピックの手順に従っていることを確認し、配布リストに正しいユーザーを追加します。
  
## <a name="outlook-on-the-web"></a>Outlook on the web

1. Outlook on the web を開き、受信トレイに移動します。 
    
2. 配布リストに送信されたメッセージを開きます。 
    
3. [ **返信] を選択します**。 
    
4. メッセージの下部にある [**その他**\>の **表示** 元] を選択します。<br/> ![[その他] を選択し、[表示元] を選択します。](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)
  
5. [差出人] アドレス `Ina@weewalter.me` を右クリックし、[削除] を選択 **します**。<br/> ![Remove the FROM alias.](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)
  
6. 次に、support@contoso.com などの配布リストを入力して、メッセージを送信します。 配布リストから次回返信すると、そのアドレスが **[差** 出人] リストのオプションとして表示されます。<br/>![共有メールボックスのエイリアスが表示されます。](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)

## <a name="outlook"></a>Outlook

1. デスクトップ クライアントOutlook開きます。

2. 新しいメールを作成します。 [ **差出人** ] フィールドをクリックし、[ **その他のメール アドレス**] を選択します。 [From] フィールドが表示されない場合は、[ **オプション]** に移動し、[フィールドの表示] セクションで **[元** ] を選択します。

3. グローバル アドレス **一覧から配布リスト** のアドレスを選択します。

4. メールを送信します。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 管理センターでセキュリティ グループを作成、編集、または削除する](../email/create-edit-or-delete-a-security-group.md) (記事)\
[電子メール コラボレーション](../email/email-collaboration.md) (記事)\
[配布グループにユーザーまたは連絡先を追加する](../email/add-user-or-contact-to-distribution-list.md) (記事)