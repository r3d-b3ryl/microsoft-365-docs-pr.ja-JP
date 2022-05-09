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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: この記事では、Microsoft Exchange Online Protection (EOP) 管理者が使用できるレポートとトラブルシューティング ツールについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 929fce14a9e128b724b4aa69d88e4a3062ed5640
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682419"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP でのレポート作成とメッセージ追跡

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを持つMicrosoft 365組織では、Exchange Onlineメールボックスがない組織では、組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートが EOP によって提供されます。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。

## <a name="usage-reports"></a>利用状況レポート

- **Microsoft 365 グループ アクティビティ**: 作成および使用されるMicrosoft 365 グループの数に関する情報を表示します。 詳細については、「[管理センターのレポートのMicrosoft 365 - Microsoft 365 グループ](../../admin/activity-reports/office-365-groups.md)」を参照してください。
- **電子メール アクティビティ**: 組織全体、および特定のユーザーが送信、受信、読み取るメッセージの数に関する情報を表示します。 詳細については、「[管理センターのレポートのMicrosoft 365 - 電子メール アクティビティ](../../admin/activity-reports/email-activity.md)」を参照してください。
- **電子メール アプリの使用状況**: 使用されている電子メール アプリに関する情報を表示します。 これには、各アプリの接続の合計数と、接続しているOutlookのバージョンが含まれます。 詳細については、「[管理センターのレポートのMicrosoft 365 - 電子メール アプリの使用状況](../../admin/activity-reports/email-apps-usage.md)」を参照してください。
- **メールボックスの使用状況: メールボックス** の使用ストレージ、クォータ使用量、アイテム数、および最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。 詳細については、「[管理センターでのレポートのMicrosoft 365 - メールボックスの使用状況](../../admin/activity-reports/mailbox-usage.md)」を参照してください。

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルのセキュリティ レポート

これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。

- **Defender for Office 365**: Microsoft Defender for Office 365の一部であるセーフリンクとセーフ添付ファイルに関する情報を表示します。 詳細については、「[Microsoft 365 Defender ポータルでレポートDefender for Office 365表示する」を参照してください](view-reports-for-mdo.md)。
- **EOP**: マルウェア検出、スプーフィングされたメール、スパム検出、組織との間のメール フローに関する情報を表示します。 詳細については、「[Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する](view-email-security-reports.md)」を参照してください。

## <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター のメール フロー インサイト

詳細については、「 [セキュリティ & コンプライアンス センターのメール フローの分析情報](mail-flow-insights-v2.md)」を参照してください。

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graphを使用したカスタム レポート

Microsoft Graphを使用して、管理センターで使用できるレポートをプログラムによって作成します。 詳細については、「[Microsoft Graphの概要と Microsoft Graph](/graph/overview)[でのOffice 365使用状況レポートの操作」を参照](/graph/api/resources/report)してください。

## <a name="message-trace"></a>メッセージの追跡

EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。

この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。

[Microsoft 365 Defender ポータルのメッセージ トレースを](message-trace-scc.md)参照してください。

## <a name="audit-logging"></a>監査ログ

組織の管理者によって行われた特定の変更を追跡します。 これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。 [Exchange Onlineの監査レポートを](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)参照してください。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>レポート機能とメッセージ トレース データの使用可能性と遅延

EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。

|レポートの種類|データ使用可能期間 (遡及期間)|遅延|
|---|---|---|
|メール保護概要レポート|90 日|メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。|
|メール保護詳細レポート|90 日|生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。 <p> 7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。|
|メッセージ追跡データ|90 日|生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。<p> 7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。|

> [!NOTE]
> データの可用性と待機時間は、管理センターまたはリモート PowerShell を介して要求された場合でも同じです。
