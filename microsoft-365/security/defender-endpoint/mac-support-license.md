---
title: Mac でのMicrosoft Defender for Endpointのライセンスの問題のトラブルシューティング
description: Mac のMicrosoft Defender for Endpointでのライセンスの問題のトラブルシューティングを行います。
keywords: microsoft、Defender、Microsoft Defender for Endpoint、mac、パフォーマンス
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
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointのライセンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS](microsoft-defender-endpoint-mac.md)
 でのMicrosoft Defender for Endpoint [Microsoft Defender for Endpointプラン 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
 [Microsoft Defender for Endpoint プラン 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS および[手動展開](mac-install-manually.md)テストまたは概念実証 (PoC) [でMicrosoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)を実行している間に、次のエラーが発生する可能性があります。

:::image type="content" source="images/no-license-found.png" alt-text="ライセンス エラー" lightbox="images/no-license-found.png":::

**メッセージ：** 

ライセンスが見つかりません

組織にMicrosoft 365 Enterpriseサブスクリプションのライセンスがないようです。

ヘルプについては、管理者にお問い合わせください。

**原因:** 

macOS パッケージ ("インストール パッケージのダウンロード" ) にMicrosoft Defender for Endpointを展開またはインストールしましたが、構成スクリプト ("オンボード パッケージのダウンロード") を実行していない可能性があります。または、ユーザーにライセンスが割り当てられていない可能性があります。

macOS エージェントのMicrosoft Defender for Endpointが最新でない場合にも、このエラーが発生する可能性があります。 


**解決方法:**

[「クライアント構成](mac-install-manually.md#client-configuration)」に記載されている MicrosoftDefenderATPOnboardingMacOs.py 手順に従います。

macOS のMicrosoft Defender for Endpointが最新でないシナリオの場合は、エージェントを更新する必要があります。 
