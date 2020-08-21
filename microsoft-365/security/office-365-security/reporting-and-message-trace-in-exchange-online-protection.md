---
title: レポート作成とメッセージ追跡
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: この記事では、メール保護 (EOP) 管理者が利用できるレポート Microsoft Exchange Onlineとトラブルシューティングのツールについて説明します。
ms.openlocfilehash: 149f7fa36a717a92d3cda5f6f3f82651f0144d73
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827631"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP でのレポート作成とメッセージ追跡

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP は、組織の全体的な状態と正常性を確認するために役立つさまざまなレポートを提供します。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。

## <a name="usage-reports"></a>利用状況レポート

**Microsoft 365 groups activity:** View information about the number of Microsoft 365 groups that are created and used.

**メール アクティビティ**: 組織全体の、および特定のユーザーによる、メッセージの送信、受信、読み取りの数に関する情報を表示します。

**メール アプリの利用状況**: 使用されているメール アプリに関する情報を表示します。 これには、各アプリの接続の合計数と、接続している Outlook のバージョンが含まれます。

**メールボックスの使用**状況: メールボックスの、使用済み記憶域、クォータ使用量、アイテムの数、最後のアクティビティ (送信または読み取り) に関する情報を表示します。

詳細については、以下のリソースを参照してください。

- [管理センターの Microsoft 365 レポート - Microsoft 365 グループ](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [管理センターでの Microsoft 365 レポート - メール アクティビティ](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [管理センターの Microsoft 365 レポート - メール アプリの利用状況](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [管理センターでの Microsoft 365 レポート - メールボックスの使用状況](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft &365 管理センターでのセキュリティ レポートのセキュリティ レポートの概要

これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。

**Advanced Threat Protection (ATP): ATP**の一部である安全なリンクと安全な添付ファイルに関する情報を表示します。

**EOP:** マルウェアの検出、なりすみメール、迷惑メールの検出、組織が外部とやり取りするメール フローに関する情報を表示します。

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph を使用したカスタム レポート

Microsoft Graph を使用して、管理センターで利用可能なレポートをプログラムで作成します。 詳細については、「Microsoft Graph Overview [of Microsoft Graph」および「Microsoft](https://docs.microsoft.com/graph/overview) [Graph での Office 365 利用状況レポートの使用」を参照してください](https://docs.microsoft.com/graph/api/resources/report)。

## <a name="message-trace"></a>メッセージの追跡

EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。

「 [コンプライアンス センターのメッセージ追跡」&をご覧ください](message-trace-scc.md)。

## <a name="audit-logging"></a>監査ログ

組織の管理者によって行われた特定の変更を追跡します。 これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。 [EOP の監査レポートを参照してください](auditing-reports-in-eop.md)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>レポート機能とメッセージ トレース データの使用可能性と遅延

EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。

****

|レポートの種類|データ使用可能期間 (遡及期間)|遅延|
|---|---|---|
|メール保護概要レポート|90 日|メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。|
|メール保護詳細レポート|90 日|生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。 <br/><br/> 7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。|
|メッセージ追跡データ|90 日|生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。<br/><br/> 7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。|
|

> [!NOTE]
> データの可用性と待機時間は、管理センターまたはリモート PowerShell の両方から要求された場合も同じです。
