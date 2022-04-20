---
title: セキュリティ ダッシュボードの概要
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 新しいセキュリティ ダッシュボードを使用して、Office 365 Threat Protection の状態を確認し、セキュリティ アラートを表示および操作します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: defda5c112cf29cb944b502f442cf0e721a32676
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64971740"
---
# <a name="security-dashboard-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターのセキュリティ ダッシュボード

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="basic-functions-and-how-to-open-security-dashboard"></a>基本的な機能とセキュリティ ダッシュボードを開く方法

セキュリティ & コンプライアンス センターを使用すると、組織で <https://protection.office.com> データ保護とコンプライアンスを管理できます。 必要なアクセス許可があると仮定すると、セキュリティ ダッシュボードを使用すると、脅威保護の状態を確認したり、セキュリティ アラートを表示したり操作したりできます。

ビデオを見て概要を確認し、この記事を読んで詳細を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

組織のサブスクリプションに含まれるものに応じて、セキュリティ ダッシュボードには、次のセクションで説明するように、脅威管理の概要、脅威の保護状態、グローバルな週次脅威検出、マルウェアなど、いくつかのウィジェットが含まれます。

セキュリティ & コンプライアンス センターでセキュリティ ダッシュボードを表示するには、**脅威管理**\>ダッシュボードに移動 **します**。 セキュリティ ダッシュボードに直接移動するには、 <https://protection.office.com/searchandinvestigation/dashboard>.

