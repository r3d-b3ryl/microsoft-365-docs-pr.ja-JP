---
title: スパム、非スパム、フィッシングのメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、優れたメッセージと不良なメッセージとファイルを分析用として Microsoft に報告するさまざまな方法について学習できます。
ms.openlocfilehash: fabe28d084361041ae9e6a8d118dd8c43c2225f7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827643"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

Exchange Online にメールボックスがある Microsoft 365 組織、または Exchange Online メールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織では、ユーザーと管理者の両方が、電子メール メッセージとファイルを Microsoft に報告するさまざまな方法を使用しています。

****

|メソッド|説明|
|---|---|
|[管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|Exchange Online メールボックスを使用している組織の管理者向けの推奨レポート方式 (スタンドアロン EOP では使用不可)。|
|[レポート メッセージ アドインを有効にする](enable-the-report-message-add-in.md)|Outlook、Outlook for Mac、および Outlook on the web (Outlook Web App) を操作するもので、推奨されるアドインです。 <br/><br/> サブスクリプションによっては、アドインで報告されたユーザーのメッセージは[管理の送信ポータル](admin-submission.md)[、AIR (自動調査および応答 )、ユーザー](air-view-investigation-results.md)から報告されたメッセージ レポート、脅威[User-reported messages report](view-email-security-reports.md#user-reported-messages-report)[エクスプローラーで確認できます](threat-explorer-views.md#email--submissions)。 <br/><br/> 報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトする構成ができます。 詳細については、「EOP でスパム [やフィッシング メッセージのユーザーを送信するためのメールボックスを指定する」を参照してください](user-submission.md)。|
|[Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook でのみ機能します。|
|[Outlook on the web で迷惑メールとフィッシング メールを報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online メールボックスを使用している組織には、Web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。 <br/><br/> ユーザー レポートに表示されるメッセージは、 [管理の送信ポータルで確認できます](admin-submission.md)。 <br/><br/> 報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトする構成ができます。 詳細については [、Exchange Online でスパムやフィッシングのメッセージを送信するためのメールボックスを指定する方法を参照してください](user-submission.md)。|
|[分析用に Microsoft に手動でメッセージを送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|スパムやフィッシング処理は、スパムおよびフィッシングでない特定の Microsoft 電子メール アドレスに手動で送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|ユーザーが分析を行うときに Microsoft にメッセージを報告するときにユーザーに知示すメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。
|||
|[マルウェアおよびマルウェアでないファイルを分析のために Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティ インテリジェンス サイトを使用して添付ファイルおよびその他のファイルを送信します。|
|

スパムまたはフィッシングのメッセージが配信ではなく検疫された場合、ユーザーはメッセージをセキュリティ & コンプライアンス センターの検疫ポータルから Microsoft に報告できます。 詳細については [、「Microsoft 365 のユーザーとして検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。
