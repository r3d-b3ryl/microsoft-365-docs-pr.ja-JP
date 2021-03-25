---
title: Microsoft Defender ATP for Mac のライセンスの問題のトラブルシューティング
description: Microsoft Defender ATP for Mac のライセンスの問題のトラブルシューティングを行います。
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066428"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender for Endpoint for Mac のライセンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) [](mac-install-manually.md)および手動展開テスト、または概念実証 (PoC) を実行している間に、次のエラーが表示される場合があります。

![ライセンス エラーのイメージ](images/no-license-found.png)

**メッセージ：** 

ライセンスが見つかりません

組織が Microsoft 365 Enterprise サブスクリプションのライセンスを持たしていないように見えます。

ヘルプについては、管理者に問い合わせてください。

**原因:** 

Microsoft Defender for Endpoint for macOS パッケージ ("Download installation package") を展開またはインストールしましたが、構成スクリプト (「オンボード パッケージのダウンロード」) を実行している可能性があります。

**解決方法:**

ここに記載されている MicrosoftDefenderATPOnboardingMacOs.py 手順に従います。クライアント [構成](mac-install-manually.md#client-configuration)

