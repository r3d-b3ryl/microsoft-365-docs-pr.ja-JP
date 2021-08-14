---
title: シミュレートされた攻撃を通じて Microsoft Defender for Endpoint を体験する
description: 提供された攻撃シナリオシミュレーションを実行して、Microsoft Defender for Endpoint が侵害を検出、調査、および対応する方法を体験します。
keywords: test, scenario, attack, Simulation, simulationed, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 4c79d3b1d53a046772ee84c809aab96bff5ae762c0e946000e11d5f8f46a9de0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53818745"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>シミュレートされた攻撃を通じて Microsoft Defender for Endpoint を体験する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)

> [!TIP]
>
> - Microsoft Defender for Endpoint の最新機能拡張: Defender for Endpoint の [新機能について説明します](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。
> - Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。 詳細については、「[MITRE ATT&CK ベース評価の分析](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)」を参照してください。

サービスに複数のデバイスをオンボードする前に、Defender for Endpoint を体験する必要がある場合があります。 これを行うには、いくつかのテスト デバイスで制御攻撃シミュレーションを実行できます。 シミュレートされた攻撃を実行した後、Defender for Endpoint が悪意のあるアクティビティを表面化する方法を確認し、効率的な対応を可能にする方法を確認できます。

## <a name="before-you-begin"></a>はじめに

提供されているシミュレーションのいずれかを実行するには、オンボードデバイスが少なくとも [1 つ必要です](onboard-configure.md)。

各攻撃シナリオで提供されるチュートリアル ドキュメントを読み取る。 各ドキュメントには、OS とアプリケーションの要件、および攻撃シナリオに固有の詳細な手順が含まれています。

## <a name="run-a-simulation"></a>シミュレーションの実行

1. **[Endpoints** Evaluation & チュートリアル &シミュレーション] で、シミュレートする利用可能な攻撃シナリオを  >    >  選択します。
   - **シナリオ 1: ドキュメントドロップバックドア** - ソーシャルエンジニアリングされたルアー ドキュメントの配信をシミュレートします。 このドキュメントは、攻撃者に制御を与える特別に細工されたバックドアを起動します。
   - **シナリオ 2: ファイル** レス攻撃の PowerShell スクリプト - PowerShell に依存するファイルレス攻撃をシミュレートし、攻撃表面の縮小と悪意のあるメモリ アクティビティのデバイス学習検出を示します。
   - **シナリオ 3: インシデント** 対応の自動化 - 自動調査がトリガーされ、侵害アーティファクトを自動的にハントして修復してインシデント対応の容量を拡張します。

2. 選択したシナリオで提供される対応するチュートリアル ドキュメントをダウンロードして読み取る。

3. シミュレーション ファイルをダウンロードするか、シミュレーション スクリプトをコピーするには、評価チュートリアル &シミュレーション&  >  **移動します**。 テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。

4. チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。

> [!NOTE]
> シミュレーション ファイルまたはスクリプトは攻撃アクティビティを模倣しますが、実際には良性であり、テスト デバイスに害を及ぼしたり、危険にさらしたりしません。
>
> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)

## <a name="related-topics"></a>関連トピック

- [デバイスのオンボード](onboard-configure.md)
- [Windows 10 デバイスのオンボード](configure-endpoints.md)
