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
description: 管理者は、良いメッセージと悪いメッセージやファイルを分析のために Microsoft に報告するさまざまな方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7818b15d97d8d7ee33005927ff899e9f5ff5a06
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682727"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、ユーザーと管理者の両方が、電子メール メッセージとファイルを Microsoft に報告するさまざまな方法があります。

|メソッド|説明|
|---|---|
|[申請ポータルを使用して、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|管理者がメールボックスを使用している組織の管理者Exchange Online推奨されるレポート方法 (スタンドアロン EOP では使用できません)。|
|[メッセージのレポートまたはフィッシング アドインのレポートを有効にする](enable-the-report-message-add-in.md)|OutlookとOutlook on the web (以前はOutlook Web App)。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは、 [管理者申請](admin-submission.md)ポータル、自動調査と応答 [(AIR)](air-view-investigation-results.md) の結果、 [ユーザー](view-email-security-reports.md#user-reported-messages-report)が報告したメッセージ レポート、 [エクスプローラー](threat-explorer-views.md#email--submissions)で利用できます。 <p> 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。
|[Outlook の誤検出と検出漏れを報告する](report-false-positives-and-false-negatives.md)|メッセージのレポート機能を使用して、誤検知 (ブロックまたは迷惑メール フォルダーに送信された適切なメール) と誤検知 (受信トレイに配信された不要なメールまたはフィッシング) を Exchange Online Protection (EOP) に送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|ユーザーが分析のために Microsoft にメッセージを報告したときに通知するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。|
|[分析のために、マルウェアおよびマルウェアでないファイルを Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティ インテリジェンス サイトを使用して、添付ファイルやその他のファイルを送信します。|

> [!NOTE]
> Microsoft への提出からのデータは、北米のデータ センターの Office 365 コンプライアンスの境界に存在します。 データは、フィルターの有効性を向上させるため、エンジニアリング チームのアナリストによってレビューされます。 申請は、フィルターの改善に役立つフィードバックと見なされ、30 日間保持されます。 その後、削除されます。
