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
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029944"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="7d0f8-103">セキュリティ/コンプライアンス センターでの自動転送&の分析情報</span><span class="sxs-lookup"><span data-stu-id="7d0f8-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7d0f8-104">セキュリティ **&** コンプライアンス センターのメール [](mail-flow-insights-v2.md)フロー ダッシュボードの [](https://protection.office.com)自動転送されたメッセージの分析情報には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![セキュリティ/コンプライアンス センターの自動転送&ウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="7d0f8-106">自動転送されたメッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="7d0f8-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="7d0f8-107">ウィジェット内のメッセージ数をクリックすると、自動転送されたメッセージに関する詳細を表示するフライアウト ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="7d0f8-108">**転送方法による自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="7d0f8-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="7d0f8-109">**メール フロー ルール別**</span><span class="sxs-lookup"><span data-stu-id="7d0f8-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="7d0f8-110">**受信トレイ ルール別**</span><span class="sxs-lookup"><span data-stu-id="7d0f8-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="7d0f8-111">**SMTP 転送による** 転送 : この方法は、「メールボックスの電子メール転送を構成する」の説明に従って、管理者がメールボックスで構成できる自動転送 [を示します](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="7d0f8-112">詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="7d0f8-113">**ドメインおよびユーザーによって自動的に転送されるメッセージ**:</span><span class="sxs-lookup"><span data-stu-id="7d0f8-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="7d0f8-114">**転送先の上位 5 つのドメイン**</span><span class="sxs-lookup"><span data-stu-id="7d0f8-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="7d0f8-115">**新しいドメイン (先週)**</span><span class="sxs-lookup"><span data-stu-id="7d0f8-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="7d0f8-116">**上位 5 人の転送ユーザー**</span><span class="sxs-lookup"><span data-stu-id="7d0f8-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="7d0f8-117">**新しいユーザー (先週)**</span><span class="sxs-lookup"><span data-stu-id="7d0f8-117">**New users (last week)**</span></span>
  - <span data-ttu-id="7d0f8-118">詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![セキュリティ/コンプライアンス センターの [自動転送されたメッセージ] レポート&詳細](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="7d0f8-120">分析情報</span><span class="sxs-lookup"><span data-stu-id="7d0f8-120">Insights</span></span>

<span data-ttu-id="7d0f8-121">レポート データに基づいて 2 つの分析情報が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="7d0f8-122">新しいユーザーがメールを転送する</span><span class="sxs-lookup"><span data-stu-id="7d0f8-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="7d0f8-123">メールを転送する新しいドメイン</span><span class="sxs-lookup"><span data-stu-id="7d0f8-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="7d0f8-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d0f8-124">See also</span></span>

<span data-ttu-id="7d0f8-125">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0f8-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
