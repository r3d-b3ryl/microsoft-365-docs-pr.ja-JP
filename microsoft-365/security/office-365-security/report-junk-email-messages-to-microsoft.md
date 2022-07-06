---
title: スパム、非スパム、フィッシング メッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、良いメッセージと悪いメッセージ、URL、電子メールの添付ファイル、管理者を分析のために Microsoft に報告するさまざまな方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 071e6329e16ecfce0e55649869d93ff31dfc9664
ms.sourcegitcommit: 4a1efedd15146744511378a44a307d44b16f3fb5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66644009"
---
# <a name="report-items-to-microsoft"></a>Microsoft にアイテムを報告する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含む Microsoft 365 組織では、Exchange Online メールボックスがない場合、ユーザーと管理者は、電子メール メッセージ、URL、および電子メール添付ファイルを Microsoft に報告するためのいくつかの異なる方法があります。 

さらに、Microsoft Defender for Endpoint管理者を持つ Microsoft 365 組織には、ファイルをレポートするためのいくつかの方法もあります。

|メソッド|説明|
|---|---|
|[送信ポータルを使用して、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に送信する](admin-submission.md)|Exchange Online メールボックスを持つ組織の管理者に推奨されるレポート方法 (スタンドアロン EOP では使用できません)。|
|[メッセージのレポートまたはフィッシング アドインのレポートを有効にする](enable-the-report-message-add-in.md)|Outlook とOutlook on the web (以前は Outlook Web App と呼ばられていました) で動作します。 <br/><br/> サブスクリプションに応じて、ユーザーがアドインを使用して報告したメッセージは[、管理申請ポータル](admin-submission.md)、[自動調査と応答 (AIR) の結果](air-view-investigation-results.md)、[ユーザーから報告されたメッセージ レポート](view-email-security-reports.md#user-reported-messages-report)、[エクスプローラーで](threat-explorer-views.md#email--submissions)利用できます。 <br/><br/> 報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトするように構成できます。 詳細については、「 [ユーザー申請ポリシー](user-submission.md)」を参照してください。
|[Outlook の誤検出と検出漏れを報告する](report-false-positives-and-false-negatives.md)|メッセージのレポート機能を使用して、誤検知 (ブロックまたは迷惑メール フォルダーに送信された適切なメール) と誤検知 (受信トレイに配信された不要なメールまたはフィッシング) を Exchange Online Protection (EOP) に送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|ユーザーが分析のために Microsoft にメッセージを報告したときに通知するメール フロー ルール (トランスポート ルールとも呼ばれます) を作成する方法について説明します。|
|[分析のために、マルウェアおよびマルウェアでないファイルを Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティ インテリジェンス サイトを使用して、添付ファイルやその他のファイルを送信します。|

> [!NOTE]
> Microsoft に電子メール エンティティを報告すると、電子メールに関連付けられているすべてのコピーが作成され、継続的なアルゴリズム レビューに含められます。 このコピーには、電子メール の内容、電子メール ヘッダー、および電子メール ルーティングに関する関連データが含まれます。 メッセージ内の添付ファイルも含まれます。
>
> Microsoft は、前述したすべての情報を分析し、メッセージの検疫アルゴリズムの微調整に取り組むお客様の組織のアクセス許可として、お客様のフィードバックを処理します。 Microsoft は、お客様から提出された提出を削除してから 30 日以内に削除されるまで、米国のセキュリティで保護された監査対象データセンターにお客様のメッセージを保持します。 Microsoft の担当者は、送信されたメッセージと添付ファイルを読み取ることができます。通常、Office 365のメールでは許可されません。 ただし、お客様の電子メールは、お客様と Microsoft の間で機密として扱われます。また、このレビュー プロセスの電子メールまたはその添付ファイルを読み取るために他のユーザーに提出を提供することはありません。
