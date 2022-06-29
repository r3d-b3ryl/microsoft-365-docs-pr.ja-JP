---
title: デバイスにオンボードして、Microsoft Defender for Endpoint 機能 を構成します
description: Windows 10 デバイス、サーバー、Windows 以外のデバイスをオンボードし、検出テストを実行する方法について説明します。
keywords: オンボード, Microsoft Defender for Endpointオンボード, sccm, グループ ポリシー, mdm, ローカル スクリプト, 検出テスト
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d218e09c8cc300552bcc9f230c1d375d33a5feb6
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66530556"
---
# <a name="onboard-devices-and-configure-microsoft-defender-for-endpoint-capabilities"></a>デバイスにオンボードして、Microsoft Defender for Endpoint 機能 を構成します

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Microsoft Defender for Endpointのデプロイは、2 段階のプロセスです。

- デバイスをサービスにオンボードする
- サービスの機能を構成する

:::image type="content" source="images/deployment-steps.png" alt-text="オンボードと構成プロセス" lightbox="images/deployment-steps.png":::

## <a name="onboard-devices-to-the-service"></a>デバイスをサービスにオンボードする
サポートされているデバイスをオンボードするには、Defender for Endpoint ポータルのオンボード セクションに移動する必要があります。 デバイスに応じて、適切な手順と、デバイスに適した管理および展開ツールのオプションが提供されます。 

デバイスをサービスにオンボードするには:

- デバイスが[最小要件](minimum-requirements.md)を満たしていることを確認する
- デバイスに応じて、Defender for Endpoint ポータルのオンボード セクションで示されている構成手順に従います。
- デバイスに適切な管理ツールと展開方法を使用する
- 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認する

この記事では、Windows クライアントとサーバーのバージョンに適用されるオンボード方法について説明します。

## <a name="onboarding-and-configuration-tool-options"></a>オンボードと構成ツールのオプション
次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールの一覧を示します。