> [!NOTE]
> セキュリティ ダッシュボードを表示するには、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーである必要があります。 一部のウィジェットでは、表示に追加のアクセス許可が必要です。 詳細については、「 [セキュリティ & コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="threat-management-summary"></a>脅威管理の概要

脅威管理の概要ウィジェットには、過去 7 日間の脅威から組織がどのように保護されたかが一目でわかります。

:::image type="content" source="../../media/SecDash-ThreatMgmtSummary.png" alt-text="セキュリティ ダッシュボード - 脅威管理の概要ウィジェット" lightbox="../../media/SecDash-ThreatMgmtSummary.png":::

脅威管理の概要に表示される情報は、サブスクリプションに含まれる内容によって異なります。 次の表では、Office 365 E3とOffice 365 E5に含まれる情報について説明します。

|Office 365 E3|Office 365 E5|
|---|---|
|ブロックされたマルウェア メッセージ<br>ブロックされたフィッシング メッセージ<br>ユーザーによって報告されたメッセージ<br><br><br><br>|ブロックされたマルウェア メッセージ<br>ブロックされたフィッシング メッセージ<br>ユーザーによって報告されたメッセージ<br>ブロックされたゼロデイ マルウェア<br>高度なフィッシング メッセージが検出されました<br>ブロックされた悪意のある URL|

脅威管理の概要ウィジェットを表示またはアクセスするには、Defender for Office 365 レポートを表示するアクセス許可が必要です。 詳細については、「[Defender for Office 365 レポートを表示するために必要なアクセス許可](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)」を参照してください。

## <a name="threat-protection-status"></a>脅威の保護の状態

Threat Protection Status ウィジェットは、フィッシングとマルウェアの傾向と詳細なビューを使用して、脅威保護の有効性を示します。

:::image type="content" source="../../media/tpswidget.png" alt-text="脅威の保護の状態ウィジェット" lightbox="../../media/tpswidget.png":::

詳細は、Microsoft 365 サブスクリプションにMicrosoft Defender for Office 365の有無にかかわらず[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) が含まれているかどうかによって異[なります。](defender-for-office-365.md)

|サブスクリプションに含まれる場合...|これらの詳細が表示されます|
|---|---|
|EOP がMicrosoft Defender for Office 365ではない|EOP によって検出され、ブロックされた悪意のある電子メール。<p> [Threat Protection 状態レポート (EOP)](view-email-security-reports.md#threat-protection-status-report) を参照してください。|
|Microsoft Defender for Office 365|EOP とDefender for Office 365によって検出され、ブロックされた悪意のあるコンテンツと悪意のある電子メール <p> マルウェア対策エンジン、[0 時間の自動消去](zero-hour-auto-purge.md)、Defender for Office 365機能 ([セーフ リンク](safe-links.md)、セーフ[添付ファイル](safe-attachments.md)、[Defender for Office 365でのフィッシング対策](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)を含む) によってブロックされた悪意のあるコンテンツを含む一意の電子メール メッセージの集計された数。 <p> [脅威保護の状態レポート](view-reports-for-mdo.md#threat-protection-status-report)を参照してください。|

Threat Protection Status ウィジェットを表示またはアクセスするには、Defender for Office 365 レポートを表示するアクセス許可が必要です。 詳細については、「[Defender for Office 365 レポートを表示するために必要なアクセス許可は何ですか?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Global Weekly Threat Detections

Global Weekly Threat Detections ウィジェットは、過去 7 日間に電子メール メッセージで検出された脅威の数を示します。

:::image type="content" source="../../media/globalweeklythreatdetections.png" alt-text="Global Weekly Threat Detections ウィジェット" lightbox="../../media/globalweeklythreatdetections.png":::

メトリックは、次の表に示すように計算されます。

|測定基準|計算方法|
|---|---|
|スキャンされたメッセージ|スキャンされた電子メール メッセージの数に受信者の数を掛けたもの|
|停止された脅威|マルウェアが含まれていると識別された電子メール メッセージの数に受信者の数を乗算した数|
|[Defender for Office 365](defender-for-office-365.md)によってブロックされる|Defender for Office 365によってブロックされた電子メール メッセージの数に受信者の数を乗算した数|
|配信後に削除されました|[ゼロ時間自動消去 (ZAP)](zero-hour-auto-purge.md) によって削除されたメッセージの数に受信者の数を乗算した数|

## <a name="malware"></a>マルウェア

マルウェア ウィジェットには、過去 7 日間のマルウェアの傾向とマルウェア ファミリの種類に関する詳細が表示されます。

:::image type="content" source="../../media/malwarewidgetatpe5.png" alt-text="マルウェアの傾向とファミリの種類" lightbox="../../media/malwarewidgetatpe5.png":::

## <a name="insights"></a>分析情報

インサイト主な問題を確認する必要があるだけでなく、考慮すべき推奨事項やアクションも含まれます。

:::image type="content" source="../../media/smartinsights.png" alt-text="Smart insights" lightbox="../../media/smartinsights.png":::

たとえば、一部のユーザーが迷惑メール オプションを無効にしているため、フィッシングメール メッセージが配信されている場合があります。 分析情報のしくみの詳細については、 [セキュリティ & コンプライアンス センターのレポートと分析情報に](reports-and-insights-in-security-and-compliance.md)関するページを参照してください。

## <a name="threat-investigation-and-response"></a>脅威の調査および対応

組織のサブスクリプションに[プラン 2 Microsoft Defender for Office 365](office-365-ti.md)含まれている場合、セキュリティ ダッシュボードには高度な脅威調査と対応ツールを含むセクションがあります。 これらのツールには [、自動調査機能と応答機能が含まれます](automated-investigation-response-office.md)。 自動調査と対応は、 [侵害されたユーザー アカウントに迅速に対処](address-compromised-users-quickly.md)するなどのシナリオで役立ちます。

詳細については、Office 365の[自動調査と応答 (AIR) の使用に関する概要を](office-365-air.md)参照してください。

## <a name="trends"></a>傾向

セキュリティ ダッシュボードの下部には、組織の電子メール フローの傾向をまとめた[ **傾向** ] セクションがあります。 レポートには、スパム、マルウェア、フィッシング詐欺の試行、および適切なメールとして分類された電子メールに関する情報が提供されます。 タイルをクリックすると、レポートの詳細情報が表示されます。

:::image type="content" source="../../media/trends.png" alt-text="組織の電子メール フローの傾向をまとめた [傾向] セクション" lightbox="../../media/trends.png":::

また、組織のサブスクリプション [にプラン 2 Defender for Office 365](office-365-ti.md)含まれている場合は、セキュリティ チームが優先度の高いセキュリティ アラートを表示してアクションを実行できるようにする、このセクションの **[最近の脅威管理アラート**] レポートもあります。

送信済みおよび受信メール ウィジェットを表示またはアクセスするには、Defender for Office 365 レポートを表示するアクセス許可が必要です。 詳細については、「[Defender for Office 365 レポートを表示するために必要なアクセス許可](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)」を参照してください。

[最近の脅威管理アラート] ウィジェットを表示またはアクセスするには、アラートを表示するアクセス許可が必要です。 詳細については、アラートを [表示するために必要な RBAC アクセス許可に関するページを参照](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)してください。

## <a name="related-articles"></a>関連記事

[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)

[Microsoft Defender for Office 365のレポートを表示する](view-reports-for-mdo.md)

[Defender for Office 365](defender-for-office-365.md)

[Office 365脅威の調査と対応](office-365-ti.md)
