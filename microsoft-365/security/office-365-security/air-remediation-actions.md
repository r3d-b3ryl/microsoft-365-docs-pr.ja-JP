---
title: Microsoft Defender for Office 365 の修復アクション
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 での自動調査に続く修復アクションについて説明します。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d50ea767a795eb8370e9e5c8c1b07a8c9877424
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176041"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の修復アクション

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="remediation-actions"></a>修復アクション

Microsoft Defender for [Office 365 の脅威保護機能](office-365-atp.md) には、特定の修復アクションが含まれます。 このような修復アクションには、次のものが含まれます。

- メール メッセージまたはクラスターの論理的な削除
- URL のブロック (クリック時)
- 外部メール転送の無効化
- 委任を無効にする

Microsoft Defender for Office 365 では、修復アクションは自動的には実行されません。 代わりに、修復アクションは、組織のセキュリティ運用チームの承認を得た場合にのみ実行されます。

## <a name="threats-and-remediation-actions"></a>脅威と修復アクション

Microsoft Defender for Office 365 には、さまざまな脅威に対処するための修復アクションが含まれています。 調査を自動化すると、多くの場合、レビューと承認を行う 1 つ以上の修復アクションが実行されます。 場合によっては、自動調査によって特定の修復アクションが実行されない場合があります。 さらに調査して適切なアクションを実行するには、次の表のガイダンスを使用します。

|カテゴリ|脅威/リスク|修復アクション|
|:---|:---|:---|
|メール|マルウェア|メール/クラスターの削除 (回復) <p> クラスター内の電子メール メッセージの数が少なからずマルウェアが含まれている場合、そのクラスターは悪意のあるメッセージであると見なされます。|
|メール|悪意のある URL<br/>(安全なリンクによって悪意のある URL [が検出されました](atp-safe-links.md)。|メール/クラスターの削除 (回復) <p>悪意のある URL を含む電子メールは、悪意のあるメールと見なされます。|
|メール|フィッシング|メール/クラスターの削除 (回復) <p> クラスター内のメール メッセージの数が少なからずフィッシング詐欺の試みを含む場合、クラスター全体がフィッシング詐欺の試みと見なされます。|
|メール|Zapped フィッシング <br>(電子メール メッセージが配信され、 [その後に zapped](zero-hour-auto-purge.md)されました。)|メール/クラスターの削除 (回復) <p>レポートを使用して、zapped メッセージを表示できます。 [ZAP がメッセージと FAQ を移動したどうか確認します](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)。|
|メール|ユーザーによって報告 [された、見つからない](enable-the-report-message-add-in.md) フィッシング メール|[ユーザーのレポートによってトリガーされる自動調査](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|メール|ボリューム異常 <br> (最近のメールの量が、一致条件の前の 7 ~ 10 日間を超えている。|自動調査では、特定の保留中のアクションは発生します。 <p>ボリューム異常は明確な脅威ではなく、過去 7 ~ 10 日間と比較した最近のメール量の増加を示しているに過言ではありません。 <p>電子メールの量が多い場合は潜在的な問題を示している可能性があります。ただし、悪意のある評価または電子メール メッセージ/クラスターの手動レビューのどちらかの観点から確認が必要です。 「配信 [された疑わしいメールを検索する」を参照してください](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)。|
|メール|脅威は検出されませんでした <br> (システムは、ファイル、URL、または電子メール クラスターの評価の分析に基づいて脅威を検出しました。)|自動調査では、特定の保留中のアクションは発生します。 <p>調査 [が完了した](zero-hour-auto-purge.md) 後に見つかった脅威とザップされた脅威は、調査の数値の結果には反映されませんが、そのような脅威は脅威エクスプローラーで [表示できます](threat-explorer.md)。|
|ユーザー|ユーザーが悪意のある URL をクリックした <br> (ユーザーが、後で悪意のあると判明したページに移動するか、ユーザーが安全なリンクの[](atp-safe-links.md#warning-pages-from-safe-links)警告ページをバイパスして悪意のあるページにアクセスしました)。)|自動調査では、特定の保留中のアクションは発生します。 <p>脅威エクスプローラーを使用して URL [に関するデータを表示し、[Verdicts] をクリックします](threat-explorer.md#view-phishing-url-and-click-verdict-data)。 <p>組織で Microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)を使用している場合は、ユーザーを調査して、アカウントが侵害されたかどうかを判断してください。|
|ユーザー|ユーザーがマルウェア/フィッシングを送信している|自動調査では、特定の保留中のアクションは発生します。 <p> ユーザーがマルウェア/フィッシングを報告していたり、攻撃の一[](anti-spoofing-protection.md)部としてユーザーをスプーフィングしている可能性があります。 脅威 [エクスプローラーを使用](threat-explorer.md) して、マルウェアやフィッシングを含むメール [を表示および](threat-explorer-views.md#email--malware) 処理 [します](threat-explorer-views.md#email--phish)。|
|ユーザー|メールの転送 <br> (メールボックス転送ルールが構成され、データの取り出しに使用できます)。|転送ルールを削除する <p> 転送[されたメールに関する](mail-flow-insights-v2.md)より具体的[](mfi-auto-forwarded-messages-report.md)な詳細を表示するには、自動転送されたメッセージ レポートを含むメール フローの分析情報を使用します。|
|ユーザー|電子メール委任ルール <br> (ユーザーのアカウントに委任が設定されています。)|委任ルールを削除する <p> 組織で Microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)を使用している場合は、委任のアクセス許可を取得しているユーザーを調査してください。|
|ユーザー|データ流出 <br> (ユーザーが電子メールまたはファイル共有 DLP ポリシーに [違反しました](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。)|自動調査では、特定の保留中のアクションは発生します。 <p> [DLP レポートを表示し、アクションを実行します](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)。|
|ユーザー|異常なメール送信 <br> (ユーザーが最近、過去 7 ~ 10 日間よりも多くのメールを送信しました。)|自動調査では、特定の保留中のアクションは発生します。 <p> 大量のメールを送信すること自体は悪意のあるものではありません。ユーザーがイベントの受信者の大きなグループにメールを送信しただけである可能性があります。 調査するには、メール フロー[マップ レポート](mail-flow-insights-v2.md)を[](mfi-mail-flow-map-report.md)含むメール フローの分析情報を使用して、何が起こっているのかを判断し、アクションを実行します。|

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Office 365 での自動調査の詳細と結果を表示する](air-view-investigation-results.md)
- [Microsoft Defender for Office 365 での自動調査の後、保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender for Endpoint での自動調査について説明します。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft 365 Defender の機能について](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
