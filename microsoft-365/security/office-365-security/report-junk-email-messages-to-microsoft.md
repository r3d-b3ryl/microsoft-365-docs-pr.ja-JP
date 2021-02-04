---
title: スパム、非スパム、フィッシングメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: 管理者は、良いメッセージや悪いメッセージやファイルを分析のために Microsoft に報告するさまざまな方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 601d0c599a815529540281679bd2b0f907031058
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099692"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、ユーザーと管理者の両方が電子メール メッセージとファイルを Microsoft に報告するさまざまな方法を使用します。

****

|メソッド|説明|
|---|---|
|[管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|Exchange Online メールボックスを使用している組織の管理者に推奨されるレポート方法 (スタンドアロン EOP では使用できません)。|
|[レポート メッセージ アドインを有効にする](enable-the-report-message-add-in.md)|Outlook および Outlook on the web (旧称: Outlook Web App) で動作します。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは、[管理者](admin-submission.md)提出ポータル、自動調査と応答[(AIR)](air-view-investigation-results.md)の結果、ユーザーから報告されたメッセージ[](view-email-security-reports.md#user-reported-messages-report)レポート、脅威エクスプローラーで利用[できます。](threat-explorer-views.md#email--submissions) <p> 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。
|[レポート フィッシング アドインを有効にする](enable-the-report-phish-add-in.md)|Outlook および Outlook on the web (旧称: Outlook Web App) で動作します。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは、[管理者](admin-submission.md)提出ポータル、自動調査と応答[(AIR)](air-view-investigation-results.md)の結果、ユーザーから報告されたメッセージ[](view-email-security-reports.md#user-reported-messages-report)レポート、脅威エクスプローラーで利用[できます。](threat-explorer-views.md#email--submissions) <p> 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。|
|[Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook でのみ動作します。|
|[Outlook on the web で迷惑メールとフィッシングメールを報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online メールボックスを持つ組織 (スタンドアロン EOP では使用できません) には、Web 上の Outlook の組み込み機能を使用します。 <p> ユーザーが報告するメッセージは、管理者 [提出ポータルで利用できます](admin-submission.md)。 <p> 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。|
|[iOS および Android 用の Outlook で迷惑メールとフィッシングメールを報告する](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Exchange Online メールボックスを使用している組織では、iOS および Android 用の Outlook の組み込み機能を使用します (スタンドアロンの EOP では使用できません)。 <p> ユーザーが報告するメッセージは、管理者 [提出ポータルで利用できます](admin-submission.md)。 <p> 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。|
|[分析のためにメッセージを Microsoft に手動で送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|スパム、スパム、フィッシングではなく、特定の Microsoft 電子メール アドレスに添付メッセージを手動で送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|ユーザーが分析のために Microsoft にメッセージを報告したときに通知するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。|
|[マルウェアとマルウェア以外のマルウェアを分析のために Microsoft に送信する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティ インテリジェンス サイトを使用して、添付ファイルや他のファイルを送信します。|

スパムまたはフィッシングメッセージが配信される代わりに検疫された場合、ユーザーはセキュリティ/コンプライアンス センターの検疫ポータルから Microsoft にメッセージ&できます。 詳細については [、「Microsoft 365 で検疫済みメッセージをユーザーとして検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

> [!NOTE]
> Microsoft への提出からのデータは、北米のデータ センターの Office 365 コンプライアンスの境界に存在します。 データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによってレビューされます。
