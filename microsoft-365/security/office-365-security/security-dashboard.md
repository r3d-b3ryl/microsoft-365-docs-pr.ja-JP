---
title: セキュリティダッシュボードの概要
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 新しいセキュリティダッシュボードを使用して、Office 365 の脅威保護の状態を確認し、セキュリティの警告を表示して操作します。
ms.openlocfilehash: 7edfcfefc379aa30b7028097b21522d63cd26268
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434269"
---
# <a name="security-dashboard"></a>セキュリティダッシュボード

## <a name="basic-functions-and-how-to-open-security-dashboard"></a>基本的な機能とセキュリティダッシュボードを開く方法

[セキュリティ & コンプライアンスセンター](../../compliance/go-to-the-securitycompliance-center.md)を使用すると、組織でデータの保護とコンプライアンスを管理することができます。 必要なアクセス許可を持っていれば、セキュリティダッシュボードを使用して、脅威保護の状態を確認したり、セキュリティの警告を表示および操作したりできます。

概要についてはビデオを参照し、詳細についてはこの記事を読んでください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

組織のサブスクリプションに含まれるものに応じて、セキュリティダッシュボードには、次のセクションで説明するように、脅威管理の概要、脅威の保護の状態、グローバルな週次の脅威の検出、マルウェアなど、いくつかのウィジェットが含まれています。

セキュリティダッシュボードを表示するには、[セキュリティ & コンプライアンスセンター](../../compliance/go-to-the-securitycompliance-center.md)で、[**脅威管理**] ダッシュボードに移動し \> **Dashboard**ます。

> [!NOTE]
> セキュリティダッシュボードを表示するには、全体管理者、セキュリティ管理者、またはセキュリティリーダーである必要があります。 一部のウィジェットには、表示するための追加のアクセス許可が必要です。 詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="threat-management-summary"></a>脅威管理の概要

脅威管理の概要ウィジェットは、過去7日間の脅威から組織がどのように保護されているかをひとめで確認できます。

![セキュリティダッシュボード-脅威管理の概要ウィジェット](../../media/SecDash-ThreatMgmtSummary.png)

脅威管理の概要に表示される情報は、サブスクリプションの内容によって異なります。 次の表では、Office 365 E3 および Office 365 E5 に含まれる情報について説明します。

|Office 365 E3|Office 365 E5|
|---|---|
|ブロックされるマルウェアメッセージ<br/>ブロックされたフィッシングメッセージ<br>ユーザーによって報告されるメッセージ<br><br><br><br>|ブロックされるマルウェアメッセージ<br>ブロックされたフィッシングメッセージ<br>ユーザーによって報告されるメッセージ<br>ゼロ日のマルウェアがブロックされる<br>検出された高度なフィッシングメッセージ<br>ブロックされた悪意のある Url|

脅威管理の概要ウィジェットを表示またはアクセスするには、高度な脅威保護レポートを表示するためのアクセス許可を持っている必要があります。 詳細については、「 [ATP レポートを表示するために必要なアクセス許可](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)」を参照してください。

## <a name="threat-protection-status"></a>脅威保護の状態

脅威保護の状態ウィジェットは、フィッシングとマルウェアの傾向と詳細な表示を使用して、脅威保護の効果を示します。

![脅威保護状態ウィジェット](../../media/tpswidget.png)

詳細は、Microsoft 365 サブスクリプションに[Office 365 Advanced Threat protection](office-365-atp.md) (ATP) を含むかどうかに関する[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) が含まれているかどうかによって異なります。

