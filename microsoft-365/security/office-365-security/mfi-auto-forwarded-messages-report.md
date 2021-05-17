---
title: 自動転送されたメッセージの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで自動転送&できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206405"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="75e9f-103">セキュリティ コンプライアンス センターでのメッセージの自動転送&分析</span><span class="sxs-lookup"><span data-stu-id="75e9f-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="75e9f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="75e9f-104">**Applies to**</span></span>
- [<span data-ttu-id="75e9f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="75e9f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="75e9f-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="75e9f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="75e9f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75e9f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="75e9f-108">セキュリティ **&** コンプライアンス センターのメール [](mail-flow-insights-v2.md)フロー ダッシュボードの [](https://protection.office.com)自動転送メッセージインサイトには、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75e9f-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![セキュリティ コンプライアンス センターの自動転送&ウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="75e9f-110">自動転送されたメッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="75e9f-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="75e9f-111">ウィジェット内のメッセージの数をクリックすると、自動転送されたメッセージの詳細を示すフライアウト ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75e9f-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="75e9f-112">**転送方法による自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="75e9f-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="75e9f-113">**メール フロー ルール別**</span><span class="sxs-lookup"><span data-stu-id="75e9f-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="75e9f-114">**受信トレイ ルール別**</span><span class="sxs-lookup"><span data-stu-id="75e9f-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="75e9f-115">**SMTP 転送 :** このメソッドは、「メールボックスの電子メール転送の構成」の説明に従って、管理者がメールボックスで構成できる自動転送 [を示します](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="75e9f-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="75e9f-116">詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="75e9f-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="75e9f-117">**ドメインとユーザーによる自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="75e9f-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="75e9f-118">**転送先の上位 5 つのドメイン**</span><span class="sxs-lookup"><span data-stu-id="75e9f-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="75e9f-119">**新しいドメイン (先週)**</span><span class="sxs-lookup"><span data-stu-id="75e9f-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="75e9f-120">**上位 5 人の転送ユーザー**</span><span class="sxs-lookup"><span data-stu-id="75e9f-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="75e9f-121">**新しいユーザー (先週)**</span><span class="sxs-lookup"><span data-stu-id="75e9f-121">**New users (last week)**</span></span>
  - <span data-ttu-id="75e9f-122">詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="75e9f-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![セキュリティ コンプライアンス センターの自動転送メッセージ レポートの詳細&飛び出し](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="75e9f-124">分析情報</span><span class="sxs-lookup"><span data-stu-id="75e9f-124">Insights</span></span>

<span data-ttu-id="75e9f-125">レポート データに基づいて 2 つの分析情報が生成されます。</span><span class="sxs-lookup"><span data-stu-id="75e9f-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="75e9f-126">新しいユーザーがメールを転送する</span><span class="sxs-lookup"><span data-stu-id="75e9f-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="75e9f-127">メールの転送中の新しいドメイン</span><span class="sxs-lookup"><span data-stu-id="75e9f-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="75e9f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="75e9f-128">See also</span></span>

<span data-ttu-id="75e9f-129">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="75e9f-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>