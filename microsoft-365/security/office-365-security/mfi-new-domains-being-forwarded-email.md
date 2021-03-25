---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、転送される新しいドメインを使用して、転送されたことがない外部ドメインにメッセージを転送するユーザーを調査する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f3a5f125a045176f152ccd079ebe7f7e40bc39f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205136"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="47d60-103">セキュリティ コンプライアンス センターで電子メールの分析情報を転送&ドメイン</span><span class="sxs-lookup"><span data-stu-id="47d60-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="47d60-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="47d60-104">**Applies to**</span></span>
- [<span data-ttu-id="47d60-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="47d60-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="47d60-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="47d60-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="47d60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47d60-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="47d60-108">特定のドメインの外部受信者に電子メール メッセージを転送するには、有効なビジネス上の理由があります。</span><span class="sxs-lookup"><span data-stu-id="47d60-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="47d60-109">ただし、組織内のユーザーが突然、組織内の誰もメッセージを (新しいドメイン) に転送したユーザーがいないドメインにメッセージを転送し始める場合、疑わしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="47d60-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="47d60-110">この条件は、ユーザー アカウントが侵害された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47d60-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="47d60-111">アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントに応答 [する」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="47d60-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="47d60-112">セキュリティ **&** コンプライアンス センターでメールを転送する新しいドメインは、組織内 [の](https://protection.office.com) ユーザーが新しいドメインにメッセージを転送するときに通知します。</span><span class="sxs-lookup"><span data-stu-id="47d60-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="47d60-113">この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。</span><span class="sxs-lookup"><span data-stu-id="47d60-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="47d60-115">ウィジェットをクリックすると、転送されたメッセージの詳細 (転送レポートへのリンクなど) を確認できるフライアウトが [表示されます](view-mail-flow-reports.md#forwarding-report)。</span><span class="sxs-lookup"><span data-stu-id="47d60-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![[転送される新しいドメイン] をクリックした後に表示される詳細フライアウト](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="47d60-117">[レポート ダッシュボード] または [ おすすめ] 領域の[トップ インサイト] 領域で [すべて表示] をクリックした後で&を選択すると、**この詳細** ページに \> **アクセス** することもできます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="47d60-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="47d60-118">外部ドメインへのメッセージの自動転送を防止するには、一部またはすべての外部ドメインにリモート ドメインを構成します。</span><span class="sxs-lookup"><span data-stu-id="47d60-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="47d60-119">詳細については [、「Exchange Online でリモート ドメインを管理する」を参照してください](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="47d60-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="47d60-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="47d60-120">Related topics</span></span>

<span data-ttu-id="47d60-121">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="47d60-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>