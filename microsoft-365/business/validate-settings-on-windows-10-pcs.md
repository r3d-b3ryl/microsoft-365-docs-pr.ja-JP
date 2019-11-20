---
title: Windows 10 PC でアプリの保護設定を検証する
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 デバイスで Microsoft 365 Business app protection の設定を検証する方法について説明します。
ms.openlocfilehash: b8793ab7f77bbc7f608f237e2455f6fd12c3bb26
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721802"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でデバイス保護設定を検証する

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 デバイス ポリシーが設定されていることを確認する

[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。 ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。 ユーザーは Windows 10 デバイスで windows Update および Windows Defender ウイルス対策の設定を変更できないため、多くのオプションが灰色表示されます。
  
1. [**設定**\>**更新&amp;セキュリティ** **** \> **** Windows update の再起動オプション] に移動し、すべての設定が淡色表示になっていることを確認します。 \> 
    
    ![すべての再起動オプションが淡色表示されます。](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. [**設定** \> ] [ ** &amp;セキュリティ** \> **Windows update** \>セキュリティ **] [詳細オプション]** の順に移動し、すべての設定が淡色表示になっていることを確認します。 
    
    ![Windows Advanced updates のオプションはすべて淡色表示になっています。](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    一部の設定が非表示になっているか、組織によって管理されており、すべてのオプションが灰色表示されていることを確認してください (赤)。
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. すべてのオプションが淡色表示になっていることを確認します。 
    
    ![ウイルスおよび脅威の保護の設定は灰色表示されています。](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 Business のドキュメントとリソース](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 Business を使い始める](microsoft-365-business-overview.md)
  
[Microsoft 365 Business の管理](manage.md)
  
[Windows 10 の PC のデバイス構成を設定する](protection-settings-for-windows-10-pcs.md)
  

