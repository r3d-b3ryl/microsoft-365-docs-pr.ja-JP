---
title: パイロット プロジェクトの計画Microsoft 365 Defenderする
description: パイロット プロジェクトを計画Microsoft 365 Defender、期待を管理し、成功した結果を確実に達成します。
keywords: Microsoft 365 Defenderパイロット、パイロット Microsoft 365 Defender プロジェクトの計画、Microsoft 365 Defender パイロット プロジェクトの評価、Microsoft 365 Defender パイロット プロジェクト、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6a52df8035ce6f84770a2d06c3b8c127e426622e
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458433"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>パイロット プロジェクトの計画Microsoft 365 Defenderする 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

|![計画](../../media/phase-diagrams/1-planning.png)<br/>計画|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[準備](prepare-m365d-eval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[攻撃のシミュレーション](m365d-pilot-simulate.md) | [![閉じて要約する](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[閉じて要約する](m365d-pilot-close.md)|
|--|--|--|--|
|*お前はここにいる!*| | | |

現在、計画段階です。

パイロット プロジェクトが成功を収めるには、最初に利害関係者の承認を得て計画を立て、承認を得る必要があります。 計画の要素には、範囲、使用例、要件、成功基準の識別が含まれます。

このガイドでは、パイロット プロジェクトを計画する方法を示します。 

>[!IMPORTANT]
>最適な結果を得る場合は、パイロットの指示に従ってください。


## <a name="scope"></a>範囲

パイロットの範囲は、環境と許容可能なテスト方法に基づいて、テストの範囲を決定します。 考慮すべきスコープの例を次に示します。

- エンドポイント、サーバー、ドメイン コントローラーを含む開発またはテスト環境。
- Microsoft 365、Azure、Active Directory サービス、エンドポイント、およびサーバーを備える実稼働環境

>[!NOTE]
>完全なライセンスがまだない場合は、パイロット プロジェクトの計画、準備、セットアップ[](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、構成、実行など、Microsoft 365 Defender を評価するための試用版ライセンスを取得できます。 関係者は、最初から最後までプロセスを円滑に進める上で大きな役割を果たします。

評価するオペレーティング システムの種類も、組織の構成に基づいて定義する必要があります。 これには[、Mac](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)エンドポイント[、Linux サーバー](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、Windows 10[エンドポイント](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)、Windows Server 2016[があります](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)。

## <a name="use-cases"></a>使用例

使用例は、テスト対象のツールが意図したユーザーによって使用される方法のステートメントを表します。 これらは、SOC アナリストなど、特定のペルソナの観点からユーザー ストーリーとして策定できます。 次に例を示します。

- SOC アナリストとして、ネットワーク内のデバイス、ユーザー、メールボックス間でアラートとイベントを表示、関連付け、評価、管理する必要があります。 [インシデント管理]
- SOC アナリストとして、ネットワーク内の悪意のあるイベントを自動的に調査して対応するツールとプロセスが必要です。 [Auto IR]
- SOC アナリストとして、既知の脅威や潜在的な脅威、疑わしいアクティビティを見つけるために、環境からデータを検索する必要があります。 [高度なハンティング]

これらの使用例は、定義されたスコープのパラメーター内に作成する必要があります。 たとえば、テストの範囲に Microsoft Cloud App Security などのツールの評価が含まれる場合は、これをデータ ソースとして使用する使用例を作成できません。

## <a name="requirements"></a>要件

使用例の一覧から、要件の作成を開始できます。 要件には、ツールが使用例を満たす必要がある機能が含まれます。 これらの要件は、構成やメンテナンス、統合のサポート、ハンティング機能やカスタム アラートの作成機能などの機能固有の要件などのカテゴリに分類できます。

## <a name="test-plan"></a>テスト計画

要件に応じて、さまざまなテスト方法が適切な場合があります。 たとえば、自動修復の有効性を評価する必要がある場合、テスト 計画には、Microsoft 365 Defender 内で自動修復アクションをトリガーする動作を生成するための手順を含める必要があります。 特定の動作または攻撃を検出する必要がある場合、テストにはさらに多くの手順が含まれる場合があります。 重要な点は、要件に対して正確にテストする計画を立て込む方法です。

## <a name="success-criteria"></a>成功条件

成功の条件は、最終的には、テスト中のテストに対して測定するバー セットです。 他のツールに対してMicrosoft 365 Defender (または他のテクノロジ) をテストする場合でも、それ自体でテストする場合でも、ツールが提供する値を決定するには、いくつかの定量化可能な条件が必要です。 スコープ、要件、およびテスト計画に基づいて、成功条件によってテストのスコア付け方法が決定されます。 これは、パスまたは失敗の少ない値で、ニーズに基づいて重み付けスコアリングを行う必要があります。 たとえば、成功するには、特定の重要な領域でツールで 80% を超えるスコアが必要になる場合があります。

## <a name="scorecard"></a>スコアカード

プランのすべての要素をまとめる方法の 1 つは、スコアカードを作成する方法です。 以下のスコアカードのサンプルを参照してください。

| ユース ケース | 要件 | 構成要件 | テスト計画 | 予想結果 | テストの状態 | スコア | メモ |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|インシデント管理|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- エンドポイント用 Microsoft Defender </br></br>- Microsoft Cloud App Security (オプション)|詳細については [、「準備](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 、セットアップ、および構成の前提条件」を参照してください。 |[攻撃のシミュレーション](m365d-pilot-simulate.md) <br></br>[インシデントの調査](./m365d-pilot-simulate.md#investigate-an-incident) |調査担当者は、インシデントの範囲と影響を理解し、インシデントを管理できます。||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- エンドポイント用 Microsoft Defender |詳細については [、「準備](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 、セットアップ、および構成の前提条件」を参照してください。 <br>自動IR を有効にする  |[攻撃のシミュレーション](m365d-pilot-simulate.md) <br></br>[自動調査](m365d-pilot-simulate.md#automated-investigation-and-remediation) |アラートとインシデントは、ユーザーが自動的に修復Microsoft 365 Defender||||
|高度な追及|- Microsoft 365 Defender </br></br>- エンドポイント用 Microsoft Defender </br></br>-Microsoft Defender for Office 365 |詳細については [、「準備](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 、セットアップ、および構成の前提条件」を参照してください。|[高度なハンティング シナリオ](./m365d-pilot-simulate.md#advanced-hunting-scenario) |調査担当者は、高度な検索、影響を受け取ったエンティティへのピボット、およびカスタム検出の作成を通じてデータを検索できます。||||

## <a name="next-step"></a>次の手順

|![準備フェーズ](../../media/mtp/prep.png) <br>[準備フェーズ](prepare-m365d-eval.md) | パイロット環境Microsoft 365 Defender準備する
|:-------|:-----|
