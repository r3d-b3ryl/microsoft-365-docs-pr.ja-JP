---
title: Microsoft Defender for Office 365 での自動調査と対応のしくみ
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
keywords: 自動インシデント対応, 調査, 修復, 脅威の保護
ms.date: 11/05/2020
description: Microsoft Defender for Office 365 での自動調査と対応の機能について説明します。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 5ca9ea941d073c7b199678631a9063cfbeae8907
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864902"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6ce98-104">Microsoft Defender for Office 365 での自動調査と対応のしくみ</span><span class="sxs-lookup"><span data-stu-id="6ce98-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6ce98-105">セキュリティの警告がトリガーされると、セキュリティ運用チームがそれらのアラートを確認し、組織を保護するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ce98-105">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="6ce98-106">場合によっては、セキュリティ運用チームが、トリガーされるアラートの量に圧倒される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ce98-106">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="6ce98-107">Microsoft Defender for Office 365 の自動調査および対応 (AIR) 機能が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-107">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="6ce98-108">AIR を使用すると、セキュリティ運用チームが効率的かつ効果的に運用できます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-108">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="6ce98-109">AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-109">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="6ce98-110">適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に対応できます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-110">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="6ce98-111">この記事では、AIR がいくつかの例を通じてどのように機能するのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-111">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="6ce98-112">AIR の使用を開始する準備ができたら、「脅威を自動的に調査して対応する」 [を参照してください](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="6ce98-112">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="6ce98-113">例 1: ユーザーから報告されたフィッシング メッセージが調査プレイブックを起動する</span><span class="sxs-lookup"><span data-stu-id="6ce98-113">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="6ce98-114">例 2: セキュリティ管理者が脅威エクスプローラーから調査を開始する</span><span class="sxs-lookup"><span data-stu-id="6ce98-114">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="6ce98-115">例 3: セキュリティ運用チームは、Office 365 マネージメント アクティビティ API を使用して AIR を SIEM と統合します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-115">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="6ce98-116">例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動</span><span class="sxs-lookup"><span data-stu-id="6ce98-116">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="6ce98-117">組織内のユーザーがフィッシング詐欺と思うメールを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="6ce98-117">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="6ce98-118">このようなメッセージを報告するトレーニングを受けたユーザーは、レポート [メッセージ](enable-the-report-message-add-in.md) アドインまたは [Report Phishing](enable-the-report-phish-add-in.md) アドインを使用して、分析のために Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-118">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="6ce98-119">申請はシステムにも送信され、エクスプローラーの [ **提出** ] ビュー (以前はユーザーによって報告されたビューと呼ばばっていました) **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-119">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="6ce98-120">さらに、ユーザーから報告されたメッセージによってシステムベースの情報アラートがトリガーされ、調査プレイブックが自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-120">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="6ce98-121">ルート調査フィーズでは、メールのさまざまな側面が評価されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-121">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="6ce98-122">次のような側面があります。</span><span class="sxs-lookup"><span data-stu-id="6ce98-122">These aspects include:</span></span>

