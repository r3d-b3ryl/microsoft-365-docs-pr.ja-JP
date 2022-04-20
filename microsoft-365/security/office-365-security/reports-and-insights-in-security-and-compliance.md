---
title: スマート レポート、分析情報 - Microsoft 365 セキュリティ & コンプライアンス センター
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: e3e95f68-36e9-4256-bcca-78fe7fe5ea5d
ms.collection:
- M365-security-compliance
description: セキュリティ & コンプライアンス センターで使用できるスマート レポートと分析情報、およびそれらを使用してデータを表示および調査し、迅速なアクションを実行する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 74ab7697dd865b581df5f9aa1fe50a983061e1ca
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941481"
---
# <a name="smart-reports-and-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターのスマート レポートと分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織のビジネス セキュリティ チーム向け Microsoft for 365 の一員であり、 [セキュリティ & コンプライアンス センターで必要なアクセス許可が割り当てられている](permissions-in-the-security-and-compliance-center.md)場合は、スマート レポートや分析情報など、さまざまなレポートにアクセスできます。 これらのレポートと分析情報の概要と、特定のレポートの詳細については、この記事を参照してください。

## <a name="smart-reports-and-insights-overview"></a>スマート レポートと分析情報の概要

セキュリティ & コンプライアンス センターで使用できる監視機能には、セキュリティ攻撃や不審なアクティビティの増加など、優先度の高い問題にコンプライアンスとセキュリティ管理者が集中できるようにするスマート レポートと分析情報が含まれます。 ダッシュボードでは、スマート レポートと分析情報は次の図のようになります。

:::image type="content" source="../../media/2a668c3d-3fa3-4e37-8149-46989b33ae8c.png" alt-text="セキュリティ & コンプライアンス センターのレポート ダッシュボード" lightbox="../../media/2a668c3d-3fa3-4e37-8149-46989b33ae8c.png":::

問題の領域の強調表示に加えて、スマート リポートおよび分析情報にはおすすめ候補が含まれ、データの表示および検索にリンクしてクイック アクションも実行します。 たとえば、組織で突然、エンド ユーザーによってスパムとしてマークされている電子メール メッセージの数が多い場合は、適切なレベルの保護が適用されるようにスパム対策ポリシーを再確認することをお勧めします。

## <a name="types-of-reports-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターのレポートの種類

セキュリティ & コンプライアンス センターでは、さまざまなレポートを利用できます。 (**レポート** > に移動するすべてのビューを取得するための **セキュリティ レポート**)。)次の表に、使用可能なレポートと、詳細を確認するためのリンクを示します。

|情報の種類|実行する方法|詳細については、こちらを参照してください。|
|---|---|---|
|**セキュリティ & コンプライアンス センター レポート** (すべて) <p> Microsoft Purview データ損失防止レポート、ラベル、電子メール セキュリティ レポート、Defender for Office 365 レポートなど、セキュリティ & コンプライアンス レポートへの主要な分析情報と推奨事項、およびリンク|セキュリティ & コンプライアンス センターで、**レポート** \> **ダッシュボード** に移動します|[セキュリティ センターとコンプライアンス センターのレポート](../../compliance/reports-in-security-and-compliance.md)|
|**データ損失防止** <p> データ損失防止ポリシーの一致、誤検知と上書き、ポリシーを作成または編集するリンク|セキュリティ & コンプライアンス センターで、**データ損失防止**\>ポリシーに移動 **します**|[データ損失防止のレポートを表示する](../../compliance/view-the-dlp-reports.md)|
|**データ ガバナンス** <p> ラベルの適用方法、レコード、ラベルの傾向などに分類されたラベルに関する情報。|セキュリティ & コンプライアンス センターで、**情報ガバナンス** \> **ダッシュボード** に移動します|[データ ガバナンスのレポートを表示する](../../compliance/view-the-data-governance-reports.md)|
|**脅威管理ダッシュボード** (これはセキュリティ ダッシュボードとも呼ばれます) <p> 脅威の検出、マルウェアの傾向、対象ユーザーの上位、送受信された電子メール メッセージに関する詳細など|セキュリティ & コンプライアンス センターで、**脆弱性管理** \> **ダッシュボード** に移動します|[Defender for Office 365のレポートを表示する](view-reports-for-mdo.md)|
|**エクスプローラー** (脅威エクスプローラーとも呼ばれます) または **リアルタイム検出** <p> Microsoft 365内の電子メールとファイルで検出されたマルウェアの疑い|セキュリティ & コンプライアンス センターで、**脆弱性管理** \> **エクスプローラー** または **リアルタイム検出** に移動します<br> |[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|
|**Defender for Office 365と電子メール セキュリティ レポート** <p> 電子メール セキュリティと脅威保護のレポート (マルウェア、スパム、フィッシング、スプーフィング レポートを含む)|セキュリティ & コンプライアンス センターで、**ReportsEmail** >  **& collaborationEmail** >  **[& コラボレーション レポート](https://security.microsoft.com/emailandcollabreport)** に移動します|[Defender for Office 365のレポートを表示する](view-reports-for-mdo.md) <p> [セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)|
|**メール フロー** <p> 送受信したメール メッセージ、最新の警告、上位の送信者と受信者、メール転送レポートなどに関する情報|セキュリティ & コンプライアンス センターで、**メール フロー** \> ダッシュボードと **レポート** \> **ダッシュボード** に移動します **。**|[セキュリティとコンプライアンス センターのメッセージ追跡の分析情報](mail-flow-insights-v2.md) <p> [セキュリティ & コンプライアンス センターでメール フロー レポートを表示する](view-mail-flow-reports.md)|
|**GDPR 準拠** <p> データ主体へのリンク、ラベルの傾向、アクティブな&クローズ ケースなど、GDPR コンプライアンスに関する情報|セキュリティ & コンプライアンス センターで、**データ プライバシー** \> **GDPR ダッシュボード** に移動します|[一般データ保護規則の概要](/compliance/regulatory/gdpr)|
|**監査ログ** <p> Microsoft 365 のアクティビティ、ユーザー、ファイルまたはフォルダーなどに関する情報|セキュリティ & コンプライアンス センターで、調査\>**監査ログ****の検索&検索** に移動します|[セキュリティ/コンプライアンス センターで監査ログを検索する](../../compliance/search-the-audit-log-in-security-and-compliance.md)|
|**コンプライアンス レポート** <p> FedRAMP のレポート、ガバナンス、リスクとコンプライアンス レポート、ISO 情報セキュリティ管理レポート、Service Organization Controls の監査レポートと評価レポート|セキュリティ & コンプライアンス センターで、**サービス 保証** \> **コンプライアンス レポート** に移動します|[Office 365でのセキュリティ&コンプライアンスの計画](../../compliance/plan-for-security-and-compliance.md)|

## <a name="related-topics"></a>関連項目

[Microsoft 365 Defender ポータル](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)

[Office 365の脅威から保護する](protect-against-threats.md)
