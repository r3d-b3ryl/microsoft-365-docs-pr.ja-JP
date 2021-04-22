---
title: パイロット Microsoft 365 Defender プロジェクトの結果の概要
description: スコアカードを完了し、レポートの結果を分析し、前進する方法を決定することで、パイロット Microsoft 365 Defender プロジェクトを終了します。
keywords: Microsoft 365 Defender パイロットは、Microsoft 365 Defender プロジェクトのパイロットの後に次に何を行うかを決定し、Microsoft 365 Defender パイロットから展開、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングに移行した後の処理を決定します。
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
ms.openlocfilehash: 64cdb37b64780a651b2689e68e21c5a385df5ba9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932871"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a>Microsoft 365 Defender パイロットの終了と概要  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



|[![計画](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[計画](m365d-pilot-plan.md) |[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[準備](prepare-m365d-eval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[攻撃のシミュレーション](m365d-pilot-simulate.md) | ![閉じて要約する](../../media/phase-diagrams/4-summary.png)<br/>閉じて要約する|
|--|--|--|--|
|| | |*お前はここにいる!*|


現在、閉じる段階と要約段階です。

ドメイン コントローラーでコードをリモートで実行する高度なメモリ専用攻撃シミュレーションを実行しました。 Microsoft Defender for Endpoint と Microsoft Defender for Identity が、ステルス的な悪意のあるアクティビティに関するアラートを検出して作成する方法を確認しました。 また、Microsoft 365 セキュリティ センター ポータルで、さまざまなソースからのアラートが他のコンテキスト情報と共に 1 つのインシデントに配信される方法も確認しました。 このような統合を経験すると、SOC アナリストは調査し、必要なアクションを実行できます。 また、ユーザーが添付ファイルを開いたか保存した受信メールを識別し、そのクエリに基づいて検出を作成する高度な検索クエリも作成しました。

すべてのテストが終了した後、プロセスの終了に達しました。

最終的な出力は次の値です。

- 完了したスコアカード
- パイロットの調査結果の詳細なレポート
- 前進する方法に関する決定

最終出力のレポートを内部関係者 (準備フェーズで特定した) と Microsoft[](./prepare-m365d-eval.md)の連絡先に提示します。 このような取り組みにより、製品とドキュメントの改善にフィードバックを使用できます。

このシミュレーションをお楽しみになって下さい。 組織で学習した情報を大規模に実装し、統合セキュリティ ソリューションを最も役立て始める。

## <a name="next-step"></a>次の手順
Microsoft 365 Defender の柱の詳細については、次の対話型ガイドを参照してください。
- [Microsoft Defender を使用して組織を保護Office 365](https://aka.ms/O365ATP-Interactive-Guide)
- [Microsoft Defender for Identity を使用して不審なアクティビティと潜在的な攻撃を検出する](https://aka.ms/AATP-Interactive-Guide)
- [Microsoft Cloud App Security を使用して脅威を検出し、アラートを管理する](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [Microsoft Defender for Endpoint を使用して脅威を調査および修復する](https://aka.ms/MDATP-IR-Interactive-Guide)