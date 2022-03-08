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
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
ms.openlocfilehash: be25acb8414705c48a8763a0530ec2a70565de83
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313595"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>PC のデバイス保護設定をWindows 10する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 デバイス ポリシーが設定されていることを確認する

デバイス ポリシー [を設定した後](protection-settings-for-windows-10-pcs.md)、ポリシーがユーザーのデバイスに適用されるのに最大で数時間かかる場合があります。 ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。 ユーザーは、Windows デバイスの Windows Update と Microsoft Defender ウイルス対策 Windows 10 の設定を変更できないので、多くのオプションがグレー表示されます。
  
1. [セキュリティの **設定** \> **更新Windows &amp;** \> **更新**\>] オプションに移動し、すべての設定が灰色で表示されているのを確認します。 
    
    ![[再起動] オプションはすべて灰色で表示されます。](../../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. [セキュリティの **設定** \> **更新Windows &amp;** \>  \>]オプションに移動し、すべての設定が灰色で表示されているのを確認します。 
    
    ![Windows詳細更新プログラムのオプションはすべて灰色で表示されます。](../../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    一部の設定が非表示または組織によって管理され、すべてのオプションが灰色で表示されるというメッセージが赤で表示されるのを確認します。
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. すべてのオプションが灰色で表示されるのを確認します。 
    
    ![ウイルスと脅威の保護の設定は灰色で表示されます。](../../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365ドキュメントとリソースの詳細](/admin)\
[Pc のデバイス構成をWindows 10ビジネス](protection-settings-for-windows-10-pcs.md)
 プランのセキュリティで保護する [10 Microsoft 365方法](../security-and-compliance/secure-your-business-data.md)