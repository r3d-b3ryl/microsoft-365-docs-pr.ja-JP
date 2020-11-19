---
title: 自動調査と応答によって侵害されたユーザーアカウントに対処する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護、侵害
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
ms.date: 02/25/2020
description: Microsoft Defender for Office 365 プラン2で自動調査および応答機能を使用して、侵害されたユーザーアカウントを検出して対処するプロセスを高速化する方法について説明します。
ms.openlocfilehash: 80e4529f864d83d2a1711007f0f095de39955e68
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357913"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>自動調査と応答によって侵害されたユーザーアカウントに対処する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender For Office 365 プラン2に](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) は [、強力な自動調査と応答](office-365-air.md) (AIR) 機能が含まれています。 このような機能を使用すると、セキュリティ運用チームに大きな脅威に対処するための時間と労力を大幅に節約できます。 Microsoft は、セキュリティ機能を引き続き強化しています。 最近では、安全なユーザーセキュリティプレイブックを含めるように、空気機能が強化されています (現在プレビュー中)。 侵害されたユーザーセキュリティのプレイブックの詳細については、この記事を参照してください。 さらに、ブログの投稿速度を確認して、 [Microsoft Defender For Office 365 を使用して、ユーザーの侵害範囲と制限違反の範囲を検出して応答する](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) ことができます。

![侵害されたユーザーの自動化された調査](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

侵害されたユーザーセキュリティのプレイブックにより、組織のセキュリティチームは次のことを行うことができます。

- 侵害されたユーザーアカウントの検出を高速化します。

- アカウントが侵害された場合に、違反の範囲を制限します。そして

- 侵害されたユーザーにより効果的かつ効率的に対応します。

## <a name="compromised-user-alerts"></a>侵害されたユーザー通知

ユーザーアカウントが侵害されると、例外的または異常な動作が発生します。 たとえば、フィッシングおよびスパムメッセージは、信頼できるユーザーアカウントから内部で送信される場合があります。 Office 365 の Defender では、Office 365 の電子メールパターンやコラボレーション作業でこのような異常を検出することができます。 これが発生すると、アラートがトリガーされ、脅威の軽減プロセスが開始されます。

たとえば、不審な電子メールの送信によってトリガーされた警告は次のようになります。

![疑わしい電子メールの送信によってトリガーされたアラート](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

また、ユーザーの送信の制限に達したときにトリガーされた警告の例を次に示します。

![送信制限に達したときにトリガーされるアラート](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>侵害されたユーザーの調査と対応

ユーザーアカウントが侵害されると、警告がトリガーされます。 場合によっては、ユーザーアカウントがブロックされ、組織のセキュリティ運用チームによって問題が解決されるまで、以降の電子メールメッセージを送信できなくなります。 その他の場合は、自動化された調査が開始され、セキュリティチームにとって推奨されるアクションが発生する可能性があります。

- [制限されたユーザーの表示と調査](#view-and-investigate-restricted-users)

- [自動調査に関する詳細を表示する](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 次のタスクを実行するには、適切なアクセス許可を持っている必要があります。 [AIR 機能を使用するには、必要なアクセス許可を](office-365-air.md#required-permissions-to-use-air-capabilities)参照してください。

### <a name="view-and-investigate-restricted-users"></a>制限されたユーザーの表示と調査

制限されたユーザーのリストに移動するためのいくつかのオプションがあります。 たとえば、セキュリティ & コンプライアンスセンターでは、[**脅威の管理**] [  >  **Review**  >  **制限付きユーザー** のレビュー] に移動できます。 次の手順では、 **通知** ダッシュボードを使用したナビゲーションについて説明します。これは、トリガーされた可能性のあるさまざまな種類の通知を確認するための適切な方法です。

1. [https://protection.office.com](https://protection.office.com) に移動し、サインインします。

2. ナビゲーションウィンドウで、[**通知** ダッシュボード] を選択し  >  **Dashboard** ます。

3. [ **その他の通知** ] ウィジェットで、[制限された **ユーザー**] を選択します。

   ![その他の通知ウィジェット](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   これにより、制限されたユーザーの一覧が開きます。

   ![Office 365 で制限されたユーザー](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. リストでユーザーアカウントを選択して、制限され [たユーザーを解放](removing-user-from-restricted-users-portal-after-spam.md)するなどの詳細情報を表示し、アクションを実行します。

### <a name="view-details-about-automated-investigations"></a>自動調査に関する詳細を表示する

自動調査が開始されたら、セキュリティ & コンプライアンスセンターでその詳細と結果を確認できます。 [**脅威管理**  >  の **調査**] に移動し、詳細を表示する調査を選択します。

詳細については、「 [調査の詳細を表示](air-view-investigation-results.md)する」を参照してください。

## <a name="keep-the-following-points-in-mind"></a>次の点に注意してください。

- **通知を常に手前に** 移動します。 ご存知のように、危険にさらされている時間が長くなるほど、組織、顧客、パートナーに対して広範な影響とコストが発生する可能性が大きくなります。 事前の検出と適時の応答は、脅威を軽減するために重要であり、特にユーザーのアカウントが侵害された場合に非常に重要です。

- **自動化は、セキュリティ運用チームを支援しますが、置き換えはしません**。 自動化された調査および応答機能により、危険にさらされているユーザーが早いうちに検出されることがありますが、セキュリティ運用チームは、多くの場合、調査と修復を行う必要があります。 この点については、いくつかのヘルプが必要ですか? 「 [レビューと承認のアクション」を](air-review-approve-pending-completed-actions.md)参照してください。

- **疑わしいログインの警告は、唯一の指標としては利用しないで** ください。 ユーザーアカウントが侵害された場合、疑わしいログイン警告が発生するか、またはトリガーされない可能性があります。 場合によっては、警告をトリガーするアカウントが侵害された後に発生する一連のアクティビティになることがあります。 アラートの詳細を知りたいですか。 「 [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)」を参照してください。

## <a name="next-steps"></a>次の手順

- [空気機能を使用するために必要なアクセス許可を確認する](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Office 365 で悪意のある電子メールを検索して調査する](investigate-malicious-email-that-was-delivered.md)

- [エンドポイントの Microsoft Defender での空気について説明します。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する](https://www.microsoft.com/microsoft-365/roadmap?filters=)
