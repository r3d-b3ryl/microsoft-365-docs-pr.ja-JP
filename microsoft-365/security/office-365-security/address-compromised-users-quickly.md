---
title: 自動調査と応答を使用して侵害されたユーザー アカウントに対処する
keywords: AIR, autoIR, Microsoft Defender for Endpoint, 自動, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護, 侵害されました
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.custom: ''
ms.date: 06/10/2021
description: Microsoft Defender for Office 365プラン 2 の自動調査と対応機能を使用して、侵害されたユーザー アカウントを検出して対処するプロセスを高速化する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8c78847e36d4a4887c4f7a3c54904cc26a012e5
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131154"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>自動調査と応答を使用して侵害されたユーザー アカウントに対処する

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) には、強力な[自動調査と対応](office-365-air.md) (AIR) 機能が含まれています。 このような機能により、セキュリティ運用チームが脅威に対処する時間と労力を大幅に節約できます。 Microsoft は、セキュリティ機能を引き続き向上させます。 最近、侵害されたユーザー セキュリティ プレイブック (現在プレビュー段階) を含む AIR 機能が強化されました。 侵害されたユーザー セキュリティ プレイブックの詳細については、この記事を参照してください。 さらに詳しくは、ブログ投稿の[「時間を短縮してユーザーの侵害を検出して対応し、Microsoft Defender for Office 365を使用して侵害範囲を制限](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)する」をご覧ください。

![侵害されたユーザーの自動調査。](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

侵害されたユーザー セキュリティ プレイブックを使用すると、組織のセキュリティ チームは次のことが可能になります。

- 侵害されたユーザー アカウントの検出を高速化する。
- アカウントが侵害された場合の侵害の範囲を制限する。そして
- 侵害されたユーザーに対して、より効果的かつ効率的に対応します。

## <a name="compromised-user-alerts"></a>侵害されたユーザー アラート

ユーザー アカウントが侵害されると、非定型または異常な動作が発生します。 たとえば、フィッシングやスパム メッセージは、信頼されたユーザー アカウントから内部的に送信される場合があります。 Defender for Office 365は、Office 365内の電子メール パターンやコラボレーション アクティビティでこのような異常を検出できます。 これが発生すると、アラートがトリガーされ、脅威軽減プロセスが開始されます。

たとえば、疑わしいメール送信が原因でトリガーされたアラートを次に示します。

![疑わしいメール送信が原因でアラートがトリガーされます。](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

また、ユーザーの送信制限に達したときにトリガーされたアラートの例を次に示します。

![上限に達した送信によってトリガーされるアラート。](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>侵害されたユーザーを調査して対応する

ユーザー アカウントが侵害されると、アラートがトリガーされます。 また、場合によっては、組織のセキュリティ運用チームによって問題が解決されるまで、そのユーザー アカウントがブロックされ、それ以降の電子メール メッセージの送信が妨げられます。 他のケースでは、自動調査が開始され、セキュリティ チームが実行する必要がある推奨されるアクションが発生する可能性があります。

- [制限付きユーザーの表示と調査](#view-and-investigate-restricted-users)

- [自動調査に関する詳細を表示する](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 次のタスクを実行するには、適切なアクセス許可が必要です。 [AIR 機能を使用するために必要なアクセス許可に関するページを](office-365-air.md#required-permissions-to-use-air-capabilities)参照してください。

### <a name="view-and-investigate-restricted-users"></a>制限付きユーザーの表示と調査

制限付きユーザーの一覧に移動するには、いくつかのオプションがあります。 たとえば、Microsoft 365 Defender ポータルで、[**電子メール] &コラボレーション** の [**制限付き**\>ユーザー **の確認**\>] に移動できます。 次の手順では、 **アラート** ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性のあるさまざまな種類のアラートを表示するのに適した方法です。

1. Microsoft 365 Defender ポータルを<https://security.microsoft.com>開き、**インシデント&アラート** \> アラートに移動 **します**。 または、**[アラート]** ページに直接移動するには、<https://security.microsoft.com/alerts> を使用します。

2. [ **アラート]** ページで、期間と **ユーザーが電子メールの送信を制限** したという名前のポリシーで結果をフィルター処理します。

   :::image type="content" source="../../media/m365-sc-alerts-page-with-restricted-user.png" alt-text="制限付きユーザーに対してフィルター処理されたMicrosoft 365 Defender ポータルの [アラート] ページ" lightbox="../../media/m365-sc-alerts-page-with-restricted-user.png":::

3. 名前をクリックしてエントリを選択すると、 **メールの送信が制限されたユーザー** ページが開き、確認するための追加の詳細が表示されます。 **[アラートの管理**] ボタンの横にある [その他のオプション] アイコンをクリック![できます。](../../media/m365-cc-sc-more-actions-icon.png) **その他のオプション** を選択し、[ **制限付きユーザーの詳細の表示** ] を選択して **[制限付きユーザー** ] ページに移動し、 [制限付きユーザーを解放](removing-user-from-restricted-users-portal-after-spam.md)できます。

  :::image type="content" source="../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png" alt-text="電子メールの送信が制限されているユーザー ページ" lightbox="../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png":::

### <a name="view-details-about-automated-investigations"></a>自動調査に関する詳細を表示する

自動調査が開始されると、セキュリティ & コンプライアンス センターでその詳細と結果を確認できます。 **脅威管理** \> **の調査** に移動し、調査を選択して詳細を表示します。

詳細については、「 [調査の詳細を表示する](air-view-investigation-results.md)」を参照してください。

## <a name="keep-the-following-points-in-mind"></a>以下の点にご注意ください。

- **アラートを常に確認します**。 ご存知のように、侵害が検出されない時間が長いほど、組織、顧客、およびパートナーに広範な影響とコストが発生する可能性が高くなります。 脅威を軽減するには、特にユーザーのアカウントが侵害された場合に、早期検出とタイムリーな対応が不可欠です。

- **オートメーションは、セキュリティ運用チームを支援しますが、置き換えることはありません**。 自動調査と対応機能により、侵害されたユーザーを早期に検出できますが、セキュリティ運用チームは調査と修復を行う必要があります。 これに関するヘルプが必要ですか? [「アクションの確認と承認」を](air-review-approve-pending-completed-actions.md)参照してください。

- **唯一のインジケーターとして疑わしいログイン アラートに依存しないでください**。 ユーザー アカウントが侵害されると、不審なログイン アラートがトリガーされる場合もあれば、トリガーされない場合もあります。 場合によっては、アラートをトリガーするアカウントが侵害された後に発生する一連のアクティビティです。 アラートの詳細を知りたいですか? [アラート ポリシーを](../../compliance/alert-policies.md)参照してください。

## <a name="next-steps"></a>次の手順

- [AIR 機能を使用するために必要なアクセス許可を確認する](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Office 365で悪意のあるメールを検索して調査する](investigate-malicious-email-that-was-delivered.md)

- [Microsoft Defender for Endpointの AIR について学習する](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する](https://www.microsoft.com/microsoft-365/roadmap?filters=)
