---
title: グループの代理として送信または送信するメンバーを許可する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: グループ メンバーがグループとして電子メールを送信したり、Microsoft 365グループに代わって電子メールを送信Microsoft 365する方法についてMicrosoft 365します。
ms.openlocfilehash: c06f8aa82f0c112e448e607d7fbc75f13e7d3b6c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174197"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>グループの代理として送信または送信するメンバーを許可する

Send **as** または send onhalf permissions が付与されているMicrosoft 365 グループのメンバーは、グループとして、またはグループの代わりに電子メールを送信できます。 (グループ内のゲストにこれらのアクセス許可を付与することはできません)。

この記事では、グローバル管理者または管理者がExchangeアクセス許可を設定する方法について説明します。
  
たとえば、Megan Bowen が Training **Microsoft 365** グループの一部であり、グループに対するアクセス許可として送信を持つ場合、そのユーザーがグループとして電子メールを送信すると、トレーニング グループが電子メールを送信したのようになります。 
  
[**代理で送信] アクセス** 許可を使用すると、ユーザーはユーザーグループに代わって電子Microsoft 365できます。 たとえば、Alex Wilber がマーケティング Microsoft 365グループの一部であり、Send **on Behalf** アクセス許可を持ち、グループとして電子メールを送信する場合、電子メールは、マーケティングに代わって **Alex Wilber** によって送信されたように見えます。

> [!IMPORTANT]
> 指定したユーザー **に代わって** [送信] **または** [代理送信] を構成できますが、両方は構成できません。 両方を構成すると、既定で [として送信] **になります**。

> [!TIP]
> [グループから電子](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)メールを送信する方法については、「Microsoft 365 グループから電子メールを送信する」を参照してください。web 上で Outlook と Outlook を使用してグループから電子メールを送信する方法について説明します。
    
## <a name="allow-members-to-send-email-as-a-group"></a>メンバーがグループとして電子メールを送信するを許可する

このセクションでは、ユーザーがグループとして電子メールを送信する方法について、Exchange管理センター [](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) でExchange Online。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。
    
2. [グループ **の編集]** ![ アイコンを選択します。  ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ユーザーに送信を許可するグループに対して指定します。 
    
3. [ **グループ委任**] を選びます。
    
4. [Send **As] セクション** で、サインを選択して、送信 **+** するユーザーをグループとして追加します。 
    
    ![ダイアログ ボックスとして送信のスクリーンショット。](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. ユーザーを入力して検索するか、一覧からユーザーを選択します。 **[OK] と [** 保存]**を選択します**。
    
    ![ユーザーを入力して検索するか、一覧からユーザーを選択します。](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>メンバーがグループに代わって電子メールを送信するを許可する

このセクションでは、ユーザーが組織の管理センター (EAC) のグループに代わって電子メールを送信Exchangeする方法についてExchange Online。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a> で、[**受信者**]、[**グループ**] の順に移動します。
    
2. [グループ **の編集]** ![ アイコンを選択します。](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ユーザーに送信を許可するグループに対して指定します。 
    
3. [ **グループ委任**] を選びます。
    
4. [代理で送信] セクションで、署名を選択して、グループとして送信する **+** ユーザーを追加します。 
    
    ![ダイアログの代わりに送信のスクリーンショット。](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. ユーザーを入力して検索するか、一覧からユーザーを選択します。 **[OK] と [** 保存]**を選択します**。
    
    ![ユーザーを入力して検索するか、一覧からユーザーを選択します。](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>関連記事

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[グループの詳細Microsoft 365する](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)