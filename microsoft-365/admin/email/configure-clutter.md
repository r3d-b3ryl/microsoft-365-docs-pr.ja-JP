---
title: 組織での低優先メールの構成
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Exchange PowerShell を使用して、組織内のすべてまたは特定のユーザーの低優先メール機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: 67267b0865dfcfd6c0ba66d59ce1d0d111d59325
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780279"
---
# <a name="configure-clutter-for-your-organization"></a>組織での低優先メールの構成

> [!TIP]
> [優先受信トレイ](../setup/configure-focused-inbox.md) が低優先メールに置き換わります。 詳細については[、「優先受信トレイに関する更新」および「低優先メール](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)機能」を参照してください。
  
管理者は、Microsoft 365 の低優先メール機能を管理する必要がある場合があります。 組織内のユーザーに低優先メール機能を有効/無効にするには、Exchange PowerShell を使用する必要があります。 (次の手順を使用して、この機能をオン/オフにすることができます。 [Outlook のオフ/低優先メール機能](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c))。
  
Exchange PowerShell の使用の詳細については、 [「Powershell を使用](https://go.microsoft.com/fwlink/?LinkID=402831)して exchange online と Exchange [Online powershell に接続する](https://go.microsoft.com/fwlink/?LinkID=722415)」をご覧ください。 少なくとも Exchange サービス管理者の役割を持ち、PowerShell を使用して Exchange Online に接続できるアカウントを持っている必要があります。 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Exchange PowerShell を使用して低優先メール機能を有効にする

[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) コマンドレットを実行することで、メールボックスの低優先メールを手動で有効にできます。組織のメールボックスの低優先メール設定を表示することもできます。 [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) コマンドレットを実行します。 
  
アリー ベリューという名前のユーザーの低優先メールをオンにする
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Exchange PowerShell を使用して低優先メールをオフにする

[Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) コマンドレットを実行することで、メールボックスの低優先メールを手動で無効にできます。組織のメールボックスの **低優先メール**設定を表示することもできます。[Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) コマンドレットを実行します。 
  
アリー ベリューという名前のユーザーの低優先メールをオフにする
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

PowerShell を使用してユーザーを一括作成する場合、各ユーザーのメールボックスに [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) を実行し、低優先メールを管理する必要があります。 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>低優先メールのオン/オフ スイッチはどのような場合に、Outlook on the web のユーザーに表示されますか?
<a name="bkmk_onoff"> </a>

管理者は、Exchange PowerShell を使用して低優先メール機能を再度有効にすることができます。 この操作が行われると、優先受信トレイは無効になり、低優先メールが再び有効になります。 
  
 **Microsoft 365 Business Premium サブスクリプションを使用して web 上の Outlook を使用している場合:**
  
- ユーザーの低優先メールが現在有効になっている場合: 
    
  - 低優先メールの設定は表示されます。
    
- ユーザーの優先受信トレイが現在有効になっている場合: 
    
  - 低優先メールの設定は表示されません。
    
- 低優先メールも優先受信トレイも有効になっていない場合: 
    
  - ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。
    
 **Outlook.com を使用している場合:**
  
- ユーザーの低優先メールが現在有効になっている場合: 
    
  - 低優先メールの設定は表示されます。
    
- ユーザーの優先受信トレイが現在有効になっている場合: 
    
  - 低優先メールの設定は表示されません。
    
- 低優先メールも優先受信トレイも有効になっていない場合: 
    
  - ユーザーの [メールの設定] にオプションとして低優先メールと優先受信トレイの両方が表示されます。
    
- ユーザーが過去のある時点で優先受信トレイを有効にした場合:
    
  - 低優先メールの設定は表示されません。
    
    それ以外の場合: 
    
  - 低優先メールの設定は表示されます。
    
## <a name="related-articles"></a>関連記事
<a name="bkmk_onoff"> </a>

[Outlook で低優先メール機能を使って優先度の低いメッセージを並べ替える](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[低優先メール機能を使用して OWA で優先度の低いメッセージを並べ替える](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Outlook の低優先メール機能をオフにする](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
    

