---
title: Microsoft Defender for Endpoint サービスへのオンボード
description: エンドポイントを Microsoft Defender for Endpoint サービスにオンボードする方法について説明します。
keywords: microsoft defender for endpoint, onboard, deploy
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
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d1e65fc2a5626a48b7673374c764d4a7c5a0d2b3
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53649181"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint サービスへのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint の展開のさまざまなフェーズと、ソリューション内の機能を構成する方法について説明します。

Defender for Endpoint の展開は、次の 3 フェーズプロセスです。

|[![展開フェーズ - 準備](images/phase-diagrams/prepare.png)](prepare-deployment.md) <br> [フェーズ 1: 準備](prepare-deployment.md)|[![展開フェーズ - セットアップ](images/phase-diagrams/setup.png)](production-deployment.md) <br> [フェーズ 2: セットアップ](production-deployment.md)|![展開フェーズ - オンボード](images/phase-diagrams/onboard.png) <br> フェーズ 3: オンボード|
|---|---|---|
|||*お前はここにいる!*|

現在、オンボーディング フェーズに入っている。

Defender for Endpoint を展開するために必要な手順は次のとおりです。

- 手順 1: サービスにエンドポイントをオンボードする
- 手順 2: 機能を構成する

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 1: サポートされている管理ツールを使用してエンドポイントをオンボードする

「 [展開の計画」](deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。

オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

アーキテクチャを特定した後、使用する展開方法を決定する必要があります。 選択した展開ツールは、エンドポイントをサービスにオンボードする方法に影響します。

### <a name="onboarding-tool-options"></a>オンボーディング ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。

|Endpoint|ツール オプション|
|---|---|
|**Windows**|[ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Azure Defender との統合](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md)|
|**Linux Server**|[ローカル スクリプト](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[アプリベース](ios-install.md)|
|**Android**|[Microsoft エンドポイント マネージャー](android-intune.md)|

## <a name="step-2-configure-capabilities"></a>手順 2: 機能を構成する

エンドポイントのオンボード後、エンドポイントの検出と応答、次世代保護、攻撃表面の縮小など、さまざまな機能を構成します。

## <a name="example-deployments"></a>展開の例

この展開ガイドでは、2 つの展開ツールを使用してエンドポイントをオンボードし、機能を構成する方法について説明します。

展開例のツールは次のとおりです。

- [Microsoft Endpoint Configuration Manager を使用したオンボーディング](onboarding-endpoint-configuration-manager.md)
- [Microsoft エンドポイント マネージャーを使用したオンボーディング](onboarding-endpoint-manager.md)

上記の展開ツールを使用して、次の Defender for Endpoint 機能の構成について説明します。

- エンドポイントの検出と応答の構成
- 次世代の保護構成
- 攻撃表面の縮小構成

## <a name="related-topics"></a>関連項目

- [Microsoft Endpoint Configuration Manager を使用したオンボーディング](onboarding-endpoint-configuration-manager.md)
- [Microsoft エンドポイント マネージャーを使用したオンボーディング](onboarding-endpoint-manager.md)
- [Microsoft 365 E5 の安全なドキュメント](../office-365-security/safe-docs.md)
