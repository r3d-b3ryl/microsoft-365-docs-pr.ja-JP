---
title: Microsoft Defender for Endpoint 展開の計画
description: 環境に最適なMicrosoft Defender for Endpoint展開戦略を選択する
keywords: デプロイ, 計画, デプロイ戦略, クラウド ネイティブ, 管理, オンプレミス, 評価, オンボード, ローカル, グループ ポリシー, gp, エンドポイント マネージャー, mem
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 63996aa4d046ac719e0e6b98ed4c5980e0d979be
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783867"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender for Endpoint 展開の計画

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

スイート内のセキュリティ機能を最大限に活用し、サイバー脅威から企業をより適切に保護できるように、Microsoft Defender for Endpointデプロイを計画します。

このソリューションでは、環境アーキテクチャを特定する方法、ニーズに最適な展開ツールの種類を選択する方法、および機能を構成する方法に関するガイダンスを提供します。

:::image type="content" source="images/deployment-guide-plan.png" alt-text="デプロイ フロー" lightbox="images/deployment-guide-plan.png":::

## <a name="step-1-identify-architecture"></a>手順 1: アーキテクチャを特定する

すべてのエンタープライズ環境が一意であることを理解しているため、サービスのデプロイ方法を柔軟に選択できるオプションがいくつか用意されています。

環境に応じて、一部のツールは特定のアーキテクチャに適しています。

次の資料を使用して、組織に最適な Defender for Endpoint アーキテクチャを選択します。

| アイテム | 説明 |
|:-----|:-----|
|[:::image type="content" source="images/mde-deployment-strategy.png" alt-text="Defender for Endpoint のデプロイ戦略" lightbox="images/mde-deployment-strategy.png":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) | アーキテクチャ教材は、次のアーキテクチャの展開を計画するのに役立ちます。 <ul><li> クラウド-ネイティブ </li><li> 共同管理 </li><li> オンプレミス</li><li>評価とローカル オンボード</li>

## <a name="step-2-select-deployment-method"></a>手順 2: デプロイ方法を選択する

| エンドポイント     | デプロイ ツール                       |
|--------------|------------------------------------------|
| **Windows**  |  [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Microsoft Defender for Cloudとの統合](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)   |
| **macOS**    | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](linux-install-manually.md) <br> [人形](linux-install-with-puppet.md) <br> [アンシブル](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft エンドポイント マネージャー](ios-install.md)                                |
| **Android**  | [Microsoft エンドポイント マネージャー](android-intune.md)               | 

次の表に、サポートされているエンドポイントと、デプロイを適切に計画できるように使用できる対応するデプロイ ツールを示します。

|エンドポイント|デプロイ ツール|
|---|---|
|**Windows**|[ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Microsoft Defender for Cloudとの統合](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud) |
|**macOS**|[ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md)|
|**Linux Server**|[ローカル スクリプト](linux-install-manually.md) <br> [人形](linux-install-with-puppet.md) <br> [アンシブル](linux-install-with-ansible.md)|
|**iOS**|[アプリベース](ios-install.md)|
|**Android**|[Microsoft エンドポイント マネージャー](android-intune.md)|

## <a name="step-3-configure-capabilities"></a>手順 3: 機能を構成する

エンドポイントをオンボードした後、Defender for Endpoint でセキュリティ機能を構成し、スイートで使用可能な堅牢なセキュリティ保護を最大限に高めることができます。 機能には、次の内容が含まれます。

- エンドポイントの検出および応答
- 次世代の保護
- 攻撃面の縮小

## <a name="related-topics"></a>関連項目

- [展開フェーズ](deployment-phases.md)
