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
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: この記事では、EOP (EOP) 管理者が使用できるレポートとトラブルシューティング Microsoft Exchange Onlineについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179159"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP でのレポートとメッセージの追跡

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP は組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートを提供します。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。

## <a name="usage-reports"></a>利用状況レポート

- **Microsoft 365グループ アクティビティ**: 作成および使用されるグループMicrosoft 365の数に関する情報を表示します。 詳細については、「管理センター[の Microsoft 365 レポート - グループ」をMicrosoft 365してください](../../admin/activity-reports/office-365-groups.md)。
- **電子メール アクティビティ**: 組織全体、および特定のユーザーによって送信、受信、読み取られたメッセージの数に関する情報を表示します。 詳細については、「管理センター[の Microsoft 365 - メール アクティビティ」を参照してください](../../admin/activity-reports/email-activity.md)。
- **メール アプリの使用状況**: 使用するメール アプリに関する情報を表示します。 これには、各アプリの接続の総数と、接続しているアプリのOutlookが含まれます。 詳細については、「管理センターの Microsoft 365レポート - メール[アプリの使用状況」を参照してください](../../admin/activity-reports/email-apps-usage.md)。
- **メールボックスの使用状況**: メールボックスの使用ストレージ、クォータ消費、アイテム数、および最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。 詳細については、「管理センターの Microsoft 365レポート - メールボックス[の使用状況」を参照してください](../../admin/activity-reports/mailbox-usage.md)。

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>ディフェンダー ポータルMicrosoft 365レポート

これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。

- **Defender for Office 365**: Microsoft Defender for セーフの一部セーフリンクと添付ファイルに関する情報をOffice 365。 詳細については、「View [Defender for Office 365ポータル」をMicrosoft 365 Defenderしてください](view-reports-for-mdo.md)。
- **EOP**: 組織のマルウェア検出、スプーフィングメール、スパム検出、メール フローに関する情報を表示します。 詳細については、「電子メール セキュリティ[レポートをポータルで表示する」をMicrosoft 365 Defenderしてください](view-email-security-reports.md)。

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph を使用したカスタム レポート

Microsoft サーバーを使用して管理センターで使用できるレポートをプログラムGraph。 詳細については[、「Microsoft Graphの](/graph/overview)概要」および「Microsoft Office 365での使用状況レポートの操作」[を参照Graph。](/graph/api/resources/report)

## <a name="message-trace"></a>メッセージの追跡

EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。

「[メッセージ のトレース」を参照Microsoft 365 Defenderします](message-trace-scc.md)。

## <a name="audit-logging"></a>監査ログ

組織の管理者によって行われた特定の変更を追跡します。 これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。 「[監査レポート」を参照Exchange Online。](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>レポート機能とメッセージ トレース データの使用可能性と遅延

EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。

<br>

****

|レポートの種類|データ使用可能期間 (遡及期間)|Latency|
|---|---|---|
|メール保護概要レポート|90 日|メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。|
|メール保護詳細レポート|90 日|生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。 <p> 7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。|
|メッセージ追跡データ|90 日|生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。<p> 7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。|
|

> [!NOTE]
> データの可用性と待機時間は、管理センターまたはリモート PowerShell 経由で要求された場合と同じです。
