---
title: Jamf Proでデバイス グループを設定する
description: macOS で Microsoft Defender for Endpoint 用に Jamf Proでデバイス グループを設定する方法について説明します
keywords: デバイス, グループ, microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamfpro, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c22a1a68af2722e6b17d155a37632c1f6417b605
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471761"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Jamf Proの macOS デバイス グループでMicrosoft Defender for Endpointを設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

グループ ポリシー組織単位 (OU)、Microsoft Endpoint Configuration Managerのデバイス コレクション、Intuneのデバイス グループに似たデバイス グループを設定します。

1. **静的コンピューター グループ** に移動します。

2. [**新規**]を選択します。 

   :::image type="content" source="images/jamf-pro-static-group.png" alt-text="Jamf Pro1 ページ" lightbox="images/jamf-pro-static-group.png":::

3. 表示名を指定し、[ **保存**] を選択します。

   :::image type="content" source="images/jamfpro-machine-group.png" alt-text="Jamf Pro2 ページ" lightbox="images/jamfpro-machine-group.png":::

4. これで、**静的コンピューター グループの下に Contoso のマシン グループ****が** 表示されます。

   :::image type="content" source="images/contoso-machine-group.png" alt-text="Jamf Pro3 ページ" lightbox="images/contoso-machine-group.png":::

## <a name="next-step"></a>次の手順
- [Jamf Proで macOS ポリシーのMicrosoft Defender for Endpointを設定する](mac-jamfpro-policies.md)
