---
title: データを使用して調査Microsoft 365 Defender
description: インシデントを調査し、インシデントに対応Microsoft 365 Defender。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: abd075ae76eefc4a86d3e99471f092b3f4f03b34
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724820"
---
# <a name="investigate-and-respond-with-microsoft-365-defender"></a>データを使用して調査Microsoft 365 Defender

次に、ユーザーの主な調査タスクと対応タスクMicrosoft 365 Defender。

- [インシデントへの対応](#incident-response)
- [自動修復アクションの確認と承認](#automated-investigation-and-remediation)
- [データ内の既知の脅威を検索する](#proactive-search-for-threats-with-advanced-hunting)
- [最新のサイバー攻撃を理解する](#get-ahead-of-emerging-threats-with-threat-analytics)
- [ヘルプを参照する](#collaborate-with-microsoft-experts)

## <a name="incident-response"></a>インシデント対応

Microsoft 365 サービスおよびアプリは、疑わしい、または悪意のあるイベントやアクティビティを検出した場合にアラートを作成します。 個々のアラートは、完了した攻撃、または進行中の攻撃に関する貴重な手がかりとなります。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなどの異なる種類のエンティティに対抗してさまざまな技術を採用しています。 その結果、テナント内の複数のエンティティに複数のアラートが表示されます。 個々のアラートを組み合わせて攻撃に関する分析情報を取得するのは困難で時間がかかるため、Microsoft 365 Defender はアラートとその関連情報を自動的にインシデントに集約します。

継続的に、インシデント キュー内で、分析と解決優先度が最も高いインシデントを特定し、対応の準備をします。 これは、次を組み合わせたものです：

- [インシデント キューの](incident-queue.md) フィルター処理と並べ替えを通じて、優先度の高いインシデントを特定するトリアージ。
- [タイトルを](manage-incidents.md) 変更し、アナリストに割り当て、タグとコメントを追加してインシデントを管理します。

インシデントごとにインシデント対応ワークフローを使用して、インシデントとそのアラートとデータを分析して攻撃を含め、脅威を根絶し、攻撃から回復し、そこから学習します。 詳細[については、この](incidents-overview.md#example-incident-response-workflow-for-microsoft-365-defender)例をMicrosoft 365 Defender。

## <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

組織が Microsoft 365 Defender を使用している場合、悪意のあるアクティビティや疑わしいアクティビティやアーティファクトが検出されると、セキュリティ運用チームは Microsoft 365 Defender ポータル内で警告を受け取ります。 脅威が終わりのない流れを考えると、セキュリティ チームは多くの場合、多くの場合、アラートの量が多い場合に対処する課題に直面します。 幸いMicrosoft 365 Defender、セキュリティ運用チームが脅威に効率的かつ効果的に対処するのに役立つ自動調査と応答 (AIR) 機能が含まれています。

自動調査が完了すると、関連するインシデントに関するあらゆる証拠に対して、評決に達します。 評決に応じて、修復アクションが識別されます。 場合によっては、修復アクションが自動的に実行されます。それ以外の場合は、修復アクションは、Microsoft 365 Defender承認を待っています。 

詳細[については、「自動調査と応答」Microsoft 365 Defender](m365d-autoir.md)を参照してください。

## <a name="proactive-search-for-threats-with-advanced-hunting"></a>高度な検索を使用した脅威のプロアクティブ検索

攻撃が発生した場合は、攻撃に対応するのに十分ではありません。 ランサムウェアなどの複数フェーズの拡張攻撃では、進行中の攻撃の証拠を積極的に検索し、完了する前に停止するアクションを実行する必要があります。

高度な検索は、最大 30 日間の生データを探索Microsoft 365 Defenderクエリ ベースの脅威検出ツールです。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを見つけることができます。 このデータへの柔軟なアクセスMicrosoft 365 Defender、既知の脅威と潜在的な脅威の両方に対する抑制されていない検出が可能です。

同じ脅威検出クエリを使用して、カスタム検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の結果を確認し、それに対応します。

詳細[については、「高度な検索を使用](advanced-hunting-overview.md)して脅威をプロアクティブにMicrosoft 365 Defenderを参照してください。

## <a name="get-ahead-of-emerging-threats-with-threat-analytics"></a>脅威分析で新たな脅威を先取りする

脅威分析は、新たな脅威に直面Microsoft 365 Defender可能な限り効率的にセキュリティ チームを支援するように設計された脅威インテリジェンス機能です。 詳細な分析と以下の情報が含まれます。

- アクティブな脅威アクターとそのキャンペーン
- 人気のある新しい攻撃手法
- 重大な脆弱性
- 一般的な攻撃対象領域
- 流行しているマルウェア

脅威分析には、特定された脅威ごとに、関連するインシデントや影響を受けたMicrosoft 365に関する情報も含まれます。

特定された各脅威には、アナリスト レポート、サイバーセキュリティの検出と分析の最前線に立ち、Microsoft 365 Defender での攻撃の表示方法に関する情報を提供できる Microsoft セキュリティ研究者によって作成された脅威の包括的な分析が含まれます。

詳細については、「脅威分析」を参照[Microsoft 365 Defender。](threat-analytics.md)

## <a name="collaborate-with-microsoft-experts"></a>Microsoft の専門家と共同作業する

Microsoft 脅威エキスパート - ターゲット攻撃通知は、管理された脅威検出サービスです。 適用して受け入れられると、Microsoft の脅威の専門家から標的型攻撃通知が届くので、環境に対する重大な脅威を見逃す必要はありません。 これらの通知は、組織のエンドポイント、電子メール、および ID を保護するのに役立ちます。 Microsoft 脅威エキスパート – エキスパート オンデマンドを使用すると、組織が直面している脅威に関する専門家のアドバイスを受け取り、組織が直面している脅威に関する支援を求めることができます。 追加のサブスクリプション サービスとして利用できます。

詳細については、「概要」[のMicrosoft 脅威エキスパートをMicrosoft 365してください](/security/mtp/microsoft-threat-experts.md)。
