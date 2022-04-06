---
title: デバイス値の割り当て - 脅威と脆弱性の管理
description: 低、通常、または高い値をデバイスに割り当て、資産の優先順位を区別する方法について学習します。
keywords: Microsoft Defender for Endpoint device value, 脅威と脆弱性の管理値, 高価値デバイス, デバイス値露出スコア
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ff6d61e02ff923cc9406412c81e9a67799e6880a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477222"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>デバイス値の割り当て - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

デバイスの値を定義すると、資産の優先順位を区別できます。 デバイス値は、個々のアセットのリスクアペタイトを露出スコアの計算に組み込脅威と脆弱性の管理使用されます。 "高い値" として割り当てられたデバイスは、より多くの重みを受け取る。

デバイス値の設定 [API を使用することもできます](set-device-value.md)。

デバイス値のオプション:

- 低
- 標準 (既定値)
- 高

高い値を割り当てる必要があるデバイスの例を次に示します。

- ドメイン コントローラー、Active Directory
- インターネットに接続するデバイス
- VIP デバイス
- 内部/外部の実稼働サービスをホストするデバイス

## <a name="choose-device-value"></a>デバイスの値を選択する

1. 任意のデバイス ページに移動し、最も簡単な場所はデバイス インベントリから行います。

2. ページ **の上部にある** アクション バーの横にある 3 つのドットから [デバイス値] を選択します。

   :::image type="content" source="images/tvm-device-value-dropdown.png" alt-text="[デバイス値] オプション" lightbox="images/tvm-device-value-dropdown.png":::

3. 現在のデバイス値とそれが何を意味するフライアウトが表示されます。 デバイスの値を確認し、デバイスに最適な値を選択します。

:::image type="content" source="images/tvm-device-value-flyout.png" alt-text="[デバイスの値] ページ" lightbox="images/tvm-device-value-flyout.png":::

## <a name="how-device-value-impacts-your-exposure-score"></a>デバイスの値が露出スコアに与える影響

露出スコアは、すべてのデバイスの加重平均です。 デバイス グループがある場合は、デバイス グループ別にスコアをフィルター処理することもできます。

- 通常のデバイスの重み 1
- 低い値のデバイスの重み 0.75
- 高い値のデバイスには、NumberOfAssets / 10 の重みがあります。
    - デバイスが 100 台の場合、各高価値デバイスの重みは 10 (100/10) になります。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [露出スコア](tvm-exposure-score.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)