---
title: 自動化された調査と応答 (AIR) の概要
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
ms.collection: M365-security-compliance
description: 自動化された調査と応答機能の概要を Office 365 Advanced Threat Protection プラン2でご覧ください。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: c977aa3f57c981cdc29037ca6f9f7803b7accd03
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46601899"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a><span data-ttu-id="0a1a4-103">Microsoft 365 の自動調査と応答 (AIR) の概要</span><span class="sxs-lookup"><span data-stu-id="0a1a4-103">An overview of Automated investigation and response (AIR) in Microsoft 365</span></span>

<span data-ttu-id="0a1a4-104">セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-104">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="0a1a4-105">場合によっては、セキュリティ運用チームが、トリガーされた通知の量に圧倒されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-105">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="0a1a4-106">自動化された調査と応答 (AIR) 機能が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-106">Automated investigation and response (AIR) capabilities can help.</span></span> <span data-ttu-id="0a1a4-107">AIR により、セキュリティ運用チームがより効率的かつ効果的に運用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-107">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="0a1a4-108">空気機能には、今日の既知の脅威への対応として、自動化された調査プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-108">AIR capabilities include automated investigation processes in response to well known threats that exist today.</span></span> <span data-ttu-id="0a1a4-109">適切な修復処置で承認を受けることができ、セキュリティ運用チームが検出された脅威に対応できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-109">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="0a1a4-110">この記事では、エアの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-110">This article provides an overview of AIR.</span></span> <span data-ttu-id="0a1a4-111">AIR の使用を開始する準備ができたら、「[脅威に自動的に調査して応答する](office-365-air.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-111">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="0a1a4-112">高レベル</span><span class="sxs-lookup"><span data-stu-id="0a1a4-112">At a high level</span></span>

