---
title: Jamf グループでデバイス グループをPro
description: MacOS 上の Microsoft Defender for Endpoint Pro Jamf Proデバイス グループをセットアップする方法について説明します。
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8d7994ac207f6f066b5cfe69de75ddfb608ddd40fa53105492a5076aced01de5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53833714"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Jamf デバイス グループの macOS デバイス グループで Microsoft Defender for Endpoint をセットアップPro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

グループ ポリシーの組織単位 (OUs)、Microsoft Endpoint Configuration Managerコレクション、Intune のデバイス グループに似たデバイス グループを設定します。

1. [静的コンピューター **グループ] に移動します**。

2. [**新規**]を選択します。 

    ![Jamf Pro1 のイメージ](images/jamf-pro-static-group.png)

3. 表示名を指定し、[保存] を **選択します**。

    ![Jamf Pro2 の画像](images/jamfpro-machine-group.png)

4. これで、[静的コンピューター グループ] の **下に Contoso のコンピューター** **グループが表示されます**。

    ![Jamf Pro3 の画像](images/contoso-machine-group.png)

## <a name="next-step"></a>次の手順
- [Jamf の macOS ポリシーで Microsoft Defender for Endpoint をセットアップPro](mac-jamfpro-policies.md)