|サブスクリプションに含まれるもの|これらの詳細が表示できます。|
|---|---|
|EOP ではないが、Office 365 ATP|EOP によって検出およびブロックされた悪意のある電子メール。<br><br> 「[脅威保護の状態レポート (EOP)](view-email-security-reports.md#threat-protection-status-report)」を参照してください。|
|Office 365 ATP|EOP および Office 365 ATP により、悪意のあるコンテンツや悪意のある電子メールが検出されブロックされる<br><br>マルウェア対策エンジン、[ゼロ時間自動削除](zero-hour-auto-purge.md)、atp 機能 ([安全なリンク](atp-safe-links.md)、[安全な添付ファイル](atp-safe-attachments.md)、 [atp のフィッシング対策](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)など) によってブロックされた一意の電子メールメッセージの集計数。<br><br>「[脅威保護の状態レポート (ATP)](view-reports-for-atp.md#threat-protection-status-report)」を参照してください。|

脅威保護状態ウィジェットを表示またはアクセスするには、Advanced Threat Protection レポートを表示する権限が必要です。 詳細については、「 [ATP レポートを表示するために必要なアクセス許可](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)」を参照してください。

## <a name="global-weekly-threat-detections"></a>グローバルな毎週の脅威の検出

グローバルな週次脅威検出ウィジェットは、過去7日間 (7 日間) の電子メールメッセージで検出された脅威の数を示します。

![グローバルな週次脅威検出ウィジェット](../../media/globalweeklythreatdetections.png)

メトリックは、次の表に示すように計算されます。

|測定基準|計算方法|
|---|---|
|スキャンされたメッセージ|スキャンされた電子メールメッセージの数を受信者の数で乗算した数|
|停止した脅威|マルウェアが含まれていると識別された電子メールメッセージの数が受信者数を乗算した回数|
|[ATP](office-365-atp.md)によるブロック|ATP によってブロックされた電子メールメッセージの数が受信者数に乗じる|
|配信後に削除|[0 時間の自動削除](zero-hour-auto-purge.md)によって削除されたメッセージの数が、受信者の数で乗算された数|

## <a name="malware"></a>マルウェア

マルウェアウィジェットは、マルウェアの傾向とマルウェアファミリの種類に関する詳細を過去7日間 (7 日間) に表示します。

![マルウェアの傾向とファミリの種類](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>分析情報

洞察では、確認すべき重要な問題が表面化するだけでなく、考慮すべき推奨事項とアクションも含まれています。

![Smart insights](../../media/smartinsights.png)

たとえば、一部のユーザーが迷惑メールのオプションを無効にしているために、フィッシング電子メールメッセージが配信されている可能性があります。 Insights の機能の詳細については、「 [Security & コンプライアンスセンターのレポートと分析](reports-and-insights-in-security-and-compliance.md)」を参照してください。

## <a name="threat-investigation-and-response"></a>脅威の調査および対応

組織のサブスクリプションに[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)が含まれている場合、セキュリティダッシュボードには、高度な脅威調査および応答ツールを含むセクションがあります。 これらのツールには[、自動調査と応答機能](automated-investigation-response-office.md)が含まれます。 自動調査と応答は、侵害された[ユーザーアカウントを迅速に解決](address-compromised-users-quickly.md)するなどのシナリオで役立ちます。

詳細については、「 [Office 365 の自動調査と応答 (AIR) の使用を開始](office-365-air.md)する」を参照してください。

## <a name="trends"></a>傾向

セキュリティダッシュボードの下部にある [**傾向**] セクションは、組織の電子メールフローの傾向を要約したものです。 レポートでは、スパム、マルウェア、フィッシングの試行、および適切な電子メールとして分類された電子メールに関する情報が提供されます。 タイルをクリックすると、レポートに詳細な情報が表示されます。

![[傾向] セクションには、組織の電子メールフローの傾向が要約されています。](../../media/trends.png)

また、組織のサブスクリプションに[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)が含まれている場合は、セキュリティチームが優先度の高いセキュリティ警告を表示してアクションを実行できるようにする、**最近の脅威管理通知**レポートもこのセクションにあります。

送信および受信した電子メールウィジェットを表示またはアクセスするには、高度な脅威保護レポートを表示するアクセス許可を持っている必要があります。 詳細については、「 [ATP レポートを表示するために必要なアクセス許可](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)」を参照してください。

最近の脅威管理通知 widget を表示またはアクセスするには、通知を表示するためのアクセス許可が必要です。 詳細については、「[通知の表示に必要な RBAC アクセス許可](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)」を参照してください。

## <a name="related-topics"></a>関連項目

[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Office 365 の脅威の調査と対応](office-365-ti.md)
