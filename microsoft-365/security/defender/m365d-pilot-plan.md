---
title: パイロット Microsoft 365 Defender プロジェクトの計画
description: 関係者とパイロット Microsoft 365 Defender プロジェクトを計画し、期待を管理し、成果を確実に得られるようにします。
keywords: Microsoft 365 Defenderパイロット、パイロット Microsoft 365 Defender プロジェクトの計画、運用環境でのMicrosoft 365 Defenderの評価、Microsoft 365 Defender パイロット プロジェクト, サイバー セキュリティ, 高度な永続的な脅威, エンタープライズ セキュリティ, デバイス, デバイス, ID, ユーザー, データ, アプリケーション, インシデント, 自動調査と修復, 高度な捜索
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
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>パイロット Microsoft 365 Defender プロジェクトの計画 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

|![計画](../../media/phase-diagrams/1-planning.png)<br/>計画|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[準備](prepare-m365d-eval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[攻撃のシミュレーション](m365d-pilot-simulate.md) | [![閉じて要約する](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[閉じて要約する](m365d-pilot-close.md)|
|--|--|--|--|
|*お客様はここにいます。*| | | |

現在、計画段階です。

パイロット プロジェクトが確実に成功するためには、最初に関係者に十分な計画を立て、承認を得ることが不可欠です。 計画の要素には、スコープ、ユース ケース、要件、成功基準の特定が含まれます。

このガイドでは、パイロット プロジェクトを計画する方法について説明します。 

>[!IMPORTANT]
>最適な結果を得るには、できるだけ詳しくパイロットの指示に従ってください。


## <a name="scope"></a>範囲

パイロットの範囲は、環境と許容できるテスト方法に基づいて、テストの範囲を決定します。 考慮すべきスコープの例を次に示します。

- エンドポイント、サーバー、ドメイン コントローラーを含む開発環境またはテスト環境。
- Microsoft 365、Azure、Active Directory サービス、エンドポイント、およびサーバーを使用する運用環境

>[!NOTE]
>完全なライセンスがまだない場合は、パイロット プロジェクトの計画、準備、セットアップ、構成、実行[Microsoft 365 Defenderを評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)するための試用版ライセンスを取得できます。 関係者は、プロセスを最初から最後まで円滑に進めるうえで大きな役割を果たします。

評価するオペレーティング システムの種類も、組織の構成に基づいて定義する必要があります。 これには、[Mac エンドポイント](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)、[Linux サーバー](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、[Windows 10 エンドポイント](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)、[Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)などがあります。

## <a name="use-cases"></a>使用例

ユース ケースは、テスト対象のツールが意図したユーザーによって使用される方法に関するステートメントを表します。 これらは、SOC アナリストなど、特定のペルソナの観点からユーザー ストーリーとして作成できます。 例:

- SOC アナリストとして、ネットワーク内のデバイス、ユーザー、メールボックス間でアラートとイベントを表示、関連付け、評価、管理する必要があります。 [インシデント管理]
- SOC アナリストとして、ネットワーク内の悪意のあるイベントを自動的に調査して対応するためのツールとプロセスが必要です。 [自動 IR]
- SOC アナリストとして、既知の潜在的な脅威や疑わしいアクティビティを見つけるために、環境からデータを検索する必要があります。 [高度なハンティング]

これらのユース ケースは、定義されたスコープのパラメーター内に作成する必要があることに注意してください。 たとえば、テストの範囲にMicrosoft Cloud App Securityなどのツールの評価が含まれていない場合は、これをデータ ソースとして使用するユース ケースを作成しないでください。

## <a name="requirements"></a>要件

ユース ケースの一覧から、要件の作成を開始できます。 要件には、ツールがユース ケースを満たすために必要な機能が含まれます。 これらの要件は、構成とメンテナンス、統合のサポート、ハンティング機能やカスタム アラートを作成する機能などの機能固有の要件などのカテゴリに分類できます。

## <a name="test-plan"></a>テスト計画

要件に応じて、さまざまなテスト方法が適切な場合があります。 たとえば、自動修復の有効性を評価することが要件である場合、テスト計画には、Microsoft 365 Defender内で自動修復アクションをトリガーする動作を生成する手順を含める必要があります。 要件が特定の動作または攻撃を検出する場合、テストにはより多くの手順が含まれる可能性があります。 ポイントは、要件に対して正確にテストする計画を立てる必要があります。

## <a name="success-criteria"></a>成功条件

最終的に、成功基準は、テスト対象に対して測定するバー セットです。 他のツールに対してMicrosoft 365 Defender (またはその他のテクノロジ) をテストする場合でも、単独でテストする場合でも、ツールが提供する値を決定するための定量化可能な基準が必要です。 スコープ、要件、およびテスト計画に基づいて、成功基準によってテストのスコア付け方法が決定されます。 これは、パスまたは失敗の数を減らし、ニーズに基づいて重み付けスコアリングの多くを行う必要があります。 たとえば、成功するには、特定の重要な領域でツールのスコアが 80% を超える必要がある場合があります。

## <a name="scorecard"></a>スコアカード

プランのすべての要素をまとめる 1 つの方法は、スコアカードを作成することです。 以下のサンプル スコアカードを参照してください。

| ユース ケース | 要件 | 構成要件 | テスト計画 | 予想結果 | テストの状態 | スコア | 備考 |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|インシデント管理|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender for Endpoint </br></br>- Microsoft Cloud App Security (省略可能)|詳細については、準備、セットアップ、および構成の [前提条件](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) を参照してください。 |[攻撃のシミュレーション](m365d-pilot-simulate.md) <br></br>[インシデントを調査する](./m365d-pilot-simulate.md#investigate-an-incident) |調査担当者は、インシデントの範囲と影響を理解し、インシデントを管理できます||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender for Endpoint |詳細については、準備、セットアップ、および構成の [前提条件](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) を参照してください。 <br>AutoIR を有効にする  |[攻撃のシミュレーション](m365d-pilot-simulate.md) <br></br>[自動調査](m365d-pilot-simulate.md#automated-investigation-and-remediation) |アラートとインシデントは、Microsoft 365 Defenderによって自動的に修復されます||||
|高度な追及|- Microsoft 365 Defender </br></br>- Microsoft Defender for Endpoint </br></br>-Microsoft Defender for Office 365 |詳細については、準備、セットアップ、および構成の [前提条件](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) を参照してください。|[高度なハンティング シナリオ](./m365d-pilot-simulate.md#advanced-hunting-scenario) |調査担当者は、高度な捜索、影響を受けるエンティティへのピボット、カスタム検出の作成を通じてデータを見つけることができます||||

## <a name="next-step"></a>次の手順

|![準備フェーズ](../../media/mtp/prep.png) <br>[準備フェーズ](prepare-m365d-eval.md) | Microsoft 365 Defenderパイロット環境を準備する
|:-------|:-----|
