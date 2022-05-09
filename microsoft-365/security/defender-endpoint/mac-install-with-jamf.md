---
title: Jamf Pro を使用した macOS へのMicrosoft Defender for Endpointのデプロイ
description: Jamf Pro を使用した macOS へのMicrosoft Defender for Endpointのデプロイ
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 0ce77d9d63aecdd3150b9dc0f536abcdab2755e8
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767363"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a>Jamf Pro を使用した macOS へのMicrosoft Defender for Endpointのデプロイ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Jamf Proを使用して macOS にMicrosoft Defender for Endpointをデプロイする方法について説明します。

> [!NOTE]
> macOS Catalina (10.15.4) 以降のバージョンの macOS を使用している場合は、「 [macOS Catalina および macOS の新しいバージョンの新しい構成プロファイル](/microsoft-365/security/defender-endpoint/mac-sysext-policies)」を参照してください。

これはマルチステップ プロセスです。 次のすべての手順を完了する必要があります。

- [Jamf ポータルにログインする](mac-install-jamfpro-login.md)
- [Jamf Proの macOS デバイス グループでMicrosoft Defender for Endpointを設定する](mac-jamfpro-device-groups.md)
- [Jamf Proで macOS ポリシーのMicrosoft Defender for Endpointを設定する](mac-jamfpro-policies.md)
- [macOS デバイスで Microsoft Defender for Endpointを Jamf Proに登録する](mac-jamfpro-enroll-devices.md)




