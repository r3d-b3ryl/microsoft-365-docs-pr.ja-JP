---
title: デバイス値の割り当て - 脅威と脆弱性の管理
description: 資産の優先順位を区別するために、デバイスに低、標準、高の値を割り当てる方法について説明します。
keywords: Microsoft Defender for Endpointデバイス値、脅威と脆弱性の管理デバイス値、高い値のデバイス、デバイス値の露出スコア
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

デバイスの値を定義すると、資産の優先順位を区別するのに役立ちます。 デバイス値は、個々の資産のリスクアペタイトを脅威と脆弱性の管理露出スコア計算に組み込むために使用されます。 "高い値" として割り当てられたデバイスは、より多くの重みを受け取ります。

[また、デバイス値の設定 API](set-device-value.md) を使用することもできます。

デバイス値オプション:

- 低
- 標準 (既定値)
- 高

高い値を割り当てる必要があるデバイスの例:

- ドメイン コントローラー、Active Directory
- インターネットに接続するデバイス
- VIP デバイス
- 内部/外部の運用サービスをホストしているデバイス

## <a name="choose-device-value"></a>デバイスの値を選択する

1. 任意のデバイス ページに移動します。最も簡単な場所はデバイス インベントリからです。

2. ページの上部にあるアクション バーの横にある 3 つのドットから **[デバイスの値** ] を選択します。

   :::image type="content" source="images/tvm-device-value-dropdown.png" alt-text="[デバイス値] オプション" lightbox="images/tvm-device-value-dropdown.png":::

3. ポップアップは、現在のデバイス値とその意味と共に表示されます。 デバイスの値を確認し、デバイスに最適なものを選択します。

:::image type="content" source="images/tvm-device-value-flyout.png" alt-text="[デバイスの値] ページ" lightbox="images/tvm-device-value-flyout.png":::

## <a name="how-device-value-impacts-your-exposure-score"></a>デバイスの値が露出スコアに与える影響

露出スコアは、すべてのデバイスの加重平均です。 デバイス グループがある場合は、デバイス グループでスコアをフィルター処理することもできます。

- 通常のデバイスの重量は 1 です。
- 低い値のデバイスの重量は 0.75 です。
- 高い値のデバイスの重みは NumberOfAssets / 10 です。
    - デバイスが 100 個ある場合、高い値を持つ各デバイスの重みは 10 (100/10) になります。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [露出スコア](tvm-exposure-score.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)