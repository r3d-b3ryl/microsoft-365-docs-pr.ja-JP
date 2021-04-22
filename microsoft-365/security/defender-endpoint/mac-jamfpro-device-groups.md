---
title: Jamf Pro でデバイス グループを設定する
description: MacOS のエンドポイント向け Microsoft Defender 用 Jamf Pro でデバイス グループを設定する方法について説明します。
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
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933807"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Jamf Pro の macOS デバイス グループで Microsoft Defender for Endpoint をセットアップする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

グループ ポリシー組織単位 (OUs)、Microsoft Endpoint Configuration Manager のデバイス コレクション、Intune のデバイス グループに似たデバイス グループを設定します。

1. [静的コンピューター **グループ] に移動します**。

2. [**新規**]を選択します。 

    ![Jamf Pro1 のイメージ](images/jamf-pro-static-group.png)

3. 表示名を指定し、[保存] を **選択します**。

    ![Jamf Pro2 の画像](images/jamfpro-machine-group.png)

4. これで、[静的コンピューター グループ] の **下に Contoso のコンピューター** **グループが表示されます**。

    ![Jamf Pro3 の画像](images/contoso-machine-group.png)

## <a name="next-step"></a>次の手順
- [Jamf Pro の macOS ポリシーで Microsoft Defender for Endpoint をセットアップする](mac-jamfpro-policies.md)
