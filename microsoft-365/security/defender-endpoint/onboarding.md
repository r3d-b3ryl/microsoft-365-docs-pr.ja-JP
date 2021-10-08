---
title: Microsoft Defender for Endpoint サービスへのオンボード
description: エンドポイントを Microsoft Defender for Endpoint サービスにオンボードする方法について説明します。
keywords: microsoft defender for endpoint, onboard, deploy
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7266a92c43e87b6ccf1bda5d78451c54066297cd
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240192"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint サービスへのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint の展開のさまざまなフェーズと、ソリューション内の機能を構成する方法について説明します。


Defender for Endpoint を展開するために必要な手順は次のとおりです。

- 手順 1: サービスにエンドポイントをオンボードする
- 手順 2: 機能を構成する

![展開手順の図](images/deployment-steps.png)



## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 1: サポートされている管理ツールを使用してエンドポイントをオンボードする

「 [展開の計画」](deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。

オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

アーキテクチャを特定した後、使用する展開方法を決定する必要があります。 選択した展開ツールは、エンドポイントをサービスにオンボードする方法に影響します。

### <a name="onboarding-tool-options"></a>オンボーディング ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。

| エンドポイント     | ツール オプション                       |
|--------------|------------------------------------------|
| **Windows**  |  [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Azure Defender との統合](azure-server-integration.md) |
| **macOS**    | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft エンドポイント マネージャー](ios-install.md)                                |
| **Android**  | [Microsoft エンドポイント マネージャー](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>手順 2: 機能を構成する
エンドポイントのオンボード後、機能を構成します。 次の表に、構成できるコンポーネントの一覧を示します。 使用するコンポーネントを選択し、適用されないコンポーネントを削除します。

| 機能 | 説明 |
|-|-|
| [エンドポイント検出&応答 (EDR)](overview-endpoint-detection-response.md) | Defender for Endpoint endpoint detection and response capabilitis provide advanced attack detections are near real-time and actionable. セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。 |
| [脅威&脆弱性管理 (TVM)](next-gen-threat-and-vuln-mgt.md) | Threat & Vulnerability Management は、Microsoft Defender for Endpoint のコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に、エンドポイントの脆弱性と関連するリアルタイムエンドポイント検出と応答 (EDR) の分析情報 ( インシデント調査中の貴重なデバイスの脆弱性コンテキスト ) - Microsoft Intune と Micr による組み込みの修復プロセスを提供します。osoft System Center Configuration Manager。  |
| [次世代保護 (NGP)](microsoft-defender-antivirus-windows.md) | Microsoft Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、およびサーバーに次世代の保護を提供する組み込みのマルウェア対策ソリューションです。 Microsoft Defender ウイルス対策には、次のものが含まれます。<br> <br>-クラウドによって提供される、新しい脅威や新しい脅威のほぼ瞬時の検出とブロックに対する保護。 機械学習やインテリジェント セキュリティ グラフに加えて、クラウドによる保護は Microsoft Defender ウイルス対策を強化する次世代テクノロジの一部です。<br> <br> - 高度なファイルとプロセスの動作監視、その他のヒューリスティック ("リアルタイム保護" とも呼ばれる) を使用した常時スキャン。<br><br> - 機械学習、人間および自動化されたビッグ データ分析、および詳細な脅威耐性の調査に基づく専用の保護更新プログラム。 |
| [攻撃表面の縮小 (ASR)](overview-attack-surface-reduction.md) | Microsoft Defender for Endpoint の攻撃表面の縮小機能は、新しい脅威や新たな脅威から組織内のデバイスとアプリケーションを保護するのに役立ちます。 |
| [自動調査&修復 (AIR)](automated-investigations.md) | Microsoft Defender for Endpoint では、自動調査を使用して、個別に調査する必要があるアラートの量を大幅に削減します。 自動調査機能は、さまざまな検査アルゴリズムと、アナリストが使用するプロセス (プレイブックなど) を活用してアラートを調べ、違反を解決するために直ちに修復アクションを実行します。 これにより、アラート量が大幅に削減され、セキュリティ運用の専門家は、より高度な脅威やその他の価値の高い業務に集中できるようになります。 |
| [Microsoft 脅威エキスパート (MTE)](microsoft-threat-experts.md) | Microsoft 脅威エキスパートは、セキュリティ オペレーション センター (SOC) にエキスパート レベルの監視と分析を提供するマネージ ハンティング サービスで、固有の環境における重大な脅威を見逃すのを防いでお手伝いします。      |

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
