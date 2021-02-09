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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで電子メールの転送される新しいドメインの分析情報を使用して、ユーザーが転送されたことがない外部ドメインにメッセージを転送する状況を調査する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150605"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="c1395-103">セキュリティ/コンプライアンス センターでメールを転送&新しいドメイン</span><span class="sxs-lookup"><span data-stu-id="c1395-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c1395-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c1395-104">**Applies to**</span></span>
- [<span data-ttu-id="c1395-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c1395-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c1395-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c1395-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c1395-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1395-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c1395-108">電子メール メッセージを特定のドメインの外部受信者に転送するには、ビジネス上の有効な理由があります。</span><span class="sxs-lookup"><span data-stu-id="c1395-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="c1395-109">ただし、組織内のユーザーが、組織内の誰もメッセージを (新しいドメイン) に転送しなきドメインにメッセージを転送し始め、疑わしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1395-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="c1395-110">この状態は、ユーザー アカウントが侵害された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c1395-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="c1395-111">アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="c1395-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="c1395-112">セキュリティ **/コンプライアンス** [&](https://protection.office.com) センターでメールの分析情報を転送する新しいドメインは、組織内のユーザーが新しいドメインにメッセージを転送するときに通知します。</span><span class="sxs-lookup"><span data-stu-id="c1395-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="c1395-113">この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。</span><span class="sxs-lookup"><span data-stu-id="c1395-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="c1395-115">ウィジェットをクリックすると、転送レポートへのリンクなど、転送されたメッセージの詳細を確認できるフライアウトが [表示されます](view-mail-flow-reports.md#forwarding-report)。</span><span class="sxs-lookup"><span data-stu-id="c1395-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![メールを転送する新しいドメインの分析情報をクリックした後に表示される詳細フライアウト](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="c1395-117">[上位の分析情報とおすすめ] 領域 **([** レポート ダッシュボード] または [ &]) で [すべて表示] をクリックした後に、分析情報を選択すると、**この詳細ページ** に移動 \> することもできます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="c1395-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="c1395-118">外部ドメインへのメッセージの自動転送を防ぐには、一部またはすべての外部ドメインのリモート ドメインを構成します。</span><span class="sxs-lookup"><span data-stu-id="c1395-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="c1395-119">詳細については [、「Exchange Online でのリモート ドメインの管理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="c1395-119">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1395-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1395-120">Related topics</span></span>

<span data-ttu-id="c1395-121">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="c1395-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
