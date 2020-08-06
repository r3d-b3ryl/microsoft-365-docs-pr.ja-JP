---
title: 転送される新しいドメインメールの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、新しい Exchange 管理センターで転送された新しいドメインを使用して、組織内のユーザーが転送されていない外部ドメインにメッセージを転送していることを調査する方法を学習できます。
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578442"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="98e8a-103">転送される新しいドメインセキュリティ & コンプライアンスセンターでのメールに関する洞察</span><span class="sxs-lookup"><span data-stu-id="98e8a-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="98e8a-104">電子メールメッセージを特定のドメインの外部の受信者に転送するのに有効なビジネス上の理由があるかもしれませんが、組織内のユーザーが外部ドメインへのメッセージ転送を突然開始したときに、組織内のユーザーがそのドメインにメッセージを転送していない場合 (新しいドメイン) は疑わしいことがあります。</span><span class="sxs-lookup"><span data-stu-id="98e8a-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="98e8a-105">この条件は、ユーザーアカウントが侵害されていることを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98e8a-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="98e8a-106">アカウントが侵害されている疑いがある場合は、「[危害を受けた電子メールアカウントへの対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e8a-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="98e8a-107">**メールを転送している新しいドメイン**は、組織内のユーザーが新しいドメインにメッセージを転送しているときに通知します。</span><span class="sxs-lookup"><span data-stu-id="98e8a-107">The **New domains being forwarded email** insight notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="98e8a-108">この洞察は、問題が検出されたときにのみ表示され、[転送レポート](view-mail-flow-reports.md#forwarding-report)ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98e8a-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![転送される新しいドメインメールの洞察](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="98e8a-110">ウィジェットをクリックすると、転送されたメッセージの詳細を確認できるポップアップが表示されます。これには、[転送レポート](view-mail-flow-reports.md#forwarding-report)へのリンクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="98e8a-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![転送される新しいドメインをクリックした後に表示される詳細ポップアップ、電子メールの洞察](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="98e8a-112">また、[詳細] を選択した後に [詳細] を選択すると、[詳細] を選択した後に、[詳細] を選択したときに、この詳細ページ**を表示でき**ます (**レポート**ダッシュボードまたは) の [**上位の分析 &** \> **Dashboard** <https://protection.office.com/insightdashboard></span><span class="sxs-lookup"><span data-stu-id="98e8a-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="98e8a-113">外部ドメインへの自動メッセージ転送を禁止するには、一部またはすべての外部ドメインに対してリモートドメインを構成します。</span><span class="sxs-lookup"><span data-stu-id="98e8a-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="98e8a-114">詳細については、「 [Manage remote domains In Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e8a-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="98e8a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="98e8a-115">Related topics</span></span>

<span data-ttu-id="98e8a-116">メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e8a-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
