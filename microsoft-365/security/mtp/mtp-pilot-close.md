---
title: パイロットの概要 Microsoft 365 Defender プロジェクトの結果
description: スコアカードを完成させる、レポートの結果を分析する、および前進する方法を決定することによって、パイロットの Microsoft 365 Defender プロジェクトを終了します。
keywords: Microsoft Threat Protection パイロット、パイロットによる microsoft の脅威保護プロジェクトを評価した後の作業、microsoft threat protection パイロットから展開への移行、サイバーセキュリティ、高度な脅威、企業セキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、および自動調査と修復、高度な検索
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130945"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a>Microsoft 365 Defender パイロットの終了および概要  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



|[![計画](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)<br/>[計画](mtp-pilot-plan.md) |[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[準備](prepare-mtpeval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[攻撃のシミュレーション](mtp-pilot-simulate.md) | ![閉じて要約する](../../media/phase-diagrams/4-summary.png)<br/>閉じて要約する|
|--|--|--|--|
|| | |*ここでは、*|


現在、決算フェーズと要約段階になっています。

ドメインコントローラー上でコードをリモートで実行する、高度なメモリのみのアタックシミュレーションが実行されました。 Stealthy 悪意のあるアクティビティについて、エンドポイントと Microsoft Defender の Id を検出して通知を作成する方法について説明してきました。 また、Microsoft 365 セキュリティセンターポータルでは、さまざまなソースからのアラートが他のコンテキスト情報と共に1つのインシデントに配信される方法についても説明してきました。 このような統合が発生すると、SOC アナリストが調査し、必要なアクションを実行できるようになります。 また、ユーザーが添付ファイルを開いたときや保存したときに、そのクエリに基づいて検出を作成した受信メールを識別する高度な検索クエリも作成されています。

すべてのテストが終了した後、プロセスの最後に到達しました。

最終的な出力は次のようになります。

- 完了したスコアカード
- パイロットの結果についての詳細なレポート
- 前方へ移動する方法の決定

最終的な出力からのレポートを、社内関係者 ( [準備](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 段階で確認したもの) と Microsoft の連絡先に提示します。 このような作業により、製品やドキュメントを改善するためにフィードバックを確実に使用できるようになります。

このシミュレーションを楽しんでいただければ幸いです。 組織内の大規模なスケールで学んだ内容の実装を開始して、統合セキュリティソリューションを最大限に活用してください。

## <a name="next-step"></a>次の手順
Microsoft 365 Defender の柱の詳細については、次の対話的なガイドを参照してください。
- [Microsoft Defender for Office 365 を使用して組織を保護する](https://aka.ms/O365ATP-Interactive-Guide)
- [身元を確認するために Microsoft Defender を使用して疑わしいアクティビティおよび潜在的な攻撃を検出する](https://aka.ms/AATP-Interactive-Guide)
- [Microsoft Cloud App Security を使用して脅威を検出し、アラートを管理する](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [エンドポイントの Microsoft Defender を使用して脅威を調査および修復する](https://aka.ms/MDATP-IR-Interactive-Guide)
