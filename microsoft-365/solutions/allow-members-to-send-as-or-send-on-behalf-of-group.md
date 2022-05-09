---
title: メンバーがグループの代理として送信または送信できるようにする
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
description: グループ メンバーがMicrosoft 365 グループとして電子メールを送信したり、Microsoft 365 グループに代わって電子メールを送信したりできるようにする方法について説明します。
ms.openlocfilehash: 588008669359629f5b59498bb7dbf776112d5408
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63401008"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>メンバーがグループの代理として送信または送信できるようにする

代理で **送信または送信** のアクセス許可が付与されているMicrosoft 365 グループのメンバー **は**、グループとして、またはグループの代理として電子メールを送信できます。 (グループ内のゲストにこれらのアクセス許可を付与することはできません。

この記事では、グローバル管理者またはExchange管理者がこれらのアクセス許可を設定する方法について説明します。
  
たとえば、Megan Bowen が **トレーニング** Microsoft 365 グループの一部であり、グループに対する [**送信]** アクセス許可を持っている場合、グループとしてメールを送信すると、**トレーニング** グループがメールを送信したように見えます。 
  
**[代理送信]** アクセス許可を使用すると、ユーザーはMicrosoft 365 グループに代わって電子メールを送信できます。 たとえば、Alex Wilber が **Marketing** Microsoft 365 グループの一部であり、**代理で送信** アクセス許可を持ち、グループとして電子メールを送信する場合、電子メールは **Marketing に代わって Alex Wilber** によって送信されたように見えます。

> [!IMPORTANT]
> 特定のユーザー **に代わって送信****または** 送信を構成できますが、両方を構成することはできません。 両方を構成する場合、既定では **[送信者]** になります。

> [!NOTE]
> ハイブリッド Exchange構成のOutlook for Macでは、代理で **送信** および **送信** はサポートされません。
    
## <a name="allow-members-to-send-email-as-a-group"></a>メンバーがグループとして電子メールを送信できるようにする

このセクションでは、Exchange Onlineの<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター (EAC)</a> でユーザーがグループとして電子メールを送信できるようにする方法について説明します。
  
1. Exchange管理センターで、[**受信者グループ]** \> に移動 <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**します**</a>。
    
2. ユーザーの送信を許可するグループを選択します。 
    
3. **[設定** > **代理人の管理編集]** を選択します。
    
4. [ **代理人の追加] セクションで** 、 **Send as** Access を使用するユーザーのメール アドレスを入力します。
  
5. ドロップダウンから [**送信]** として [**アクセス許可の種類**] を選択します。

6.  **[変更の保存]** を選択します。
    
    
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>メンバーがグループに代わって電子メールを送信できるようにする

このセクションでは、ユーザーがExchange Onlineの<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター (EAC)</a> でグループに代わって電子メールを送信できるようにする方法について説明します。
  
1. Exchange管理センターで、[**受信者グループ]** \> に移動 <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**します**</a>。
    
2. ユーザーが代理で送信できるようにするグループを選択します。 
    
3. **[設定** > **代理人の管理編集]** を選択します。
    
4. [ **代理人の追加] セクションで** 、 **Send as** Access を使用するユーザーのメール アドレスを入力します。
  
5. ドロップダウンから [**アクセス許可の種類****] を [代理送信**] として選択します。

6.  **[変更の保存]** を選択します。

## <a name="related-articles"></a>関連記事

[Microsoft 365 グループとの間または代理でメールを送信する](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[Microsoft 365 グループの詳細を確認する](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)
