---
title: パイロット Microsoft 365 Defender プロジェクトを実行する
description: Microsoft 365 Defender のメリットと導入を効果的に判断するには、パイロット Microsoft 365 Defender プロジェクトを実稼働環境で実行します。
keywords: Microsoft Threat Protection パイロット、パイロット Microsoft Threat Protection プロジェクトの実行、実稼働での Microsoft Threat Protection の評価、Microsoft Threat Protection パイロット プロジェクト、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
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
ms.openlocfilehash: c6c373d084c7f7cf12073c6402695af644944bad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910872"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>パイロット Microsoft 365 Defender プロジェクトを実行する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


このガイドは、パイロット プロジェクトを実行する場合に役立ちます。ポインターを使用して、適切に構造化された計画を作成し、攻撃シミュレーション機能を使用してガイドし、最終的にパイロットに主なテイクアウェイを設定して結果を反映して文書化します。

![Microsoft 365 Defender パイロットの実行のフェーズ](../../media/pilotphases.png)


パイロットを実行すると、Microsoft 365 Defender を採用するメリットを効果的に判断できます。 実稼働環境で Microsoft 365 Defender を有効にし、使用例を開始する前に、パイロット プロジェクトで実行するタスクを決定し、成功基準を設定する計画をお試しください。 


## <a name="how-to-use-this-pilot-playbook"></a>このパイロット プレイブックの使い方

このガイドでは、Microsoft 365 Defender の概要とパイロット プロジェクトのセットアップ方法に関する手順を説明します。 

Microsoft 365 Defender は、エンドポイント、ID、電子メール、およびアプリケーション全体の保護、検出、防止、調査、および応答をネイティブに調整し、高度な攻撃に対する統合保護を提供する統合された侵害前および侵害後のエンタープライズ防御スイートです。 これは、次の機能を 1 つのセキュリティ ソリューションに組み合わせて調整することで行います。
  - Microsoft Defender for Endpoint、Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前
  - Microsoft Defender for Office 365、365 ATP のOffice名 (電子メール) 
  - Microsoft Defender for Identity、Azure ATP の新しい名前 (ID) 
  - Microsoft Cloud App Security (アプリ)

![イメージ of_Microsoftユーザー向け 365 Defender ソリューション、Microsoft Defender for Identity、エンドポイント用 Microsoft Defender for Endpoint、クラウド アプリ、Microsoft Cloud App Security、およびデータの場合、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ専門家は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security が受け取る脅威信号をまとめ、脅威の全範囲と影響、環境に入った方法、影響を受けたもの、組織にどのような影響を与えているかを判断できます。 Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復するために自動アクションを実行します。 詳細については [、「Microsoft 365 Defender の概要」](./microsoft-threat-protection.md) を参照してください。



次のサンプル タイムラインは、環境に適切なリソースを持つことによって異なります。 検出とワークフローによっては、他の検出よりも多くの学習時間が必要になる場合があります。

![Microsoft 365 Defender パイロットの実行のサンプル タイムライン](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>最適な結果を得る場合は、パイロットの指示に従ってください。


### <a name="pilot-playbook-phases"></a>パイロット プレイブックのフェーズ 

Microsoft 365 Defender パイロットの実行には 4 つのフェーズがあります。

|段階 | 説明 | 
|:-------|:-----|
| [計画](mtp-pilot-plan.md)<br> ~ 1 日| Microsoft 365 Defender パイロット プロジェクトを実行する前に考慮する必要がある点について説明します。 <br><br>- スコープ <br> - 使用例 <br>- 要件 <br>- テスト計画 <br> - 成功条件 <br> - スコアカード 
| [準備](mtp-evaluation.md) <br>~2 日間|  Microsoft 365 セキュリティ センターにアクセスして、Microsoft 365 Defender パイロット環境をセットアップします。 次の情報に案内されます。<br><br>- 利害関係者を特定し、パイロットのサインオフを求める <br> - 環境に関する考慮事項 <br>- Access <br>- Azure Active Directory のセットアップ <br> - 構成順序 <br> - Microsoft 365 E5 試用版にサインアップする <br> - ドメインの構成 <br>- Microsoft 365 E5 ライセンスの割り当て <br> - ポータルでセットアップ ウィザードを完了する|
| [攻撃シミュレーション](mtp-pilot-simulate.md) <br>~2 日間| 攻撃をシミュレートするには、次の情報に案内されます。<br><br>- テスト環境の要件を確認する <br>- シミュレーションを実行する <br>- インシデントを調査する <br>- インシデントを解決する 
| [閉じると概要](mtp-pilot-close.md) <br>~ 1 日| プロセスの最後に達すると、次の手順に案内されます。<br><br>- 最終的な出力を確認する<br>- 出力を関係者に提示する <br>- フィードバックを提供する <br>- 次の手順を実行する 

## <a name="next-step"></a>次の手順
|[計画フェーズ](mtp-pilot-plan.md) | Microsoft 365 Defender パイロット プロジェクトを計画する 
|:-------|:-----|