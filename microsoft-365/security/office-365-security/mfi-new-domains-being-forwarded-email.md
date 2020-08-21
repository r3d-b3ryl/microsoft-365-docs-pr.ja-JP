---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、最新の Exchange 管理センターでメールの分析情報の転送中の新しいドメインを使用して、組織内のユーザーが転送されなかった外部ドメインにメッセージを転送しているときに調査する方法を学習できます。
ms.openlocfilehash: 0b4cd0490feebc8e05deb889b3cf54e1ea9f5928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826931"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="df773-103">セキュリティ センターのセキュリティ マネージャーでメールインサイトを転送している新&するドメイン</span><span class="sxs-lookup"><span data-stu-id="df773-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="df773-104">特定のドメインの外部受信者に電子メール メッセージを転送する有効な業務上の理由が存在する場合がありますが、組織内のユーザーがメッセージを外部のドメインに不審に転送し始めたときに、これ以上にそれらのドメインにメッセージを転送したこと (新しいドメイン) がない場合にこれが不審です。</span><span class="sxs-lookup"><span data-stu-id="df773-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="df773-105">この状態は、ユーザー アカウントが侵害されたことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df773-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="df773-106">アカウントが侵害されている可能性がある場合は、「侵害 [されたメール アカウントへの対応」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。</span><span class="sxs-lookup"><span data-stu-id="df773-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="df773-107">電子 **メールの分析情報が転送されている** 新しいドメインは、組織内のユーザーが新しいドメインにメッセージを転送しているときに通知します。</span><span class="sxs-lookup"><span data-stu-id="df773-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="df773-108">この分析情報は、問題が検出されたときのみ表示され、[転送レポート] [ページに表示](view-mail-flow-reports.md#forwarding-report) されます。</span><span class="sxs-lookup"><span data-stu-id="df773-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="df773-110">ウィジェットをクリックすると、転送されたメッセージに関する詳細が、転送レポートへのリンクなど、チップアップ [が表示されます](view-mail-flow-reports.md#forwarding-report)。</span><span class="sxs-lookup"><span data-stu-id="df773-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![[新しいドメイン] をクリックすると表示される詳細ポップアップ (メールのページに移動します)](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="df773-112">この詳細ページは、**トップ**インサイト &推奨事項領域 (レポート ダッシュボードまたはレポート**View all**) で [すべてのインサイトを表示] をクリックした後で、そのインサイト**を** \> **選択すると**表示されます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="df773-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="df773-113">外部ドメインへのメッセージ自動転送を防ぐためには、一部またはすべての外部ドメイン用にリモート ドメインを構成します。</span><span class="sxs-lookup"><span data-stu-id="df773-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="df773-114">詳細については [、「Exchange Online でリモート ドメインを管理する」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="df773-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="df773-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="df773-115">Related topics</span></span>

<span data-ttu-id="df773-116">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="df773-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
