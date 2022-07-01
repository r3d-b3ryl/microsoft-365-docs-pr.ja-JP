---
title: Microsoft 365 Defenderで調査して応答する
description: Microsoft 365 Defenderの機能を使用してインシデントを調査し、対応します。
keywords: インシデント, アラート, 調査, 分析, 対応, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a919e8893fff0486d7a9a3eb89be1822a73ce437
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66603552"
---
# <a name="investigate-and-respond-with-microsoft-365-defender"></a>Microsoft 365 Defenderで調査して応答する

Microsoft 365 Defenderの主な調査と対応タスクを次に示します。

- [インシデントへの対応](#incident-response)
- [自動修復アクションを確認して承認する](#automated-investigation-and-remediation)
- [データ内の既知の脅威を検索する](#proactive-search-for-threats-with-advanced-hunting)
- [最新のサイバー攻撃について理解する](#get-ahead-of-emerging-threats-with-threat-analytics)
- [ヘルプを参照する](#collaborate-with-microsoft-experts)

## <a name="incident-response"></a>インシデント対応

Microsoft 365 サービスおよびアプリは、疑わしい、または悪意のあるイベントやアクティビティを検出した場合にアラートを作成します。 個々のアラートは、完了した攻撃、または進行中の攻撃に関する貴重な手がかりとなります。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなどの異なる種類のエンティティに対抗してさまざまな技術を採用しています。 その結果、テナント内の複数のエンティティに複数のアラートが表示されます。 個々のアラートを組み合わせて攻撃に関する分析情報を取得するのは困難で時間がかかるため、Microsoft 365 Defender はアラートとその関連情報を自動的にインシデントに集約します。

継続的に、インシデント キュー内の分析と解決に最も優先度の高いインシデントを特定し、対応の準備を整える必要があります。 これは、次を組み合わせたものです：

- インシデント キューのフィルター処理と並べ替えを通じて、最も優先度の高いインシデントを決定することに[優先順位](incident-queue.md)を付けます。 これはトリエージングとも呼ばれます。
- タイトルを変更し、アナリストに割り当て、タグとコメントを追加し、解決したらそれらを分類することでインシデントを[管理](manage-incidents.md)します。

インシデントごとに、インシデント対応ワークフローを使用して、インシデントとそのアラートとデータを分析して攻撃を含め、脅威を根絶し、攻撃から回復し、そこから学習します。 [Microsoft 365 Defenderについては、この例](incidents-overview.md#example-incident-response-workflow-for-microsoft-365-defender)を参照してください。

## <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

組織がMicrosoft 365 Defenderを使用している場合、セキュリティ運用チームは、悪意のあるアクティビティや疑わしいアクティビティまたはアーティファクトが検出されるたびに、Microsoft 365 Defender ポータル内でアラートを受け取ります。 脅威が終わることのないフローを考えると、セキュリティ チームは多くの場合、大量のアラートに対処するという課題に直面します。 幸いにも、Microsoft 365 Defenderには、セキュリティ運用チームがより効率的かつ効果的に脅威に対処するのに役立つ自動調査と対応 (AIR) 機能が含まれています。

自動調査が完了すると、インシデントの証拠ごとに判定に達します。 判定に応じて、修復アクションが識別されます。 場合によっては、修復アクションが自動的に実行されます。その他の場合、修復アクションはMicrosoft 365 Defenderアクション センターを通じて承認を待ちます。 

詳細については、「[Microsoft 365 Defenderの自動調査と対応](m365d-autoir.md)」を参照してください。

## <a name="proactive-search-for-threats-with-advanced-hunting"></a>高度な捜索で脅威をプロアクティブに検索する

攻撃が発生したときに対応するには十分ではありません。 ランサムウェアなどの拡張された多フェーズ攻撃の場合は、攻撃が進行中の証拠を積極的に検索し、完了する前に停止するアクションを実行する必要があります。

高度なハンティングは、最大 30 日間の生データを探索できる、Microsoft 365 Defenderのクエリベースの脅威検出ツールです。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを見つけることができます。 Microsoft 365 Defender データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する制約のない捜索が可能になります。

同じ脅威検出クエリを使用して、カスタム検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、不適切な構成されたマシン、およびその他の結果を確認して対応します。

詳細については、「[Microsoft 365 Defenderで高度なハンティングを使用して脅威をプロアクティブに検出](advanced-hunting-overview.md)する」を参照してください。

## <a name="get-ahead-of-emerging-threats-with-threat-analytics"></a>脅威分析を使用して、新たな脅威を先取りする

脅威分析は、新たな脅威に直面しながら、セキュリティ チームができるだけ効率的になるように設計されたMicrosoft 365 Defenderの脅威インテリジェンス機能です。 詳細な分析と次に関する情報が含まれています。

- アクティブな脅威アクターとそのキャンペーン
- 一般的な攻撃手法と新しい攻撃手法
- 重大な脆弱性
- 一般的な攻撃対象領域
- 流行しているマルウェア

脅威分析には、特定された脅威ごとに、Microsoft 365 テナント内の関連インシデントと影響を受けた資産に関する情報も含まれます。

特定された各脅威には、サイバーセキュリティの検出と分析の最前線にいる Microsoft セキュリティ研究者によって作成された脅威の包括的な分析であるアナリスト レポートが含まれています。 これらのレポートでは、Microsoft 365 Defenderでの攻撃の表示方法に関する情報も提供できます。

詳細については、[Microsoft 365 Defenderの脅威分析に関するページを](threat-analytics.md)参照してください。

## <a name="collaborate-with-microsoft-experts"></a>Microsoft エキスパートと共同作業する

Microsoft 脅威エキスパート - ターゲット攻撃通知はマネージド脅威ハンティング サービスです。 適用して承諾されると、Microsoft 脅威の専門家からターゲットを絞った攻撃通知を受け取ります。そのため、環境に対する重大な脅威を見逃すことはありません。 これらの通知は、組織のエンドポイント、電子メール、ID を保護するのに役立ちます。 Microsoft 脅威エキスパート – エキスパート オンデマンドを使用すると、組織が直面している脅威に関する専門家のアドバイスを受けることができます。また、組織が直面している脅威に関するヘルプを受けることができます。 追加のサブスクリプション サービスとして利用できます。

詳細については、[Microsoft 365 の概要のMicrosoft 脅威エキスパートを](/microsoft-365/security/defender/microsoft-threat-experts)参照してください。
