---
title: スパム、非スパム、フィッシングメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、問題のあるメッセージを Microsoft に報告するさまざまな方法について説明します。
ms.openlocfilehash: 19e00300b09674c5d44ffa7e38e0f4f3f93dda90
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634366"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

Exchange Online または Exchange online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織のユーザーと管理365者は、メッセージとファイルを Microsoft に報告するためのいくつかの異なる方法があります。

|||
|---|---|
|**メソッド**|**説明**|
|[管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|Exchange Online メールボックスを使用する組織での管理者に推奨される報告方法 (スタンドアロン EOP では利用できません)。|
|[Microsoft 365 でレポートメッセージアドインを有効にする](enable-the-report-message-add-in.md)|Outlook、Outlook for Mac、および web 上の Outlook (旧称 Outlook Web App) と共に動作し、推奨されるアドインです。 <br/><br/> サブスクリプションによっては、ユーザーがアドインで報告したメッセージが、自動化された[調査と応答 (航空) 結果](air-view-investigation-results.md)、[ユーザーが報告したメッセージレポート](view-email-security-reports.md#user-reported-messages-report)、および[脅威エクスプローラー](threat-explorer-views.md#email--submissions)で利用できるようになります。|
|[Microsoft Outlook の迷惑メール報告アドインをインストールして使用する365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook でのみ動作します。|
|[Microsoft 365 の Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online のメールボックスを使用する組織では、web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。|
|[分析のためにメッセージを手動で Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|スパムやフィッシングではなく、特定の Microsoft 電子メールアドレスに、添付されたメッセージを手動で送信します。 <br/><br/> また、ユーザーがこれらのレポート電子メールアドレスにメッセージを送信するときに通知するメールフロールール (トランスポートルールとも呼ばれます) を作成する方法についても説明します。|
|[マルウェアおよびマルウェアでないものを分析のために Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティインテリジェンスサイトを使用して、添付ファイルやその他のファイルを送信します。|
|

スパムまたはフィッシングメッセージが配信されずに検疫された場合、ユーザーはセキュリティ & コンプライアンスセンターの検疫ポータルから Microsoft にメッセージを報告できます。 詳細については、「 [Microsoft 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。