<span data-ttu-id="0a1a4-113">アラートがトリガーされると、セキュリティのプレイブックが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-113">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="0a1a4-114">状況に応じて、自動化された[調査プロセス](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)を開始できます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-114">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="0a1a4-115">自動化された調査の最中および実行後に、[修復アクション](air-remediation-actions.md)をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-115">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="0a1a4-116">Office 365 Advanced Threat Protection では、アクションは自動的には行われません。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-116">No actions are taken automatically in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="0a1a4-117">セキュリティ運用チームは、各修復アクションをレビューし、[承認または拒否](air-review-approve-pending-completed-actions.md)します。この操作が完了すると、各調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-117">Your security operations team reviews, and then [approves or rejects each remediation action](air-review-approve-pending-completed-actions.md), and when this is done, each investigation completes.</span></span> <span data-ttu-id="0a1a4-118">これらのすべてのアクティビティは、セキュリティ & コンプライアンスセンターで追跡および表示できます (「[調査の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-118">All of these activities are tracked and viewable in the Security & Compliance Center (see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="0a1a4-119">次のセクションでは、警告、セキュリティプレイブック、および動作の例の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-119">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="0a1a4-120">アラート</span><span class="sxs-lookup"><span data-stu-id="0a1a4-120">Alerts</span></span>

<span data-ttu-id="0a1a4-121">[アラート](../../compliance/alert-policies.md#viewing-alerts)は、セキュリティ運用チームのインシデント対応ワークフローに対するトリガーを表します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-121">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="0a1a4-122">すべての脅威に対処しつつ、優先的に調査するアラートのセットを適切に特定することは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-122">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="0a1a4-123">アラートへの調査を手動で実行する場合、セキュリティ運用チームは脅威からのリスクでエンティティ (コンテンツ、デバイス、ユーザーなど) をハントして関連付けなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-123">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="0a1a4-124">このようなタスクやワークフローは、非常に時間がかかる場合があり、複数のツールやシステムが関係しています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-124">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="0a1a4-125">AIR では、セキュリティイベントの調査と応答が自動化されています。キーセキュリティと脅威管理の警告を使用すると、セキュリティ応答プレイブックが自動的にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-125">With AIR, investigation and response for security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="0a1a4-126">現時点では、次の種類のアラートポリシーから生成されたアラートは、エアに対して自動的に調査されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-126">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="0a1a4-127">悪意のある可能性がある URL のクリックが検出されました</span><span class="sxs-lookup"><span data-stu-id="0a1a4-127">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="0a1a4-128">ユーザーによりメールがフィッシングとして報告されました\*</span><span class="sxs-lookup"><span data-stu-id="0a1a4-128">Email reported by user as phish\*</span></span>
- <span data-ttu-id="0a1a4-129">マルウェアを含んだメール メッセージが配信後に削除されました\*</span><span class="sxs-lookup"><span data-stu-id="0a1a4-129">Email messages containing malware removed after delivery\*</span></span>
- <span data-ttu-id="0a1a4-130">フィッシング URL を含んだメール メッセージが配信後に削除されました\*</span><span class="sxs-lookup"><span data-stu-id="0a1a4-130">Email messages containing phish URLs removed after delivery\*</span></span>
- <span data-ttu-id="0a1a4-131">不審なメール送信パターンが検出されました#</span><span class="sxs-lookup"><span data-stu-id="0a1a4-131">Suspicious email sending patterns detected#</span></span>
- <span data-ttu-id="0a1a4-132">ユーザーに対してメールの送信が制限されました#</span><span class="sxs-lookup"><span data-stu-id="0a1a4-132">User restricted from sending email#</span></span>

> [!NOTE]
> <span data-ttu-id="0a1a4-133">アスタリスク (*) が付いているアラートには、セキュリティ/コンプライアンス センター内の各アラート ポリシーで重要度*情報\*が割り当てられ、メール通知が無効に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-133">The alerts marked with an asterisk (\*) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="0a1a4-134">メール通知は、[アラート ポリシーの構成](../../compliance/alert-policies.md#alert-policy-settings)で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-134">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="0a1a4-135">ハッシュ (#) が付いているアラートは、パブリック プレビュー プレイブックに関連付けられている、一般公開のアラートです。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-135">Alerts marked with a hash (#) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="0a1a4-136">アラートを表示するには、セキュリティ/コンプライアンス センターで、[**アラート**]  >  [**アラートの表示**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-136">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="0a1a4-137">詳細情報を表示するアラートを選択し、通知を選択して詳細を表示します。次に、[**調査を表示**] リンクを使用して当該[調査](air-view-investigation-results.md#investigation-graph)に移動します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-137">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="0a1a4-138">情報通知は、既定では通知ビューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-138">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="0a1a4-139">それらを表示するには、通知フィルターを変更して情報通知を含めます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-139">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="0a1a4-140">アラート管理システム、サービス管理システム、またはセキュリティ情報およびイベント管理 (SIEM) システムを使用してセキュリティ警告を管理する組織では、電子メール通知または[Office 365 Management ACTIVITY API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用して、そのシステムに通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-140">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="0a1a4-141">メールまたは API 経由の調査アラート通知には、セキュリティ/コンプライアンス センターでアラートにアクセスするためのリンクが含まれているので、割り当てられているセキュリティ管理者は簡単に調査に移動できます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-141">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![調査にリンクされるアラート](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="0a1a4-143">セキュリティ プレイブック</span><span class="sxs-lookup"><span data-stu-id="0a1a4-143">Security playbooks</span></span>

<span data-ttu-id="0a1a4-144">セキュリティプレイブックは、Office Advanced Threat Protection および Microsoft Threat Protection の自動化の中核となるバックエンドポリシーです。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-144">Security playbooks are back-end policies that are at the heart of automation in Office Advanced Threat Protection and Microsoft Threat Protection.</span></span> <span data-ttu-id="0a1a4-145">AIR で提供されるセキュリティプレイブックは、現実の一般的なセキュリティシナリオに基づいており、セキュリティ運用チームからのフィードバックに基づいて開発されています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-145">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from Security Operations teams.</span></span> <span data-ttu-id="0a1a4-146">組織内で特定のアラートがトリガーされると、セキュリティによるプレイブックが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-146">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="0a1a4-147">アラートがトリガーされると、関連付けられたプレイブックは自動調査および応答 (AIR) システムによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-147">Once the alert triggers, the associated playbook is run by the Automated Investigation and Response (AIR) system.</span></span> <span data-ttu-id="0a1a4-148">この調査では、特定のアラートのプレイブックに基づいてアラートを分析し、関連するすべてのメタデータ (電子メールメッセージ、ユーザー、件名、送信者などを含む) を確認します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-148">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="0a1a4-149">調査の調査結果に基づいて、組織のセキュリティチームが脅威を制御し、軽減するために実行できる一連の操作を航空で推奨します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-149">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="0a1a4-150">空気で得られるセキュリティプレイブックは、組織が現在直面している電子メールの最も頻繁な脅威に取り組むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-150">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="0a1a4-151">これらは、Microsoft とお客様の資産を保護する手助けをしているユーザーを含む、セキュリティ運用チームとインシデント対応チームからの入力に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-151">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers' assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="0a1a4-152">セキュリティ プレイブックは段階的に展開されています</span><span class="sxs-lookup"><span data-stu-id="0a1a4-152">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="0a1a4-153">セキュリティ プレイブックは AIR の一環として段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-153">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="0a1a4-154">フェーズ 1 は現在一般公開されており、セキュリティ管理者が確認して承認できる処理に関する推奨事項を提供する、いくつかのプレイブックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-154">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>

- <span data-ttu-id="0a1a4-155">ユーザーから報告されたフィッシング メッセージ</span><span class="sxs-lookup"><span data-stu-id="0a1a4-155">User-reported phish message</span></span>
- <span data-ttu-id="0a1a4-156">URL クリック判定の変更</span><span class="sxs-lookup"><span data-stu-id="0a1a4-156">URL click verdict change</span></span>
- <span data-ttu-id="0a1a4-157">配信後のマルウェア検出 (マルウェア ZAP)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-157">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="0a1a4-158">配信後のフィッシング検出 ZAP (フィッシング ZAP)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-158">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="0a1a4-159">フェーズ1には、管理者によってトリガーされた電子メール調査のサポート ([脅威エクスプローラー](threat-explorer.md)を使用) も含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-159">Phase 1 also includes support for administrator triggered e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="0a1a4-160">現在進行中のフェーズ 2 では、次のプレイブックが **パブリック プレビュー**中です。処理に関する推奨事項が提供され、セキュリティ管理者が問題を調査するのに役立っています。　</span><span class="sxs-lookup"><span data-stu-id="0a1a4-160">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions and aiding security administrators in investigating issues:</span></span>

- <span data-ttu-id="0a1a4-161">ユーザーから報告された侵害の発生 (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-161">User reported as compromised (public preview)</span></span>

<span data-ttu-id="0a1a4-162">追加のプレイブックは、出来上がり次第公開されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-162">Further playbooks will be released as they are completed.</span></span> <span data-ttu-id="0a1a4-163">[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) にアクセスすると、準備中および近日公開予定のプレイブックを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-163">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="0a1a4-164">プレイブックには調査と推奨事項が含まれます</span><span class="sxs-lookup"><span data-stu-id="0a1a4-164">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="0a1a4-165">AIR では、各セキュリティ プレイブックに含まれるものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-165">In AIR, each security playbook includes:</span></span> 

- <span data-ttu-id="0a1a4-166">電子メールのエンティティ (ファイル、Url、受信者、IP アドレスなど) のルート調査</span><span class="sxs-lookup"><span data-stu-id="0a1a4-166">a root investigation of an email's entities (files, URLs, recipients, IP addresses, etc.),</span></span>
- <span data-ttu-id="0a1a4-167">組織で受信した類似メールをさらに探す</span><span class="sxs-lookup"><span data-stu-id="0a1a4-167">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="0a1a4-168">他の潜在的な脅威を特定し、相関関係を特定するための手順</span><span class="sxs-lookup"><span data-stu-id="0a1a4-168">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="0a1a4-169">脅威に関する推奨修復処理</span><span class="sxs-lookup"><span data-stu-id="0a1a4-169">recommended threat remediation actions.</span></span>

<span data-ttu-id="0a1a4-170">各高度な手順には、さまざまな手順が実行されており、脅威への深く、詳細で完全な応答が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-170">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="0a1a4-171">例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動</span><span class="sxs-lookup"><span data-stu-id="0a1a4-171">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="0a1a4-172">組織内のユーザーが、フィッシング詐欺であると思われる電子メールを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-172">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="0a1a4-173">このようなメッセージを報告するようにトレーニングされたユーザーは、[レポートメッセージアドイン](enable-the-report-message-add-in.md)を使用して、分析のために Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-173">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="0a1a4-174">送信は、システムにも送信さ**れ、[送信] ビューの**エクスプローラーに表示されます (以前はユーザーによって**報告**されたビューと呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-174">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="0a1a4-175">さらに、ユーザーによって報告されたメッセージがシステムベースの情報通知をトリガーするようになります。これにより、調査のプレイブックが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-175">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="0a1a4-176">ルート調査フィーズでは、メールのさまざまな側面が評価されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-176">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="0a1a4-177">これらには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-177">These include:</span></span>

- <span data-ttu-id="0a1a4-178">可能性のある脅威の種類の特定</span><span class="sxs-lookup"><span data-stu-id="0a1a4-178">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="0a1a4-179">誰が送信したか</span><span class="sxs-lookup"><span data-stu-id="0a1a4-179">Who sent it;</span></span>
- <span data-ttu-id="0a1a4-180">メールはどこから送信されたか (送信元のインフラストラクチャ)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-180">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="0a1a4-181">メールの他のインスタンスは、配信されたのか、それともブロックされたのか</span><span class="sxs-lookup"><span data-stu-id="0a1a4-181">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="0a1a4-182">Microsoft のアナリストによる評価</span><span class="sxs-lookup"><span data-stu-id="0a1a4-182">An assessment from our analysts;</span></span>
- <span data-ttu-id="0a1a4-183">メールが既知のキャンペーンと関連するものかどうか</span><span class="sxs-lookup"><span data-stu-id="0a1a4-183">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="0a1a4-184">その他</span><span class="sxs-lookup"><span data-stu-id="0a1a4-184">and more.</span></span>

<span data-ttu-id="0a1a4-185">ルート調査が完了すると、元のメールとそれに関連付けられているエンティティに対する推奨処理の一覧がプレイブックにより提供されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-185">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="0a1a4-186">次に、脅威の調査と捜索のための手順がいくつか実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-186">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="0a1a4-187">同様の電子メールメッセージは、電子メールクラスター検索によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-187">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="0a1a4-188">シグナルが [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) などの他のプラットフォームと共有されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-188">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="0a1a4-189">不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-189">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="0a1a4-190">チェックは、Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) および Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) に対して実行され、ユーザーによって報告された他の類似メッセージがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-190">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="0a1a4-191">ユーザーに対する侵害があったかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-191">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="0a1a4-192">このチェックは、Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)、および[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用して、関連するすべてのユーザーアクティビティの異常を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-192">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="0a1a4-193">捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-193">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="0a1a4-194">修復は、プレイブックの最後のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-194">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="0a1a4-195">このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-195">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="0a1a4-196">例: セキュリティ管理者が脅威エクスプローラーから調査を開始する</span><span class="sxs-lookup"><span data-stu-id="0a1a4-196">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="0a1a4-197">アラートによりトリガーされる自動調査に加え、組織のセキュリティ オペレーション チームは[脅威エクスプローラー](threat-explorer.md)内のビューから自動調査をトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-197">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="0a1a4-198">たとえば、脅威エクスプローラーの**マルウェア**表示を使用しているとします。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-198">For example, suppose that you are using the **Malware** view in Threat Explorer.</span></span> <span data-ttu-id="0a1a4-199">グラフの下にあるタブを使用して、[**電子メール**] タブを選択します。リストで1つ以上のアイテムを選択すると、[ **+ Actions** ] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-199">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![選択されたメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="0a1a4-201">[ **Actions** ] メニューを使用して、**トリガー調査**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-201">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選択されたメッセージの [アクション] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="0a1a4-203">アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a1a4-203">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a1a4-204">次の手順</span><span class="sxs-lookup"><span data-stu-id="0a1a4-204">Next steps</span></span>

- [<span data-ttu-id="0a1a4-205">空気の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="0a1a4-205">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="0a1a4-206">Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する</span><span class="sxs-lookup"><span data-stu-id="0a1a4-206">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
