---
title: パイロット Microsoft 365 Defender プロジェクトの計画
description: 関係者と一緒にパイロット Microsoft 365 Defender プロジェクトを計画し、期待を管理し、成功を確実に達成します。
keywords: Microsoft Threat Protection パイロット、パイロット Microsoft Threat Protection プロジェクトの計画、Microsoft Threat Protection の実稼働における Microsoft Threat Protection の評価、Microsoft Threat Protection パイロット プロジェクト、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜ティング
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930176"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>パイロット Microsoft 365 Defender プロジェクトの計画 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

|![計画](../../media/phase-diagrams/1-planning.png)<br/>計画|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[準備](prepare-mtpeval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[攻撃のシミュレーション](mtp-pilot-simulate.md) | [![閉じて要約する](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[閉じて要約する](mtp-pilot-close.md)|
|--|--|--|--|
|*ここにいます。*| | | |

現在、計画段階です。

パイロット プロジェクトが成功を収めるには、最初に関係者と十分に協力して承認を得る計画を立て、承認を得る必要があります。 計画の要素には、範囲、使用事例、要件、および成功基準の識別が含まれます。

このガイドでは、パイロット プロジェクトを計画する方法を示します。 

>[!IMPORTANT]
>最適な結果を得る場合は、パイロット手順にできる限り近い手順に従ってください。


## <a name="scope"></a>範囲

パイロットの範囲は、環境と許容可能なテスト方法に基づいて、テストの範囲を決定します。 考慮すべきスコープの例を次に示します。
- エンドポイント、サーバー、ドメイン コントローラーを含む開発またはテスト環境。
- Microsoft 365、Azure、Active Directory サービス、エンドポイント、サーバーを使用する実稼働環境

>[!NOTE]
>まだ完全なライセンスを持っていない場合は [、Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) を評価するための試用版ライセンスを取得できます。パイロット プロジェクトの計画、準備、セットアップ、構成、実行を行います。 関係者は、最初から最後までプロセスを円滑に進める上で大きな役割を果たします。

評価するオペレーティング システムの種類も、組織の構成に基づいて定義する必要があります。 これには[、Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)エンドポイント[、Linux サーバー](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [、Windows 10 エンドポイント](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)[、Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)が含まれる場合があります。

## <a name="use-cases"></a>使用例

Use cases represent statements of how the tool being tested is intended users. SOC アナリストなど、特定のペルソナの観点からユーザー ストーリーとして作成できます。 例:
- SOC アナリストとして、ネットワーク内のデバイス、ユーザー、メールボックス全体でアラートとイベントを表示、関連付け、評価、管理する必要があります。 [インシデント管理]
- SOC アナリストとして、ネットワーク内の悪意のあるイベントを自動的に調査して対応するツールとプロセスが必要です。 [自動 IR]
- SOC アナリストとして、環境からデータを検索して、既知の脅威や潜在的な脅威、疑わしいアクティビティを見つける必要があります。 [高度な検索]

これらの使用例は、定義されたスコープのパラメーター内に作成する必要があります。 たとえば、テストの範囲に Microsoft Cloud App Security などのツールの評価が含まれる場合は、これをデータ ソースとして利用する使用例を作成する必要があります。

## <a name="requirements"></a>要件

使用例の一覧から、要件の作成を開始できます。 要件には、ツールが使用事例を満たすために必要な機能が含まれます。 これらの要件は、構成とメンテナンス、統合のサポート、検索機能やカスタム アラートの作成機能などの機能固有の要件などのカテゴリに分類できます。

## <a name="test-plan"></a>テスト計画

要件に応じて、さまざまなテスト方法が適している場合があります。 たとえば、自動化された修復の効果を評価する要件がある場合、テスト計画には、Microsoft 365 Defender 内で自動修復アクションをトリガーする動作を生成する手順を含める必要があります。 特定の動作や攻撃を検出する必要がある場合、テストにはさらに多くの手順が含まれる可能性があります。 要するに、要件に対して正確にテストする計画を立てます。

## <a name="success-criteria"></a>成功条件

成功の条件は、最終的には、テストする項目に対して測定するバー セットです。 他のツールに対して、またはそれ自体に対して Microsoft 365 Defender (またはその他のテクノロジ) をテストする場合でも、ツールが提供する値を決定するための定量化可能な条件が必要です。 範囲、要件、およびテスト計画に基づいて、成功条件によってテストのスコアを付け方が決定されます。 これは、パスまたは失敗の少なく、必要に応じて重み付けスコアリングを多くする必要があります。 たとえば、ツールを成功するには、特定の重要な領域で 80% を超えるスコアが必要になる場合があります。

## <a name="scorecard"></a>スコアカード

プランのすべての要素をまとめる方法の 1 つは、スコアカードを作成する方法です。 以下のサンプル スコアカードを参照してください。

| ユース ケース | 要件 | 構成要件 | テスト計画 | 予想結果 | テストの状態 | スコア | Notes |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|インシデント管理|- Microsoft 365 Defender  </br></br>- Id 用 Microsoft Defender </br></br>- Microsoft Defender for Endpoint </br></br>- Microsoft Cloud App Security (オプション)|詳細については [、準備](https://aka.ms/mtp-trial-lab) 、セットアップ、および構成の前提条件を参照してください。 |[攻撃のシミュレーション](mtp-pilot-simulate.md) <br></br>[インシデントを調査する](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |調査担当者は、インシデントの範囲と影響を理解し、インシデントを管理できます。||||
|AutoIR|- Microsoft 365 Defender </br></br>- Id 用 Microsoft Defender </br></br>- Microsoft Defender for Endpoint |詳細については [、準備](https://aka.ms/mtp-trial-lab) 、セットアップ、および構成の前提条件を参照してください。 <br>AutoIR を有効にする  |[攻撃のシミュレーション](mtp-pilot-simulate.md) <br></br>[自動調査](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |アラートとインシデントは、Microsoft 365 Defender によって自動的に修復されます。||||
|高度な検出|- Microsoft 365 Defender </br></br>- Microsoft Defender for Endpoint </br></br>-Microsoft Defender for Office 365 |詳細については [、準備](https://aka.ms/mtp-trial-lab) 、セットアップ、および構成の前提条件を参照してください。|[高度な検索シナリオ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |調査担当者は、高度な検索、影響を受け取ったエンティティへのピボット、カスタム検出の作成を通じてデータを検索できます。||||



## <a name="next-step"></a>次の手順
|![準備フェーズ](../../media/mtp/prep.png) <br>[準備フェーズ](prepare-mtpeval.md) | Microsoft 365 Defender パイロット環境を準備する
|:-------|:-----|
