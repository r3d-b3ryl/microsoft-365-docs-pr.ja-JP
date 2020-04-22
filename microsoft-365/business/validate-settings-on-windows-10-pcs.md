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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 for business アプリの保護設定がユーザーの Windows 10 デバイスで有効になっていることを確認する方法について説明します。
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635706"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でデバイス保護設定を検証する

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 デバイス ポリシーが設定されていることを確認する

[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。 ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。 ユーザーは Windows 10 デバイスで windows Update および Windows Defender ウイルス対策の設定を変更できないため、多くのオプションが灰色表示されます。
  
1. [**設定**\>**更新&amp;セキュリティ** **Windows Update** \> **Restart options** Windows update の再起動オプション] に移動し、すべての設定が淡色表示になっていることを確認します。 \> 
    
    ![すべての再起動オプションが淡色表示されます。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. [**設定** \> ] [ ** &amp;セキュリティ** \> **Windows update** \>セキュリティ **] [詳細オプション]** の順に移動し、すべての設定が淡色表示になっていることを確認します。 
    
    ![Windows Advanced updates のオプションはすべて淡色表示になっています。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    一部の設定が非表示になっているか、組織によって管理されており、すべてのオプションが灰色表示されていることを確認してください (赤)。
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. すべてのオプションが淡色表示になっていることを確認します。 
    
    ![ウイルスおよび脅威の保護の設定は灰色表示されています。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 for business のドキュメントとリソース](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 for business の使用を開始する](microsoft-365-business-overview.md)
  
[Microsoft 365 for business の管理](manage.md)
  
[Windows 10 の PC のデバイス構成を設定する](protection-settings-for-windows-10-pcs.md)
  

