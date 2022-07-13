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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: 監査ポリシーとアラート ポリシーとデータ主体の要求を使用して、個人データ インシデントを監視し、対応します。
ms.openlocfilehash: 2a19154b9b0602eded09e6521dc285c00fd56a10
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66748288"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>組織内のデータ プライバシー インシデントを監視して対応する

Microsoft 365 機能は、関連する機能を運用する際に、組織内のデータ プライバシー インシデントを監視、調査、および対応するのに役立ちます。 それぞれのプロセス、手順、およびその他のドキュメントを持つことは、規制機関へのコンプライアンスを示すためにも重要な場合があります。

たとえば、次の環境です。: 

- 監査ポリシーとアラート ポリシー
- データ主体の要求 (コンテンツ検索と電子情報開示を含む)
- その他の調査ツールとレポート

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>監視ツールと応答ツールの使用に影響を与えるデータ プライバシー規制

情報ガバナンス管理に関連する可能性のあるデータ プライバシー規制のサンプル一覧を次に示します。

- LGPD 記事 46
- LGPD 記事 48
- GDPR 記事 (5)(1)(f)
- GDPR 記事 (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

詳細については、「 [データ プライバシー リスクを評価し、機密情報を特定する](information-protection-deploy-assess.md)」を参照してください。

データ プライバシー規制では、一般に、監視と対応のために次のものが必要です。

- 個人データの保存、共有、処理に関連するアクティビティの監査、アラート、およびレポート
- データ主体要求 (DSR) に応答する機能と、場合によっては、そのような要求に準拠するために調査やその他の管理措置を実行する機能。

組織では、他のコンプライアンス ニーズやビジネス上の理由など、他の目的で監視と対応アクティビティを実行することもできます。 データプライバシーの監視と対応スキームの確立は、全体的な監視と対応の計画、実装、および管理の一環として行う必要があります。

データプライバシー規制に関する Microsoft 365 の監視と対応スキームの使用を開始するために、この記事では、次のような質問に答えるために、Microsoft 365 の便利な機能を一覧表示します。 

- さまざまなデータの種類とソースに対して、どのような日常的な監視、調査、およびレポート手法を利用できますか?
- データ主体要求 (DSR) と、匿名化、再実行、削除などの修復アクションを処理するために必要なメカニズム。

## <a name="auditing-and-alert-policies-in-the-microsoft-purview-compliance-portal"></a>Microsoft Purview コンプライアンス ポータルの監査ポリシーとアラート ポリシー

監査、高度な監査、アラート ポリシーの設定については、次の記事を参照してください。

- [統合監査](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [メールボックスの監査](../compliance/enable-mailbox-auditing.md)
- [監査 (プレミアム)](../compliance/advanced-audit.md)
- [通知ポリシー](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR と CCPA のデータ主体要求

Microsoft 365 の DSR への対応については、 [GDPR と CCPA のデータ主体](/compliance/regulatory/gdpr-dsr-Office365) 要求に関するページを参照してください。

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Streamで削除されたユーザーを管理する

Microsoft Streamでは、ユーザーが Azure Active Directory (Azure AD) から削除されたときに、その名前がその時点より前に投稿された Stream ビデオに関連付けられていた場合、そのメール アドレスはビデオに関連付けられたままになります。 削除するには、「[Microsoft Streamから削除されたユーザーを管理](/stream/managing-deleted-users)する」を参照してください。

## <a name="insider-risk-management-as-an-investigative-tool"></a>調査ツールとしてのインサイダー リスク管理

[インサイダー リスク管理](../compliance/insider-risk-management.md)は、組織内の危険なアクティビティを検出、調査、および実行できるようにすることで内部リスクを最小限に抑えるのに役立つ、Microsoft Purview コンプライアンス ポータルの機能です。
