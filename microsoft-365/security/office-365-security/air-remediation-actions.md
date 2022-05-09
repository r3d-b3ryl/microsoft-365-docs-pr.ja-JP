---
title: Microsoft Defender for Office 365の修復アクション
keywords: AIR, autoIR, Microsoft Defender for Endpoint, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
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
description: Microsoft Defender for Office 365での自動調査後の修復アクションについて説明します。
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5435c063234c2b803e172d6cdc06ff0b9bf417b2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312321"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365の修復アクション

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>修復アクション

[Microsoft Defender for Office 365](defender-for-office-365.md)の脅威保護機能には、特定の修復アクションが含まれます。 このような修復アクションには、次のものが含まれます。

- メール メッセージまたはクラスターの論理的な削除
- URL のブロック (クリック時)
- 外部メール転送の無効化
- 委任を無効にする

Microsoft Defender for Office 365では、修復アクションは自動的には実行されません。 代わりに、修復アクションは、組織のセキュリティ運用チームによる承認時にのみ実行されます。

## <a name="threats-and-remediation-actions"></a>脅威と修復アクション

Microsoft Defender for Office 365には、さまざまな脅威に対処するための修復アクションが含まれています。 自動化された調査では、多くの場合、確認と承認を行う 1 つ以上の修復アクションが発生します。 場合によっては、自動調査によって特定の修復アクションが実行されない場合があります。 さらに調査し、適切なアクションを実行するには、次の表のガイダンスを使用します。

|カテゴリ|脅威/リスク|修復アクション|
|:---|:---|:---|
|メール|マルウェア|メール/クラスターを論理的に削除する <p> クラスター内の複数の電子メール メッセージにマルウェアが含まれている場合、クラスターは悪意のあると見なされます。|
|メール|悪意のある URL <br> ([セーフ リンク](safe-links.md)によって悪意のある URL が検出されました。)|メール/クラスターを論理的に削除する <br> ブロック URL (クリック時の確認) <p> 悪意のある URL を含む電子メールは、悪意のあると見なされます。|
|メール|フィッシュ|メール/クラスターを論理的に削除する <p> クラスター内の少数の電子メール メッセージにフィッシングの試行が含まれている場合、クラスター全体がフィッシングの試行と見なされます。|
|メール|ザップフィッシング <br> (電子メール メッセージが配信され、 [その後表示されました](zero-hour-auto-purge.md))。)|メール/クラスターを論理的に削除する <p> レポートは、表示されたメッセージを表示するために使用できます。 [ZAP がメッセージと FAQ を移動したかどうかを確認します](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)。|
|メール|ユーザーによって [報告](enable-the-report-message-add-in.md) されたフィッシングメールが見落とされました|[ユーザーのレポートによってトリガーされる自動調査](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|メール|ボリュームの異常 <br> (最近の電子メールの量は、一致する条件で前の 7 ~ 10 日間を超えています)。|自動調査では、特定の保留中のアクションは発生しません。 <p>ボリュームの異常は明確な脅威ではありませんが、過去 7 ~ 10 日間に比べて最近のメールの量が多いことを示すにすぎません。 <p>大量の電子メールが潜在的な問題を示している可能性がありますが、悪意のある判定または電子メール メッセージ/クラスターの手動レビューの観点から確認が必要です。 [「配信された不審なメールを検索する」を](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)参照してください。|
|メール|脅威は検出されませんでした <br> (システムは、ファイル、URL、または電子メール クラスターの判定の分析に基づいて脅威を見つけることができませんでした。|自動調査では、特定の保留中のアクションは発生しません。 <p>調査が完了した後に検出され [、ザップ](zero-hour-auto-purge.md) された脅威は、調査の数値的な結果には反映されませんが、このような脅威は [脅威エクスプローラー](threat-explorer.md)で確認できます。|
|User|ユーザーが悪意のある URL をクリックした <br> (ユーザーが後で悪意のあるページに移動した場合、またはユーザーが[セーフリンク警告ページ](safe-links.md#warning-pages-from-safe-links)をバイパスして悪意のあるページにアクセスした場合)。|自動調査では、特定の保留中のアクションは発生しません。 <p> URL のブロック (クリック時) <p> 脅威エクスプローラーを使用して [URL に関するデータを表示し、判定をクリックします](threat-explorer.md#view-phishing-url-and-click-verdict-data)。 <p> 組織で[Microsoft Defender for Endpoint](/windows/security/threat-protection/)を使用している場合は、[ユーザーのアカウントが](/microsoft-365/security/defender-endpoint/investigate-user)侵害されているかどうかを判断するためにユーザーを調査することを検討してください。|
|User|ユーザーがマルウェアやフィッシングを送信している|自動調査では、特定の保留中のアクションは発生しません。 <p> ユーザーがマルウェアやフィッシングを報告しているか、攻撃の一環として [ユーザーをスプーフィングしている](anti-spoofing-protection.md) 可能性があります。 [脅威エクスプローラー](threat-explorer.md)を使用して、[マルウェア](threat-explorer-views.md#email--malware)や[フィッシングを](threat-explorer-views.md#email--phish)含むメールを表示および処理します。|
|User|メールの転送 <br> (メールボックス転送ルールが構成されている場合は、データ流出に chch を使用できます)。|転送ルールを削除する <p> [自動転送メッセージ レポート](mfi-auto-forwarded-messages-report.md)を含む[メール フローの分析情報](mail-flow-insights-v2.md)を使用して、転送された電子メールに関するより具体的な詳細を表示します。|
|User|電子メール委任ルール <br> (ユーザーのアカウントに委任が設定されています。)|委任規則を削除する <p> 組織で[Microsoft Defender for Endpoint](/windows/security/threat-protection/)を使用している場合は、委任アクセス許可を取得している[ユーザーの調査](/microsoft-365/security/defender-endpoint/investigate-user)を検討してください。|
|User|データ流出 <br> (ユーザーが電子メールまたはファイル共有 [DLP ポリシー](../../compliance/dlp-learn-about-dlp.md)に違反した場合) |自動調査では、特定の保留中のアクションは発生しません。 <p> [DLP レポートを表示し、アクションを実行します](../../compliance/view-the-dlp-reports.md)。|
|User|異常な電子メール送信 <br> (ユーザーが最近、前の 7 ~ 10 日間よりも多くのメールを送信しました)。|自動調査では、特定の保留中のアクションは発生しません。 <p> 大量の電子メールを送信しても、それ自体は悪意はありません。ユーザーは、イベントの受信者の大規模なグループにメールを送信しただけかもしれません。 調査するには、メール フロー [マップ レポート](mfi-mail-flow-map-report.md)を含む[メール フロー分析情報](mail-flow-insights-v2.md)を使用して、何が起こっているかを判断し、アクションを実行します。|

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Office 365で自動調査の詳細と結果を表示する](air-view-investigation-results.md)
- [Microsoft Defender for Office 365での自動調査の後に、保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender for Endpointでの自動調査について学習する](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft 365 Defenderの機能について学習する](/microsoft-365/security/defender/microsoft-365-defender)
