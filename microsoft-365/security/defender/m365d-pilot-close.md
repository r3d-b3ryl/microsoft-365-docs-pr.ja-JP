---
title: パイロット Microsoft 365 Defender プロジェクトの結果の概要
description: スコアカードを完了し、レポートの結果を分析し、前に進む方法を決定することで、パイロットMicrosoft 365 Defenderプロジェクトを終了します。
keywords: パイロットMicrosoft 365 Defender、パイロット Microsoft 365 Defender プロジェクトの後に次に何をするか、運用環境のMicrosoft 365 Defenderを評価した後に何をするか、Microsoft 365 Defenderから移行する方法を決定します デプロイへのパイロット、サイバー セキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜索
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
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458440"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a>Microsoft 365 Defender パイロットの終了と要約  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



|[![計画](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[計画](m365d-pilot-plan.md) |[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[準備](prepare-m365d-eval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[攻撃のシミュレーション](m365d-pilot-simulate.md) | ![閉じて要約する](../../media/phase-diagrams/4-summary.png)<br/>閉じて要約する|
|--|--|--|--|
|| | |*お客様はここにいます。*|


現在、終了フェーズと集計段階です。

ドメイン コントローラーでコードをリモートで実行する高度なメモリのみの攻撃シミュレーションを実行しました。 Microsoft Defender for EndpointとMicrosoft Defender for Identityが、隠れた悪意のあるアクティビティに関するアラートを検出して作成する方法を確認しました。 また、Microsoft 365 Security Center ポータルで、さまざまなソースからのアラートが他のコンテキスト情報と共に 1 つのインシデントにどのように配信されるかも確認しました。 このような統合を経験すると、SOC アナリストは調査し、必要なアクションを実行できます。 また、ユーザーが添付ファイルを開いたり保存したり、そのクエリに基づいて検出を作成した受信メールを識別する高度なハンティング クエリも作成しました。

すべてのテストが完了したら、プロセスの終了に達しました。

最終的な出力は次のようになります。

- 完了したスコアカード
- パイロットの結果の詳細なレポート
- 前に進む方法に関する決定

最終的な出力から内部関係者 ( [準備](./prepare-m365d-eval.md) 段階で特定した) と Microsoft の連絡先にレポートを表示します。 このような取り組みにより、フィードバックを使用して製品やドキュメントを改善できます。

このシミュレーションをお楽しみいただければ幸いです。 統合セキュリティ ソリューションを最大限に活用するために、組織の大規模な学習内容の実装を開始します。

## <a name="next-step"></a>次の手順
次の対話型ガイドを使用して、Microsoft 365 Defenderの柱の詳細を確認します。
- [Microsoft Defender for Office 365を使用して組織を保護する](https://aka.ms/O365ATP-Interactive-Guide)
- [Microsoft Defender for Identityを使用して疑わしいアクティビティと潜在的な攻撃を検出する](https://aka.ms/AATP-Interactive-Guide)
- [Microsoft Cloud App Security で脅威を検出し、アラートを管理する](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [Microsoft Defender for Endpointを使用して脅威を調査し、修復する](https://aka.ms/MDATP-IR-Interactive-Guide)