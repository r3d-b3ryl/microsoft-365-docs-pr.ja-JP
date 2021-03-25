---
title: スパム、非スパム、フィッシング メッセージを Microsoft に報告する
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
description: 管理者は、良いメッセージと悪いメッセージやファイルを分析のために Microsoft に報告するさまざまな方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206605"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織で Exchange Online メールボックスを持つ Microsoft 365 組織では、ユーザーと管理者の両方が、電子メール メッセージとファイルを Microsoft に報告するさまざまな方法があります。

****

|メソッド|説明|
|---|---|
|[管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|Exchange Online メールボックスを持つ組織の管理者に推奨されるレポート方法 (スタンドアロン EOP では使用できません)。|
|[レポート メッセージ アドインを有効にする](enable-the-report-message-add-in.md)|Outlook と Outlook on the web (旧称: Outlook Web App) で動作します。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは [、Admin Submissions ポータル](admin-submission.md)、自動調査と応答 [(AIR)](air-view-investigation-results.md)の結果、 [ユーザー](view-email-security-reports.md#user-reported-messages-report)が報告したメッセージ レポート、および脅威エクスプローラーで [利用できます](threat-explorer-views.md#email--submissions)。 <p> 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。
|[レポート フィッシング アドインを有効にする](enable-the-report-phish-add-in.md)|Outlook と Outlook on the web (旧称: Outlook Web App) で動作します。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージは [、Admin Submissions ポータル](admin-submission.md)、自動調査と応答 [(AIR)](air-view-investigation-results.md)の結果、 [ユーザー](view-email-security-reports.md#user-reported-messages-report)が報告したメッセージ レポート、および脅威エクスプローラーで [利用できます](threat-explorer-views.md#email--submissions)。 <p> 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。|
|[Microsoft Outlook の迷惑メール レポート アドインをインストールして使用する](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook でのみ動作します。|
|[Outlook on the web で迷惑メールとフィッシングメールを報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online メールボックスを持つ組織 (スタンドアロン EOP では使用できません) には、Outlook on the web の組み込み機能を使用します。 <p> ユーザーが報告するメッセージは、 [管理者申請ポータルで使用できます](admin-submission.md)。 <p> 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。|
|[Outlook for iOS および Android で迷惑メールとフィッシングメールを報告する](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Outlook for iOS および Android の組み込み機能を Exchange Online メールボックスを持つ組織に使用します (スタンドアロン EOP では使用できません)。 <p> ユーザーが報告するメッセージは、 [管理者申請ポータルで使用できます](admin-submission.md)。 <p> 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。|
|[分析のために Microsoft にメッセージを手動で送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|スパムやフィッシングではなく、スパムのために、添付されたメッセージを特定の Microsoft の電子メール アドレスに手動で送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|ユーザーが分析のために Microsoft にメッセージを報告したときに通知するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する方法について説明します。|
|[分析のためにマルウェアとマルウェア以外のファイルを Microsoft に送信する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|添付ファイルや他のファイルを送信するには、Microsoft セキュリティ インテリジェンス サイトを使用します。|

スパムメッセージまたはフィッシング メッセージが配信される代わりに検疫された場合、ユーザーはセキュリティ コンプライアンス センターの検疫ポータルから Microsoft にメッセージ&できます。 詳細については、「Microsoft 365 で検疫済みメッセージ [をユーザーとして検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

> [!NOTE]
> Microsoft への提出からのデータは、北米のデータ センター Office 365 コンプライアンス境界に存在します。 データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによって確認されます。
