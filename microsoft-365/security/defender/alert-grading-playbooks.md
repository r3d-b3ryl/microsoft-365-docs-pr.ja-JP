---
title: アラート グレーディング プレイブック
description: 既知の攻撃のアラートを確認し、推奨されるアクションを実行して攻撃を修復し、ネットワークを保護します。
keywords: インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365
search.appverid: met150
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
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 129a4f2efd9a47c09535be3ba0f56504f3da697c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328009"
---
# <a name="alert-grading-playbooks"></a>アラート グレーディング プレイブック

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

アラート の採点プレイブックを使用すると、既知の攻撃のアラートを体系的に確認して迅速に分類し、攻撃を修復し、ネットワークを保護するための推奨されるアクションを実行できます。 アラートの採点は、インシデント全体を適切に分類するのにも役立ちます。

セキュリティ研究者またはセキュリティオペレーション センター (SOC) アナリストは、次のことができるように、Microsoft 365 Defender ポータルにアクセスできる必要があります。

- 生成されたアラートと関連するインシデントを評価して確認します。 [アラートの調査を参照してください](investigate-alerts.md)。
- テナントのセキュリティ信号データを検索し、潜在的な脅威と疑わしいアクティビティを確認します。 [高度なハンティングを](advanced-hunting-overview.md)参照してください。

>[!Note]
>調査の最後だけでなく、調査プロセス中にも、真陽性と偽陽性のアラートに関するフィードバックを Microsoft に提供できます。 これにより、Microsoft は将来のセキュリティ イベントの分析と分類に役立ちます。
>

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[Microsoft Defender for Office 365は、](/microsoft-365/security/office-365-security/defender-for-office-365)電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによってもたらされる悪意のある脅威から組織を保護します。 Defender for Office 365 には次のものが含まれます。

- 脅威に対する保護ポリシー

   脅威保護ポリシーを定義して、組織に対して適切なレベルの保護を設定します。

- レポート

  組織内のDefender for Office 365パフォーマンスを監視するリアルタイム レポートを表示します。

- 脅威の調査と対応の機能

  最先端のツールを使用して、脅威を調査、理解、シミュレート、防止します。

- 自動調査と対応機能

  脅威の調査と軽減に時間と労力を節約します。

Defender for Office 365アラートは次のように分類できます。 

- 確認された悪意のあるアクティビティの真陽性 (TP)。 
- 悪意のないアクティビティが確認された場合の誤検知 (FP)。

>[!Note]
>Microsoft 365 Defender ポータル[https://security.microsoft.com](https://security.microsoft.com)には、既存の Microsoft セキュリティ ポータルの機能がまとめられます。 Microsoft 365 Defender ポータルは、情報への迅速なアクセス、よりシンプルなレイアウト、およびより簡単に使用できるように関連情報をまとめることを重視しています。
>

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

[Microsoft Defender for Cloud Apps](/defender-cloud-apps)は、ログ収集、API コネクタ、リバース プロキシなど、さまざまなデプロイ モードをサポートする Cloud Access Security Broker (CASB) です。 Microsoft およびサードパーティのすべてのクラウド サービスでサイバー攻撃の脅威を特定して対処するための、機能豊富な表示、データ移動の制御機能、洗練された分析機能を提供します。

Defender for Cloud Apps は、主要な Microsoft ソリューションとネイティブに統合され、セキュリティの専門家を念頭に置いて設計されています。 これは、シンプルな配置、集中管理、革新的な自動化機能を提供します。

Defender for Cloud Apps フレームワークには、サイバー脅威や異常からネットワークを保護し、クラウド アプリ全体で異常な動作を検出してランサムウェア、侵害されたユーザー、または不正なアプリケーションを識別する機能が含まれています。 これにより、リスクの高い使用状況の分析が可能になり、組織にリスクを制限するために自動的に修復できます。

Defender for Cloud Apps アラートは、次のように分類できます。 

- 確認された悪意のあるアクティビティの TP。 
- 侵入テストやその他の承認された疑わしいアクションなど、疑わしいが悪意のないアクティビティに対する良性の真陽性 (B-TP)。 
- 確認された非悪意のあるアクティビティの FP。

## <a name="alert-grading-playbooks"></a>アラート グレーディング プレイブック

次の脅威に対するアラートをより迅速に評価する手順については、次のプレイブックを参照してください。

- [疑わしいメール転送アクティビティ](alert-grading-playbook-email-forwarding.md)
- [疑わしい受信トレイ操作ルール](alert-grading-playbook-inbox-manipulation-rules.md)
- [疑わしい受信トレイ転送ルール](alert-grading-playbook-inbox-forwarding-rules.md)

Microsoft 365 Defender ポータルでアラートを調べる方法については、「アラートの[調査](investigate-alerts.md)」を参照してください。
