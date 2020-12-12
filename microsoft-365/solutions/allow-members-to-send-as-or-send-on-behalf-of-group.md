---
title: メンバーがグループとして送信またはグループの代わりに送信を許可する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: メンバーが Microsoft 365 グループとしてメールを送信したり、Microsoft 365 グループの代わりにメールを送信したりする方法について説明します。
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663585"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>メンバーがグループとして送信またはグループの代わりに送信を許可する

[送信者] または [代理送信] アクセス許可が付与されているMicrosoft 365 グループのメンバーは、グループとして、またはグループの代理として電子メールを送信できます。 この記事では、グローバル管理者または Exchange 管理者がこれらのアクセス許可を設定する方法について説明します。
  
たとえば、Megan Bowen が **Training** Microsoft 365 グループの一部であり、グループに対する送信アクセス許可を持つ場合、そのユーザーがグループとしてメールを送信すると、そのメールを送信したトレーニング グループのようになります。 
  
[ **代理送信] アクセス** 許可を使用すると、ユーザーは Microsoft 365 グループの代わりにメールを送信できます。 たとえば、Alex Wilber が **Marketing** Microsoft 365 グループの一部であり、代理送信のアクセス許可を持ち、グループとしてメールを送信する場合、電子メールはマーケティングの代わりに **Alex Wilber** によって送信されたように見えます。

> [!IMPORTANT]
> 指定したユーザー **の [ユーザーとして送信]** または [ **代理** 送信] を構成できますが、両方を構成することはできません。 両方を構成する場合は、既定で [次のように **送信] が設定されます**。

> [!TIP]
> Outlook と Outlook on the Web を使用してグループからメールを送信する方法については [、「Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) グループからメールを送信する」または「Microsoft 365 グループの代理でメールを送信する」を参照してください。
    
## <a name="allow-members-to-send-email-as-a-group"></a>メンバーがグループとしてメールを送信する

このセクションでは、ユーザーが Exchange Online の [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) 管理センター (EAC) でグループとしてメールを送信する方法について説明します。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。
    
2. ユーザー **に送信** を許可するグループの [グループの編集] ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) アイコンを選択します。   
    
3. [ **グループ委任**] を選びます。
    
4. [送信 **者] セクション** で、署名を選択して、グループとして送信 **+** するユーザーを追加します。 
    
    ![[送信] ダイアログ ボックスのスクリーンショット](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. ユーザーを入力して検索するか、一覧からユーザーを選択します。 **[OK] を選択** し、[保存 **] を選択します**。
    
    ![一覧からユーザーを検索または選択する入力](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>グループの代わりにメンバーが電子メールを送信できる

このセクションでは、ユーザーが Exchange Online の Exchange 管理センター (EAC) でグループの代理として電子メールを送信する方法について説明します。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。
    
2. ユーザー **に送信** を許可するグループの [グループの編集] ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) アイコンを選択します。 
    
3. [ **グループ委任**] を選びます。
    
4. [代理送信] セクションで、署名を選択して、グループとして送信 **+** するユーザーを追加します。 
    
    ![[代理送信] ダイアログのスクリーンショット](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. ユーザーを入力して検索するか、一覧からユーザーを選択します。 **[OK] を選択** し、[保存 **] を選択します**。
    
    ![一覧からユーザーを検索または選択する入力](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>関連記事

[グループコラボレーション ガバナンスの計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[Microsoft 365 グループの詳細](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
