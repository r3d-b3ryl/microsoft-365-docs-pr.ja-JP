---
title: Microsoft 365 自動調査と応答の修復アクション
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の修復アクションについて説明します。
ms.openlocfilehash: 8dfb203cfdae179d8d88842a2d2b55aeab2e17fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634654"
---
# <a name="remediation-actions-in-microsoft-365"></a>Microsoft 365 の修復アクション

## <a name="remediation-actions"></a>修復アクション

Office 365 の[自動調査および応答機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)(AIR) [Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) プラン2には、特定の修復アクションが含まれています。 自動化された調査を実行している場合や、完了した場合は、通常、セキュリティ運用チームによる承認を必要とする1つ以上の修復アクションが表示されます。 このような修復アクションには、次のようなものがあります。

- メール メッセージまたはクラスターの論理的な削除
- URL のブロック (クリック時)
- 外部メール転送の無効化
- 委任を無効にする

> [!NOTE]
> Office 365 ATP では、自動調査は自動的に修復されません。 修復処理は、組織のセキュリティチームによる承認時にのみ行われます。

## <a name="threats-and-remediation-actions"></a>脅威と修復アクション

次の表に、Office 365 ATP での脅威と適切な修復アクションの概要を示します。 場合によっては、自動調査によって特定の修復アクションが発生しないことがあります。 次の表に示すように、セキュリティ運用チームはさらに調査して適切なアクションを実行できます。

||||
|---|---|---|
|**カテゴリ**|**脅威/リスク**|**修復アクション**|
|電子メール|マルウェア| ソフト削除電子メール/クラスター <br/><br/>クラスター内のメールメッセージの数が多く、マルウェアが含まれている場合、クラスターは悪意のあるものと見なされます。|
|電子メール|悪意のある URL<br/>(悪意のある URL が[Office 365 の ATP の安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)によって検出されました)。|ソフト削除電子メール/クラスター <br/><br/>悪意のある URL を含む電子メールは、悪意のあるものと見なされます。|
|電子メール|フィッシング| ソフト削除電子メール/クラスター <br/><br/>1つのクラスター内に多数の電子メールメッセージが含まれていると、そのクラスターはフィッシングと見なされます。|
|電子メール|Zapped フィッシング <br/>(電子メールメッセージが配信され、 [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)。)|ソフト削除電子メール/クラスター <br/><br/>Zapped メッセージを表示するためにレポートを使用できます。 [ZAP がメッセージと faq を移動したかどうかを確認](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)します。|
|電子メール|ユーザーによって[報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)された不在フィッシング電子メール| [ユーザーのレポートによってトリガーされる自動化された調査](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|電子メール|ボリューム異常 <br/>(一致する条件の場合、最近の電子メールの数量は過去7-10 日を超えています。)|自動調査を実行しても、特定の保留中のアクションは発生しません。 <br/><br/>ボリューム異常は明確な脅威ではありませんが、過去7-10 日を超えた最近の電子メールボリュームを示すだけではありません。 このことは潜在的な問題を示していますが、悪意のある verdicts か、電子メールメッセージ/クラスターの手動による確認のために確認が必要です。 「[配信された不審な電子メールを検索して削除する」を](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered)参照してください。|
|電子メール|脅威なし <br/>(電子メールクラスター verdicts のファイル、url、または分析に基づく脅威は検出されませんでした)。|自動調査を実行しても、特定の保留中のアクションは発生しません。 <br/><br/>調査の完了後に発見および[zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge)される脅威は、調査の数値の結果には反映されませんが、そのような脅威は[脅威エクスプローラー](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)で表示できます。|
|User|ユーザーが悪意のある URL をクリックした <br/>(後で悪意があると検出されたページにユーザーがアクセスしたか、悪意のあるページに移動するためにユーザーが[安全なリンクの警告ページ](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages)をバイパスした場合)。|自動調査を実行しても、特定の保留中のアクションは発生しません。 <br/><br/>脅威エクスプローラーを使用し[て、url に関するデータを表示し、[verdicts] をクリック](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict)します。 <br/><br/>組織で[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)を使用している場合は、[ユーザーの](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)アカウントが侵害されているかどうかを調査することを検討してください。|
|User|ユーザーがマルウェア/フィッシングを送信している|自動調査を実行しても、特定の保留中のアクションは発生しません。 <br/><br/>ユーザーがマルウェア/フィッシングを報告しているか、攻撃の一環として[ユーザーがユーザーをスプーフィング](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection)している可能性があります。 [脅威エクスプローラー](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)を使用して、[マルウェア](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware)または[フィッシング](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)を含む電子メールを表示し、処理します。|
|User|メールの転送 <br/>(メールボックス転送ルールが構成されているため、データ exfiltration フィルターに使用できます)。|転送ルールの削除 <br/><br/>転送されたメールに関する詳細情報を表示するには、[自動転送](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)されたメッセージレポートを含む[メールフローインサイト](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)を使用します。|
|User|電子メール委任ルール <br/>(ユーザーのアカウントには委任が設定されています。)|委任ルールの削除 <br/><br/> 組織で[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)を使用している場合は、委任のアクセス許可を取得している[ユーザーの調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)を検討してください。|
|User|データ exfiltration フィルター<br/>(ユーザーが電子メールまたはファイル共有[DLP ポリシー](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)に違反しました)。|自動調査を実行しても、特定の保留中のアクションは発生しません。 <br/><br/>[DLP レポートを表示し、アクションを実行](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)します。|
|User|異常メール送信 <br/>(ユーザーが以前の7-10 日より多くの電子メールを送信しました)。|自動調査を実行しても、特定の保留中のアクションは発生しません。 <br/><br/>多くの電子メールを送信することは、それ自体では悪意がありません。ユーザーは、1つのイベントについて大量の受信者グループに電子メールを送信しただけの場合があります。 調査するには、[メールフローのマップレポート](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report)を含む[メールフローインサイト](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)を使用して、何が起こっているのかを特定し、処理を行います。|
|

## <a name="next-steps"></a>次の手順

- [Microsoft 365 の自動調査の詳細と結果を表示する](air-view-investigation-results.md)

- [Microsoft 365 で自動調査を行った後に、保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>関連記事

- [Microsoft Defender Advanced Threat Protection の自動調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft の脅威保護について](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)