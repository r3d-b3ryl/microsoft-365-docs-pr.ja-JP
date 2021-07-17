---
title: パイロットMicrosoft 365 Defenderインシデント対応機能を試して、インシデントの優先順位付けと管理、自動調査と対応の構成、高度な検索の使用を行います。
description: インシデント対応機能を試Microsoft 365 Defender、インシデントの優先順位付けと管理、調査の自動化、脅威検出での高度な検出の使用を行います。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458115"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a><span data-ttu-id="49e2e-104">パイロットMicrosoft 365 Defenderインシデント対応機能を試す</span><span class="sxs-lookup"><span data-stu-id="49e2e-104">Try Microsoft 365 Defender incident response capabilities in a pilot environment</span></span>

<span data-ttu-id="49e2e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="49e2e-105">**Applies to:**</span></span>
- <span data-ttu-id="49e2e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49e2e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="49e2e-107">この記事は[、パイロット環境を使用](eval-defender-investigate-respond.md)してインシデントの調査と対応を実行するプロセスの手順 2 Microsoft 365 Defenderです。</span><span class="sxs-lookup"><span data-stu-id="49e2e-107">This article is [Step 2 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="49e2e-108">このプロセスの詳細については、概要の記事を [参照](eval-defender-investigate-respond.md) してください。</span><span class="sxs-lookup"><span data-stu-id="49e2e-108">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="49e2e-109">シミュレートされた攻撃[に対して](eval-defender-investigate-respond-simulate-attack.md)インシデント対応を実行したら、次のMicrosoft 365 Defenderを確認できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-109">Once you have performed an [incident response for a simulated attack](eval-defender-investigate-respond-simulate-attack.md), here are some Microsoft 365 Defender capabilities to explore:</span></span>

