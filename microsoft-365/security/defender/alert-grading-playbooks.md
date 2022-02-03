---
title: アラート の採点プレイブック
description: 既知の攻撃に関するアラートを確認し、推奨されるアクションを実行して攻撃を修復し、ネットワークを保護します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
search.appverid: met150
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
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fe0beb88cf613a5a966fc0534dfa4def715e81d2
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355237"
---
# <a name="alert-grading-playbooks"></a>アラート の採点プレイブック

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

アラート の評価プレイブックを使用すると、既知の攻撃に関するアラートを方法的に確認して迅速に分類し、攻撃を修復してネットワークを保護するために推奨されるアクションを実行できます。 アラートの評価は、インシデント全体を適切に分類する場合にも役立ちます。

セキュリティ研究者またはセキュリティ 運用センター (SOC) アナリストとして、次の操作を実行するには、Microsoft 365 Defender ポータルにアクセスできる必要があります。

- 生成されたアラートと関連するインシデントを評価および確認します。 「アラート [の調査」を参照してください](investigate-alerts.md)。
- テナントのセキュリティ信号データを検索し、潜在的な脅威や疑わしいアクティビティを確認します。 詳細については [、「高度な検索」を参照してください](advanced-hunting-overview.md)。

>[!Note]
>調査の最後だけでなく、調査プロセス中にも、正陽性と誤検知の警告に関するフィードバックを Microsoft に提供できます。 これにより、Microsoft は将来のセキュリティ イベントの分析と分類に役立ちます。
>

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによる悪意のある脅威から組織を保護します。 Defender for Office 365 には次のものが含まれます。

- 脅威に対する保護ポリシー

   脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。

- レポート

  リアルタイム レポートを表示して、組織内のパフォーマンスOffice 365 Defender を監視します。

- 脅威の調査と対応の機能

  最先端のツールを使用して、脅威を調査、理解、シミュレート、および防止します。

- 自動調査と対応機能

  脅威の調査と軽減に時間と労力を節約します。

アラートのOffice 365は、次のように分類できます。 

- 確認された悪意のあるアクティビティに対して正の値 (TP) を指定します。 
- 悪意のあるアクティビティ以外の確認済みアクティビティに対する誤検知 (FP)。

>[!Note]
>Microsoft 365 Defenderは、[https://security.microsoft.com](https://security.microsoft.com)既存の Microsoft セキュリティ ポータルの機能をまとめます。 このMicrosoft 365 Defenderポータルでは、情報への迅速なアクセス、レイアウトの簡易性、および関連情報のまとめが強調され、使いやすくなっています。
>

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

[Microsoft Defender for Cloud Apps](/defender-cloud-apps) は、ログ コレクション、API コネクタ、リバース プロキシなど、さまざまな展開モードをサポートするクラウド アクセス セキュリティ ブローカー (CASB) です。 Microsoft およびサードパーティのすべてのクラウド サービスでサイバー攻撃の脅威を特定して対処するための、機能豊富な表示、データ移動の制御機能、洗練された分析機能を提供します。

Defender for Cloud Apps は、主要な Microsoft ソリューションとネイティブに統合され、セキュリティ専門家を念頭に置いて設計されています。 これは、シンプルな配置、集中管理、革新的な自動化機能を提供します。

Defender for Cloud Apps フレームワークには、ネットワークをサイバー脅威や異常から保護し、クラウド アプリ全体で異常な動作を検出して、ランサムウェア、侵害されたユーザー、または不正なアプリケーションを特定する機能が含まれています。 これにより、リスクの高い使用状況の分析が可能になります。また、リスクを組織に限定するために自動的に修復できます。

クラウド アプリの Defender アラートは、次のように分類できます。 

- 確認された悪意のあるアクティビティの TP。 
- 侵入テストや他の承認された疑わしいアクションなど、疑わしいが悪意のないアクティビティに対する良性真陽性 (B-TP)。 
- 確認済み非悪意のあるアクティビティの FP。

## <a name="alert-grading-playbooks"></a>アラート の採点プレイブック

以下の脅威に対するアラートを迅速に評価する手順については、以下のプレイブックを参照してください。

- [疑わしいメール転送アクティビティ](alert-grading-playbook-email-forwarding.md)
- [疑わしい受信トレイ操作ルール](alert-grading-playbook-inbox-manipulation-rules.md)
- [不審な受信トレイ転送ルール](alert-grading-playbook-inbox-forwarding-rules.md)

ポータル[でアラートを](investigate-alerts.md)調べる方法については、「アラートを調査する」をMicrosoft 365 Defenderしてください。
