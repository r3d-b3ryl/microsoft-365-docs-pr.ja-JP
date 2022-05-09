---
title: パイロット Microsoft 365 Defender プロジェクトを実行する
description: パイロット Microsoft 365 Defender プロジェクトを運用環境で実行して、Microsoft 365 Defenderの利点と導入を効果的に決定します。
keywords: パイロットMicrosoft 365 Defender、パイロット Microsoft 365 Defender プロジェクトの実行、運用環境でのMicrosoft 365 Defenderの評価、Microsoft 365 Defender パイロット プロジェクト, サイバー セキュリティ, 高度な永続的な脅威, エンタープライズ セキュリティ, デバイス, デバイス, ID, ユーザー, データ, アプリケーション, インシデント, 自動調査と修復, 高度な捜索
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
# <a name="run-your-pilot-microsoft-365-defender-project"></a>パイロット Microsoft 365 Defender プロジェクトを実行する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、適切に構造化された計画を持っていることを確認するためのポインターを提供し、攻撃シミュレーション機能を使用してガイドを作成し、最終的にパイロットに重要な引き取りを結び付けて結果を反映し、文書化することで、パイロット プロジェクトを実行するのに役立ちます。

![Microsoft 365 Defender パイロットを実行するフェーズ](../../media/pilotphases.png)


パイロットを実行すると、Microsoft 365 Defenderを採用する利点を効果的に判断できます。 運用環境でMicrosoft 365 Defenderを有効にしてユース ケースを開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功条件を設定することを計画することをお勧めします。 


## <a name="how-to-use-this-pilot-playbook"></a>このパイロット プレイブックを使用する方法

このガイドでは、パイロット プロジェクトを設定する方法に関するMicrosoft 365 Defenderと詳細な手順の概要について説明します。 

Microsoft 365 Defenderは、高度な攻撃に対する統合された保護を提供するために、エンドポイント、ID、電子メール、アプリケーション全体の保護、検出、防止、調査、および応答をネイティブに調整する、侵害前および侵害後の統合エンタープライズ防御スイートです。 これは、次の機能を 1 つのセキュリティ ソリューションに組み合わせて調整することによって行われます。

- Microsoft Defender for Endpoint (エンドポイント)
- Microsoft Defender for Office 365 (電子メール)
- Microsoft Defender for Identity (ID)
- Microsoft Cloud App Security (アプリ)

![ユーザー、Microsoft Defender for Identity、エンドポイント Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データ用の 365 Defender ソリューションof_MicrosoftイメージMicrosoft Defender for Office 365](../../media/mtp/m365pillars.png)

統合されたMicrosoft 365 Defender ソリューションを使用すると、セキュリティプロフェッショナルは、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、および脅威の完全な範囲と影響、環境への侵入方法、影響、組織への現在の影響をMicrosoft Defender for Identityし、Microsoft Cloud App Security受け取り、決定します。 Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己修復する自動アクションを実行します。 詳細については、[Microsoft 365 Defenderの概要](microsoft-365-defender.md)を参照してください。

次のサンプル タイムラインは、環境内に適切なリソースがある場合に応じて異なります。 検出とワークフローによっては、他の検出よりも多くの学習時間が必要になる場合があります。

![Microsoft 365 Defender パイロットの実行におけるサンプル タイムライン](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> 最適な結果を得るには、できるだけ詳しくパイロットの指示に従ってください。

### <a name="pilot-playbook-phases"></a>パイロット プレイブック フェーズ

Microsoft 365 Defender パイロットの実行には、次の 4 つのフェーズがあります。

|段階 | 説明 |
|:-------|:-----|
| [計画](m365d-pilot-plan.md)<br> ~ 1 日| Microsoft 365 Defender パイロット プロジェクトを実行する前に考慮する必要がある点について説明します。 <br><br>- スコープ <br> - ユース ケース <br>- 要件 <br>- テスト計画 <br> - 成功条件 <br> - スコアカード 
| [準備](m365d-evaluation.md) <br>~2 日間|  Security Center Microsoft 365アクセスして、Microsoft 365 Defenderパイロット環境を設定します。 次の手順に従います。<br><br>- 関係者を特定し、パイロットのサインオフを求める <br> - 環境に関する考慮事項 <br>- アクセス <br>- Azure Active Directoryセットアップ <br> - 構成順序 <br> - Microsoft 365 E5試用版にサインアップする <br> - ドメインを構成する <br>- Microsoft 365 E5 ライセンスを割り当てる <br> - ポータルでセットアップ ウィザードを完了する|
| [攻撃シミュレーション](m365d-pilot-simulate.md) <br>~2 日間| 攻撃をシミュレートするには、次の手順に従います。<br><br>- テスト環境の要件を確認する <br>- シミュレーションを実行する <br>- インシデントを調査する <br>- インシデントを解決する 
| [終了と概要](m365d-pilot-close.md) <br>~ 1 日| プロセスの終わりに達すると、次の手順に従います。<br><br>- 最終的な出力を確認する<br>- 利害関係者に出力を表示する <br>- フィードバックを提供する <br>- 次の手順を実行する 

## <a name="next-step"></a>次の手順

|[計画フェーズ](m365d-pilot-plan.md) | Microsoft 365 Defenderパイロット プロジェクトを計画する 
|:-------|:-----|
