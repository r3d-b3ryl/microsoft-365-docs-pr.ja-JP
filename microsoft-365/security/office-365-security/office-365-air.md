---
title: Office 365 での自動調査および対応 (AIR)
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
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
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の使用を開始します。
ms.custom: air
ms.openlocfilehash: 8871329d254057a0f9d6f10d3ae7acc10139832e
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710536"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="15c2d-104">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="15c2d-104">Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="15c2d-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) Plan 2 には、強力な自動化された調査と応答 (航空) 機能が含まれており、セキュリティ運用チームの時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="15c2d-106">アラートがトリガーされると、その通知をレビュー、優先度設定、応答するためのセキュリティ運用チームが必要になります。</span><span class="sxs-lookup"><span data-stu-id="15c2d-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="15c2d-107">受信通知の音量を維持することは非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="15c2d-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="15c2d-108">これを自動化することによって役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="15c2d-108">Automating some of this can help.</span></span> <span data-ttu-id="15c2d-109">AIR を使用すると、セキュリティ運用チームは、トリガーされた通知を失うことなく、優先度の高いタスクに集中できます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="15c2d-110">この記事では、空気の[全体的な流れ](#the-overall-flow-of-air)、空気を[取得する方法](#how-to-get-air)、および航空機能を構成または使用するために[必要なアクセス許可](#required-permissions-to-use-air-capabilities)について説明します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-110">This article describes the [overall flow](#the-overall-flow-of-air) of AIR, [how to get AIR](#how-to-get-air), and the [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="15c2d-111">AIR の全体的な流れ</span><span class="sxs-lookup"><span data-stu-id="15c2d-111">The overall flow of AIR</span></span>

<span data-ttu-id="15c2d-112">高いレベルでは、アラートがトリガーされ、セキュリティによるプレイの開始と自動化された調査が行われて、結果と推奨事項が得られます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-112">At a high level, an alert is triggered, and a security playbook starts and automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="15c2d-113">エアフローの全体的な流れについては、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15c2d-113">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="15c2d-114">自動調査は、次のいずれかの方法で開始されます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-114">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="15c2d-115">[通知](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)は Office イベントによってトリガーされ、インシデントを作成します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-115">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="15c2d-116">インシデントの種類に応じて、[セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks)が自動調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-116">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="15c2d-117">--- または ---</span><span class="sxs-lookup"><span data-stu-id="15c2d-117">--- or ---</span></span>
   
   - <span data-ttu-id="15c2d-118">セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して、自動化された[調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-118">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="15c2d-119">自動化された調査を実行している間は、問題の電子メールとその電子メールに関連するエンティティに関する追加のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-119">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="15c2d-120">このようなエンティティには、ファイル、Url、受信者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-120">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="15c2d-121">調査の範囲は、新しい通知および関連するアラートがトリガーされると増加することがあります。</span><span class="sxs-lookup"><span data-stu-id="15c2d-121">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="15c2d-122">自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-122">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="15c2d-123">結果には、検出された脅威に対処し、修復を行うためにとることができる[推奨処理](air-remediation-actions.md) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-123">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="15c2d-124">また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-124">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="15c2d-125">組織でカスタム レポート ソリューションまたはサード パーティのソリューションを使用している場合は、[Office 365 マネージメント アクティビティ API を使用して](air-custom-reporting.md)自動調査と脅威に関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-125">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="15c2d-126">セキュリティ運用チームは、[調査結果と推奨事項](air-view-investigation-results.md)を確認し、[修復処置を承認または拒否](air-remediation-actions.md#approve-or-reject-pending-actions)します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-126">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-remediation-actions.md#approve-or-reject-pending-actions).</span></span> 

    <span data-ttu-id="15c2d-127">保留中の修復操作が承認 (却下) されると、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-127">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="15c2d-128">Office 365 ATP では、修復アクションは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="15c2d-128">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="15c2d-129">修復処理は、組織のセキュリティチームによる承認時にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-129">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="15c2d-130">自動化された調査プロセスにおいて、セキュリティチームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-130">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="15c2d-131">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="15c2d-131">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="15c2d-132">調査の結果の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="15c2d-132">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="15c2d-133">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="15c2d-133">Review and approve actions as a result of an investigation</span></span>](air-remediation-actions.md#approve-or-reject-pending-actions)

> [!TIP]
> <span data-ttu-id="15c2d-134">詳細については、「[エアのしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15c2d-134">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="15c2d-135">AIR の入手方法</span><span class="sxs-lookup"><span data-stu-id="15c2d-135">How to get AIR</span></span>

<span data-ttu-id="15c2d-136">Office 365 の航空機能は、 [office 365 Advanced Threat Protection プラン 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="15c2d-136">Office 365 AIR capabilities are included in [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="15c2d-137">ただし、Office 365 の ATP ポリシーは、エアが期待どおりに動作するように[構成する必要があり](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)ます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-137">However, your [Office 365 ATP policies should be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="15c2d-138">さらに、組織の[通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)を確認し、必要に応じて構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15c2d-138">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="15c2d-139">Office 365 には、Exchange 管理者のアクセス許可の悪用、マルウェアのアクティビティ、外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込み通知ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="15c2d-139">Office 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="15c2d-140">[既定の通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)のいくつかでは、自動調査をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-140">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="15c2d-141">これらには次のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="15c2d-141">These include the following:</span></span>

- <span data-ttu-id="15c2d-142">悪意のある可能性がある URL のクリックが検出される</span><span class="sxs-lookup"><span data-stu-id="15c2d-142">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="15c2d-143">ユーザーが電子メールメッセージをフィッシングとして報告する</span><span class="sxs-lookup"><span data-stu-id="15c2d-143">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="15c2d-144">配信後にマルウェアを含む電子メールメッセージが削除される</span><span class="sxs-lookup"><span data-stu-id="15c2d-144">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="15c2d-145">配信後にフィッシング Url を含む電子メールメッセージが削除される</span><span class="sxs-lookup"><span data-stu-id="15c2d-145">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="15c2d-146">疑わしい電子メール送信パターンが検出される</span><span class="sxs-lookup"><span data-stu-id="15c2d-146">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="15c2d-147">ユーザーが電子メールの送信を制限されている</span><span class="sxs-lookup"><span data-stu-id="15c2d-147">A user is restricted from sending email</span></span>

<span data-ttu-id="15c2d-148">[通知とエアの詳細について説明](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)します。</span><span class="sxs-lookup"><span data-stu-id="15c2d-148">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="15c2d-149">空気機能を使用するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="15c2d-149">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="15c2d-150">アクセス許可は、次の表に記載されているような特定の役割によって付与されます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-150">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="15c2d-151">タスク</span><span class="sxs-lookup"><span data-stu-id="15c2d-151">Task</span></span> |<span data-ttu-id="15c2d-152">必要な役割</span><span class="sxs-lookup"><span data-stu-id="15c2d-152">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="15c2d-153">エア機能を設定するには</span><span class="sxs-lookup"><span data-stu-id="15c2d-153">To set up AIR features</span></span> |<span data-ttu-id="15c2d-154">次のいずれかの役割:</span><span class="sxs-lookup"><span data-stu-id="15c2d-154">One of the following roles:</span></span> <br/><span data-ttu-id="15c2d-155">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="15c2d-155">- Global Administrator</span></span><br/><span data-ttu-id="15c2d-156">-セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="15c2d-156">- Security Administrator</span></span> <br/><span data-ttu-id="15c2d-157">これらの役割は、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-157">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="15c2d-158">推奨されるアクションを承認または拒否するには</span><span class="sxs-lookup"><span data-stu-id="15c2d-158">To approve or reject recommended actions</span></span>|<span data-ttu-id="15c2d-159">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てられている次のいずれかの役割。</span><span class="sxs-lookup"><span data-stu-id="15c2d-159">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="15c2d-160">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="15c2d-160">- Global Administrator</span></span> <br/><span data-ttu-id="15c2d-161">-セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="15c2d-161">- Security Administrator</span></span><br/><span data-ttu-id="15c2d-162">-セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="15c2d-162">- Security Reader</span></span> <br/><span data-ttu-id="15c2d-163">--- さらに ---</span><span class="sxs-lookup"><span data-stu-id="15c2d-163">--- and ---</span></span><br/><span data-ttu-id="15c2d-164">-検索と削除 (この役割は、 [Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)でのみ割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="15c2d-164">- Search and Purge (this role is assigned only in the [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="15c2d-165">そこで新しい役割グループを作成し、その新しい役割グループに検索役割と削除役割を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="15c2d-165">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

## <a name="next-steps"></a><span data-ttu-id="15c2d-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="15c2d-166">Next steps</span></span>

- [<span data-ttu-id="15c2d-167">自動化された調査の詳細と結果を参照する</span><span class="sxs-lookup"><span data-stu-id="15c2d-167">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="15c2d-168">保留中のアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="15c2d-168">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="15c2d-169">関連記事</span><span class="sxs-lookup"><span data-stu-id="15c2d-169">Related articles</span></span>

- [<span data-ttu-id="15c2d-170">Microsoft Defender Advanced Threat Protection の自動化された調査と修復</span><span class="sxs-lookup"><span data-stu-id="15c2d-170">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="15c2d-171">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="15c2d-171">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
