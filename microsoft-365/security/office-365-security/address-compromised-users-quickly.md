---
title: 自動調査と対応により、侵害されたユーザー アカウントに対処する
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度な, 脅威, 保護, 侵害
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
description: microsoft Defender for Office 365 プラン 2 の自動調査および対応機能を使用して、侵害されたユーザー アカウントを検出して対処するプロセスを高速化する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288743"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>自動調査と対応により、侵害されたユーザー アカウントに対処する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


[Microsoft Defender for Office 365 プラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) には、強力な自動調査および対応 [(AIR)](office-365-air.md) 機能が含まれています。 このような機能により、セキュリティ運用チームは脅威に対処するために多くの時間と労力を節約できます。 Microsoft は引き続きセキュリティ機能を強化しています。 最近、AIR の機能が強化され、セキュリティが侵害されたユーザー セキュリティ プレイブック (現在プレビュー中) が含まれます。 侵害されたユーザー セキュリティ プレイブックの詳細については、この記事を参照してください。 さらに詳細については、Microsoft Defender for [Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) でユーザーの侵害を検出して対応し、侵害の範囲を制限する時間の高速化に関するブログ投稿をご覧ください。

![侵害されたユーザーの自動調査](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

侵害されたユーザー セキュリティ プレイブックにより、組織のセキュリティ チームは次の操作を実行できます。

- 侵害されたユーザー アカウントの検出を高速化します。

- アカウントが侵害された場合に、侵害の範囲を制限する。そして

- 侵害されたユーザーに対して、より効果的かつ効率的に対応します。

## <a name="compromised-user-alerts"></a>侵害されたユーザーアラート

ユーザー アカウントが侵害された場合、異常または異常な動作が発生します。 たとえば、フィッシングメッセージやスパム メッセージは、信頼できるユーザー アカウントから内部的に送信される場合があります。 Defender for Office 365 は、365 内のメール パターンやコラボレーション アクティビティでこのような異常Officeできます。 この場合、アラートがトリガーされ、脅威軽減プロセスが開始されます。

たとえば、不審な電子メール送信のためにトリガーされたアラートを次に示します。

![不審な電子メール送信のためにトリガーされたアラート](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

次に、ユーザーの送信制限に達するとトリガーされたアラートの例を示します。

![送信制限に達した場合にトリガーされるアラート](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>侵害されたユーザーを調査して対応する

ユーザー アカウントが侵害されると、アラートがトリガーされます。 場合によっては、組織のセキュリティ運用チームによって問題が解決されるまで、そのユーザー アカウントがブロックされ、それ以上電子メール メッセージを送信できない場合があります。 それ以外の場合は、自動調査が開始され、セキュリティ チームが推奨するアクションが実行される可能性があります。

- [制限されたユーザーの表示と調査](#view-and-investigate-restricted-users)

- [自動調査に関する詳細を表示する](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 次のタスクを実行するには、適切なアクセス許可が必要です。 AIR [機能を使用するために必要なアクセス許可を参照してください](office-365-air.md#required-permissions-to-use-air-capabilities)。

### <a name="view-and-investigate-restricted-users"></a>制限されたユーザーの表示と調査

制限されたユーザーの一覧に移動するには、いくつかのオプションがあります。 たとえば、セキュリティ/コンプライアンス センター&、脅威管理の [制限されたユーザー  ] \> **のレビューに** \> **移動できます**。 次の手順では、アラート ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性があるさまざまな種類のアラートを確認するための優れた方法です。

1. <https://protection.office.com> に移動し、サインインします。

2. ナビゲーション ウィンドウで、[通知ダッシュボード] **を** \> **選択します**。

3. [その他の **通知] ウィジェットで** 、[制限付きユーザー **] を選択します**。

   ![その他の通知ウィジェット](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   これにより、制限されたユーザーの一覧が開きます。

   ![Office 365 での制限付きユーザー](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. 制限されたユーザーの解放など、詳細を表示してアクションを実行するには、一覧でユーザー [アカウントを選択します](removing-user-from-restricted-users-portal-after-spam.md)。

### <a name="view-details-about-automated-investigations"></a>自動調査に関する詳細を表示する

自動調査が開始すると、セキュリティ/コンプライアンス センターで、その詳細と結果&確認できます。 [脅威 **管理の** \> **調査] に移動** し、調査を選択して詳細を表示します。

詳細については、「調査の [詳細を表示する」を参照してください](air-view-investigation-results.md)。

## <a name="keep-the-following-points-in-mind"></a>次の点に気を付ける

- **アラートを最新の情報に残します**。 ご存知のように、侵害が検出されなくなるほど、組織、顧客、パートナーに広範な影響とコストが発生する可能性が大きくなります。 脅威を軽減するために、特にユーザーのアカウントが侵害された場合は、早期検出と適切な対応が重要です。

- **自動化は、セキュリティ運用チームを支援しますが、置き換わるのではありません**。 調査と対応の自動化機能は、セキュリティが侵害されたユーザーを早期に検出できますが、セキュリティ運用チームは調査と修復を行う必要があります。 サポートが必要な場合 「アクション [の確認と承認」を参照してください](air-review-approve-pending-completed-actions.md)。

- **不審なログインアラートを唯一のインジケーターとして使用していけな 。** ユーザー アカウントが侵害されると、疑わしいログインアラートがトリガーされる場合とトリガーされない場合があります。 アカウントが侵害された後に発生し、アラートをトリガーする一連のアクティビティである場合があります。 アラートについて詳しくは、次のリンクを参照してください。 アラート [ポリシーを参照してください](../../compliance/alert-policies.md)。

## <a name="next-steps"></a>次の手順

- [AIR 機能を使用するために必要なアクセス許可を確認する](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Office 365 で悪意のあるメールを検索して調査する](investigate-malicious-email-that-was-delivered.md)

- [Microsoft Defender for Endpoint の AIR について](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する](https://www.microsoft.com/microsoft-365/roadmap?filters=)
