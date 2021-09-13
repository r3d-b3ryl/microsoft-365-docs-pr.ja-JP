---
title: Pc のアプリ保護設定をWindows 10する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: ビジネス アプリ保護の設定Microsoft 365ユーザーのデバイスに適用されたことを確認するWindows 10します。
ms.openlocfilehash: 67608c2c4b8396bced350685f439cb15f6378e6a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176639"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>PC のデバイス保護設定Windows 10する

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 デバイス ポリシーが設定されていることを確認する

[デバイス ポリシーを設定](protection-settings-for-windows-10-pcs.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。 ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。 ユーザーは Windows 10 デバイスの Windows Update と Windows Defender ウイルス対策 の設定を変更できないので、多くのオプションがグレー表示されます。
  
1. [セキュリティの **更新設定** 更新Windows]オプションに移動し、すべての設定が \> **&amp;** \>  \> 灰色で表示されているのを確認します。 
    
    ![[再起動] オプションはすべて灰色で表示されます。](../../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. [セキュリティの **設定** 更新Windows]オプションに移動し、すべての設定が灰色 \> **&amp;** \>  \> で表示されているのを確認します。 
    
    ![Windows詳細な更新プログラムのオプションはすべて灰色で表示されます。](../../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    一部の設定が非表示または組織によって管理され、すべてのオプションが灰色で表示されるというメッセージが赤で表示されるのを確認します。
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. すべてのオプションが灰色で表示されるのを確認します。 
    
    ![ウイルスと脅威の保護の設定は灰色で表示されます。](../../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365ドキュメントとリソースの詳細](./index.yml)\
[Windows 10 の PC のデバイス構成を設定する](protection-settings-for-windows-10-pcs.md)
