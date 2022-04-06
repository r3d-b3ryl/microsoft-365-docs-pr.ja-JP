---
title: Mac 上の Microsoft Defender for Endpoint のライセンスの問題のトラブルシューティング
description: Microsoft Defender for Endpoint on Mac のライセンスの問題のトラブルシューティングを行います。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 35b77183ee9ceb00569c956d30debb0dd61e63f7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471739"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上の Microsoft Defender for Endpoint のライセンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS 上のエンドポイント用 Microsoft Defender](microsoft-defender-endpoint-mac.md)
[Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
[Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

MacOS および手動展開テストまたは概念実証 (PoC[](mac-install-manually.md)) で [Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) を実行している間に、次のエラーが表示される場合があります。

:::image type="content" source="images/no-license-found.png" alt-text="ライセンス エラー" lightbox="images/no-license-found.png":::

**メッセージ：** 

ライセンスが見つかりません

組織がサブスクリプションのライセンスを持Microsoft 365 Enterpriseします。

ヘルプについては、管理者に問い合わせてください。

**原因:** 

Microsoft Defender for Endpoint on macOS パッケージ ("Download installation package") を展開またはインストールしましたが、構成スクリプト ("オンボード パッケージのダウンロード") を実行していないか、ユーザーにライセンスが割り当てられていない可能性があります。

macOS エージェントの Microsoft Defender for Endpoint が最新の状態ではない場合にも、このエラーが発生する可能性があります。 


**解決方法:**

ここに記載 MicrosoftDefenderATPOnboardingMacOs.py 手順に従います。クライアント [構成](mac-install-manually.md#client-configuration)

macOS 上の Microsoft Defender for Endpoint が最新ではないシナリオでは、エージェントを更新する必要があります。 
