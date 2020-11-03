---
title: パイロットを実行する Microsoft 365 Defender プロジェクト
description: 試験的な Microsoft 365 Defender プロジェクトを運用環境で実行して、Microsoft 365 Defender の利点と導入を効果的に決定します。
keywords: Microsoft Threat Protection パイロット、パイロットを実行する Microsoft threat protection プロジェクトを実行する、microsoft threat protection を運用環境において評価する、Microsoft Threat Protection パイロットプロジェクト、サイバーセキュリティ、高度な永続脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 350904022ec86acdbebf109dd5946598643aea83
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843662"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>パイロットを実行する Microsoft 365 Defender プロジェクト 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender の利点と導入を効果的に決定するために、パイロットプロジェクトを実行できます。 運用環境で Microsoft 365 Defender を有効にし、ユースケースを開始する前に、パイロットプロジェクトに対して実行するタスクを決定し、成功の基準を設定することを計画することをお勧めします。 


## <a name="how-to-use-this-pilot-playbook"></a>このパイロットプレイブックの使用方法

このガイドでは、パイロットプロジェクトをセットアップする方法について、Microsoft 365 Defender の概要と詳細な手順について説明します。 

Microsoft 365 Defender は、統合された事前違反および適用後のエンタープライズ防衛スイートで、エンドポイント、id、電子メール、およびアプリケーション間の応答をネイティブに調整し、高度な攻撃に対する統合保護を提供します。 そのためには、次の機能を結合して、単一のセキュリティソリューションにオーケストレーションします。
  - エンドポイントの microsoft Defender。 Microsoft Defender Advanced Threat Protection (エンドポイント) の新しい名前
  - Microsoft Defender for Office 365、Office 365 ATP (電子メール) の新しい名前 
  - Id の Microsoft Defender。 Azure ATP (identity) の新しい名前 
  - Microsoft Cloud App Security (apps)

![画像 of_Microsoft ユーザーの場合は 365 Defender ソリューション、エンドポイントの場合は microsoft defender、エンドポイントの場合は microsoft defender、クラウドアプリの場合は microsoft Cloud App Security、データについては Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

統合された Microsoft 365 Defender ソリューションを使用することにより、セキュリティ担当者は microsoft Defender for Endpoint、microsoft defender for Office 365、Id 用 Microsoft Defender、および Microsoft Cloud App Security receive という脅威について協力することができ、脅威の完全な範囲と影響、その脅威がどのような影響を受けるか、どのように組織をどのように Microsoft 365 Defender は、攻撃を阻止または停止する、または影響を受けるメールボックス、エンドポイント、ユーザー id を自己回復させるための自動操作を行います。 詳細については、 [Microsoft 365 Defender の概要](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) を参照してください。

![Microsoft 365 Defender パイロットの実行フェーズ](../../media/pilotphases.png)

次のサンプルタイムラインは、環境内に適切なリソースがあるかによって異なります。 一部の検出とワークフローでは、他のユーザーよりも多くの学習時間が必要になることがあります。

![Microsoft 365 Defender パイロットの実行におけるサンプルタイムライン](../../media/pilotimeline.png)

>[!IMPORTANT]
>最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。


### <a name="pilot-playbook-phases"></a>パイロットプレイブックのフェーズ 

Microsoft 365 Defender パイロットの実行には、次の4つのフェーズがあります。

|フェーズ | 説明 | 
|:-------|:-----|
| ![計画](../../media/mtp/plan.png)<br>[計画](mtp-pilot-plan.md)| Microsoft 365 Defender パイロットプロジェクトを実行する前に考慮する必要のある事項について説明します。 <br><br>-スコープ <br> -ユースケース <br>- 要件 <br>-テスト計画 <br> -成功の条件 <br> -スコアカード 
| ![準備](../../media/mtp/prep.png) <br>[準備](mtp-evaluation.md)|  Microsoft 365 セキュリティセンターにアクセスして、Microsoft 365 Defender パイロット環境を設定します。 次のようなガイドが表示されます。<br><br>-パイロットの関係者を特定し、承認を求める <br> -環境に関する考慮事項 <br>-アクセス <br>-Azure Active Directory のセットアップ <br> -構成の順序 <br> -Microsoft 365 E5 試用版にサインアップする <br> -ドメインの構成 <br>-Microsoft 365 E5 ライセンスを割り当てる <br> -ポータルのセットアップウィザードを完了します。|
| ![攻撃シミュレーション](../../media/mtp/run-sim.png) <br>[攻撃シミュレーション](mtp-pilot-simulate.md) | 攻撃をシミュレートするために、次のように指導します。<br><br>-テスト環境の要件を確認する <br>-シミュレーションを実行する <br>-インシデントを調査する <br>-インシデントを解決する 
| ![決算と概要](../../media/mtp/close.png) <br>[決算と概要](mtp-pilot-close.md) | プロセスの最後に達すると、次のようになります。<br><br>-最終出力に進む<br>-利害関係者への出力を提示する <br>-フィードバックを提供する <br>-次の手順を実行します。 

## <a name="next-step"></a>次のステップ
|![計画フェーズ](../../media/mtp/plan.png) <br>[計画フェーズ](mtp-pilot-plan.md) | Microsoft 365 Defender パイロットプロジェクトを計画する 
|:-------|:-----|
