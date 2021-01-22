---
title: パイロット Microsoft 365 Defender プロジェクトを実行する
description: 実稼働環境で Microsoft 365 Defender のパイロット プロジェクトを実行し、Microsoft 365 Defender のメリットと導入を効果的に決定します。
keywords: Microsoft Threat Protection パイロット、パイロット Microsoft Threat Protection プロジェクトの実行、Microsoft Threat Protection の実稼働での Microsoft Threat Protection の評価、Microsoft Threat Protection パイロット プロジェクト、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜ティング
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933032"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>パイロット Microsoft 365 Defender プロジェクトを実行する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、十分に構造化された計画を立て、攻撃シミュレーション機能を使用してパイロットを終了し、最終的にパイロットを終了して結果を反映および文書化することにより、パイロット プロジェクトを実行するのに役立ちます。

![Microsoft 365 Defender パイロットの実行のフェーズ](../../media/pilotphases.png)


パイロットを実行すると、Microsoft 365 Defender を導入するメリットを効果的に判断できます。 実稼働環境で Microsoft 365 Defender を有効にし、使用例を開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功基準を設定する計画を立ておきます。 


## <a name="how-to-use-this-pilot-playbook"></a>このパイロット プレイブックの使い方

このガイドでは、Microsoft 365 Defender の概要と、パイロット プロジェクトのセットアップ方法に関する詳細な手順について説明します。 

Microsoft 365 Defender は、高度な攻撃に対する統合された保護を提供するために、エンドポイント、ID、電子メール、アプリケーション間で保護、検出、防止、調査、応答をネイティブに調整する、侵害前および侵害後の統合エンタープライズ防御スイートです。 これは、次の機能を組み合わせて 1 つのセキュリティ ソリューションに統合することで実現されます。
  - Microsoft Defender for Endpoint、Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前
  - Microsoft Defender for Office 365、 Office 365 ATP の新しい名前 (メール) 
  - Microsoft Defender for Identity、Azure ATP (ID) の新しい名前 
  - Microsoft Cloud App Security (アプリ)

![ユーザー向of_Microsoft 365 Defender ソリューション、Id 用 Microsoft Defender、エンドポイント用の Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、データ用の Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ担当者は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、および Microsoft Cloud App Security が受信する脅威シグナルをまとめ、脅威の全範囲と影響、環境に入った方法、影響を受ける対象、組織に現在どのような影響を与えているかを判断できます。 Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、ユーザー ID を自己回復する自動アクションを実行します。 詳細については [、Microsoft 365 Defender の概要](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) を参照してください。



次のサンプル タイムラインは、環境に適切なリソースがある場合に異なります。 検出とワークフローによっては、他の検出とワークフローよりも多くの学習時間が必要になる場合があります。

![Microsoft 365 Defender パイロットの実行に関するサンプル タイムライン](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>最適な結果を得る場合は、パイロット手順にできる限り近い手順に従ってください。


### <a name="pilot-playbook-phases"></a>パイロット プレイブックフェーズ 

Microsoft 365 Defender パイロットの実行には、次の 4 つのフェーズがあります。

|フェーズ | 説明 | 
|:-------|:-----|
| [計画](mtp-pilot-plan.md)<br> ~ 1 日| Microsoft 365 Defender パイロット プロジェクトを実行する前に考慮する必要がある点について説明します。 <br><br>- スコープ <br> - 使用事例 <br>- 要件 <br>- テスト計画 <br> - 成功条件 <br> - スコアカード 
| [準備](mtp-evaluation.md) <br>~2 日|  Microsoft 365 セキュリティ センターにアクセスして、Microsoft 365 Defender パイロット環境をセットアップします。 次のガイドが表示されます。<br><br>- 関係者を特定し、パイロットのサインオフを求める <br> - 環境に関する考慮事項 <br>- Access <br>- Azure Active Directory のセットアップ <br> - 構成順序 <br> - Microsoft 365 E5 試用版にサインアップする <br> - ドメインを構成する <br>- Microsoft 365 E5 ライセンスを割り当てる <br> - ポータルでセットアップ ウィザードを完了する|
| [攻撃シミュレーション](mtp-pilot-simulate.md) <br>~2 日| 攻撃をシミュレートするには、次のガイドが表示されます。<br><br>- テスト環境の要件を確認する <br>- シミュレーションを実行する <br>- インシデントを調査する <br>- インシデントを解決する 
| [終了と概要](mtp-pilot-close.md) <br>~ 1 日| プロセスの最後に到達すると、次のガイドが表示されます。<br><br>- 最終的な出力を確認する<br>- 関係者に出力を表示する <br>- フィードバックの提供 <br>- 次の手順を実行する 

## <a name="next-step"></a>次の手順
|[計画フェーズ](mtp-pilot-plan.md) | Microsoft 365 Defender パイロット プロジェクトを計画する 
|:-------|:-----|