|<span data-ttu-id="49e2e-110">機能</span><span class="sxs-lookup"><span data-stu-id="49e2e-110">Capability</span></span> |<span data-ttu-id="49e2e-111">説明</span><span class="sxs-lookup"><span data-stu-id="49e2e-111">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="49e2e-112">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="49e2e-112">Prioritize incidents</span></span>](#prioritize-incidents) | <span data-ttu-id="49e2e-113">次に対処するインシデントを決定するには、インシデント キューのフィルター処理と並べ替えを使用します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-113">Use filtering and sorting of the incidents queue to determine which incidents to address next.</span></span> |
| [<span data-ttu-id="49e2e-114">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="49e2e-114">Manage incidents</span></span>](#manage-incidents) | <span data-ttu-id="49e2e-115">インシデント のプロパティを変更して、正しい割り当てを確認し、タグとコメントを追加し、インシデントを解決します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-115">Modify incident properties to ensure correct assignment, add tags and comments, and to resolve an incident.</span></span> |
| [<span data-ttu-id="49e2e-116">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="49e2e-116">Automated investigation and response</span></span>](#examine-automated-investigation-and-response-with-the-action-center) | <span data-ttu-id="49e2e-117">セキュリティ運用チームが脅威に効率的かつ効果的に対処するのに役立つ、自動調査と応答 (AIR) 機能。</span><span class="sxs-lookup"><span data-stu-id="49e2e-117">Automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span> <span data-ttu-id="49e2e-118">アクション センターは、保留中の修復アクションの承認など、インシデントタスクおよびアラート タスクの "単一ウィンドウ" エクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="49e2e-118">The Action center is a "single pane of glass" experience for incident and alert tasks such as approving pending remediation actions.</span></span> |
| [<span data-ttu-id="49e2e-119">高度な追求</span><span class="sxs-lookup"><span data-stu-id="49e2e-119">Advanced hunting</span></span>](#advanced-hunting) | <span data-ttu-id="49e2e-120">ネットワーク内のイベントを積極的に検査し、脅威インジケーターとエンティティを見つけ出すクエリ ベースの脅威検出ツール。</span><span class="sxs-lookup"><span data-stu-id="49e2e-120">A query-based threat-hunting tool that lets you proactively inspect events in your network and locate threat indicators and entities.</span></span> <span data-ttu-id="49e2e-121">また、インシデントの調査と修復中に高度な検索を使用します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-121">You also use advanced hunting during the investigation and remediation of an incident.</span></span> |
||||

## <a name="prioritize-incidents"></a><span data-ttu-id="49e2e-122">インシデントの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="49e2e-122">Prioritize incidents</span></span>

<span data-ttu-id="49e2e-123">インシデント ポータル (security.microsoft.com)の&でインシデント>アラートからインシデント キューに[Microsoft 365 Defender取得します](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-123">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="49e2e-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-124">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例":::

<span data-ttu-id="49e2e-126">[ **最新のインシデントと** 通知] セクションには、過去 24 時間に受信したアラートとインシデントが作成された数のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-126">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="49e2e-127">インシデントの一覧を確認し、割り当てと調査の重要度を優先するには、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-127">To examine the list of incidents and prioritize their importance for assignment and investigation, you can:</span></span> 

- <span data-ttu-id="49e2e-128">カスタマイズ可能な列 ([列の **選択**] を選択) を構成して、インシデントまたは影響を受けたエンティティの異なる特性を可視化します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-128">Configure customizable columns (select **Choose columns**) to give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="49e2e-129">これにより、分析のためのインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-129">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

- <span data-ttu-id="49e2e-130">特定のシナリオまたは脅威に焦点を当てるには、フィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-130">Use filtering to focus on a specific scenario or threat.</span></span> <span data-ttu-id="49e2e-131">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-131">Applying filters on the incident queue can help determine which incidents require immediate attention.</span></span> 

<span data-ttu-id="49e2e-132">既定のインシデント キューから、[フィルター] を **選択して**[フィルター] ウィンドウを表示し、そこから特定のインシデント のセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-132">From the default incident queue, select **Filters** to see a **Filters** pane, from which you can specify a specific set of incidents.</span></span> <span data-ttu-id="49e2e-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-133">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="インシデント キューのフィルター ウィンドウの例":::

<span data-ttu-id="49e2e-135">詳細については、「インシデントの優先順位付 [け」を参照してください](incident-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-135">For more information, see [Prioritize incidents](incident-queue.md).</span></span>

## <a name="manage-incidents"></a><span data-ttu-id="49e2e-136">インシデントを管理する</span><span class="sxs-lookup"><span data-stu-id="49e2e-136">Manage incidents</span></span>

<span data-ttu-id="49e2e-137">インシデントを管理するには、[インシデントの **管理] ウィンドウ** でインシデントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-137">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="49e2e-138">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-138">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="インシデントの [インシデントの管理] ウィンドウの例":::

<span data-ttu-id="49e2e-140">このウィンドウは、次の [インシデントの **管理** ] リンクから表示できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-140">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="49e2e-141">インシデント キュー内のインシデントのプロパティ ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="49e2e-141">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="49e2e-142">**インシデントの** 概要ページ。</span><span class="sxs-lookup"><span data-stu-id="49e2e-142">**Summary** page of an incident.</span></span>

<span data-ttu-id="49e2e-143">インシデントを管理する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49e2e-143">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="49e2e-144">インシデント名を編集する</span><span class="sxs-lookup"><span data-stu-id="49e2e-144">Edit the incident name</span></span>

  <span data-ttu-id="49e2e-145">セキュリティ チームのベスト プラクティスに基づいて、utomatically に割り当てられた名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-145">Change the utomatically assigned name based on your security team best practices.</span></span>
  
- <span data-ttu-id="49e2e-146">インシデント タグを追加する</span><span class="sxs-lookup"><span data-stu-id="49e2e-146">Add incident tags</span></span>

  <span data-ttu-id="49e2e-147">セキュリティ チームがインシデントを分類するために使用するタグを追加します。これは後でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-147">Add tags that your security team uses to classify incidents, which can be later filtered.</span></span>
  
- <span data-ttu-id="49e2e-148">インシデントを自分に割り当てる</span><span class="sxs-lookup"><span data-stu-id="49e2e-148">Assign the incident to yourself</span></span>

  <span data-ttu-id="49e2e-149">ユーザー アカウント名に割り当て、後でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-149">Assign it to your user account name, which can be later filtered.</span></span>
  
- <span data-ttu-id="49e2e-150">インシデントの解決</span><span class="sxs-lookup"><span data-stu-id="49e2e-150">Resolve an incident</span></span>

  <span data-ttu-id="49e2e-151">修復後にインシデントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-151">Close the incident after it has been remediated.</span></span>
  
- <span data-ttu-id="49e2e-152">分類と決定を設定する</span><span class="sxs-lookup"><span data-stu-id="49e2e-152">Set its classification and determination</span></span>

  <span data-ttu-id="49e2e-153">インシデントを解決するときに脅威の種類を分類して選択します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-153">Classify and select the threat type when you resolve an incident.</span></span>
  
- <span data-ttu-id="49e2e-154">コメントを追加する</span><span class="sxs-lookup"><span data-stu-id="49e2e-154">Add comments</span></span>

  <span data-ttu-id="49e2e-155">セキュリティ チームのベスト プラクティスに基づいて、進行状況、メモ、その他の情報にコメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-155">Use comments for progress, notes, or other information based on your security team best practices.</span></span> <span data-ttu-id="49e2e-156">完全なコメント履歴は、インシデントの詳細 **ページの** [コメントと履歴] オプションから使用できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-156">The full comment history is available from the **Comments and history** option in the details page of an incident.</span></span>

<span data-ttu-id="49e2e-157">詳細については、「インシデントの管理 [」を参照してください](manage-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-157">For more information, see [Manage incidents](manage-incidents.md).</span></span>

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a><span data-ttu-id="49e2e-158">アクション センターで自動調査と対応を確認する</span><span class="sxs-lookup"><span data-stu-id="49e2e-158">Examine automated investigation and response with the Action center</span></span>

<span data-ttu-id="49e2e-159">組織の自動調査および対応機能の構成方法に応じて、修復アクションは自動的に実行するか、セキュリティ運用チームによる承認を受けた場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-159">Depending on how automated investigation and response capabilities are configured for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="49e2e-160">保留中か完了かに関係ないすべてのアクションは、デバイスの保留中および完了[](m365d-action-center.md)済み修復アクション、電子メール & コラボレーション コンテンツ、および ID を 1 つの場所に一覧表示するアクション センターに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-160">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md), which lists pending and completed remediation actions for your devices, email & collaboration content, and identities in one location.</span></span>

<span data-ttu-id="49e2e-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-161">Here's an example.</span></span>

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="統合アクション センター (Microsoft 365 Defender":::

<span data-ttu-id="49e2e-163">アクション センターから保留中のアクションを選択し、フライアウト ウィンドウで承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-163">From the Action center, you can select pending actions and then approve or reject them in the flyout pane.</span></span> <span data-ttu-id="49e2e-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-164">Here's an example.</span></span>

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="アクションを承認または拒否する":::

<span data-ttu-id="49e2e-166">保留中のアクションをできるだけ早く承認 (または拒否) して、自動化された調査を実行し、時間に合った方法で完了できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-166">Approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span>

<span data-ttu-id="49e2e-167">詳細については、「自動調査と [対応と](m365d-autoir.md) アクション センター」 [を参照してください](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-167">For more information, see [Automated investigation and response](m365d-autoir.md) and [Action center](m365d-action-center.md).</span></span>

## <a name="advanced-hunting"></a><span data-ttu-id="49e2e-168">高度な追及</span><span class="sxs-lookup"><span data-stu-id="49e2e-168">Advanced hunting</span></span>

> [!NOTE]
> <span data-ttu-id="49e2e-169">高度な狩猟シミュレーションについて説明する前に、次のビデオを見て、高度な狩猟の概念を理解し、ポータルで検索できる場所を確認し、セキュリティ操作でどのように役立つのかをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="49e2e-169">Before we walk you through the advanced hunting simulation, watch the following video to understand advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


<span data-ttu-id="49e2e-170">オプションのファイルレス [PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) 攻撃シミュレーションが、既に資格情報アクセス ステージに達した実際の攻撃である場合は、調査の任意の時点で高度な検索を使用して、生成されたアラートと影響を受けるエンティティから既に知っている情報を使用して、ネットワーク内のイベントやレコードを積極的に検索できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-170">If the [optional fileless PowerShell attack simulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) were a real attack that had already reached the credential access stage, you can use advanced hunting at any point in the investigation to proactively search through events and records in the network using what you already know from the generated alerts and affected entities.</span></span> <span data-ttu-id="49e2e-171">たとえば、過去 30 日間に外部 IP アドレスへの接続を照会できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-171">For instance, you can query for any connections to the external IP address in the past 30 days.</span></span>

### <a name="hunting-environment-requirements"></a><span data-ttu-id="49e2e-172">ハンティング環境の要件</span><span class="sxs-lookup"><span data-stu-id="49e2e-172">Hunting environment requirements</span></span>

<span data-ttu-id="49e2e-173">このシミュレーションには、内部メールボックスとデバイスが 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="49e2e-173">There's a single internal mailbox and device required for this simulation.</span></span> <span data-ttu-id="49e2e-174">テスト メッセージを送信するには、外部メール アカウントも必要です。</span><span class="sxs-lookup"><span data-stu-id="49e2e-174">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="49e2e-175">テナントが有効[になっているMicrosoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="49e2e-175">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="49e2e-176">電子メールの受信に使用するターゲット メールボックスを特定します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-176">Identify a target mailbox to be used for receiving email.</span></span>

   - <span data-ttu-id="49e2e-177">このメールボックスは、Microsoft Defender によって監視されている必要Office 365</span><span class="sxs-lookup"><span data-stu-id="49e2e-177">This mailbox must be monitored by Microsoft Defender for Office 365</span></span>

   - <span data-ttu-id="49e2e-178">要件 3 のデバイスは、このメールボックスにアクセスする必要があります</span><span class="sxs-lookup"><span data-stu-id="49e2e-178">The device from requirement 3 needs to access this mailbox</span></span>

3. <span data-ttu-id="49e2e-179">テスト デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-179">Configure a test device:</span></span>

    <span data-ttu-id="49e2e-180">a.</span><span class="sxs-lookup"><span data-stu-id="49e2e-180">a.</span></span> <span data-ttu-id="49e2e-181">バージョン 1903 以降Windows 10を使用してください。</span><span class="sxs-lookup"><span data-stu-id="49e2e-181">Make sure you are using Windows 10 version 1903 or later version.</span></span>

    <span data-ttu-id="49e2e-182">b.</span><span class="sxs-lookup"><span data-stu-id="49e2e-182">b.</span></span> <span data-ttu-id="49e2e-183">テスト デバイスをテスト ドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-183">Join the test device to the test domain.</span></span>

    <span data-ttu-id="49e2e-184">c.</span><span class="sxs-lookup"><span data-stu-id="49e2e-184">c.</span></span> <span data-ttu-id="49e2e-185">[[オンにする] をWindows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-185">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="49e2e-186">問題が発生した場合は、このトラブルシューティング Windows Defender ウイルス対策を[参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-186">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

    <span data-ttu-id="49e2e-187">d.</span><span class="sxs-lookup"><span data-stu-id="49e2e-187">d.</span></span> <span data-ttu-id="49e2e-188">[エンドポイント用 Microsoft Defender にオンボードします](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-188">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="49e2e-189">シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="49e2e-189">Run the simulation</span></span>

1. <span data-ttu-id="49e2e-190">外部メール アカウントから、ハンティング環境の要件セクションの手順 2 で識別されたメールボックスに電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-190">From an external email account, send an email to the mailbox identified in step 2 of the hunting environment requirements section.</span></span> <span data-ttu-id="49e2e-191">既存の電子メール フィルター ポリシーで許可される添付ファイルを含める。</span><span class="sxs-lookup"><span data-stu-id="49e2e-191">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="49e2e-192">このファイルは、悪意のあるファイルや実行可能ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="49e2e-192">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="49e2e-193">推奨されるファイルの種類は<i>、.pdf、.exe</i><i>場合</i>)、または Word ファイルなどのOfficeドキュメントの種類です。</span><span class="sxs-lookup"><span data-stu-id="49e2e-193">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or an Office document type such as a Word file.</span></span>

2. <span data-ttu-id="49e2e-194">[ハンティング環境の要件] セクションの手順 3 で定義されているデバイスから送信された電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-194">Open the sent email from the device configured as defined in step 3 of the hunting environment requirements section.</span></span> <span data-ttu-id="49e2e-195">添付ファイルを開くか、ファイルをデバイスに保存します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-195">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="49e2e-196">Go hunting</span><span class="sxs-lookup"><span data-stu-id="49e2e-196">Go hunting</span></span>

1. <span data-ttu-id="49e2e-197">ポータルを[開Microsoft 365 Defenderします](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="49e2e-197">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="49e2e-198">ナビゲーション ウィンドウで、[ハンティング と高度な **>を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49e2e-198">From the navigation pane, select **Hunting > Advanced hunting**.</span></span>

3. <span data-ttu-id="49e2e-199">電子メール イベントの収集から始まるクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-199">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="49e2e-200">[クエリ **の実行] >新規を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49e2e-200">Select **Query > New**.</span></span>

   1. <span data-ttu-id="49e2e-201">[高度 **な検索]** の **[メール** グループ] で **、[EmailEvents] をダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="49e2e-201">In the **Email** groups under **Advanced hunting**, double-click **EmailEvents**.</span></span> <span data-ttu-id="49e2e-202">これはクエリ ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-202">You should see this in the query window.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="49e2e-203">クエリの時間枠を過去 24 時間に変更します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-203">Change the time frame of the query to the last 24 hours.</span></span> <span data-ttu-id="49e2e-204">上記のシミュレーションを実行した際に送信したメールが過去 24 時間だったと仮定し、それ以外の場合は必要に応じて時間枠を変更します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-204">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame as needed.</span></span>

   1. <span data-ttu-id="49e2e-205">**[クエリの実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-205">Select **Run query**.</span></span> <span data-ttu-id="49e2e-206">パイロット環境によって結果が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49e2e-206">You may have differing results depending on your pilot environment.</span></span>

      > [!NOTE]
      > <span data-ttu-id="49e2e-207">データの取得を制限するオプションのフィルター処理については、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49e2e-207">See the next step for filtering options to limit data return.</span></span>

      ![高度な検索クエリの結果の例](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="49e2e-209">高度な検索では、クエリ結果が表形式のデータとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-209">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="49e2e-210">グラフなどの他の形式のデータを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-210">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="49e2e-211">結果を確認し、開いたメールを識別できる場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-211">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="49e2e-212">高度な検索でメッセージが表示されるには、最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49e2e-212">It may take up to two hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="49e2e-213">結果を絞り込むには、クエリにwhere 条件を追加して、SenderMailFromDomain として "yahoo.com" を持つメールのみを検索できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-213">To narrow down the results, you can add the **where** condition to your query to only look for emails that have "yahoo.com" as their SenderMailFromDomain.</span></span> <span data-ttu-id="49e2e-214">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-214">Here is an example.</span></span>

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="49e2e-215">クエリの結果の行をクリックして、レコードを検査できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-215">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![高度な検索結果が選択されている場合に開く検査レコード側パネルの例](../../media/mtp/fig21.png)

4. <span data-ttu-id="49e2e-217">メールが表示されるのを確認したので、添付ファイルのフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-217">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="49e2e-218">環境内の添付ファイルを含むすべてのメールに焦点を当てる。</span><span class="sxs-lookup"><span data-stu-id="49e2e-218">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="49e2e-219">このシミュレーションでは、環境から送信されるメールではなく、受信メールに焦点を当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="49e2e-219">For this simulation, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="49e2e-220">追加したフィルターを削除して、メッセージを見つけて "メッセージ" を追加|AttachmentCount **> 0** と **EmailDirection**  ==  **"Inbound""**</span><span class="sxs-lookup"><span data-stu-id="49e2e-220">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="49e2e-221">次のクエリは、すべての電子メール イベントに対する最初のクエリよりも短いリストを持つ結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-221">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="49e2e-222">次に、添付ファイルに関する情報 (ファイル名、ハッシュなど) を結果セットに含める。</span><span class="sxs-lookup"><span data-stu-id="49e2e-222">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="49e2e-223">これを行うには **、EmailAttachmentInfo テーブルに参加** します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-223">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="49e2e-224">参加に使用する一般的なフィールドは **、NetworkMessageId** と **RecipientObjectId です**。</span><span class="sxs-lookup"><span data-stu-id="49e2e-224">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="49e2e-225">次のクエリには、追加の行 "| **project-rename EmailTimestamp=Timestamp**" は、次の手順で追加するファイルアクションに関連するタイムスタンプとメールに関連したタイムスタンプを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-225">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="49e2e-226">次に **、EmailAttachmentInfo** テーブルの **SHA256** 値を使用して、そのハッシュの **DeviceFileEvents** (エンドポイントで発生したファイル アクション) を検索します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-226">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="49e2e-227">ここでの共通フィールドは、添付ファイルの SHA256 ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="49e2e-227">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="49e2e-228">結果の表には、エンドポイント (Microsoft Defender for Endpoint) の詳細 (デバイス名、実行されたアクション (この場合は FileCreated イベントのみを含むフィルター処理)、ファイルが格納された場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-228">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="49e2e-229">プロセスに関連付けられたアカウント名も含まれます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-229">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="49e2e-230">これで、ユーザーが添付ファイルを開いた、または保存した受信メールを識別するクエリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="49e2e-230">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="49e2e-231">このクエリを絞り込み、特定の送信者ドメイン、ファイル サイズ、ファイルの種類などについてフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-231">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="49e2e-232">関数は、有病率、署名者、発行者情報などのファイルに関するより多くの TI データを取得できる、特別な種類の結合です。ファイルの詳細を取得するには **、FileProfile() 関数エンリッチメントを** 使用します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-232">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="49e2e-233">検出を作成する</span><span class="sxs-lookup"><span data-stu-id="49e2e-233">Create a detection</span></span>

<span data-ttu-id="49e2e-234">将来発生した場合に通知を受け取る情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-234">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="49e2e-235">カスタム検出では、設定した頻度に従ってクエリが実行され、クエリの結果によって、選択した影響を受け取ったアセットに基づいてセキュリティアラートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-235">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="49e2e-236">これらのアラートはインシデントに関連付け、製品の 1 つによって生成される他のセキュリティ アラートとしてトリアージできます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-236">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="49e2e-237">クエリ ページで、Go ハンティング手順の手順 7 で追加された行 7 と 8 を削除し、[検出ルールの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="49e2e-237">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![高度な検索ページで [検出ルールの作成] をクリックできる場所の例](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="49e2e-239">[検出ルール **の作成] を** クリックし、クエリに構文エラーがある場合、検出ルールは保存されません。</span><span class="sxs-lookup"><span data-stu-id="49e2e-239">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="49e2e-240">クエリをダブルクリックして、エラーがないか確認します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-240">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="49e2e-241">必要なフィールドに、セキュリティ チームがアラートを理解できる情報、アラートが生成された理由、および必要なアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-241">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![アラートの詳細を定義できる検出ルールの作成ページの例](../../media/mtp/fig23.png)

   <span data-ttu-id="49e2e-243">この検出ルールアラートに関する情報に基づいた決定を次のユーザーに提供するために、フィールドに明確な情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="49e2e-243">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="49e2e-244">このアラートで影響を受け取るエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-244">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="49e2e-245">この場合、[デバイスとメールボックス **] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="49e2e-245">In this case, select **Device** and **Mailbox**.</span></span>

   ![影響を受け取ったエンティティのパラメーターを選択できる検出ルールの作成ページの例](../../media/mtp/fig24.png)

4. <span data-ttu-id="49e2e-247">アラートがトリガーされた場合に実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-247">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="49e2e-248">この場合、ウイルス対策スキャンを実行しますが、他の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-248">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![脅威への対処に役立つアラートがトリガーされた場合にウイルス対策スキャンを実行できる検出ルールの作成ページの例](../../media/mtp/fig25.png)

5. <span data-ttu-id="49e2e-250">アラート ルールのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-250">Select the scope for the alert rule.</span></span> <span data-ttu-id="49e2e-251">このクエリにはデバイスが含まれるので、デバイス グループは Microsoft Defender for Endpoint コンテキストに従って、このカスタム検出に関連します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-251">Since this query involves devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="49e2e-252">影響を受け取ったエンティティとしてデバイスを含めないカスタム検出を作成する場合、スコープは適用されません。</span><span class="sxs-lookup"><span data-stu-id="49e2e-252">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![アラート ルールのスコープを設定できる検出ルールの作成ページの例は、表示される結果に対する期待値を管理します。](../../media/mtp/fig26.png)

   <span data-ttu-id="49e2e-254">このパイロットの場合は、このルールを実稼働環境のテスト デバイスのサブセットに制限できます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-254">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="49e2e-255">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-255">Select **Create**.</span></span> <span data-ttu-id="49e2e-256">次に、ナビゲーション **パネルから [カスタム** 検出ルール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-256">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![メニューの [カスタム検出ルール] オプションの例](../../media/mtp/fig27a.png)

   ![ルールと実行の詳細を表示する検出ルール ページの例](../../media/mtp/fig27b.png)

   <span data-ttu-id="49e2e-259">このページから検出ルールを選択すると、詳細ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="49e2e-259">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![ルールの実行の状態、トリガーされたアラートとアクション、検出の編集などがある電子メールの添付ファイル ページの例](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a><span data-ttu-id="49e2e-261">高度な狩猟に関する専門家のトレーニング</span><span class="sxs-lookup"><span data-stu-id="49e2e-261">Expert training on advanced hunting</span></span>

<span data-ttu-id="49e2e-262">**敵を追跡する方法は** 、新しいセキュリティ アナリストや、新しい脅威ハンター向け Web キャスト シリーズです。</span><span class="sxs-lookup"><span data-stu-id="49e2e-262">**Tracking the adversary** is a webcast series for new security analysts and seasoned threat hunters.</span></span> <span data-ttu-id="49e2e-263">高度な検索の基本を説明し、独自の高度なクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="49e2e-263">It guides you through the basics of advanced hunting all the way to creating your own sophisticated queries.</span></span> 

<span data-ttu-id="49e2e-264">詳細については [、「高度な狩猟に関する専門家のトレーニングを受け取る」](advanced-hunting-expert-training.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49e2e-264">See [Get expert training on advanced hunting](advanced-hunting-expert-training.md) to get started.</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="49e2e-265">必要なナビゲーション</span><span class="sxs-lookup"><span data-stu-id="49e2e-265">Navigation you may need</span></span>

[<span data-ttu-id="49e2e-266">評価環境Microsoft 365 Defender作成する</span><span class="sxs-lookup"><span data-stu-id="49e2e-266">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
