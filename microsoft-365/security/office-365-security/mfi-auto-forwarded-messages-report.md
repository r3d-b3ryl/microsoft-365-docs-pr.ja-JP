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
description: 管理者は、セキュリティ/コンプライアンス センターのメール フロー ダッシュボードで、自動転送&確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290635"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="dfd11-103">セキュリティ/コンプライアンス センターでの自動転送&の分析情報</span><span class="sxs-lookup"><span data-stu-id="dfd11-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dfd11-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="dfd11-104">**Applies to**</span></span>
- [<span data-ttu-id="dfd11-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dfd11-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dfd11-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="dfd11-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="dfd11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dfd11-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="dfd11-108">セキュリティ **&** コンプライアンス センターのメール [](mail-flow-insights-v2.md)フロー ダッシュボードの [](https://protection.office.com)自動転送メッセージの分析情報には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfd11-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![セキュリティ/コンプライアンス センターの自動転送&ウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="dfd11-110">自動転送されたメッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="dfd11-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="dfd11-111">ウィジェット内のメッセージ数をクリックすると、自動転送されたメッセージに関する詳細を示すフライアウト ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfd11-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="dfd11-112">**転送方法による自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="dfd11-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="dfd11-113">**メール フロー ルール別**</span><span class="sxs-lookup"><span data-stu-id="dfd11-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="dfd11-114">**受信トレイ ルール別**</span><span class="sxs-lookup"><span data-stu-id="dfd11-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="dfd11-115">**SMTP 転送による** 転送 : この方法は、「メールボックスの電子メール転送を構成する」の説明に従って、管理者がメールボックスで構成できる自動転送 [を示します](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="dfd11-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="dfd11-116">詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="dfd11-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="dfd11-117">**ドメインおよびユーザーによって自動的に転送されるメッセージ**:</span><span class="sxs-lookup"><span data-stu-id="dfd11-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="dfd11-118">**転送先の上位 5 つのドメイン**</span><span class="sxs-lookup"><span data-stu-id="dfd11-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="dfd11-119">**新しいドメイン (先週)**</span><span class="sxs-lookup"><span data-stu-id="dfd11-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="dfd11-120">**上位 5 人の転送ユーザー**</span><span class="sxs-lookup"><span data-stu-id="dfd11-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="dfd11-121">**新しいユーザー (先週)**</span><span class="sxs-lookup"><span data-stu-id="dfd11-121">**New users (last week)**</span></span>
  - <span data-ttu-id="dfd11-122">詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="dfd11-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![セキュリティ/コンプライアンス センターの [自動転送されたメッセージ] レポート&詳細](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="dfd11-124">分析情報</span><span class="sxs-lookup"><span data-stu-id="dfd11-124">Insights</span></span>

<span data-ttu-id="dfd11-125">レポート データに基づいて 2 つの分析情報が生成されます。</span><span class="sxs-lookup"><span data-stu-id="dfd11-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="dfd11-126">新しいユーザーがメールを転送する</span><span class="sxs-lookup"><span data-stu-id="dfd11-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="dfd11-127">メールを転送する新しいドメイン</span><span class="sxs-lookup"><span data-stu-id="dfd11-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="dfd11-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfd11-128">See also</span></span>

<span data-ttu-id="dfd11-129">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd11-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
