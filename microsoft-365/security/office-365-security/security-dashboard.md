---
title: セキュリティ ダッシュボードの概要
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 新しいセキュリティ ダッシュボードを使用して、Office 365 Threat Protection の状態を確認し、セキュリティの警告を表示して処理します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 72743f1b052d39ac4762dffc0b3e3e694befa8bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "50288325"
---
# <a name="security-dashboard"></a>セキュリティ ダッシュボード

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>基本的な機能とセキュリティ ダッシュボードを開く方法

セキュリティ [& コンプライアンス センター](../../compliance/go-to-the-securitycompliance-center.md) を使用すると、組織でデータ保護とコンプライアンスを管理できます。 必要なアクセス許可がある場合、セキュリティ ダッシュボードを使用すると、脅威保護の状態を確認し、セキュリティの警告を表示して操作できます。

概要については、ビデオをご覧ください。詳しくは、この記事をご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

組織のサブスクリプションに含まれるものに応じて、セキュリティ ダッシュボードには、次のセクションで説明するように、脅威管理の概要、脅威保護の状態、グローバルな毎週の脅威の検出、マルウェアなど、いくつかのウィジェットが含まれます。

セキュリティ ダッシュボードを表示するには、セキュリティ & [コンプライアンス センター](../../compliance/go-to-the-securitycompliance-center.md)で、脅威管理 **ダッシュボードに移動** \> **します**。

