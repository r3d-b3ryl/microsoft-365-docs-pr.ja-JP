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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'PowerShell Exchangeを使用して、組織内のすべてのユーザーまたは特定のユーザーのクラッター機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: 5037e7cb6518ca90f3d12c183fcff3c838c29907
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165089"
---
# <a name="configure-clutter-for-your-organization"></a>組織での低優先メールの構成

> [!TIP]
> [優先受信トレイ](../setup/configure-focused-inbox.md) が低優先メールに置き換わります。 詳細情報: [優先受信トレイとクラッターのプランに関する更新](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
管理者は、Microsoft 365でクラッター機能を管理する必要がある場合があります。 組織内のユーザーのクラッター機能をオン/オフにするには、powerShell Exchange使用する必要があります。 (個人は、次の手順を使用してオン/オフにできます。[[Outlookでクラッターをオフ/オンにする]](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) を選択します。
  
PowerShell の使用の詳細については、「[PowerShell と powerShell のExchange Online](/powershell/exchange/exchange-online-powershell)と[Connectを使用して PowerShell をExchange Online](/powershell/exchange/connect-to-exchange-online-powershell)する」Exchange参照してください。 少なくともExchangeサービス管理者ロールを持ち、PowerShell を使用してExchange Onlineに接続できるアカウントが必要です。 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Exchange PowerShell を使用して低優先メール機能を有効にする

[Set-Clutter](/powershell/module/exchange/set-clutter) コマンドレットを実行することで、メールボックスの低優先メールを手動で有効にできます。組織のメールボックスの低優先メール設定を表示することもできます。 [Get-Clutter](/powershell/module/exchange/get-clutter) コマンドレットを実行します。 
  
アリー ベリューという名前のユーザーの低優先メールをオンにする
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Exchange PowerShell を使用して低優先メールをオフにする

[Set-Clutter](/powershell/module/exchange/set-clutter) コマンドレットを実行することで、メールボックスの低優先メールを手動で無効にできます。組織のメールボックスの **低優先メール** 設定を表示することもできます。[Get-Clutter](/powershell/module/exchange/get-clutter) コマンドレットを実行します。 
  
アリー ベリューという名前のユーザーの低優先メールをオフにする
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

PowerShell を使用してユーザーを一括作成する場合、各ユーザーのメールボックスに [Set-Clutter](/powershell/module/exchange/set-clutter) を実行し、低優先メールを管理する必要があります。 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>低優先メールのオン/オフ スイッチはどのような場合に、Outlook on the web のユーザーに表示されますか?
<a name="bkmk_onoff"> </a>

管理者は、PowerShell を使用してクラッター Exchange再度有効にすることができます。 この操作が行われると、優先受信トレイは無効になり、低優先メールが再び有効になります。 
  
 **Microsoft 365 Business Premium サブスクリプションでOutlook on the webを使用している場合:**
  
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
    
## <a name="related-content"></a>関連コンテンツ

[クラッターを使用して、優先度の低いメッセージをOutlook (article)\ で並べ替える](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
[低優先度メッセージを OWA で並べ替えるには、クラッターを使用](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) します (記事)\
[Outlookで [クラッター] をオフにする](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (記事)
