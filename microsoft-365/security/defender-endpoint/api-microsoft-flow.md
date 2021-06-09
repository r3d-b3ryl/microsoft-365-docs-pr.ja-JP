---
title: Microsoft Defender for Endpoint Flow コネクタ
ms.reviewer: ''
description: Microsoft Defender for Endpoint Flow コネクタを使用して、セキュリティを自動化し、テナントで新しいアラートが発生するといつでもトリガーされるフローを作成します。
keywords: flow, サポートされている api, api, Microsoft flow, query, automation
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0718f8e3aba27e6fbfc92a4308278f4c629275f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843796"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="80be3-104">Microsoft Power Automate (以前はMicrosoft Flow)、Azure Functions</span><span class="sxs-lookup"><span data-stu-id="80be3-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80be3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="80be3-105">**Applies to:**</span></span>
- [<span data-ttu-id="80be3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="80be3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80be3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80be3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="80be3-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="80be3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80be3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="80be3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="80be3-110">セキュリティ手順の自動化は、最新のセキュリティ 運用センターの標準要件です。</span><span class="sxs-lookup"><span data-stu-id="80be3-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="80be3-111">専門的なサイバー防御者がいないので、SOC は最も効率的な方法で作業し、自動化が必要です。</span><span class="sxs-lookup"><span data-stu-id="80be3-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="80be3-112">Microsoft Power Automateは、このために正確に構築されたさまざまなコネクタをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="80be3-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="80be3-113">数分以内にエンドツーエンドのプロシージャオートメーションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="80be3-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="80be3-114">Microsoft Defender API には、多くの機能Flow公式のコネクタがあります。</span><span class="sxs-lookup"><span data-stu-id="80be3-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![編集資格情報のイメージ1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="80be3-116">プレミアム コネクタライセンスの前提条件の詳細については、「Premium [Connectors のライセンス」を参照してください](/power-automate/triggers-introduction#licensing-for-premium-connectors)。</span><span class="sxs-lookup"><span data-stu-id="80be3-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="80be3-117">使用例</span><span class="sxs-lookup"><span data-stu-id="80be3-117">Usage example</span></span>

<span data-ttu-id="80be3-118">次の例では、テナントで新Flowアラートが発生する場合にトリガーされる新しいアラートを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="80be3-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="80be3-119">Microsoft Power Automate[にログインします](https://flow.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="80be3-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="80be3-120">[マイ フロー **] [**  >  **新しい**  >  **自動入力から] 空白に移動します**。</span><span class="sxs-lookup"><span data-stu-id="80be3-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![編集資格情報のイメージ2](images/api-flow-1.png)

3. <span data-ttu-id="80be3-122">ユーザーの名前を選択Flowトリガーとして "Microsoft Defender ATPトリガー" を検索し、新しいアラート トリガーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80be3-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![編集資格情報のイメージ3](images/api-flow-2.png)

<span data-ttu-id="80be3-124">これで、新Flow発生するごとにトリガーされるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80be3-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![編集資格情報のイメージ4](images/api-flow-3.png)

<span data-ttu-id="80be3-126">ここで行う必要があるのは、次の手順を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80be3-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="80be3-127">たとえば、アラートの重大度が高い場合にデバイスを分離し、そのデバイスに関する電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="80be3-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="80be3-128">アラート トリガーは、アラート ID とコンピューター ID のみを提供します。</span><span class="sxs-lookup"><span data-stu-id="80be3-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="80be3-129">コネクタを使用して、これらのエンティティを展開できます。</span><span class="sxs-lookup"><span data-stu-id="80be3-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="80be3-130">コネクタを使用して Alert エンティティを取得する</span><span class="sxs-lookup"><span data-stu-id="80be3-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="80be3-131">新 **しいMicrosoft Defender ATP** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80be3-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="80be3-132">[アラート **] - [単一のアラート API を取得する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80be3-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="80be3-133">最後の **手順の [アラート ID]** を [入力] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="80be3-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![編集資格情報のイメージ5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="80be3-135">アラートの重大度が [高] の場合はデバイスを分離する</span><span class="sxs-lookup"><span data-stu-id="80be3-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="80be3-136">新 **しい手順として** 条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="80be3-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="80be3-137">アラートの重大度が High に **等しいか確認** します。</span><span class="sxs-lookup"><span data-stu-id="80be3-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="80be3-138">[はい] の場合Microsoft Defender ATP **コンピューター** の操作を [コンピューター ID とコメントで分離する] を追加します。</span><span class="sxs-lookup"><span data-stu-id="80be3-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![資格情報の編集のイメージ6](images/api-flow-5.png)

3. <span data-ttu-id="80be3-140">アラートと分離に関する電子メールを送信する新しい手順を追加します。</span><span class="sxs-lookup"><span data-stu-id="80be3-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="80be3-141">メール コネクタや Gmail など、非常に使いやすいOutlookがあります。</span><span class="sxs-lookup"><span data-stu-id="80be3-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="80be3-142">フローを保存します。</span><span class="sxs-lookup"><span data-stu-id="80be3-142">Save your flow.</span></span>

<span data-ttu-id="80be3-143">また、高度な検索 **クエリを** 実行するスケジュールされたフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="80be3-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="80be3-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="80be3-144">Related topic</span></span>
- [<span data-ttu-id="80be3-145">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="80be3-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