| エンドポイント     | ツール オプション                       |
|--------------|------------------------------------------|
| **Windows クライアント**  |     [モバイル デバイス管理/Microsoft Intune](configure-endpoints-mdm.md) <br> [グループ ポリシー](configure-endpoints-gp.md) <br> [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br>[VDI スクリプト](configure-endpoints-vdi.md) <br> [Microsoft Defender for Cloudとの統合](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)   |
| **Windows Server**  | [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [VDI スクリプト](configure-endpoints-vdi.md) <br> [Microsoft Defender for Cloudとの統合](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)   |
| **macOS**    | [ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](linux-install-manually.md) <br> [人形](linux-install-with-puppet.md) <br> [アンシブル](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft エンドポイント マネージャー](ios-install.md)               |
| **Android**  | [Microsoft エンドポイント マネージャー](android-intune.md)            | 


> [!NOTE]
> Microsoft エンドポイント マネージャー (Microsoft Intune または Microsoft Endpoint Configuration Manager) によって管理されていないデバイスの場合は、セキュリティ管理を使用してMicrosoft Defender for Endpoint Microsoft Defender のセキュリティ構成をエンドポイント マネージャーから直接受信できます。

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールの一覧を示します。

## <a name="configure-capabilities-of-the-service"></a>サービスの機能を構成する
デバイスをオンボードすると、Microsoft Defender for Endpointのエンドポイント検出と応答機能が効果的に有効になります。

デバイスをオンボードした後、サービスの他の機能を構成する必要があります。 次の表に、環境に最適な保護を得るために構成できる機能の一覧を示します。

| 機能 | 説明 |
|-|-|
| [脅威&脆弱性管理 (TVM) を構成する](tvm-prerequisites.md) | 脅威&脆弱性管理は、Microsoft Defender for Endpointのコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に、次のような一意の価値を提供します。 <br><br> - エンドポイントの脆弱性と関連付けられたリアルタイムのエンドポイント検出と応答 (EDR) の分析情報。 <br><br> - インシデント調査中の非常に貴重なデバイスの脆弱性コンテキスト。 <br><br> - Microsoft Intuneと Microsoft System Center Configuration Managerによる組み込みの修復プロセス。  |
| [次世代保護 (NGP) を構成する](configure-microsoft-defender-antivirus-features.md) | Microsoft Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、およびサーバーに次世代の保護を提供する組み込みのマルウェア対策ソリューションです。 Microsoft Defender ウイルス対策には、次のものが含まれます。<br> <br>-クラウドによって提供される、新しい脅威と新しい脅威のほぼ瞬時の検出とブロックのための保護。 機械学習やインテリジェント セキュリティ グラフに加えて、クラウドによる保護は Microsoft Defender ウイルス対策を強化する次世代テクノロジの一部です。<br> <br> - 高度なファイルとプロセス動作の監視とその他のヒューリスティック ("リアルタイム保護" とも呼ばれます) を使用した常時オンスキャン。<br><br> - 機械学習、人間と自動化されたビッグ データ分析、詳細な脅威対策の研究に基づく専用の保護更新。 |
| [攻撃面の削減 (ASR) を構成する](overview-attack-surface-reduction.md) | Microsoft Defender for Endpointの攻撃面の縮小機能は、組織内のデバイスとアプリケーションを新しい脅威や新しい脅威から保護するのに役立ちます。 |
| [自動調査&修復 (AIR) 機能を構成する](configure-automated-investigations-remediation.md) | Microsoft Defender for Endpointでは、自動調査を使用して、個別に調査する必要があるアラートの量を大幅に減らします。 自動調査機能は、さまざまな検査アルゴリズムと、アナリスト (プレイブックなど) によって使用されるプロセスを利用して、アラートを調べ、侵害を解決するための直ちに修復アクションを実行します。 これにより、アラート量が大幅に削減され、セキュリティ運用の専門家は、より高度な脅威やその他の価値の高い業務に集中できるようになります。 |
| [Microsoft 脅威エキスパート (MTE) 機能を構成する](configure-microsoft-threat-experts.md) | Microsoft 脅威エキスパートは、セキュリティ オペレーション センター (SOC) に専門家レベルの監視と分析を提供するマネージド ハンティング サービスであり、固有の環境で重大な脅威が見逃されないように支援します。      |


## <a name="supported-capabilities-for-windows-devices"></a>Windows デバイスでサポートされている機能

|オペレーティング システム  |Windows 10 & 11  |Windows Server 2012 R2 <sup>[[1](#fn1)]<sup></sup>  |<sup>Windows Server 2016[[1](#fn1)]<sup></sup>   |Windows Server 2019 & 2022|Windows Server 1803 以降|
|---------|---------|---------|---------|---------|---------|
|**防止**    |         |         |         |         |         |
|攻撃面の縮小ルール     |    Y     |   Y      |    Y     |    Y     |    Y     |
|デバイス コントロール     |     Y    |    N     |    N     |    N     |    N     |  
|ファイアウォール     |      Y   |    Y     |     Y    |    Y    |    Y   |
|ネットワーク保護     |      Y   |    Y     |     Y    |    Y    |    Y   |
|次世代の保護     |      Y   |    Y     |     Y    |    Y    |    Y   |
|改ざん防止     |        Y   |    Y     |     Y    |    Y    |    Y   |
|Web Protection     |       Y   |    Y     |     Y    |    Y    |    Y   |
|||||||
|**検出**     |         |         |         |||
|高度なハンティング     |      Y   |    Y     |     Y    |    Y    |    Y   |
|カスタム ファイル インジケーター     |      Y   |    Y     |     Y    |    Y    |    Y   |
|カスタム ネットワーク インジケーター     |      Y   |    Y     |     Y    |    Y    |    Y   |
|パッシブ モード& EDR ブロック     |      Y   |    Y     |     Y    |    Y    |    Y   |
|センス検出センサー     |      Y   |    Y     |     Y    |    Y    |    Y   |
|エンドポイント&ネットワーク デバイス検出     |      Y   |    N     |     N    |    N    |    N   |
|||||||
|**Response**     |         |         |         |||
|自動調査&応答 (AIR)    |      Y   |    Y     |     Y    |    Y    |    Y   |
|デバイス応答機能: 分離、調査パッケージの収集、AV スキャンの実行     |      Y   |    Y     |     Y    |    Y    |    Y   |
|ファイル応答機能: ファイルの収集、詳細な分析、ファイルのブロック、停止、検疫のプロセス     |      Y   |    Y     |     Y    |    Y    |    Y   |
|ライブ応答    |      Y   |    Y     |     Y    |    Y    |    Y   |

(<a id="fn1">1</a>) Windows Server 2012 R2 と 2016 の最新の統合ソリューションを参照します。 詳細については、「 [Defender for Endpoint サービスへの Windows サーバーのオンボード」を](configure-server-endpoints.md)参照してください。

>[!NOTE]
>Windows 7、8.1、Windows Server 2008 R2 には、System Center Endpoint Protection (SCEP) を使用した EDR センサーと AV のサポートが含まれています。
