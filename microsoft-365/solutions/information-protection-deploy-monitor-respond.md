---
title: 組織内のデータ プライバシー インシデントの監視と対応
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 監査ポリシーとアラート ポリシーとデータ主体要求を使用して、個人データ インシデントの監視と対応を行います。
ms.openlocfilehash: 225c0969f932490012a6cd54cb920cc59322ea9a8cea11c214a866ad58cecfca
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53804734"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>組織内のデータ プライバシー インシデントの監視と対応

Microsoft 365機能を運用する場合、組織内のデータ プライバシー インシデントの監視、調査、対応に役立つ機能を利用できます。 これらの各ドキュメントのプロセス、手順、その他のドキュメントを持つことは、規制機関へのコンプライアンスを実証する上でも重要な場合があります。

たとえば、次の環境です。: 

- 監査ポリシーとアラート ポリシー
- データ主体要求 (コンテンツ検索および電子情報開示を含む)
- その他の調査ツールとレポート

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>監視および応答ツールの使用に影響を与えるデータプライバシー規制

情報ガバナンス制御に関連する可能性があるデータプライバシー規制の一覧の例を次に示します。

- LGPD 第 46 条
- LGPD 第 48 条
- GDPR 記事 (5)(1)(f)
- GDPR 記事 (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

詳細については、「データプライバシーリスク [を評価し、機密情報を特定する」を参照してください](information-protection-deploy-assess.md)。

一般に、データのプライバシーに関する規制では、監視と対応のために次の要求が必要です。

- 個人データのストレージ、共有、および処理に関連するアクティビティの監査、警告、およびレポート
- データ主体要求 (DSR) に応答する機能、および場合によっては、そのような要求に準拠するための調査および他の管理措置を実行する機能。

組織は、他のコンプライアンスニーズやビジネス上の理由など、他の目的で監視および対応活動を実行することもできます。 データプライバシーの監視と対応のスキームを確立するには、全体的な監視と対応の計画、実装、および管理の一環として行う必要があります。

データ プライバシー規制に関する Microsoft 365 の監視と対応のスキームを開始するために、この記事では、Microsoft 365 で次のような質問に答えるのに役立つ機能を一覧表示します。 

- さまざまなデータ型とソースに対して、どのような種類の監視、調査、レポートの手法が利用できますか?
- データ主体要求 (DSR) と、匿名化、やり直し、削除などの修復アクションを処理するために必要なメカニズム。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>セキュリティ/コンプライアンス センターの監査ポリシーとアラート ポリシー

監査ポリシー、高度な監査ポリシー、およびアラート ポリシーの設定については、次の記事を参照してください。

- [統合監査](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [メールボックスの監査](../compliance/enable-mailbox-auditing.md)
- [高度な監査](../compliance/advanced-audit.md)
- [通知ポリシー](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR と CCPA のデータ主体要求

詳細[については、「GDPR](/compliance/regulatory/gdpr-dsr-Office365)および CCPA のデータ 主体要求」を参照してください。このサイトの DSR へのMicrosoft 365。

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Stream で削除されたユーザーを管理する

Microsoft Stream の場合、ユーザーが Azure Active Directory (Azure AD) から削除された場合、その時点より前に投稿された Stream ビデオに自分の名前が関連付けられている場合、そのユーザーの電子メール アドレスはビデオに関連付けられたままです。 「 [削除したユーザーを Microsoft Stream から管理して削除](/stream/managing-deleted-users) する」を参照してください。

## <a name="insider-risk-management-as-an-investigative-tool"></a>調査ツールとしてのインサイダー リスク管理

[Microsoft 365](../compliance/insider-risk-management.md)の Insider リスク管理は、組織内の危険なアクティビティを検出、調査、および実行することで、内部リスクを最小限に抑えるための Microsoft コンプライアンス管理センターの機能です。