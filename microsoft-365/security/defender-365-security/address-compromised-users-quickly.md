---
title: 調査と対応を自動化して、侵害されたユーザー アカウントに対処する
keywords: AIR、autoIR、ATP、自動化、調査、対応、修復、脅威、高度、脅威、保護、侵害
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Microsoft Defender for Office 365 Plan 2 で、侵害されたユーザー アカウントを検出して対処するプロセスを高速化する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2428cc2c1f82b4f2b881433fde991dd04b268d6e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065675"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>調査と対応を自動化して、侵害されたユーザー アカウントに対処する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) には、強力な自動調査と応答 [(AIR)](office-365-air.md) 機能が含まれています。 このような機能により、セキュリティ運用チームが脅威に対処するために多くの時間と労力を節約できます。 Microsoft は引き続きセキュリティ機能を強化しています。 最近、AIR の機能が強化され、セキュリティが侵害されたユーザー セキュリティ プレイブック (現在プレビュー中) が含まれます。 侵害されたユーザー セキュリティ プレイブックの詳細については、この記事を参照してください。 詳細については、「Microsoft Defender for microsoft Defender for Office [365」](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) を参照してください。

![侵害されたユーザーの自動調査](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

侵害されたユーザー セキュリティ プレイブックを使用すると、組織のセキュリティ チームは次の操作を実行できます。

- 侵害されたユーザー アカウントの検出を高速化します。

- アカウントが侵害された場合に侵害の範囲を制限する。そして

- 侵害されたユーザーに対して、より効果的かつ効率的に対応します。

## <a name="compromised-user-alerts"></a>侵害されたユーザー通知

ユーザー アカウントが侵害された場合、異常または異常な動作が発生します。 たとえば、フィッシングメッセージとスパム メッセージは、信頼できるユーザー アカウントから内部的に送信される場合があります。 365 Office 365 の Defender は、365 内の電子メール パターンやコラボレーション アクティビティでこのような異常をOfficeできます。 この場合、アラートがトリガーされ、脅威の軽減プロセスが開始されます。

たとえば、疑わしいメール送信のためにトリガーされたアラートを次に示します。

![不審なメール送信が発生した場合に発生するアラート](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

次に、ユーザーの送信制限に達した際にトリガーされたアラートの例を示します。

![送信制限に達した場合にトリガーされるアラート](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>侵害されたユーザーを調査して対応する

ユーザー アカウントが侵害されると、アラートがトリガーされます。 場合によっては、組織のセキュリティ運用チームによって問題が解決されるまで、そのユーザー アカウントがブロックされ、それ以上の電子メール メッセージの送信がブロックされ、防止されます。 それ以外の場合は、自動調査が開始され、セキュリティ チームが推奨するアクションが実行される可能性があります。

- [制限付きユーザーの表示と調査](#view-and-investigate-restricted-users)

- [自動調査の詳細を表示する](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 次のタスクを実行するには、適切なアクセス許可が必要です。 「AIR [機能を使用するために必要なアクセス許可」を参照してください](office-365-air.md#required-permissions-to-use-air-capabilities)。

### <a name="view-and-investigate-restricted-users"></a>制限付きユーザーの表示と調査

制限付きユーザーの一覧に移動するためのいくつかのオプションがあります。 たとえば、セキュリティ コンプライアンス センター&、脅威管理の [制限付きユーザーの確認 \> **]** \> **に移動できます**。 次の手順では、アラート ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性があるさまざまな種類のアラートを確認するための良い方法です。

1. <https://protection.office.com> に移動し、サインインします。

2. ナビゲーション ウィンドウで、[アラート ダッシュボード] **を** \> **選択します**。

3. [その他 **の通知] ウィジェットで** 、[制限付きユーザー **] を選択します**。

   ![その他のアラート ウィジェット](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   これにより、制限付きユーザーの一覧が開きます。

   ![365 の制限付きユーザー Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. リストでユーザー アカウントを選択して詳細を表示し、制限付きユーザーを解放するなどの [アクションを実行します](removing-user-from-restricted-users-portal-after-spam.md)。

### <a name="view-details-about-automated-investigations"></a>自動調査の詳細を表示する

自動調査が開始すると、その詳細と結果をセキュリティ コンプライアンス センター&確認できます。 [脅威管理 **の** \> **調査] に** 移動し、調査を選択して詳細を表示します。

詳細については、「調査の詳細 [を表示する」を参照してください](air-view-investigation-results.md)。

## <a name="keep-the-following-points-in-mind"></a>以下の点に気を付ける

- **アラートの上に滞在します**。 ご存知のように、妥協点が検出されなくなるほど、組織、顧客、パートナーに対する広範な影響とコストの可能性が大きくなります。 脅威を軽減するために、特にユーザーのアカウントが侵害された場合は、早期の検出と適切な対応が重要です。

- **オートメーションは、セキュリティ運用チームを支援しますが、置き換えは行ないます**。 調査と対応の自動化機能は、侵害されたユーザーを早期に検出できますが、セキュリティ運用チームは調査と修復を行う必要があります。 これにはいくつかのヘルプが必要ですか? 「アクション [の確認と承認」を参照してください](air-review-approve-pending-completed-actions.md)。

- **疑わしいログインアラートを唯一のインジケーターとして使用しない**。 ユーザー アカウントが侵害されると、疑わしいログイン 通知がトリガーされる場合と、トリガーされない場合があります。 アカウントが侵害された後に発生する一連のアクティビティがアラートをトリガーする場合があります。 アラートについて詳しくは、お知りください。 「 [アラート ポリシー」を参照してください](../../compliance/alert-policies.md)。

## <a name="next-steps"></a>次の手順

- [AIR 機能を使用するために必要なアクセス許可を確認する](office-365-air.md#required-permissions-to-use-air-capabilities)

- [365 で悪意のあるメールを検索Officeする](investigate-malicious-email-that-was-delivered.md)

- [エンドポイント向け Microsoft Defender の AIR について説明します。](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する](https://www.microsoft.com/microsoft-365/roadmap?filters=)