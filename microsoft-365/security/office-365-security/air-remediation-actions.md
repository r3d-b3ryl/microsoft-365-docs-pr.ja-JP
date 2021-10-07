---
title: Microsoft Defender の修復アクション (Office 365
keywords: AIR、autoIR、Microsoft Defender for Endpoint、自動化、調査、対応、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 での自動調査に続く修復アクションについてOffice 365。
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c994783506f1ba8bc2807b7261d98303cc72f76b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196659"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Microsoft Defender の修復アクション (Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>修復アクション

Microsoft Defender for microsoft Defender の脅威[保護機能Office 365特定の](defender-for-office-365.md)修復アクションが含まれます。 このような修復アクションには、次のものが含まれます。

- メール メッセージまたはクラスターの論理的な削除
- URL のブロック (クリック時)
- 外部メール転送の無効化
- 委任を無効にする

Microsoft Defender for Office 365修復アクションは自動的には実行されません。 代わりに、修復アクションは、組織のセキュリティ運用チームによる承認時にのみ実行されます。

## <a name="threats-and-remediation-actions"></a>脅威と修復のアクション

Microsoft Defender for Office 365さまざまな脅威に対処するための修復アクションが含まれています。 自動調査では、多くの場合、1 つ以上の修復アクションを確認して承認します。 場合によっては、自動調査によって特定の修復アクションが発生しない場合があります。 さらに調査し、適切なアクションを実行するには、次の表のガイダンスを使用します。

|カテゴリ|脅威/リスク|修復アクション|
|:---|:---|:---|
|メール|マルウェア|メール/クラスターのソフト削除 <p> クラスター内の一握り以上の電子メール メッセージにマルウェアが含まれている場合、クラスターは悪意のあるメッセージと見なされます。|
|メール|悪意のある URL <br> (悪意のある URL がリンク[によってセーフされました](safe-links.md)。)|メール/クラスターのソフト削除 <br> ブロック URL (クリック時の検証) <p> 悪意のある URL を含む電子メールは、悪意のあるメールと見なされます。|
|メール|フィッシング|メール/クラスターのソフト削除 <p> クラスター内のメール メッセージの数が一握りを超える場合は、クラスター全体がフィッシング詐欺の試みと見なされます。|
|メール|Zapped フィッシング <br> (電子メール メッセージが配信され、その後 [zapped](zero-hour-auto-purge.md).)|メール/クラスターのソフト削除 <p> レポートは、Zapped メッセージを表示するために使用できます。 [ZAP がメッセージと FAQ を移動した場合を確認します](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)。|
|メール|ユーザーが報告した [フィッシングメール](enable-the-report-message-add-in.md) が見つからない|[ユーザーのレポートによってトリガーされる自動調査](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|メール|ボリューム異常 <br> (最近の電子メールの数量は、一致する条件の前の 7 ~ 10 日間を超えている)。|自動調査では、特定の保留中のアクションは発生しない。 <p>ボリューム異常は明確な脅威ではなく、過去 7 ~ 10 日間と比較して、最近の数日間のメール量の増加を示しているに過言ではありません。 <p>電子メールの量が多い場合は潜在的な問題を示しますが、悪意のある評決または電子メール メッセージ/クラスターの手動レビューの観点から確認が必要です。 「 [配信された疑わしいメールを検索する」を参照してください](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)。|
|メール|脅威は検出されませんでした <br> (システムは、ファイル、URL、または電子メール クラスターの評決の分析に基づく脅威を見つけなかった。|自動調査では、特定の保留中のアクションは発生しない。 <p>調査が完了 [した](zero-hour-auto-purge.md) 後に検出され、座り込みされた脅威は、調査の数値結果には反映されませんが、そのような脅威は Threat Explorer で [表示できます](threat-explorer.md)。|
|ユーザー|ユーザーが悪意のある URL をクリックした <br> (ユーザーは、後で悪意のあるページに移動するか、悪意のあるページにアクセスするために セーフ[リンク](safe-links.md#warning-pages-from-safe-links)の警告ページをバイパスしました)。|自動調査では、特定の保留中のアクションは発生しない。 <p> URL のブロック (クリック時) <p> 脅威エクスプローラーを使用して [URL に関するデータを表示し、[評決] をクリックします](threat-explorer.md#view-phishing-url-and-click-verdict-data)。 <p> 組織で Microsoft [Defender for Endpoint](/windows/security/threat-protection/)[](/microsoft-365/security/defender-endpoint/investigate-user)を使用している場合は、ユーザーの調査を検討して、アカウントが侵害されたかどうかを判断してください。|
|ユーザー|ユーザーがマルウェア/フィッシングを送信している|自動調査では、特定の保留中のアクションは発生しない。 <p> ユーザーがマルウェア/フィッシングを報告している場合や、攻撃の[](anti-spoofing-protection.md)一部としてユーザーをスプーフィングしている可能性があります。 脅威[エクスプローラーを使用して](threat-explorer.md)、マルウェアやフィッシングを含むメール[を表示および](threat-explorer-views.md#email--malware)[処理します](threat-explorer-views.md#email--phish)。|
|ユーザー|メールの転送 <br> (メールボックス転送ルールが構成されている場合、chch をデータの取り出しに使用できます)。|転送ルールの削除 <p> 自動 [転送されたメッセージ レポート](mail-flow-insights-v2.md)を含 [むメール](mfi-auto-forwarded-messages-report.md)フローの分析情報を使用して、転送されたメールの詳細を表示します。|
|ユーザー|電子メール委任ルール <br> (ユーザーのアカウントに委任が設定されています)。|委任ルールの削除 <p> 組織で Microsoft Defender for Endpoint[](/microsoft-365/security/defender-endpoint/investigate-user)を[使用している場合](/windows/security/threat-protection/)は、委任のアクセス許可を取得しているユーザーの調査を検討してください。|
|ユーザー|データ流出 <br> (電子メールまたはファイル共有 DLP ポリシーに違反 [したユーザー](../../compliance/dlp-learn-about-dlp.md) |自動調査では、特定の保留中のアクションは発生しない。 <p> [DLP レポートを表示し、アクションを実行します](../../compliance/view-the-dlp-reports.md)。|
|ユーザー|異常なメール送信 <br> (ユーザーが最近送信したメールの数が、過去 7 ~ 10 日間よりも多かった)。|自動調査では、特定の保留中のアクションは発生しない。 <p> 大量の電子メールの送信は、それ自体が悪意のあるものではありません。ユーザーがイベントの受信者の大規模なグループにメールを送信しただけである可能性があります。 調査するには、メール[フロー マップ レポート](mail-flow-insights-v2.md)を[](mfi-mail-flow-map-report.md)含むメール フロー分析情報を使用して、何が起こっているのかを判断し、アクションを実行します。|

## <a name="next-steps"></a>次の手順

- [Microsoft Office 365 Defender の自動調査の詳細と結果を表示する](air-view-investigation-results.md)
- [Microsoft Defender の自動調査に続き、保留中または完了した修復アクションを表示Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender for Endpoint での自動調査の詳細](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [アプリの機能についてMicrosoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
