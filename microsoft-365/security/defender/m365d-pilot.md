---
title: パイロット プロジェクトをMicrosoft 365 Defenderする
description: 実稼働環境でパイロット Microsoft 365 Defenderプロジェクトを実行して、プロジェクトのメリットと導入を効果的にMicrosoft 365 Defender。
keywords: Microsoft 365 Defenderパイロット、パイロット Microsoft 365 Defender プロジェクトの実行、実稼働での Microsoft 365 Defender の評価、Microsoft 365 Defender パイロット プロジェクト、サイバーセキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458417"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>パイロット プロジェクトをMicrosoft 365 Defenderする 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、パイロット プロジェクトを実行する場合に役立ちます。ポインターを使用して、適切に構造化された計画を作成し、攻撃シミュレーション機能を使用してガイドし、最終的にパイロットに主なテイクアウェイを設定して結果を反映して文書化します。

![パイロットの実行Microsoft 365 Defenderフェーズ](../../media/pilotphases.png)


パイロットを実行すると、パイロットを採用するメリットを効果的にMicrosoft 365 Defender。 実稼働環境Microsoft 365 Defenderを有効にし、使用例を開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功基準を設定してください。 


## <a name="how-to-use-this-pilot-playbook"></a>このパイロット プレイブックの使い方

このガイドでは、パイロット プロジェクトMicrosoft 365 Defenderの手順と手順の概要を説明します。 

Microsoft 365 Defender は、エンドポイント、ID、電子メール、およびアプリケーション間で保護、検出、防止、調査、応答をネイティブに調整し、高度な攻撃に対する統合保護を提供する統合された侵害前および侵害後のエンタープライズ防御スイートです。 これは、次の機能を 1 つのセキュリティ ソリューションに組み合わせて調整することで行います。

- エンドポイント用 Microsoft Defender (エンドポイント)
- Microsoft Defender for Office 365 (メール)
- Microsoft Defender for Identity (IDENTITY)
- Microsoft Cloud App Security (アプリ)

![イメージ of_Microsoftユーザー向け 365 Defender ソリューション、Microsoft Defender for Identity、エンドポイント用 Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データの場合は Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ専門家は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、および Microsoft Cloud App Security が受け取る脅威信号をまとめ、脅威の全範囲と影響、環境への影響、影響を受ける環境への影響、組織に対する現在の影響を判断できます。 Microsoft 365 Defender攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復する自動アクションを実行します。 詳細については[、「Microsoft 365 Defender概要」](microsoft-365-defender.md)を参照してください。

次のサンプル タイムラインは、環境に適切なリソースを持つことによって異なります。 検出とワークフローによっては、他の検出よりも多くの学習時間が必要になる場合があります。

![パイロットの実行に関するタイムラインMicrosoft 365 Defender例](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> 最適な結果を得る場合は、パイロットの指示に従ってください。

### <a name="pilot-playbook-phases"></a>パイロット プレイブックのフェーズ

パイロットの実行には 4 つのMicrosoft 365 Defenderがあります。

|段階 | 説明 |
|:-------|:-----|
| [計画](m365d-pilot-plan.md)<br> ~ 1 日| パイロット プロジェクトを実行する前に考慮する必要Microsoft 365 Defender確認します。 <br><br>- スコープ <br> - 使用例 <br>- 要件 <br>- テスト計画 <br> - 成功条件 <br> - スコアカード 
| [準備](m365d-evaluation.md) <br>~2 日間|  セキュリティ Microsoft 365にアクセスして、パイロット環境Microsoft 365 Defender設定します。 次の情報に案内されます。<br><br>- 利害関係者を特定し、パイロットのサインオフを求める <br> - 環境に関する考慮事項 <br>- Access <br>- Azure Active Directoryセットアップ <br> - 構成順序 <br> - 試用版にMicrosoft 365 E5する <br> - ドメインの構成 <br>- ライセンスMicrosoft 365 E5割り当てる <br> - ポータルでセットアップ ウィザードを完了する|
| [攻撃シミュレーション](m365d-pilot-simulate.md) <br>~2 日間| 攻撃をシミュレートするには、次の情報に案内されます。<br><br>- テスト環境の要件を確認する <br>- シミュレーションを実行する <br>- インシデントを調査する <br>- インシデントを解決する 
| [閉じると概要](m365d-pilot-close.md) <br>~ 1 日| プロセスの最後に達すると、次の手順に案内されます。<br><br>- 最終的な出力を確認する<br>- 出力を関係者に提示する <br>- フィードバックを提供する <br>- 次の手順を実行する 

## <a name="next-step"></a>次の手順

|[計画フェーズ](m365d-pilot-plan.md) | パイロット プロジェクトMicrosoft 365 Defender計画する 
|:-------|:-----|
