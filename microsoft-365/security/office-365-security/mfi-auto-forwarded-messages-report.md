---
title: 自動転送されたメッセージのインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで自動転送メッセージ レポート &について確認できます。
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827029"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="90d06-103">セキュリティ センターの自動転送されたメッセージ&分析情報</span><span class="sxs-lookup"><span data-stu-id="90d06-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="90d06-104">セキュリティ**コンプライアンス センターのメール フロー**ダッシュボードの自動[Mail flow dashboard](mail-flow-insights-v2.md)転送メッセージ インサイト &に、組織から自動的に外部ドメイン内の受信者に転送されるメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d06-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![セキュリティ センターの自動転送メッセージ ウィジェット&ッジ](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="90d06-106">自動転送メッセージの詳細</span><span class="sxs-lookup"><span data-stu-id="90d06-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="90d06-107">ウィジェットのメッセージ数をクリックすると、自動転送されたメッセージに関する詳細情報を示すポップアップ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d06-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="90d06-108">**転送方法による自動転送メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="90d06-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="90d06-109">**メール フロー ルール別**</span><span class="sxs-lookup"><span data-stu-id="90d06-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="90d06-110">**受信トレイのルールを使用する**</span><span class="sxs-lookup"><span data-stu-id="90d06-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="90d06-111">**SMTP 転送によるフィルター**</span><span class="sxs-lookup"><span data-stu-id="90d06-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="90d06-112">詳細については、 [転送レポート](view-mail-flow-reports.md#forwarding-report) へのリンク。</span><span class="sxs-lookup"><span data-stu-id="90d06-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="90d06-113">**ドメインおよびユーザー別に自動転送されたメッセージ**:</span><span class="sxs-lookup"><span data-stu-id="90d06-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="90d06-114">**上位 5 つのドメインに転送**</span><span class="sxs-lookup"><span data-stu-id="90d06-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="90d06-115">**新しいドメイン (過去 1 週間)**</span><span class="sxs-lookup"><span data-stu-id="90d06-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="90d06-116">**転送ユーザー数 5 名**</span><span class="sxs-lookup"><span data-stu-id="90d06-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="90d06-117">**新規ユーザー (過去 1 週間)**</span><span class="sxs-lookup"><span data-stu-id="90d06-117">**New users (last week)**</span></span>
  - <span data-ttu-id="90d06-118">詳細については、 [転送変更レポート](mfi-new-users-forwarding-email.md#forwarding-modifications-report) へのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90d06-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![セキュリティ コンプライアンス センターの自動転送メッセージ レポートの詳細&詳細情報](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="90d06-120">分析情報</span><span class="sxs-lookup"><span data-stu-id="90d06-120">Insights</span></span>

<span data-ttu-id="90d06-121">レポート データに基づいて、次の 2 つのインサイトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="90d06-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="90d06-122">新しいユーザーのメール転送</span><span class="sxs-lookup"><span data-stu-id="90d06-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="90d06-123">メール転送される新しいドメイン</span><span class="sxs-lookup"><span data-stu-id="90d06-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="90d06-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="90d06-124">See also</span></span>

<span data-ttu-id="90d06-125">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="90d06-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
