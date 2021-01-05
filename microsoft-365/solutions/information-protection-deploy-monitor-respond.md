---
title: 組織内のデータ プライバシー インシデントを監視して対応する
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
description: 個人データ インシデントの監視と対応には、監査ポリシーとアラート ポリシーとデータ主体要求を使用します。
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749589"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>組織内のデータ プライバシー インシデントを監視して対応する

Microsoft 365 の機能を使用すると、関連する機能を運用する組織内のデータ プライバシー インシデントの監視、調査、対応に役立ちます。 これらのそれぞれについてプロセス、手順、その他のドキュメントを用意することが、規制機関への準拠を示す上でも重要な場合があります。

これには次のものが含まれます。 

- 監査ポリシーとアラート ポリシー
- データ主体要求 (コンテンツ検索と電子情報開示を含む)
- その他の調査ツールとレポート

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>監視および対応ツールの使用に影響を与えるデータ プライバシー規制

情報ガバナンスコントロールに関連する可能性があるデータ プライバシー規制のサンプルリストを次に示します。

- LGPD 第 46 条
- LGPD 第 48 条
- GDPR 記事 (5)(1)(f)
- GDPR 記事 (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

詳細については、「データ のプライバシー リスク [を評価し、機密情報を特定する」を参照してください](information-protection-deploy-assess.md)。

一般に、データプライバシー規制では、監視と対応のために次の情報が必要です。

- 個人データの保存、共有、処理に関連するアクティビティの監査、警告、レポート
- データ主体要求 (DSR) に対応する機能、および場合によっては、そのような要求に準拠するために調査などの管理手段を実行する機能。

また、組織は、その他のコンプライアンスニーズやビジネス上の理由など、他の目的のために監視および対応活動を実行することもできます。 データ プライバシーの監視および対応スキームの確立は、全体的な監視と対応の計画、実装、および管理の一部として行う必要があります。

データ プライバシー規制に関する Microsoft 365 の監視および対応スキームを開始するために、この記事では、Microsoft 365 で次のような質問に答えるのに役立つ機能の一覧を示します。 

- さまざまなデータの種類とソースに対して、どのような種類の監視、調査、レポート作成の手法が利用できますか。
- データ主体要求 (DSR) と、匿名化、変更、削除などの修復アクションを処理するために必要なメカニズム。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>セキュリティ/コンプライアンス センターの監査ポリシーとアラート ポリシー

監査、高度な監査、アラート ポリシーの設定については、次の記事を参照してください。

- [統合監査](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [メールボックスの監査](../compliance/enable-mailbox-auditing.md)
- [高度な監査](../compliance/advanced-audit.md)
- [通知ポリシー](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のためのデータ主体要求

Microsoft 365 での DSR への対応については [、GDPR](../compliance/gdpr-dsr-office365.md) および CCPA に関するデータ主体要求を参照してください。

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Stream で削除されたユーザーを管理する

Microsoft Stream の場合、ユーザーが Azure Active Directory (Azure AD) から削除された場合、その時点より前に投稿された Stream ビデオにユーザーの名前が関連付けられている場合、そのユーザーの電子メール アドレスはビデオに関連付けられたままです。 削除 [するには、「Microsoft Stream から削除されたユーザーを管理](https://docs.microsoft.com/stream/managing-deleted-users) する」を参照してください。

## <a name="insider-risk-management-as-an-investigative-tool"></a>調査ツールとしてのインサイダー リスク管理

[Microsoft 365](../compliance/insider-risk-management.md) のインサイダー リスク管理は、Microsoft コンプライアンス管理センターの機能の 1 つで、組織内の危険なアクティビティを検出、調査、およびアクションを実行することで、内部リスクを最小限に抑えるのに役立ちます。
