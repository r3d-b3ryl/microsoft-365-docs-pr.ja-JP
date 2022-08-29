---
title: Microsoft Defender for Endpoint サービスへのオンボード
description: エンドポイントをMicrosoft Defender for Endpoint サービスにオンボードする方法について説明します
keywords: microsoft Defender for endpoint, onboard, deploy
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
- m365solution-endpointprotect
- m365solution-scenario
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: da4dc661754a94dbdfa25579426edba8356a7497
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331647"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint サービスへのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpointのデプロイのさまざまなフェーズと、ソリューション内で機能を構成する方法について説明します。


Defender for Endpoint をデプロイするために必要な手順は次のとおりです。

- 手順 1: エンドポイントをサービスにオンボードする
- 手順 2: 機能を構成する

:::image type="content" source="images/deployment-steps.png" alt-text="デプロイ手順" lightbox="images/deployment-steps.png":::




## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 1: サポートされている管理ツールのいずれかを使用してエンドポイントをオンボードする

[「計画展開」](deployment-strategy.md)トピックでは、Defender for Endpoint をデプロイするために必要な一般的な手順について説明します。

このビデオでは、オンボード プロセスの概要と、使用可能なツールと方法について説明します。


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

アーキテクチャを特定したら、使用するデプロイ方法を決定する必要があります。 選択したデプロイ ツールは、エンドポイントをサービスにオンボードする方法に影響します。

### <a name="onboarding-tool-options"></a>オンボード ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールの一覧を示します。

| エンドポイント     | ツール オプション                       |
|--------------|------------------------------------------|
| **Windows**  |  [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ Mobile デバイス マネージャー](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Microsoft Defender for Cloudとの統合](azure-server-integration.md)  |
| **macOS**    | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](linux-install-manually.md) <br> [人形](linux-install-with-puppet.md) <br> [アンシブル](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft エンドポイント マネージャー](ios-install.md)                                |
| **Android**  | [Microsoft エンドポイント マネージャー](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>手順 2: 機能を構成する
エンドポイントをオンボードした後、機能を構成します。 次の表に、構成できるコンポーネントの一覧を示します。 使用するコンポーネントを選択し、適用しないコンポーネントを削除します。

| 機能 | 説明 |
|-|-|
| [エンドポイント検出&応答 (EDR)](overview-endpoint-detection-response.md) | Defender for Endpoint エンドポイントの検出と応答機能は、ほぼリアルタイムで実用的な高度な攻撃検出を提供します。 セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 |
| [Microsoft Defender 脆弱性の管理 (MDVM)](next-gen-threat-and-vuln-mgt.md) | Defender Vulnerability Management は、Microsoft Defender for Endpointのコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に、エンドポイントの脆弱性と関連するリアルタイムのエンドポイント検出と応答 (EDR) 分析情報 - インシデント調査中の貴重なデバイスの脆弱性コンテキスト - 組み込みの修復プロセスなど、一意の価値を提供します。Microsoft Intuneと Microsoft System Center Configuration Manager。  |
| [次世代保護 (NGP)](microsoft-defender-antivirus-windows.md) | Microsoft Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、およびサーバーに次世代の保護を提供する組み込みのマルウェア対策ソリューションです。 Microsoft Defender ウイルス対策には、次のものが含まれます。<br> <br>-クラウドによって提供される、新しい脅威と新しい脅威のほぼ瞬時の検出とブロックのための保護。 機械学習やインテリジェント セキュリティ グラフに加えて、クラウドによる保護は Microsoft Defender ウイルス対策を強化する次世代テクノロジの一部です。<br> <br> - 高度なファイルとプロセス動作の監視とその他のヒューリスティック ("リアルタイム保護" とも呼ばれます) を使用した常時オンスキャン。<br><br> - 機械学習、人間と自動化されたビッグ データ分析、詳細な脅威対策の研究に基づく専用の保護更新。 |
| [攻撃面の縮小 (ASR)](overview-attack-surface-reduction.md) | Microsoft Defender for Endpointの攻撃面の縮小機能は、組織内のデバイスとアプリケーションを新しい脅威や新しい脅威から保護するのに役立ちます。 |
| [自動調査&修復 (AIR)](automated-investigations.md) | Microsoft Defender for Endpointでは、自動調査を使用して、個別に調査する必要があるアラートの量を大幅に減らします。 自動調査機能は、さまざまな検査アルゴリズムと、アナリスト (プレイブックなど) によって使用されるプロセスを利用して、アラートを調べ、侵害を解決するための直ちに修復アクションを実行します。 これにより、アラート量が大幅に削減され、セキュリティ運用の専門家は、より高度な脅威やその他の価値の高い業務に集中できるようになります。 |
| [Microsoft 脅威エキスパート (MTE)](microsoft-threat-experts.md) | Microsoft 脅威エキスパートは、セキュリティ オペレーション センター (SOC) に専門家レベルの監視と分析を提供するマネージド ハンティング サービスであり、固有の環境で重大な脅威が見逃されないように支援します。      |

エンドポイントをオンボードした後、エンドポイントの検出と応答、次世代の保護、攻撃面の削減など、さまざまな機能を構成します。

## <a name="example-deployments"></a>デプロイの例

このデプロイ ガイドでは、2 つのデプロイ ツールを使用してエンドポイントをオンボードし、機能を構成する方法について説明します。

デプロイ例のツールは次のとおりです。

- [Microsoft Endpoint Configuration Manager を使用したオンボーディング](onboarding-endpoint-configuration-manager.md)
- [Microsoft エンドポイント マネージャーを使用したオンボーディング](onboarding-endpoint-manager.md)

上記のデプロイ ツールを使用して、次の Defender for Endpoint 機能の構成について説明します。

- エンドポイントの検出と応答の構成
- 次世代の保護構成
- 攻撃面の縮小構成

## <a name="related-topics"></a>関連項目

- [Microsoft Endpoint Configuration Manager を使用したオンボーディング](onboarding-endpoint-configuration-manager.md)
- [Microsoft エンドポイント マネージャーを使用したオンボーディング](onboarding-endpoint-manager.md)
- [Microsoft 365 E5 の安全なドキュメント](../office-365-security/safe-docs.md)
