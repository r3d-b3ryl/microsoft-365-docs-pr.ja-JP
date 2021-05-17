---
title: Microsoft Defender での自動調査と対応の仕組みOffice 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動インシデント対応、調査、修復、脅威保護
ms.date: 01/29/2021
description: Microsoft Defender で自動調査と応答機能がどのように機能Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8d33804e8c1405093843709e06250beb7f10512
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269638"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c432a-104">Microsoft Defender での自動調査と対応の仕組みOffice 365</span><span class="sxs-lookup"><span data-stu-id="c432a-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c432a-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c432a-105">**Applies to**</span></span>
- [<span data-ttu-id="c432a-106">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="c432a-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c432a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c432a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c432a-108">セキュリティアラートがトリガーされると、セキュリティ運用チームがこれらのアラートを確認し、組織を保護するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c432a-108">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="c432a-109">場合によっては、セキュリティ運用チームがトリガーされるアラートの量に圧倒される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c432a-109">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="c432a-110">Microsoft Defender の自動調査と応答 (AIR) 機能は、Office 365役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c432a-110">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="c432a-111">AIR を使用すると、セキュリティ運用チームは、より効率的かつ効果的に運用できます。</span><span class="sxs-lookup"><span data-stu-id="c432a-111">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="c432a-112">AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c432a-112">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="c432a-113">適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に対応できます。</span><span class="sxs-lookup"><span data-stu-id="c432a-113">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="c432a-114">この記事では、いくつかの例を通して AIR がどのように動作するのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c432a-114">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="c432a-115">AIR の使用を開始する準備ができたら、「脅威を自動的に調査 [して対応する」を参照してください](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="c432a-115">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="c432a-116">例 1: ユーザーが報告したフィッシング メッセージが調査プレイブックを起動する</span><span class="sxs-lookup"><span data-stu-id="c432a-116">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="c432a-117">例 2: セキュリティ管理者が脅威エクスプローラーから調査をトリガーする</span><span class="sxs-lookup"><span data-stu-id="c432a-117">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="c432a-118">例 3: セキュリティ運用チームは、セキュリティ管理アクティビティ API を使用して AIR と SIEM を統合Office 365します。</span><span class="sxs-lookup"><span data-stu-id="c432a-118">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="c432a-119">例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動</span><span class="sxs-lookup"><span data-stu-id="c432a-119">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="c432a-120">組織内のユーザーがフィッシング詐欺の試みと思うメールを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="c432a-120">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="c432a-121">このようなメッセージを報告するトレーニングを受けたユーザーは[](enable-the-report-message-add-in.md)、レポート メッセージ アドインまたは[](enable-the-report-phish-add-in.md)レポート フィッシング アドインを使用して、分析のために Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="c432a-121">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="c432a-122">申請はシステムにも送信され、[申請] ビュー (以前はユーザーレポート ビューと呼ばば) の **エクスプローラーに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-122">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="c432a-123">さらに、ユーザーが報告したメッセージによってシステムベースの情報アラートがトリガーされ、調査プレイブックが自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-123">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="c432a-124">ルート調査フィーズでは、メールのさまざまな側面が評価されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-124">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="c432a-125">これらの側面は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c432a-125">These aspects include:</span></span>

- <span data-ttu-id="c432a-126">可能性のある脅威の種類の特定</span><span class="sxs-lookup"><span data-stu-id="c432a-126">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="c432a-127">誰が送信したか</span><span class="sxs-lookup"><span data-stu-id="c432a-127">Who sent it;</span></span>
- <span data-ttu-id="c432a-128">メールはどこから送信されたか (送信元のインフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="c432a-128">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="c432a-129">メールの他のインスタンスは、配信されたのか、それともブロックされたのか</span><span class="sxs-lookup"><span data-stu-id="c432a-129">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="c432a-130">Microsoft のアナリストによる評価</span><span class="sxs-lookup"><span data-stu-id="c432a-130">An assessment from our analysts;</span></span>
- <span data-ttu-id="c432a-131">メールが既知のキャンペーンと関連するものかどうか</span><span class="sxs-lookup"><span data-stu-id="c432a-131">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="c432a-132">その他</span><span class="sxs-lookup"><span data-stu-id="c432a-132">and more.</span></span>

<span data-ttu-id="c432a-133">ルート調査が完了すると、元のメールとそれに関連付けられているエンティティに対する推奨処理の一覧がプレイブックにより提供されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-133">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>

<span data-ttu-id="c432a-134">次に、脅威の調査と捜索のための手順がいくつか実行されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-134">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="c432a-135">同様の電子メール メッセージは、電子メール クラスター検索を介して識別されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-135">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="c432a-136">信号は、Microsoft Defender for Endpoint などの [他のプラットフォームと共有されます](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="c432a-136">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="c432a-137">不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-137">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="c432a-138">ユーザーによって報告される他の同様のメッセージExchange Online Protection ([EOP](exchange-online-protection-overview.md)) と ([Microsoft Defender for Office 365](defender-for-office-365.md)) の間でチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="c432a-138">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](defender-for-office-365.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="c432a-139">ユーザーに対する侵害があったかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c432a-139">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="c432a-140">このチェックでは、関連するユーザー アクティビティの異常をOffice 365、Microsoft Cloud App Security、Azure Active Directory[](/azure/active-directory)の信号を活用します。 [](/cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="c432a-140">This check leverages signals across Office 365, [Microsoft Cloud App Security](/cloud-app-security), and [Azure Active Directory](/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="c432a-141">捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c432a-141">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>

<span data-ttu-id="c432a-142">修復は、プレイブックの最後のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="c432a-142">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="c432a-143">このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-143">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span>

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="c432a-144">例: セキュリティ管理者が脅威エクスプローラーから調査を開始する</span><span class="sxs-lookup"><span data-stu-id="c432a-144">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="c432a-145">アラートによってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは、脅威エクスプローラーのビューから自動調査 [をトリガーできます](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="c432a-145">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="c432a-146">また、この調査によってアラートが作成され、Microsoft Defender Incidents と外部 SIEM ツールは、この調査がトリガーされたと確認できます。</span><span class="sxs-lookup"><span data-stu-id="c432a-146">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span>

<span data-ttu-id="c432a-147">たとえば、エクスプローラーでマルウェア ビューを **使用すると** します。</span><span class="sxs-lookup"><span data-stu-id="c432a-147">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="c432a-148">グラフの下のタブを使用して、[メール] タブ **を選択** します。リストで 1 つ以上のアイテムを選択すると **、[+ アクション] ボタンが** アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="c432a-148">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span>

![選択したメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="c432a-150">[アクション] **メニューを** 使用して、[調査のトリガー **] を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="c432a-150">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選択したメッセージの [操作] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="c432a-152">アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c432a-152">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="c432a-153">例: セキュリティ運用チームは、セキュリティ管理アクティビティ API を使用して AIR と SIEM Office 365統合します。</span><span class="sxs-lookup"><span data-stu-id="c432a-153">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="c432a-154">Microsoft Defender for Office 365の AIR 機能[](air-view-investigation-results.md)には、&を監視および対処するためにセキュリティ運用チームが使用できる詳細に関するレポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c432a-154">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="c432a-155">ただし、AIR 機能を他のソリューションと統合できます。</span><span class="sxs-lookup"><span data-stu-id="c432a-155">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="c432a-156">たとえば、セキュリティ情報とイベント管理 (SIEM) システム、ケース管理システム、またはカスタム レポート ソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="c432a-156">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="c432a-157">これらの種類の統合は、管理アクティビティ API Office 365[使用して実行できます](/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="c432a-157">These kinds of integrations can be done by using the [Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="c432a-158">たとえば、最近、組織はセキュリティ運用チームが AIR によって既に処理されたユーザーが報告したフィッシングアラートを表示する方法をセットアップしました。</span><span class="sxs-lookup"><span data-stu-id="c432a-158">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="c432a-159">ソリューションは、関連するアラートを組織の SIEM サーバーとそのケース管理システムと統合します。</span><span class="sxs-lookup"><span data-stu-id="c432a-159">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="c432a-160">このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるよう、誤検知の数を大幅に削減します。</span><span class="sxs-lookup"><span data-stu-id="c432a-160">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="c432a-161">このカスタム ソリューションの詳細については、「Tech Community blog: Improve the EFFECTIVENESS of your [SOC with Microsoft Defender for Office 365」および「O365 Management API」](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c432a-161">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c432a-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="c432a-162">Next steps</span></span>

- [<span data-ttu-id="c432a-163">AIR の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c432a-163">Get started using AIR</span></span>](office-365-air.md)
- [<span data-ttu-id="c432a-164">保留中または完了した修復アクションの表示</span><span class="sxs-lookup"><span data-stu-id="c432a-164">View pending or completed remediation actions</span></span>](air-review-approve-pending-completed-actions.md)