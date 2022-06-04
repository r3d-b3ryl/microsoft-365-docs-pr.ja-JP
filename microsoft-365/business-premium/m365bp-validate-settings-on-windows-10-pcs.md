---
title: Windows 10 PC のアプリ保護設定を検証する
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
description: Microsoft 365 Business Premium アプリ保護設定がユーザーの Windows 10 デバイスで有効になっていることを確認する方法について説明します。
ms.openlocfilehash: 5ce28946c5df84ffe2bfac9d4cc52d4178996936
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893247"
---
# <a name="validate-device-protection-settings-for-windows-10-or-11-pcs"></a>Windows 10 または 11 PC のデバイス保護設定を検証する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

## <a name="verify-that-windows-10-or-11-device-policies-are-set"></a>Windows 10 または 11 のデバイス ポリシーが設定されていることを確認する

[デバイス ポリシーを設定](../business-premium/m365bp-protection-settings-for-windows-10-devices.md)すると、ポリシーがユーザーのデバイスに反映されるまでに最大で数時間かかる場合があります。 ユーザーのデバイス上でさまざまな Windows の設定画面を表示して、ポリシーが反映されていることを確認できます。 ユーザーは Windows 10 または 11 デバイスで Windows Update と Microsoft Defender ウイルス対策の設定を変更できないため、多くのオプションが淡色表示されます。
  
1. **[Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart] オプション** に移動し、すべての設定が淡色表示になっていることを確認します。

    ![[再起動] オプションはすべて淡色表示されます。](../business-premium/media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. **[Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced] オプション** に移動し、すべての設定が淡色表示になっていることを確認します。

    ![Windows Advanced Updates オプションはすべて淡色表示されます。](../business-premium/media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.

    一部の設定が組織によって非表示または管理されており、すべてのオプションが淡色表示されていることを示すメッセージが赤で表示されることを確認します。

    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../business-premium/media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.

5. すべてのオプションが淡色表示されていることを確認します。

    ![[ウイルスと脅威の保護] 設定は淡色表示されます。](../business-premium/media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 for business のドキュメントとリソース](/admin)

[Windows 10 PC](../business-premium/m365bp-protection-settings-for-windows-10-devices.md)
 のデバイス構成を設定する[ビジネス プラン用の Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>次の目標

[保護ポリシーを確認および編集する](m365bp-view-edit-create-mdb-policies.md)