> [!NOTE]
> セキュリティ ダッシュボードを表示するには、グローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者である必要があります。 一部のウィジェットでは、表示に追加のアクセス許可が必要です。 詳細については、セキュリティ/コンプライアンス [センターの「アクセス許可&参照してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="threat-management-summary"></a>脅威管理の概要

脅威管理の概要ウィジェットは、過去 7 日間の脅威から組織がどのように保護されたのかが一目でわかります。

![セキュリティ ダッシュボード - 脅威管理の概要ウィジェット](../../media/SecDash-ThreatMgmtSummary.png)

脅威管理の概要に表示される情報は、サブスクリプションに含まれる内容によって異なります。 次の表では、365 E3 および Office 365 E5 に含Office説明します。

|Office 365 E3|Office 365 E5|
|---|---|
|ブロックされたマルウェア メッセージ<br>フィッシング メッセージのブロック<br>ユーザーによって報告されるメッセージ<br><br><br><br>|ブロックされたマルウェア メッセージ<br>フィッシング メッセージのブロック<br>ユーザーによって報告されるメッセージ<br>ゼロデイ マルウェアのブロック<br>高度なフィッシング メッセージが検出されました<br>ブロックされた悪意のある URL|

脅威管理の概要ウィジェットを表示またはアクセスするには、365 レポートの Defender を表示するアクセス許可Office必要があります。 詳細については、「Defender for [Office 365](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)レポートを表示するために必要なアクセス許可について」を参照してください。

## <a name="threat-protection-status"></a>脅威保護の状態

脅威保護状態ウィジェットは、フィッシングとマルウェアの傾向と詳細なビューで脅威保護の有効性を示します。

![脅威保護状態ウィジェット](../../media/tpswidget.png)

詳細は、Microsoft 365 サブスクリプションに Microsoft Defender for Office [365](office-365-atp.md)の[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) が含まれるかどうかによって異なる。

|サブスクリプションに含まれる場合...|次の詳細が表示されます。|
|---|---|
|EOP が、Microsoft Defender for Office 365 ではない|EOP によって検出およびブロックされた悪意のある電子メール。<p> 「 [脅威保護の状態レポート (EOP)」を参照してください](view-email-security-reports.md#threat-protection-status-report)。|
|Microsoft Defender for Office 365|EOP と Defender によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子Office 365 <p> マルウェア対策エンジン、ゼロアワー自動消去、および Office 365[](zero-hour-auto-purge.md)の機能 (Defender [for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)の安全なリンク、[](atp-safe-links.md)安全な添付[](atp-safe-attachments.md)ファイル、フィッシング対策など) でブロックされた悪意のあるコンテンツを含む一意の電子メール メッセージの集計数。 <p> 「 [脅威保護の状態レポート」を参照してください](view-reports-for-atp.md#threat-protection-status-report)。|

脅威保護状態ウィジェットを表示またはアクセスするには、365 レポートの Defender を表示するためのアクセスOffice必要があります。 詳細については、「Defender for Office 365 レポートを表示するために必要なアクセス許可 [」を参照してください。](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>グローバルな週次脅威検出

Global Weekly Threat Detections ウィジェットは、過去 7 日間に電子メール メッセージで検出された脅威の数を表示します。

![Global Weekly Threat Detections ウィジェット](../../media/globalweeklythreatdetections.png)

測定基準は、次の表に示すとおりに計算されます。

|測定基準|計算方法|
|---|---|
|スキャンされたメッセージ|スキャンされた電子メール メッセージの数と受信者の数の乗算|
|脅威の停止|マルウェアが含まれていると識別された電子メール メッセージの数と受信者の数の乗算|
|Defender による Office [365 のブロック ](office-365-atp.md)|Defender によってブロックされるメール メッセージの数 (Office 365 と受信者の数の乗算)|
|配信後に削除|ゼロアワー自動消去によって削除 [された](zero-hour-auto-purge.md) メッセージの数と受信者の数の乗算|

## <a name="malware"></a>マルウェア

マルウェア ウィジェットは、過去 7 日間のマルウェアの傾向とマルウェア ファミリの種類に関する詳細を表示します。

![マルウェアの傾向と家族の種類](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>分析情報

分析情報には、確認する必要がある主要な問題だけでなく、考慮すべき推奨事項やアクションも含まれます。

![スマートインサイト](../../media/smartinsights.png)

たとえば、一部のユーザーが迷惑メール オプションを無効にしたため、フィッシングメール メッセージが配信されている場合があります。 分析情報の動作の詳細については、セキュリティ/コンプライアンス センターの「レポート [と分析&参照してください](reports-and-insights-in-security-and-compliance.md)。

## <a name="threat-investigation-and-response"></a>脅威の調査および対応

組織のサブスクリプションに Office  [365 プラン 2](office-365-ti.md)用の Microsoft Defender が含まれる場合、セキュリティ ダッシュボードには高度な脅威の調査と対応のツールを含むセクションがあります。 これらのツールには [、自動調査および対応機能が含まれます](automated-investigation-response-office.md)。 侵害されたユーザー アカウントに迅速に対処するなどのシナリオでは、自動調査 [と対応が役立ちます](address-compromised-users-quickly.md)。

詳細については、「Office [365](office-365-air.md)での自動調査と対応 (AIR) の使用を開始する」を参照してください。

## <a name="trends"></a>傾向

セキュリティ ダッシュボードの下部にある **[Trends]** セクションでは、組織のメール フローの傾向を要約します。 レポートは、スパム、マルウェア、フィッシング詐欺、および優れたメールとして分類された電子メールに関する情報を提供します。 タイルをクリックすると、レポートに詳細情報が表示されます。

![[Trends] セクションは、組織のメール フローの傾向を要約します。](../../media/trends.png)

また、組織のサブスクリプションに defender [for Office 365 プラン 2](office-365-ti.md)が含まれる場合は、セキュリティ チームが優先度の高いセキュリティ警告を表示してアクションを実行できる Recent **threat Management** アラート レポートもこのセクションに表示されます。

送信メールと受信メール ウィジェットを表示またはアクセスするには、365 レポートの Defender を表示するためのアクセス許可Office必要があります。 詳細については、「Defender for [Office 365](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)レポートを表示するために必要なアクセス許可について」を参照してください。

Recent Threat Management Alerts ウィジェットを表示またはアクセスするには、アラートを表示するためのアクセス許可が必要です。 詳細については、「アラートを表示 [するために必要な RBAC のアクセス許可」を参照してください](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。

## <a name="related-topics"></a>関連項目

[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)

[Microsoft Defender for Office 365 のレポートを表示する](view-reports-for-atp.md)

[Defender for Office 365](office-365-atp.md)

[Office 365 脅威の調査と対応](office-365-ti.md)
