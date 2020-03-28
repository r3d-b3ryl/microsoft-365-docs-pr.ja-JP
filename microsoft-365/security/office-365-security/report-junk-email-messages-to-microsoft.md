---
title: スパム、非スパム、フィッシングメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Microsoft Office Outlook 用迷惑メール報告アドインでは、次のような複数の方法で迷惑メール メッセージを報告できます。
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033664"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

Office 365 のユーザーおよび管理者 Exchange Online にメールボックスがある組織、または Exchange online のメールボックスを送信していないスタンドアロンの Exchange Online Protection (EOP) 組織では、メッセージを報告するためのいくつかの異なる方法があります。ファイルを Microsoft に。

|||
|---|---|
|**メソッド**|**説明**|
|[管理者提出を使用して、疑いのあるスパム、フィッシング、Url、およびファイルを Microsoft に送信する](admin-submission.md)|これは、Exchange Online メールボックス (スタンドアロン EOP では使用できません) を持つ組織での管理者のための推奨レポート方法です。|
|[Office 365 でレポートメッセージアドインを有効にする](enable-the-report-message-add-in.md)|Outlook、outlook for Mac、および Outlook on the web で動作します。 このアドインは推奨されています。 <br/><br/> ライセンスに応じて、報告されたメッセージは[自動調査と応答 (AIR) の結果](air-view-investigation-results.md)、[ユーザーが報告したメッセージレポート](view-email-security-reports.md#user-reported-messages-report)および[脅威エクスプローラー](threat-explorer-views.md#email--submissions)で利用できます。|
|[Office 365 で Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook でのみ動作します。|
|[Office 365 の Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online のメールボックスを使用する組織では、web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。|
|[マルウェアおよびマルウェアでないものを分析のために Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティインテリジェンスサイトを使用して、添付ファイルやその他のファイルを送信します。|
|

スパムまたはフィッシングメッセージが配信されずに検疫された場合、ユーザーは Office 365 セキュリティ & コンプライアンスセンターの検疫ポータルから Microsoft にメッセージを報告できます。 詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。