- <span data-ttu-id="6ce98-123">可能性のある脅威の種類の特定</span><span class="sxs-lookup"><span data-stu-id="6ce98-123">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="6ce98-124">誰が送信したか</span><span class="sxs-lookup"><span data-stu-id="6ce98-124">Who sent it;</span></span>
- <span data-ttu-id="6ce98-125">メールはどこから送信されたか (送信元のインフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="6ce98-125">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="6ce98-126">メールの他のインスタンスは、配信されたのか、それともブロックされたのか</span><span class="sxs-lookup"><span data-stu-id="6ce98-126">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="6ce98-127">Microsoft のアナリストによる評価</span><span class="sxs-lookup"><span data-stu-id="6ce98-127">An assessment from our analysts;</span></span>
- <span data-ttu-id="6ce98-128">メールが既知のキャンペーンと関連するものかどうか</span><span class="sxs-lookup"><span data-stu-id="6ce98-128">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="6ce98-129">その他</span><span class="sxs-lookup"><span data-stu-id="6ce98-129">and more.</span></span>

<span data-ttu-id="6ce98-130">ルート調査が完了すると、元のメールとそれに関連付けられているエンティティに対する推奨処理の一覧がプレイブックにより提供されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-130">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>

<span data-ttu-id="6ce98-131">次に、脅威の調査と捜索のための手順がいくつか実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-131">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="6ce98-132">同様の電子メール メッセージは、電子メール クラスター検索によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-132">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="6ce98-133">信号は、Microsoft Defender for Endpoint などの他 [のプラットフォームと共有されます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="6ce98-133">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="6ce98-134">不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-134">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="6ce98-135">チェックは、Exchange Online Protection ([EOP)](exchange-online-protection-overview.md)と ([Office 365](office-365-atp.md)の Microsoft Defender) を通して行われ、ユーザーによって報告された他の同様のメッセージが他にはないか確認します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-135">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="6ce98-136">ユーザーに対する侵害があったかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-136">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="6ce98-137">このチェックでは、Office 365、Microsoft Cloud [App Security、Azure](https://docs.microsoft.com/cloud-app-security) [Active Directory](https://docs.microsoft.com/azure/active-directory)のシグナルを活用して、関連するユーザー アクティビティの異常を関連付ける。</span><span class="sxs-lookup"><span data-stu-id="6ce98-137">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="6ce98-138">捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-138">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>

<span data-ttu-id="6ce98-139">修復は、プレイブックの最後のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="6ce98-139">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="6ce98-140">このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-140">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span>

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="6ce98-141">例: セキュリティ管理者が脅威エクスプローラーから調査を開始する</span><span class="sxs-lookup"><span data-stu-id="6ce98-141">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="6ce98-142">アラートによってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは、脅威エクスプローラーのビューから自動調査 [をトリガーできます](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="6ce98-142">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="6ce98-143">この調査ではアラートも作成され、Microsoft Defender インシデントと外部 SIEM ツールは、この調査がトリガーされたと確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-143">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span>

<span data-ttu-id="6ce98-144">たとえば、エクスプローラーの [マルウェア] ビュー **を** 使用するとします。</span><span class="sxs-lookup"><span data-stu-id="6ce98-144">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="6ce98-145">グラフの下のタブを使用して、[メール] タブ **を選択** します。リスト内の 1 つ以上のアイテムを選択すると、[+ **アクション] ボタン** がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-145">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span>

![選択されたメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="6ce98-147">[操作] **メニューを使用** して、[調査のトリガー] **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="6ce98-147">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選択したメッセージの [操作] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="6ce98-149">アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-149">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="6ce98-150">例: セキュリティ運用チームは、Office 365 マネージメント アクティビティ API を使用して AIR を SIEM と統合します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-150">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="6ce98-151">Office 365 向け Microsoft Defender の[](air-view-investigation-results.md)AIR 機能には、セキュリティ運用&チームが脅威の監視と対処に使用できる詳細なレポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-151">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="6ce98-152">ただし、AIR 機能を他のソリューションと統合できます。</span><span class="sxs-lookup"><span data-stu-id="6ce98-152">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="6ce98-153">たとえば、セキュリティ情報とイベント管理 (SIEM) システム、ケース管理システム、カスタム レポート ソリューションなどです。</span><span class="sxs-lookup"><span data-stu-id="6ce98-153">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="6ce98-154">これらの種類の統合は、365 管理アクティビティ API Office [使用して実行できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="6ce98-154">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="6ce98-155">たとえば最近、組織はセキュリティ運用チームが、AIR によって既に処理されているユーザーから報告されたフィッシングアラートを表示する方法をセットアップしました。</span><span class="sxs-lookup"><span data-stu-id="6ce98-155">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="6ce98-156">ソリューションは、関連するアラートを組織の SIEM サーバーとそのケース管理システムと統合します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-156">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="6ce98-157">このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるよう、誤検知の数を大幅に減らします。</span><span class="sxs-lookup"><span data-stu-id="6ce98-157">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="6ce98-158">このカスタム ソリューションの詳細については、Tech Community ブログを参照してください [。microsoft Defender for Office 365 および O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)を使用して SOC の有効性を向上させる。</span><span class="sxs-lookup"><span data-stu-id="6ce98-158">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ce98-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="6ce98-159">Next steps</span></span>

- [<span data-ttu-id="6ce98-160">AIR の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6ce98-160">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="6ce98-161">Microsoft 365 ロードマップにアクセスして、近日予定の予定とリリースを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ce98-161">Visit the Microsoft 365 Roadmap to see what's planned and releasing soon</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="6ce98-162">Microsoft 365 Defender の自動調査および対応機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ce98-162">Learn about automated investigation and response capabilities in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
