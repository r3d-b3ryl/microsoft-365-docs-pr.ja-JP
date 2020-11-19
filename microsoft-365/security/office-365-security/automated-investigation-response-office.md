---
title: Microsoft Defender for Office 365 での自動化された調査と応答の仕組み
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: インシデント対応、調査、修復、脅威保護の自動化
ms.date: 11/05/2020
description: Microsoft Defender for Office 365 での自動化された調査と応答機能の仕組みを参照してください。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b901585f0a25c51c377e974c56faffe560eab5f3
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357673"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d3e22-104">Microsoft Defender for Office 365 での自動化された調査と応答の仕組み</span><span class="sxs-lookup"><span data-stu-id="d3e22-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3e22-105">セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。</span><span class="sxs-lookup"><span data-stu-id="d3e22-105">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="d3e22-106">場合によっては、セキュリティ運用チームが、トリガーされた通知の量に圧倒されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d3e22-106">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="d3e22-107">Microsoft Defender for Office 365 の自動調査と応答 (AIR) 機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-107">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="d3e22-108">AIR により、セキュリティ運用チームがより効率的かつ効果的に運用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3e22-108">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="d3e22-109">空気機能には、今日の既知の脅威への対応として、自動化された調査プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-109">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="d3e22-110">適切な修復処置で承認を受けることができ、セキュリティ運用チームが検出された脅威に対応できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3e22-110">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="d3e22-111">この記事では、いくつかの例を使用した空気のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-111">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="d3e22-112">AIR の使用を開始する準備ができたら、「 [脅威に自動的に調査して応答する](office-365-air.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3e22-112">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="d3e22-113">例 1: ユーザーから報告されたフィッシングメッセージが、調査のプレイブックを起動する</span><span class="sxs-lookup"><span data-stu-id="d3e22-113">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="d3e22-114">例 2: セキュリティ管理者が脅威エクスプローラーから調査をトリガーする</span><span class="sxs-lookup"><span data-stu-id="d3e22-114">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="d3e22-115">例 3: セキュリティ運用チームが Office 365 Management Activity API を使用して、SIEM に航空を統合する</span><span class="sxs-lookup"><span data-stu-id="d3e22-115">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="d3e22-116">例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動</span><span class="sxs-lookup"><span data-stu-id="d3e22-116">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="d3e22-117">組織内のユーザーが、フィッシング詐欺であると思われる電子メールを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="d3e22-117">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="d3e22-118">このようなメッセージを報告するようにトレーニングされたユーザーは、 [レポートメッセージアドイン](enable-the-report-message-add-in.md) を使用して、分析のために Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-118">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="d3e22-119">送信は、システムにも送信さ **れ、[送信] ビューの** エクスプローラーに表示されます (以前はユーザーによって **報告** されたビューと呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="d3e22-119">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="d3e22-120">さらに、ユーザーによって報告されたメッセージがシステムベースの情報通知をトリガーするようになります。これにより、調査のプレイブックが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-120">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="d3e22-121">ルート調査フィーズでは、メールのさまざまな側面が評価されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-121">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="d3e22-122">次のような側面があります。</span><span class="sxs-lookup"><span data-stu-id="d3e22-122">These aspects include:</span></span>

- <span data-ttu-id="d3e22-123">可能性のある脅威の種類の特定</span><span class="sxs-lookup"><span data-stu-id="d3e22-123">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="d3e22-124">誰が送信したか</span><span class="sxs-lookup"><span data-stu-id="d3e22-124">Who sent it;</span></span>
- <span data-ttu-id="d3e22-125">メールはどこから送信されたか (送信元のインフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="d3e22-125">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="d3e22-126">メールの他のインスタンスは、配信されたのか、それともブロックされたのか</span><span class="sxs-lookup"><span data-stu-id="d3e22-126">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="d3e22-127">Microsoft のアナリストによる評価</span><span class="sxs-lookup"><span data-stu-id="d3e22-127">An assessment from our analysts;</span></span>
- <span data-ttu-id="d3e22-128">メールが既知のキャンペーンと関連するものかどうか</span><span class="sxs-lookup"><span data-stu-id="d3e22-128">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="d3e22-129">その他</span><span class="sxs-lookup"><span data-stu-id="d3e22-129">and more.</span></span>

<span data-ttu-id="d3e22-130">ルート調査が完了すると、元のメールとそれに関連付けられているエンティティに対する推奨処理の一覧がプレイブックにより提供されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-130">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="d3e22-131">次に、脅威の調査と捜索のための手順がいくつか実行されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-131">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="d3e22-132">同様の電子メールメッセージは、電子メールクラスター検索によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-132">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="d3e22-133">このシグナルは、 [エンドポイントの Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)など、他のプラットフォームと共有されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-133">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="d3e22-134">不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-134">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="d3e22-135">チェックは、Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) および ([Microsoft Defender for Office 365](office-365-atp.md)) で行われ、ユーザーによって報告された他の類似メッセージがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-135">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="d3e22-136">ユーザーに対する侵害があったかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-136">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="d3e22-137">このチェックは、Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)、および [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用して、関連するすべてのユーザーアクティビティの異常を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-137">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="d3e22-138">捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-138">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="d3e22-139">修復は、プレイブックの最後のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="d3e22-139">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="d3e22-140">このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-140">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="d3e22-141">例: セキュリティ管理者が脅威エクスプローラーから調査を開始する</span><span class="sxs-lookup"><span data-stu-id="d3e22-141">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="d3e22-142">通知によってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは [脅威エクスプローラー](threat-explorer.md)のビューから自動化された調査を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-142">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="d3e22-143">この調査では、Microsoft Defender インシデントおよび外部の SIEM ツールがこの調査がトリガーされたことを確認できるように、通知も作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-143">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span> 

<span data-ttu-id="d3e22-144">たとえば、エクスプローラーで **マルウェア** 表示を使用しているとします。</span><span class="sxs-lookup"><span data-stu-id="d3e22-144">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="d3e22-145">グラフの下にあるタブを使用して、[ **電子メール** ] タブを選択します。リストで1つ以上のアイテムを選択すると、[ **+ Actions** ] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="d3e22-145">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![選択されたメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="d3e22-147">[ **Actions** ] メニューを使用して、 **トリガー調査** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-147">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選択されたメッセージの [アクション] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="d3e22-149">アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-149">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="d3e22-150">例: セキュリティ運用チームは、Office 365 Management Activity API を使用して、SIEM とそのエアを統合します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-150">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="d3e22-151">Microsoft Defender for Office 365 の空気機能には、セキュリティ運用チームが脅威を監視および解決するために使用できる [詳細 & のレポート](air-view-investigation-results.md) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3e22-151">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="d3e22-152">ただし、他のソリューションには空気の機能を統合することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-152">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="d3e22-153">例としては、セキュリティ情報およびイベント管理 (SIEM) システム、ケース管理システム、カスタムレポートソリューションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="d3e22-153">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="d3e22-154">これらの種類の統合は、 [Office 365 Management ACTIVITY API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3e22-154">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="d3e22-155">たとえば、組織では、既に AIR によって処理されたユーザーレポートフィッシング通知をセキュリティ運用チームが表示する方法を設定しています。</span><span class="sxs-lookup"><span data-stu-id="d3e22-155">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="d3e22-156">これらのソリューションは、関連するアラートを組織の SIEM サーバーおよびそのケース管理システムと統合します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-156">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="d3e22-157">このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるように、誤検知の数を大幅に減らします。</span><span class="sxs-lookup"><span data-stu-id="d3e22-157">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="d3e22-158">このカスタムソリューションの詳細については、「Tech Community blog」を参照してください。 [Microsoft Defender For Office 365 および O365 管理 API を使用して SOC の効果を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="d3e22-158">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3e22-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="d3e22-159">Next steps</span></span>

- [<span data-ttu-id="d3e22-160">空気の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="d3e22-160">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="d3e22-161">Microsoft 365 ロードマップを参照して、計画およびリリースされたことを確認してください</span><span class="sxs-lookup"><span data-stu-id="d3e22-161">Visit the Microsoft 365 Roadmap to see what's planned and releasing soon</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="d3e22-162">Microsoft 365 Defender の自動調査および応答機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3e22-162">Learn about automated investigation and response capabilities in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
