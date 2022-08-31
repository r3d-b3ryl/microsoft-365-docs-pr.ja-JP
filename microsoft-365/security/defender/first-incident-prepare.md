---
title: 初めてのインシデントに備え、セキュリティ体制を整える
description: Microsoft 365 Defenderでの最初のインシデントに対する Microsoft 365 テナントのセキュリティ体制を設定します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365solution-firstincident
- highpri
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7915c2dac12980283e45f0d389c2e13cd9753f66
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67471105"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>初めてのインシデントに備え、セキュリティ体制を整える

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

インシデント処理の準備には、さまざまな種類のセキュリティ インシデントから組織のネットワークを十分に保護する必要があります。 セキュリティ インシデントのリスクを軽減するために、米国標準技術研究所 (NIST) では、リスク評価、ホスト セキュリティの強化、ネットワークの安全な構成、マルウェアの防止など、いくつかのセキュリティプラクティスを推奨しています。

Microsoft 365 Defenderは、インシデント防止のいくつかの側面に対処するのに役立ちます。

- [ゼロ トラスト](/security/zero-trust/) フレームワークの実装
- [Microsoft Secure](microsoft-secure-score.md) Score でスコアを割り当ててセキュリティ体制を決定する
- [Defender 脆弱性管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)の脆弱性評価による脅威の防止
- 脅威分析を使用して準備できるように、最新のセキュリティ[の脅威](threat-analytics.md)について理解する

## <a name="step-1-implement-zero-trust"></a>手順 1。 ゼロ トラストを実装する

[ゼロ トラスト](/security/zero-trust/)は、モバイル従業員やユーザー、デバイス、アプリケーション、データなど、あらゆる最新環境の複雑な性質を考慮した統合セキュリティ哲学とエンド ツー エンド戦略です。 すべての検出を一貫した方法で管理するための単一のウィンドウを提供することで、Microsoft 365 Defenderセキュリティ運用チームがゼロ トラストの[基本原則を](/security/zero-trust/#guiding-principles-of-zero-trust)実装しやすくなります。

Microsoft 365 Defenderのコンポーネントは、Microsoft Defender for Endpointからのデータを統合することで、ゼロ トラストの条件付きアクセス ポリシーを確立するために実装されたルールの違反を表示できます。 またはデバイス コンプライアンス ポリシーの情報ソースとしての他のモバイル セキュリティ ベンダーや、デバイス ベースの条件付きアクセス ポリシーの実装。

デバイス リスクは、そのデバイスのユーザーがアクセスできるリソースに直接影響します。 特定の条件に基づくリソースへのアクセス拒否は、ゼロ トラストの主なテーマであり、Microsoft 365 Defenderは信頼レベルの基準を決定するために必要な情報を提供します。 たとえば、Microsoft 365 Defenderは、以前は脅威&脆弱性管理ページと呼ばMicrosoft Defender 脆弱性の管理を通じてデバイスのソフトウェア バージョン レベルを提供し、条件付きアクセス ポリシーでは、古いバージョンまたは脆弱なバージョンを持つデバイスを制限できます。

自動化は、ゼロ トラスト環境の実装と保守の重要な部分であり、インシデント対応 (IR) イベントにつながる可能性のあるアラートの数を減らします。 Microsoft 365 Defenderのコンポーネントは、[修復アクション](m365d-autoir.md) (Microsoft 365 Defender ポータルでのインシデントの調査と呼ばれます)、通知アクション、[ServiceNow](https://microsoft.service-now.com/sp/) などのサポート チケットの作成など、自動化できます。

## <a name="step-2-determine-your-organizations-security-posture"></a>手順 2。 組織のセキュリティ体制を決定する

次に、組織は、Microsoft 365 Defenderで [Microsoft Secure Score](microsoft-secure-score.md) を使用して、現在のセキュリティ体制を決定し、それを改善する方法に関する推奨事項を検討できます。 スコアが高いほど、組織によって実行されたセキュリティに関する推奨事項と改善アクションが多くなります。 セキュリティスコアに関する推奨事項は、さまざまな製品で取得でき、組織はスコアをさらに高くすることができます。

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft 365 Defender ポータルの Microsoft Secure Score ページ" lightbox="../../media/first-incident-prepare/first-incident-secure-score.png":::

## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>手順 3. 組織の脆弱性の露出を評価する

インシデントを防ぐことは、セキュリティ運用の取り組みを効率化し、継続的な重大で重要なセキュリティ インシデントに焦点を当てるのに役立ちます。 多くの場合、ソフトウェアの脆弱性は、データの盗難、データの損失、または業務の中断につながる可能性がある攻撃の予防可能なエントリ ポイントです。 攻撃が進行中でない場合、セキュリティ操作は、組織で許容可能なレベルの [脆弱性にさらされるように](../defender-endpoint/tvm-exposure-score.md) 努める必要があります。

ソフトウェアの修正プログラムの進行状況を確認するには、Defender for Endpoint の [[Microsoft Defender 脆弱性の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)] ページにアクセスします。このページには、[**その他のリソース**] タブMicrosoft 365 Defenderからアクセスできます。

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft 365 Defender ポータル ポータルの [脅威と脆弱性] ページ" lightbox="../../media/first-incident-prepare/first-incident-vulnerability.png":::

## <a name="4-understand-emerging-threats"></a>4. 新たな脅威について理解する

Microsoft 365 Defender ポータルで[脅威分析](threat-analytics.md)を使用して、現在のセキュリティ脅威の状況を最新の状態に保ちます。 エキスパートの Microsoft セキュリティ研究者は、最新のサイバー脅威を詳細に説明するレポートを作成し、Microsoft 365 サブスクリプション、デバイス、ユーザーにどのような影響を与えるかを理解できるようにします。 これらのレポートには、次のものが含まれます。

- アクティブな脅威アクターとそのキャンペーン
- 一般的な攻撃手法と新しい攻撃手法
- 重大な脆弱性
- 一般的な攻撃対象領域
- 流行しているマルウェア

脅威分析では、構成とアラートも調べて、リスクの高い状況と、レポートに適用できるアクティブなアラートがあるかどうかを判断します。

新たな脅威の推奨事項を実装して、セキュリティ体制を強化し、攻撃領域を最小限に抑えることができます。

スケジュールに時間を取って、Microsoft 365 Defender ポータルの [Threat Analytics](threat-analytics.md) セクションを定期的に確認します。 詳細については、[Microsoft 365 Defenderのセキュリティ操作の例](incidents-overview.md#example-security-operations-for-microsoft-365-defender)を参照してください。

## <a name="next-step"></a>次のステップ

[インシデントをトリアージして分析する](first-incident-analyze.md)方法について説明します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
