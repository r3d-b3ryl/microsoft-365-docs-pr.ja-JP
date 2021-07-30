---
title: Microsoft Defender for Endpoint 展開の計画
description: 環境に最適な Microsoft Defender for Endpoint 展開戦略を選択する
keywords: 展開、計画、展開戦略、クラウド ネイティブ、管理、prem、評価、オンボーディング、ローカル、グループ ポリシー、gp、エンドポイント マネージャー、mem
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7bef13e2a7e85b10a103175de55d4d721bde2573
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53649428"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender for Endpoint 展開の計画 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

Microsoft Defender for Endpoint の展開を計画して、スイート内のセキュリティ機能を最大限に活用し、企業をサイバー脅威からより良く保護できます。

このソリューションでは、環境アーキテクチャを特定する方法、ニーズに最も適した展開ツールの種類を選択する方法、および機能を構成する方法に関するガイダンスを提供します。

![展開フローのイメージ](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>手順 1: アーキテクチャを識別する
すべてのエンタープライズ環境は一意なので、サービスの展開方法を柔軟に選択するためのオプションがいくつか用意されています。

環境に応じて、一部のツールは特定のアーキテクチャに適しています。 

次の資料を使用して、組織に最適なエンドポイント向け Defender アーキテクチャを選択します。

| アイテム | 説明 |
|:-----|:-----|
|[![Defender for Endpoint 展開戦略のサム イメージ](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | アーキテクチャ教材は、次のアーキテクチャの展開を計画するのに役立ちます。 <ul><li> クラウド-ネイティブ </li><li> 共同管理 </li><li> オンプレミス</li><li>評価とローカル オンボード</li>

## <a name="step-2-select-deployment-method"></a>手順 2: 展開方法の選択
Defender for Endpoint は、サービスにオンボードできるさまざまなエンドポイントをサポートします。 

次の表に、サポートされているエンドポイントと、適切に展開を計画するために使用できる対応する展開ツールの一覧を示します。

| Endpoint     | 展開ツール                       |
|--------------|------------------------------------------|
| **Windows**  |  [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Azure Defender との統合](configure-server-endpoints.md#integration-with-azure-defender)  |
| **macOS**    | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [アプリベース](ios-install.md)                                |
| **Android**  | [Microsoft エンドポイント マネージャー](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>手順 3: 機能を構成する
エンドポイントのオンボード後、Defender for Endpoint のセキュリティ機能を構成して、スイートで使用可能な堅牢なセキュリティ保護を最大限に活用できます。 機能には、次のものが含まれます。

- エンドポイントの検出および応答
- 次世代の保護
- 攻撃面の縮小


  
## <a name="related-topics"></a>関連項目
- [展開フェーズ](deployment-phases.md)
