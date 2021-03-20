---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 for Business アプリ保護設定がユーザーの Windows 10 デバイスに適用されたことを確認する方法について説明します。
ms.openlocfilehash: ff99b3a4fce49aebdb5c72f51e46678a7821e186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912416"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でデバイス保護設定を検証する

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 デバイス ポリシーが設定されていることを確認する

[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。 ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。 ユーザーは Windows Update を変更したり、Windows 10 デバイスWindows Defenderウイルス対策の設定を変更したりできないので、多くのオプションがグレー表示されます。
  
1. [設定更新 \> **プログラムの &amp; セキュリティ]** \> **[Windows Update** \> **Restart] オプションに移動** し、すべての設定が灰色で表示されているのを確認します。 
    
    ![[再起動] オプションはすべて灰色で表示されます。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. [設定の \> **更新] &amp; セキュリティ** \> **の [Windows Update** \> **Advanced] オプションに移動** し、すべての設定がグレー表示に設定されているのを確認します。 
    
    ![Windows Advanced 更新プログラムのオプションはすべて灰色で表示されます。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    一部の設定が非表示または組織によって管理され、すべてのオプションが灰色で表示されるというメッセージが赤で表示されるのを確認します。
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. すべてのオプションが灰色で表示されるのを確認します。 
    
    ![ウイルスと脅威の保護の設定は灰色で表示されます。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 for business のドキュメントとリソース](./index.yml)
  
[Microsoft 365 for business の使用を開始する](microsoft-365-business-overview.md)
  
[ビジネス向け Microsoft 365 の管理](manage.md)
  
[Windows 10 の PC のデバイス構成を設定する](protection-settings-for-windows-10-pcs.md)
