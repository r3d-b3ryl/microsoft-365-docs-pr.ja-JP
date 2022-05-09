---
title: シミュレートされた攻撃を通じてMicrosoft Defender for Endpointを体験する
description: 提供された攻撃シナリオ シミュレーションを実行して、Microsoft Defender for Endpointが侵害を検出、調査、および対応する方法を体験します。
keywords: テスト, シナリオ, 攻撃, シミュレーション, シミュレート, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: da02e1391b7624dc3e091ca1024a68c5756227a2
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171223"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>シミュレートされた攻撃を通じてMicrosoft Defender for Endpointを体験する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)

> [!TIP]
>
> - Microsoft Defender for Endpointの最新の機能強化について説明します。[Defender for Endpoint の新機能](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。
> - 最近の MITRE 評価において、Defender for Endpoint の業界をリードする分析力と検出能力が示されました。詳しくは、「[MITRE ATT&CK ベース評価の分析](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)」を参照してください。

複数のデバイスをサービスにオンボードする前に、Defender for Endpoint を体験したい場合があります。 これを行うには、いくつかのテスト デバイスで制御された攻撃シミュレーションを実行できます。 シミュレートされた攻撃を実行した後、Defender for Endpoint が悪意のあるアクティビティを表示する方法を確認し、効率的な対応を可能にする方法を調べることができます。

## <a name="before-you-begin"></a>開始する前に

指定されたシミュレーションのいずれかを実行するには、少なくとも [1 台のオンボードデバイスが必要です](onboard-configure.md)。

各攻撃シナリオで提供されるチュートリアル ドキュメントをお読みください。 各ドキュメントには、OS とアプリケーションの要件、および攻撃シナリオに固有の詳細な手順が含まれています。

## <a name="run-a-simulation"></a>シミュレーションを実行する

1. **Endpoints** \> **Evaluation & チュートリアル** \> **& シミュレーション** で、シミュレートする使用可能な攻撃シナリオを選択します。
   - **シナリオ 1: ドキュメントがバックドアを削除** する - ソーシャルに設計されたルアー ドキュメントの配信をシミュレートします。 このドキュメントは、攻撃者に制御を与える特別に作成されたバックドアを起動します。
   - **シナリオ 2: ファイルレス攻撃の PowerShell スクリプト - PowerShell** に依存するファイルレス攻撃をシミュレートし、攻撃面の削減と悪意のあるメモリ アクティビティのデバイスラーニング検出を示します。
   - **シナリオ 3: 自動インシデント対応** - 自動調査がトリガーされます。これにより、侵害アーティファクトを自動的に検出および修復して、インシデント対応能力をスケーリングします。

2. 選択したシナリオで提供されている対応するチュートリアル ドキュメントをダウンロードして読み取ります。

3. シミュレーション ファイルをダウンロードするか、評価 **&チュートリアル**\>チュートリアル **&シミュレーション** に移動してシミュレーション スクリプトをコピーします。 テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。

4. チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。

> [!NOTE]
> シミュレーション ファイルまたはスクリプトは攻撃アクティビティを模倣しますが、実際には無害であり、テスト デバイスに害を与えたり侵害したりすることはありません。
>
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [デバイスのオンボード](onboard-configure.md)
- [Windows デバイスのオンボード](configure-endpoints.md)
