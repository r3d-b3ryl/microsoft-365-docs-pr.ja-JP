---
title: パイロット Microsoft Defender for Endpoint
description: パイロット グループの検証や機能の試用など、Microsoft Defender for Endpoint (MDE) のパイロットを実行する方法について説明します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c12d1bca36884a7b43580b0685f38df99e51ba1d
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750409"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>パイロット Microsoft Defender for Endpoint

この記事では、Microsoft Defender for Endpointのパイロットを実行するプロセスについて説明します。 

次の手順に従って、Microsoft Defender for Endpointのパイロットをセットアップして構成します。 

:::image type="content" source="../../media/defender/m365-defender-endpoint-pilot-steps.png" alt-text="Microsoft Defender 評価環境にMicrosoft Defender for Identityを追加する手順" lightbox="../../media/defender/m365-defender-endpoint-pilot-steps.png":::

- 手順 1. パイロット グループを確認する
- 手順 2。 機能を試す

Microsoft Defender for Endpointをパイロットする場合は、組織全体をオンボードする前に、いくつかのデバイスをサービスにオンボードすることもできます。  

その後、攻撃シミュレーションの実行、Defender for Endpoint による悪意のあるアクティビティの表示方法、効率的な対応を可能にする方法など、使用可能な機能を試すことができます。 

## <a name="step-1-verify-pilot-group"></a>手順 1. パイロット グループを確認する
[[評価を有効にする]](eval-defender-endpoint-enable-eval.md) セクションで説明されているオンボード手順を完了すると、約 1 時間後にデバイス インベントリの一覧にデバイスが表示されます。 

オンボードされたデバイスが表示されたら、機能の試用に進むことができます。 

## <a name="step-2-try-out-capabilities"></a>手順 2。 機能を試す
一部のデバイスのオンボードが完了し、サービスに報告されていることを確認したので、すぐに使用できる強力な機能を試して、製品に慣れ親しみます。

パイロットの間は、複雑な構成手順を実行せずに、一部の機能を簡単に試して製品の動作を確認できます。

ダッシュボードを確認することから始めましょう。

### <a name="view-the-device-inventory"></a>デバイス インベントリを表示する
デバイス インベントリには、ネットワーク内のエンドポイント、ネットワーク デバイス、IoT デバイスの一覧が表示されます。 ネットワーク内のデバイスのビューが提供されるだけでなく、ドメイン、リスク レベル、OS プラットフォームなどの詳細な情報も提供され、最も危険にさらされているデバイスを簡単に識別できます。

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>脅威と脆弱性の管理ダッシュボードを表示する 
脅威と脆弱性の管理は、組織にとって最も緊急でリスクの高い弱点に焦点を当てるのに役立ちます。 ダッシュボードから、組織の公開スコア、Microsoft Secure Score for Devices、デバイスの公開分布、セキュリティに関する推奨事項、脆弱なソフトウェアの上位、修復アクティビティの上位、および公開された上位デバイス データの概要を確認します。 

### <a name="run-a-simulation"></a>シミュレーションを実行する
Microsoft Defender for Endpointには、パイロット デバイスで実行できる ["Do It Yourself" 攻撃シナリオ](https://securitycenter.windows.com/tutorials)が付属しています。  各ドキュメントには、OS とアプリケーションの要件、および攻撃シナリオに固有の詳細な手順が含まれています。 これらのスクリプトは、安全で文書化されており、使いやすいです。 これらのシナリオでは、Defender for Endpoint 機能が反映され、調査エクスペリエンスについて説明します。

指定されたシミュレーションのいずれかを実行するには、少なくとも [1 台のオンボードデバイスが必要です](../defender-endpoint/onboard-configure.md)。

1. **ヘルプ** > **シミュレーション&チュートリアル** で、シミュレートする使用可能な攻撃シナリオを選択します。

   - **シナリオ 1: ドキュメントがバックドアを削除** する - ソーシャルに設計されたルアー ドキュメントの配信をシミュレートします。 このドキュメントは、攻撃者に制御を与える特別に作成されたバックドアを起動します。

   - **シナリオ 2: ファイルレス攻撃の PowerShell スクリプト - PowerShell** に依存するファイルレス攻撃をシミュレートし、攻撃面の削減と悪意のあるメモリ アクティビティのデバイスラーニング検出を示します。

   - **シナリオ 3: 自動インシデント対応** - 自動調査がトリガーされます。これにより、侵害アーティファクトを自動的に検出および修復して、インシデント対応能力をスケーリングします。

2. 選択したシナリオで提供されている対応するチュートリアル ドキュメントをダウンロードして読み取ります。

3. シミュレーション ファイルをダウンロードするか、ヘルプ **シミュレーション&チュートリアル****に移動** して > シミュレーション スクリプトをコピーします。 テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。

4. チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。

> [!NOTE]
> シミュレーション ファイルまたはスクリプトは攻撃アクティビティを模倣しますが、実際には無害であり、テスト デバイスに害を与えたり侵害したりすることはありません。

## <a name="next-steps"></a>次の手順
[Microsoft Defender for Cloud Appsを評価する](eval-defender-mcas-overview.md)

[Microsoft Defender for Endpointの評価](eval-defender-endpoint-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
