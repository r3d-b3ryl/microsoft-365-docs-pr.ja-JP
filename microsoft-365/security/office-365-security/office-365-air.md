---
title: 自動化された調査と応答 (AIR)-はじめに
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365 の Microsoft Defender で自動調査および応答機能の使用を開始します。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 340fc4851043ff917eaff6f237c3ad7d5810a4cb
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430921"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="61908-104">Office 365 で自動調査と応答 (AIR) の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="61908-104">Get started using automated investigation and response (AIR) in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61908-105">[Microsoft Defender For Office 365 に](office-365-atp.md) は、セキュリティ運用チームの時間と労力を節約できる強力な自動化された調査および応答 (AIR) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="61908-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="61908-106">アラートがトリガーされると、その通知をレビュー、優先度設定、応答するためのセキュリティ運用チームが必要になります。</span><span class="sxs-lookup"><span data-stu-id="61908-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="61908-107">受信通知の音量を維持することは非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="61908-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="61908-108">これを自動化することによって役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="61908-108">Automating some of this can help.</span></span> <span data-ttu-id="61908-109">AIR を使用すると、セキュリティ運用チームは、トリガーされた通知を失うことなく、優先度の高いタスクに集中できます。</span><span class="sxs-lookup"><span data-stu-id="61908-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="61908-110">この記事には、以下の問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="61908-110">This article includes:</span></span>
- <span data-ttu-id="61908-111">空気の [全体的な流れ](#the-overall-flow-of-air) 。</span><span class="sxs-lookup"><span data-stu-id="61908-111">The [overall flow](#the-overall-flow-of-air) of AIR;</span></span>
- <span data-ttu-id="61908-112">[エアを入手する方法](#how-to-get-air)そして</span><span class="sxs-lookup"><span data-stu-id="61908-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="61908-113">AIR 機能を構成または使用するために [必要なアクセス許可](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="61908-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="61908-114">AIR の全体的な流れ</span><span class="sxs-lookup"><span data-stu-id="61908-114">The overall flow of AIR</span></span>

<span data-ttu-id="61908-115">高いレベルでは、アラートがトリガーされ、セキュリティによるプレイが自動化された調査が開始され、結果と推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61908-115">At a high level, an alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="61908-116">エアフローの全体的な流れについては、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61908-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="61908-117">自動調査は、次のいずれかの方法で開始されます。</span><span class="sxs-lookup"><span data-stu-id="61908-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="61908-118">[通知](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)は Office イベントによってトリガーされ、インシデントを作成します。</span><span class="sxs-lookup"><span data-stu-id="61908-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="61908-119">インシデントの種類に応じて、 [セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks) が自動調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="61908-119">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="61908-120">--- または ---</span><span class="sxs-lookup"><span data-stu-id="61908-120">--- or ---</span></span>
   
   - <span data-ttu-id="61908-121">セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して、自動化された[調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)します。</span><span class="sxs-lookup"><span data-stu-id="61908-121">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="61908-122">自動化された調査を実行している間は、問題の電子メールとその電子メールに関連するエンティティに関する追加のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="61908-122">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="61908-123">このようなエンティティには、ファイル、Url、受信者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="61908-123">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="61908-124">調査の範囲は、新しい通知および関連するアラートがトリガーされると増加することがあります。</span><span class="sxs-lookup"><span data-stu-id="61908-124">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="61908-125">自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="61908-125">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="61908-126">結果には、検出された脅威に対処し、修復を行うためにとることができる[推奨処理](air-remediation-actions.md) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="61908-126">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="61908-127">また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。</span><span class="sxs-lookup"><span data-stu-id="61908-127">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="61908-128">組織でカスタム レポート ソリューションまたはサード パーティのソリューションを使用している場合は、[Office 365 マネージメント アクティビティ API を使用して](air-custom-reporting.md)自動調査と脅威に関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="61908-128">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="61908-129">セキュリティ運用チームは、 [調査結果と推奨事項](air-view-investigation-results.md)を確認し、 [修復処置を承認または拒否](air-review-approve-pending-completed-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="61908-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="61908-130">保留中の修復操作が承認 (却下) されると、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="61908-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="61908-131">Office 365 ATP では、修復アクションは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="61908-131">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="61908-132">修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="61908-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="61908-133">自動化された調査プロセスにおいて、セキュリティチームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="61908-133">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="61908-134">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="61908-134">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="61908-135">調査の結果の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="61908-135">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="61908-136">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="61908-136">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="61908-137">詳細については、「 [エアのしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61908-137">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="61908-138">AIR の入手方法</span><span class="sxs-lookup"><span data-stu-id="61908-138">How to get AIR</span></span>

<span data-ttu-id="61908-139">AIR 機能は、 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="61908-139">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="61908-140">ただし、必要に応じてエアを機能させるために、 [ポリシーを構成する必要があり](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) ます。</span><span class="sxs-lookup"><span data-stu-id="61908-140">However, your [policies must be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="61908-141">さらに、組織の [通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)を確認し、必要に応じて構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61908-141">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="61908-142">Microsoft 365 には、Exchange 管理者のアクセス許可の悪用、マルウェアのアクティビティ、外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込み通知ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="61908-142">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="61908-143">[既定の通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)のいくつかでは、自動調査をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="61908-143">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="61908-144">これらには次のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="61908-144">These include the following:</span></span>

- <span data-ttu-id="61908-145">悪意のある可能性がある URL のクリックが検出される</span><span class="sxs-lookup"><span data-stu-id="61908-145">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="61908-146">ユーザーが電子メールメッセージをフィッシングとして報告する</span><span class="sxs-lookup"><span data-stu-id="61908-146">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="61908-147">配信後にマルウェアを含む電子メールメッセージが削除される</span><span class="sxs-lookup"><span data-stu-id="61908-147">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="61908-148">配信後にフィッシング Url を含む電子メールメッセージが削除される</span><span class="sxs-lookup"><span data-stu-id="61908-148">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="61908-149">疑わしい電子メール送信パターンが検出される</span><span class="sxs-lookup"><span data-stu-id="61908-149">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="61908-150">ユーザーが電子メールの送信を制限されている</span><span class="sxs-lookup"><span data-stu-id="61908-150">A user is restricted from sending email</span></span>

<span data-ttu-id="61908-151">[通知とエアの詳細について説明](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)します。</span><span class="sxs-lookup"><span data-stu-id="61908-151">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="61908-152">空気機能を使用するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="61908-152">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="61908-153">アクセス許可は、次の表に記載されているような特定の役割によって付与されます。</span><span class="sxs-lookup"><span data-stu-id="61908-153">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="61908-154">タスク</span><span class="sxs-lookup"><span data-stu-id="61908-154">Task</span></span> |<span data-ttu-id="61908-155">必要な役割</span><span class="sxs-lookup"><span data-stu-id="61908-155">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="61908-156">エア機能を設定するには</span><span class="sxs-lookup"><span data-stu-id="61908-156">To set up AIR features</span></span> |<span data-ttu-id="61908-157">次のいずれかの役割:</span><span class="sxs-lookup"><span data-stu-id="61908-157">One of the following roles:</span></span> <br/><span data-ttu-id="61908-158">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="61908-158">- Global Administrator</span></span><br/><span data-ttu-id="61908-159">-セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="61908-159">- Security Administrator</span></span> <br/><span data-ttu-id="61908-160">これらのロールは、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) または [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="61908-160">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="61908-161">推奨されるアクションを承認または拒否するには</span><span class="sxs-lookup"><span data-stu-id="61908-161">To approve or reject recommended actions</span></span>|<span data-ttu-id="61908-162">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てられている次のいずれかの役割。</span><span class="sxs-lookup"><span data-stu-id="61908-162">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="61908-163">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="61908-163">- Global Administrator</span></span> <br/><span data-ttu-id="61908-164">-セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="61908-164">- Security Administrator</span></span><br/><span data-ttu-id="61908-165">-セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="61908-165">- Security Reader</span></span> <br/><span data-ttu-id="61908-166">--- さらに ---</span><span class="sxs-lookup"><span data-stu-id="61908-166">--- and ---</span></span><br/><span data-ttu-id="61908-167">-検索と削除 (この役割は [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)のみで割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="61908-167">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="61908-168">そこで新しい役割グループを作成し、その新しい役割グループに検索役割と削除役割を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="61908-168">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="61908-169">[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ライセンスは次のものに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="61908-169">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="61908-170">セキュリティ管理者 (全体管理者を含む)</span><span class="sxs-lookup"><span data-stu-id="61908-170">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="61908-171">組織のセキュリティ運用チーム (セキュリティ閲覧者と、検索と削除の役割を含む)</span><span class="sxs-lookup"><span data-stu-id="61908-171">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="61908-172">エンド ユーザー</span><span class="sxs-lookup"><span data-stu-id="61908-172">End users</span></span>

<span data-ttu-id="61908-173">さらに、保護を適切に行うために、 [Microsoft Defender For Office 365 ポリシー](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) を定義して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61908-173">In addition, [Microsoft Defender for Office 365 policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="61908-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="61908-174">Next steps</span></span>

- [<span data-ttu-id="61908-175">自動化された調査の詳細と結果を参照する</span><span class="sxs-lookup"><span data-stu-id="61908-175">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="61908-176">保留中のアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="61908-176">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="61908-177">関連記事</span><span class="sxs-lookup"><span data-stu-id="61908-177">Related articles</span></span>

- [<span data-ttu-id="61908-178">エンドポイントの Microsoft Defender での自動化された調査と修復</span><span class="sxs-lookup"><span data-stu-id="61908-178">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="61908-179">Microsoft 365 Defender での自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="61908-179">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
