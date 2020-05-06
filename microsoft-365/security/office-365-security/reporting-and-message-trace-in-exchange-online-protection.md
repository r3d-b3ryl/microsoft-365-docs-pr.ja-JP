---
title: Exchange Online Protection でのレポート作成とメッセージ追跡
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: この記事では、Microsoft Exchange Online Protection (EOP) 管理者が利用できるレポートとトラブルシューティングツールについて説明します。
ms.openlocfilehash: 44b4223b4310a2de1d90f99f8a7af23cc6054f94
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034382"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection でのレポート作成とメッセージ追跡

Microsoft Exchange Online Protection (EOP) には、組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートが用意されています。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。

## <a name="usage-reports"></a>利用状況レポート

**Microsoft 365 groups activity**: 作成および使用されている microsoft 365 グループの数に関する情報を表示します。

**電子メールアクティビティ**: 組織全体で送受信されたメッセージの数と、特定のユーザーに関する情報を表示します。

**電子メールアプリの使用状況**: 使用されている電子メールアプリに関する情報を表示します。 これには、各アプリの合計接続数、および接続している Outlook のバージョンが含まれます。

**メールボックスの使用状況**: メールボックスの使用済み記憶域、クォータ消費、アイテム数、最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。

詳細については、以下のリソースを参照してください。

- [管理センターの microsoft 365 レポート-Microsoft 365 グループ](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [管理センターの Microsoft 365 レポート-電子メールアクティビティ](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [管理センターの Microsoft 365 レポート-電子メールアプリの使用状況](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [管理センターでの Microsoft 365 レポート-メールボックスの使用状況](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターのセキュリティ & コンプライアンスレポート

これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。

**Advanced Threat Protection (atp)**: atp の一部である安全なリンクと安全な添付ファイルに関する情報を表示します。

**EOP**: マルウェアの検出、スプーフィングされたメール、スパム検出、組織との間のメールフローに関する情報を表示します。

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph を使用するカスタムレポート

Microsoft Graph を使用して、Microsoft 365 管理センターで利用可能なレポートをプログラムで作成します。 「 [Microsoft Graph で Office 365 の使用状況レポートを](https://docs.microsoft.com/graph/api/resources/report)使用する」のサブトピックを参照してください。

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph を使用するカスタムレポート

プログラムでレポートを作成します。 [Microsoft Graph の概要を](https://docs.microsoft.com/graph/overview)参照してください。

## <a name="message-trace"></a>メッセージの追跡

EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。

「 [Trace an email message」を](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)参照してください。

## <a name="audit-logging"></a>監査ログ

組織の管理者によって行われた特定の変更を追跡します。 これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。 「 [EOP の監査レポート」を](auditing-reports-in-eop.md)参照してください。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>レポート機能とメッセージ トレース データの使用可能性と遅延

EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。

||||
|:-----|:-----|:-----|
|**レポートの種類**|**データ使用可能期間 (遡及期間)**|**待機時間**|
|メール保護概要レポート|90 日間|メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。|
|メール保護詳細レポート|90 日|生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。 <br/><br/> 7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。|
|メッセージ追跡データ|90 日|生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。<br/><br/> 7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。|

> [!NOTE]
> データの可用性と待機時間は、Microsoft 365 管理センターまたはリモート PowerShell を介して要求された場合と同じです。
