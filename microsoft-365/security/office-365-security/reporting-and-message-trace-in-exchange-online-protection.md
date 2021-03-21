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
ms.openlocfilehash: 1307fa1431a4fdd46c9ab070a2986a015891568f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918680"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP でのレポートとメッセージの追跡

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、EOP は組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートを提供します。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。

## <a name="usage-reports"></a>利用状況レポート

**Microsoft 365 グループ アクティビティ**: 作成および使用される Microsoft 365 グループの数に関する情報を表示します。

**電子メール アクティビティ**: 組織全体で、および特定のユーザーによって送信、受信、読み取られたメッセージの数に関する情報を表示します。

**メール アプリの使用状況**: 使用するメール アプリに関する情報を表示します。 これには、各アプリの接続の総数と、接続している Outlook のバージョンが含まれます。

**メールボックスの使用状況**: メールボックスの使用ストレージ、クォータ消費、アイテム数、および最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。

詳細については、以下のリソースを参照してください。

- [管理センターの Microsoft 365 レポート - Microsoft 365 グループ](../../admin/activity-reports/office-365-groups.md)

- [管理センターの Microsoft 365 レポート - メール アクティビティ](../../admin/activity-reports/email-activity.md)

- [管理センターの Microsoft 365 レポート - メール アプリの使用状況](../../admin/activity-reports/email-apps-usage.md)

- [管理センターの Microsoft 365 レポート - メールボックスの使用状況](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft 365 &センターのセキュリティ とコンプライアンス レポート

これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。

**Defender for Office 365**: Microsoft Defender for Office 365 の一部である安全なリンクと安全な添付ファイルに関する情報を表示します。

**EOP**: 組織のマルウェア検出、スプーフィングメール、スパム検出、メール フローに関する情報を表示します。

[Defender for Office 365 のレポートを表示する](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph を使用したカスタム レポート

Microsoft Graph を使用して管理センターで使用できるレポートをプログラムで作成します。 詳細については [、「Microsoft Graph の概要」および「Microsoft Graph](/graph/overview) での [365](/graph/api/resources/report)使用状況Officeの操作」を参照してください。

## <a name="message-trace"></a>メッセージの追跡

EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。

「 [セキュリティ コンプライアンス センター」の「メッセージ &」を参照してください](message-trace-scc.md)。

## <a name="audit-logging"></a>監査ログ

組織の管理者によって行われた特定の変更を追跡します。 これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。 [「EOP でのレポートの監査」を参照してください](auditing-reports-in-eop.md)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>レポート機能とメッセージ トレース データの使用可能性と遅延

EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。

****

|レポートの種類|データ使用可能期間 (遡及期間)|遅延|
|---|---|---|
|メール保護概要レポート|90 日|メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。|
|メール保護詳細レポート|90 日|生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。 <p> 7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。|
|メッセージ追跡データ|90 日|生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。<p> 7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。|
|

> [!NOTE]
> データの可用性と待機時間は、管理センターまたはリモート PowerShell 経由で要求された場合と同じです。