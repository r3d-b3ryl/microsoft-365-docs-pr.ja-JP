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
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: グループ メンバーがグループとして電子メールを送信したり、Microsoft 365グループに代わって電子メールを送信したりするMicrosoft 365します。
ms.openlocfilehash: 588008669359629f5b59498bb7dbf776112d5408
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63401008"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>グループの代理として送信または送信するメンバーを許可する

Send **as** または send onhalf permissions が付与されている Microsoft 365 グループのメンバーは、グループとして、またはグループの代理として電子メールを送信できます。 (グループ内のゲストにこれらのアクセス許可を付与することはできません)。

この記事では、グローバル管理者または管理者がExchangeアクセス許可を設定する方法について説明します。
  
たとえば、Megan Bowen が **トレーニング Microsoft 365 グループ** の一部であり、グループに対するアクセス許可として送信を持つ場合、グループとして電子メールを送信すると、トレーニング グループが電子メールを送信したのようになります。 
  
[**代理で送信] アクセス** 許可を使用すると、ユーザーはユーザーグループに代わって電子Microsoft 365できます。 たとえば、**Alex Wilber** がマーケティング Microsoft 365 グループの一部であり、[代理で送信] アクセス許可を持ち、グループとして電子メールを送信する場合、電子メールは、マーケティングに代わって **Alex Wilber** によって送信されたように見えます。

> [!IMPORTANT]
> 指定したユーザー **に代わって** [送信] **または [** 代理送信] を構成できますが、両方は構成できません。 両方を構成すると、既定で [送信] **に設定されます**。

> [!NOTE]
> **送信および****代理送信** は、ハイブリッド 構成Outlook for MacではExchangeされません。
    
## <a name="allow-members-to-send-email-as-a-group"></a>メンバーがグループとして電子メールを送信するを許可する

このセクションでは、ユーザーがグループとして電子メールを送信する方法について、Exchange 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">(EAC)</a> でExchange Online。
  
1. 管理センター Exchange[受信者グループ **] に移動** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**します**</a>。
    
2. ユーザーに送信を許可するグループを選択します。 
    
3. [代理人 **設定** > **編集] を選択します**。
    
4. [代理人 **の追加] セクション** で、アクセスとして送信するユーザーの電子メール アドレス **を入力** します。
  
5. ドロップダウン **から [Send** **as] として** [アクセス許可の種類] を選択します。

6.  **[変更の保存]** を選択します。
    
    
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>メンバーがグループに代わって電子メールを送信するを許可する

このセクションでは、ユーザーがグループの代わりに、Exchange 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">(EAC)</a> で電子メールを送信Exchange Online。
  
1. 管理センター Exchange[受信者グループ **] に移動** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**します**</a>。
    
2. ユーザーに代わって送信を許可するグループを選択します。 
    
3. [代理人 **設定** > **編集] を選択します**。
    
4. [代理人 **の追加] セクション** で、アクセスとして送信するユーザーの電子メール アドレス **を入力** します。
  
5. ドロップダウン **から [代理****送信] として [** アクセス許可の種類] を選択します。

6.  **[変更の保存]** を選択します。

## <a name="related-articles"></a>関連記事

[グループからまたはグループに代わって電子メールをMicrosoft 365する](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[グループの詳細Microsoft 365する](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)
