---
title: エンドポイント抑制ルールの Microsoft Defender の管理
description: 抑制ルールを使用して、ポータルにアラートが表示されるのを防ぐ必要がある場合があります。 Microsoft Defender ATP で抑制ルールを管理する方法について説明します。
keywords: 抑制、ルール、ルール名、スコープ、アクション、アラートの管理、オン、オフ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063964"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="237f5-105">抑制ルールの管理</span><span class="sxs-lookup"><span data-stu-id="237f5-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="237f5-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="237f5-106">**Applies to:**</span></span>
- [<span data-ttu-id="237f5-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="237f5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="237f5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="237f5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="237f5-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="237f5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="237f5-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="237f5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="237f5-111">ポータルへのアラートの表示を抑制する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="237f5-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="237f5-112">組織内の既知のツールやプロセスなど、無実と知られている特定のアラートに対して抑制ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="237f5-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="237f5-113">アラートを抑制する方法の詳細については、「アラートを抑制する」 [を参照してください](manage-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="237f5-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="237f5-114">すべての抑制ルールの一覧を表示し、1 か所で管理できます。</span><span class="sxs-lookup"><span data-stu-id="237f5-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="237f5-115">アラート抑制ルールをオンまたはオフに切り替えできます。</span><span class="sxs-lookup"><span data-stu-id="237f5-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="237f5-116">ナビゲーション ウィンドウで、[設定アラートの抑制 **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="237f5-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="237f5-117">組織内のユーザーが作成した抑制ルールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="237f5-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="237f5-118">ルール名の横にあるチェック ボックスをクリックして、ルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="237f5-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="237f5-119">[ルール **を有効にする]** **、[ルールの編集]**、または [  **ルールの削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="237f5-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="237f5-120">ルールに変更を加える場合、これらのアラートが新しい条件と一致するかどうかに関係なく、既に抑制されているアラートを解放できます。</span><span class="sxs-lookup"><span data-stu-id="237f5-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="237f5-121">抑制ルールの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="237f5-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="237f5-122">ナビゲーション ウィンドウで、[設定アラートの抑制 **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="237f5-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="237f5-123">組織内のユーザーが作成した抑制ルールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="237f5-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="237f5-124">ルール名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="237f5-124">Click on a rule name.</span></span> <span data-ttu-id="237f5-125">ルールの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="237f5-125">Details of the rule is displayed.</span></span> <span data-ttu-id="237f5-126">ルールが作成された状態、スコープ、アクション、一致するアラートの数、作成日時などのルールの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="237f5-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="237f5-127">関連付けられたアラートとルールの条件を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="237f5-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="237f5-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="237f5-128">Related topics</span></span>

- [<span data-ttu-id="237f5-129">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="237f5-129">Manage alerts</span></span>](manage-alerts.md)
