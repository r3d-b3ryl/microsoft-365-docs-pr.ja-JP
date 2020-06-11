---
title: 組織内のデータプライバシーインシデントを監視して応答する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 監査およびアラートポリシーとデータ主体要求を使用して、個人データインシデントを監視して応答します。
ms.openlocfilehash: 5760bb40eb26e2ff0636ea9604cc7c45b7d0ca63
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695069"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>組織内のデータプライバシーインシデントを監視して応答する

Microsoft 365 の機能は、operationalize 関連の機能を使用して、組織内のデータプライバシーインシデントの監視、調査、および対応に役立てることができます。 これらのプロセス、手順、およびその他のドキュメントについては、規制機関に準拠していることを示すためにも重要な場合があります。

これには次のものが含まれます。 

- 監査と警告ポリシー
- データ主体要求 (コンテンツ検索と電子情報開示を含む)
- その他の調査ツールおよびレポート

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>監視および応答ツールの使用に影響を与えるデータプライバシーの規制

以下は、情報ガバナンス統制に関連する可能性があるデータプライバシー規制の例です。

- LGPD 記事46
- LGPD 記事48
- GDPR 記事 (5) (1) (f)
- GDPR 記事 (15) (1) (e)
- HIPAA のエコー (45 C.F.R. 164.308 (a) (1) (ii) (D))
- HIPAA のエコー (45 C.F.R. 164.308 (a) (6.0) (ii)
- HIPAA のエコー (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

詳細については、「[データプライバシーのリスクを評価し、機密情報を識別](information-protection-deploy-assess.md)する」を参照してください。

データのプライバシーに関する規制では、通常、次のものが監視と対応のために呼び出されます。

- 個人データの保存、共有、処理に関連するアクティビティの監査、警告、およびレポート
- データ主体要求 (DSR) に応答する機能と、場合によっては、調査やその他の管理手段を実行してそのような要求に準拠することができます。

組織では、他の法令遵守やビジネス上の理由など、他の目的のために監視と応答のアクティビティを実行することも必要になる場合があります。 データのプライバシーに関する監視および応答スキームの確立は、全体的な監視および応答の計画、実装、および管理の一環として行う必要があります。

データプライバシー規制に関する Microsoft 365 の監視と応答のスキームを開始するために、この記事では、次のような質問に回答するために Microsoft 365 の便利な機能を示します。 

- さまざまなデータの種類とソースについて、どのような種類の日常の監視、調査、レポートの手法を使用できますか。
- データ主体要求 (DSRs) と、匿名化、墨消し、削除などの是正措置を処理するには、どのようなメカニズムが必要になります。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>セキュリティ/コンプライアンスセンターの監査とアラートポリシー

監査、詳細な監査、およびアラートポリシーの設定については、次の記事を参照してください。

- [統合監査](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [メールボックスの監査](../compliance/enable-mailbox-auditing.md)
- [詳細な監査](../compliance/advanced-audit.md)
- [通知ポリシー](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のデータ主体要求

Microsoft 365 での DSR への対応については[、「GDPR および CCPA のデータ主体要求](../compliance/gdpr-dsr-office365.md)」を参照してください。

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Stream で削除されたユーザーを管理する

Microsoft Stream の場合、ユーザーが Azure Active Directory (Azure AD) から削除されると、そのユーザーの名前がその時点より前のポストされたストリームビデオに関連付けられていた場合、そのユーザーの電子メールアドレスはビデオと関連付けられたままになります。 削除するには、「 [Microsoft Stream から削除されたユーザーを管理](https://docs.microsoft.com/stream/managing-deleted-users)する」を参照してください。

## <a name="additional-investigative-tools"></a>その他の調査ツール

以下に、組織内のデータプライバシーに関連するインシデントの監視、調査、および修復に役立つ可能性がある、次の2つのツールが追加されています。

- Microsoft [365 の Insider リスク管理](../compliance/insider-risk-management.md)(microsoft コンプライアンス管理センター) は、組織内のリスクの高い活動を検出、調査、処理を行うことによって、内部的なリスクを最小限に抑えるために役立ちます。
- Microsoft [365 のデータ調査](../compliance/overview-data-investigations.md)。 Microsoft のコンプライアンス管理センターの機能で、microsoft の365で機密データ、悪意のあるデータ、または誤ったデータを検索し、そのインシデントを修復するための適切な処置を実行するために何が起こったかを調査します。
