---
title: 自動転送されたメッセージの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの自動転送メッセージレポートについて説明します。
ms.openlocfilehash: 05e3f62610c32bc95caf579ef4dd46bf1ed90275
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577821"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="ef068-103">セキュリティ & コンプライアンスセンターでの自動転送メッセージの洞察</span><span class="sxs-lookup"><span data-stu-id="ef068-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="ef068-104">セキュリティ & コンプライアンスセンターの[メールフローダッシュボード](mail-flow-insights-v2.md)に表示される**自動転送メッセージ**には、組織から外部ドメインの受信者に自動的に転送されるメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef068-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![セキュリティ & コンプライアンスセンターの自動転送メッセージウィジェット](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="ef068-106">自動転送されたメッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="ef068-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="ef068-107">ウィジェット内のメッセージ数をクリックすると、自動的に転送されるメッセージに関する詳細情報を示すフライアウトウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef068-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="ef068-108">**転送方法による自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="ef068-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="ef068-109">**メールフロールール**</span><span class="sxs-lookup"><span data-stu-id="ef068-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="ef068-110">**受信トレイルール**</span><span class="sxs-lookup"><span data-stu-id="ef068-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="ef068-111">**SMTP 転送による**</span><span class="sxs-lookup"><span data-stu-id="ef068-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="ef068-112">詳細については、[転送レポート](view-mail-flow-reports.md#forwarding-report)へのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef068-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="ef068-113">**ドメインおよびユーザーによる自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="ef068-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="ef068-114">**上位5ドメイン転送先**</span><span class="sxs-lookup"><span data-stu-id="ef068-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="ef068-115">**新しいドメイン (先週)**</span><span class="sxs-lookup"><span data-stu-id="ef068-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="ef068-116">**上位5人のユーザーの転送**</span><span class="sxs-lookup"><span data-stu-id="ef068-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="ef068-117">**新しいユーザー (先週)**</span><span class="sxs-lookup"><span data-stu-id="ef068-117">**New users (last week)**</span></span>
  - <span data-ttu-id="ef068-118">詳細については、[転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report)へのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef068-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![セキュリティ & コンプライアンスセンターの自動転送されたメッセージレポートの詳細ポップアップ](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="ef068-120">分析情報</span><span class="sxs-lookup"><span data-stu-id="ef068-120">Insights</span></span>

<span data-ttu-id="ef068-121">レポートデータに基づいて、2つの洞察が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ef068-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="ef068-122">新しいユーザーがメールを転送する</span><span class="sxs-lookup"><span data-stu-id="ef068-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="ef068-123">メールを転送する新しいドメイン</span><span class="sxs-lookup"><span data-stu-id="ef068-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="ef068-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef068-124">See also</span></span>

<span data-ttu-id="ef068-125">メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef068-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
