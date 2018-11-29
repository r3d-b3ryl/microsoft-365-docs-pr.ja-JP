---
title: Windows 10 PC でアプリの保護設定を検証する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 10 の Windows デバイスで Microsoft 365 のビジネス アプリケーションの保護設定を検証する方法について説明します。
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869166"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でデバイス保護設定を検証する

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 デバイス ポリシーが設定されていることを確認する

[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。ユーザーは自分の Windows 10 デバイス上で Windows Update および Windows Defender ウイルス対策の設定を変更することはできないため、このような多くのオプションは灰色表示されます。
  
1. **設定**に移動\>**更新&amp;セキュリティ** \> **Windows の更新プログラム** \> **オプションを再起動**し、すべての設定がグレーになっていることを確認します。 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. **設定**に移動\>**更新&amp;セキュリティ** \> **Windows 更新プログラム** \> **オプションの詳細設定**し、すべての設定が淡色表示にすることを確認します。 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. **設定**に\>**更新&amp;セキュリティ** \> **Windows の更新プログラム** \> **オプションを高度な** \> **更新プログラムの配布方法を選択してください**。
    
    一部の設定が組織によって非表示になっているか、管理されていますというメッセージ (赤色) が表示され、すべてのオプションが灰色表示されていることを確認します。
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. **設定**に移動し、Windows Defender のセキュリティ センターを開くには、 \> **更新&amp;セキュリティ** \> **Windows Defender** \> **Windows Defender のセキュリティ センターを開く**をクリックして\>**ウイルス&amp;スレッド保護** \> **ウイルス&amp;脅威の保護の設定**。 
    
5. すべてのオプションが灰色表示されていることを確認します。 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>関連トピック

[Microsoft 365 Business のドキュメントとリソース](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Microsoft 365 Business を使い始める](microsoft-365-business-overview.md)
  
[Microsoft 365 Business の管理](manage.md)
  
[Windows 10 の PC のデバイス構成を設定する](protection-settings-for-windows-10-pcs.md)
  

