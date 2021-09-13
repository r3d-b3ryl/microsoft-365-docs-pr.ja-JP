---
title: スパム、非スパム、フィッシング メッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、良いメッセージと悪いメッセージやファイルを分析のために Microsoft に報告するさまざまな方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 898fd42e687ec9d5776c1791ed353937921af4ff
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179160"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、ユーザーと管理者の両方が、電子メール メッセージとファイルを Microsoft に報告するさまざまな方法があります。

<br>

****

|メソッド|説明|
|---|---|
|[申請ポータルを使用して、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|管理者がメールボックスを使用している組織の管理者Exchange Online推奨されるレポート方法 (スタンドアロン EOP では使用できません)。|
|[メッセージのレポートまたはフィッシング アドインのレポートを有効にする](enable-the-report-message-add-in.md)|OutlookとOutlook on the web (旧称: Outlook Web App)。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは、[管理者](admin-submission.md)申請ポータル、自動調査と応答[(AIR)](air-view-investigation-results.md)の結果、ユーザー報告メッセージ レポート、[](view-email-security-reports.md#user-reported-messages-report)エクスプローラーで利用[できます](threat-explorer-views.md#email--submissions)。 <p> 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。
|[Outlook の誤検出と検出漏れを報告する](report-false-positives-and-false-negatives.md)|メッセージのレポート機能を使用して、誤検知 (ブロックまたは迷惑メール フォルダーに送信された適切なメール) と誤検知 (受信トレイに配信された不要なメールまたはフィッシング) を Exchange Online Protection (EOP) に送信します。|
|[分析のために、メッセージを手動で Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|迷惑メールや迷惑メールではないメール、またフィッシングとして、特定の Microsoft メール アドレスに添付メッセージを手動で送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|ユーザーが分析のために Microsoft にメッセージを報告したときに通知するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。|
|[分析のために、マルウェアおよびマルウェアでないファイルを Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティ インテリジェンス サイトを使用して、添付ファイルやその他のファイルを送信します。|
|

スパムメッセージまたはフィッシング メッセージが配信される代わりに検疫された場合、ユーザーはポータルの検疫から Microsoft にメッセージをMicrosoft 365 Defenderできます。 詳細については、「検疫済み[メッセージをユーザーとして](find-and-release-quarantined-messages-as-a-user.md)検索して解放する」を参照Microsoft 365。

> [!NOTE]
> Microsoft への提出からのデータは、北米のデータ センターの Office 365 コンプライアンスの境界に存在します。 データは、フィルターの有効性を向上させるため、エンジニアリング チームのアナリストによってレビューされます。
