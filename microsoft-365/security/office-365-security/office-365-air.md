---
title: Microsoft Defender for Office 365 の自動調査と応答の概要
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
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
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925606"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9df6a-104">Office 365 の Microsoft Defender で自動調査と応答 (AIR) の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="9df6a-104">Get started using automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9df6a-105">[Microsoft Defender For Office 365 に](office-365-atp.md) は、セキュリティ運用チームの時間と労力を節約できる強力な自動化された調査および応答 (AIR) 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9df6a-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="9df6a-106">アラートがトリガーされると、その通知をレビュー、優先度設定、応答するためのセキュリティ運用チームが必要になります。</span><span class="sxs-lookup"><span data-stu-id="9df6a-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="9df6a-107">受信通知の音量を維持することは非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="9df6a-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="9df6a-108">これらのタスクの一部を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-108">Automating some of those tasks can help.</span></span> <span data-ttu-id="9df6a-109">AIR を使用すれば、セキュリティ運用チームは、トリガーされる重要な警告を見失うことなく、優先度の高いタスクに集中できます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of important alerts that are triggered.</span></span>

<span data-ttu-id="9df6a-110">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="9df6a-110">This article describes:</span></span>
- <span data-ttu-id="9df6a-111">[空気の全体的な流れ](#the-overall-flow-of-air)。</span><span class="sxs-lookup"><span data-stu-id="9df6a-111">The [overall flow of AIR](#the-overall-flow-of-air);</span></span>
- <span data-ttu-id="9df6a-112">[エアを入手する方法](#how-to-get-air)そして</span><span class="sxs-lookup"><span data-stu-id="9df6a-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="9df6a-113">AIR 機能を構成または使用するために [必要なアクセス許可](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="9df6a-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="9df6a-114">AIR の全体的な流れ</span><span class="sxs-lookup"><span data-stu-id="9df6a-114">The overall flow of AIR</span></span>

<span data-ttu-id="9df6a-115">アラートがトリガーされ、セキュリティのプレイブックが自動調査を開始します。これにより、調査結果と推奨される処置が行われます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-115">An alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommended actions.</span></span> <span data-ttu-id="9df6a-116">エアフローの全体的な流れについては、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9df6a-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="9df6a-117">自動調査は、次のいずれかの方法で開始されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="9df6a-118">[警告](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)は、電子メール内の疑わしいもの (メッセージ、添付ファイル、URL など) によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by something suspicious in email (such as a message, attachment, or URL).</span></span> <span data-ttu-id="9df6a-119">インシデントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-119">An incident is created.</span></span> <span data-ttu-id="9df6a-120">インシデントの種類に応じて、 [セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks) が実行され、自動調査が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-120">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) runs, and an automated investigation begins.</span></span> 

     <span data-ttu-id="9df6a-121">--- または ---</span><span class="sxs-lookup"><span data-stu-id="9df6a-121">--- or ---</span></span>
   
   - <span data-ttu-id="9df6a-122">セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して、自動化された[調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)します。</span><span class="sxs-lookup"><span data-stu-id="9df6a-122">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="9df6a-123">自動化された調査を実行している間は、問題の電子メールとその電子メールに関連するエンティティに関する追加のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-123">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="9df6a-124">このようなエンティティには、ファイル、Url、受信者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-124">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="9df6a-125">調査の範囲は、新しい通知および関連するアラートがトリガーされると増加することがあります。</span><span class="sxs-lookup"><span data-stu-id="9df6a-125">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="9df6a-126">自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-126">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="9df6a-127">結果には、検出された脅威に対応して修復するために実行できる [推奨アクション](air-remediation-actions.md) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-127">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond to and remediate any threats that were found.</span></span> <span data-ttu-id="9df6a-128">また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-128">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>


4. <span data-ttu-id="9df6a-129">セキュリティ運用チームは、 [調査結果と推奨事項](air-view-investigation-results.md)を確認し、 [修復処置を承認または拒否](air-review-approve-pending-completed-actions.md)します。</span><span class="sxs-lookup"><span data-stu-id="9df6a-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

5. <span data-ttu-id="9df6a-130">保留中の修復操作が承認 (却下) されると、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="9df6a-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9df6a-131">Microsoft Defender for Office 365 では、修復アクションは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="9df6a-131">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="9df6a-132">修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> <span data-ttu-id="9df6a-133">ただし、空気機能は、修復アクションを識別し、情報に基づいた意思決定を行うために必要な詳細情報を提供することによって、セキュリティ運用チームの時間を節約します。</span><span class="sxs-lookup"><span data-stu-id="9df6a-133">However, AIR capabilities save your security operations team time by identifying remediation actions and providing the details needed to make an informed decision.</span></span>

<span data-ttu-id="9df6a-134">自動化された各調査の間およびセキュリティ運用チームは、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-134">During and after each automated investigation, your security operations team can:</span></span>

- [<span data-ttu-id="9df6a-135">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="9df6a-135">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="9df6a-136">調査の結果の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="9df6a-136">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="9df6a-137">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="9df6a-137">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="9df6a-138">詳細については、「 [航空のしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9df6a-138">For a more detailed overview, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="9df6a-139">AIR の入手方法</span><span class="sxs-lookup"><span data-stu-id="9df6a-139">How to get AIR</span></span>

<span data-ttu-id="9df6a-140">ポリシーとアラートが構成されている場合は、 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)に AIR 機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9df6a-140">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), provided your policies and alerts are configured.</span></span> <span data-ttu-id="9df6a-141">この点については、「 [脅威から保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) する」のガイダンスに従って、以下の保護設定をセットアップまたは構成してください。</span><span class="sxs-lookup"><span data-stu-id="9df6a-141">If you would like some help with this, follow the guidance in [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) to set up or configure the following protection settings:</span></span> 

1. <span data-ttu-id="9df6a-142">[監査ログ](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (有効にする必要があります)</span><span class="sxs-lookup"><span data-stu-id="9df6a-142">[Audit logging](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (should be turned on)</span></span>

2. [<span data-ttu-id="9df6a-143">マルウェア対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="9df6a-143">Antimalware policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [<span data-ttu-id="9df6a-144">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="9df6a-144">Antiphishing protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. <span data-ttu-id="9df6a-145">[スパム対策の保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="9df6a-145">[Antispam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).</span></span>
   
5. <span data-ttu-id="9df6a-146">[安全なリンクと安全な添付ファイル](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="9df6a-146">[Safe Links and Safe Attachments](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).</span></span>
   
6. <span data-ttu-id="9df6a-147">[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。</span><span class="sxs-lookup"><span data-stu-id="9df6a-147">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).</span></span>
   
7. <span data-ttu-id="9df6a-148">[電子メールのゼロ時間自動削除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)。</span><span class="sxs-lookup"><span data-stu-id="9df6a-148">[Zero-hour auto purge for email](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).</span></span>

<span data-ttu-id="9df6a-149">さらに、 [組織のアラートポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)、特に [脅威管理カテゴリの既定のポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9df6a-149">In addition, make sure to [review your organization's alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especially the [default policies in the Threat management category](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).</span></span> 

## <a name="which-alert-policies-trigger-automated-investigations"></a><span data-ttu-id="9df6a-150">自動調査をトリガーするアラートポリシーはどれですか。</span><span class="sxs-lookup"><span data-stu-id="9df6a-150">Which alert policies trigger automated investigations?</span></span>

<span data-ttu-id="9df6a-151">Microsoft 365 には、Exchange 管理者のアクセス許可の悪用、マルウェアのアクティビティ、外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込み通知ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9df6a-151">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="9df6a-152">[既定の通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)のいくつかでは、自動調査をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-152">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="9df6a-153">これらには次のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="9df6a-153">These include the following:</span></span>

- <span data-ttu-id="9df6a-154">悪意のある可能性がある URL のクリックが検出される</span><span class="sxs-lookup"><span data-stu-id="9df6a-154">A potentially malicious URL click is detected</span></span>
- <span data-ttu-id="9df6a-155">ユーザーが電子メールメッセージをフィッシングとして報告する</span><span class="sxs-lookup"><span data-stu-id="9df6a-155">An email message is reported by a user as phish</span></span>
- <span data-ttu-id="9df6a-156">配信後にマルウェアを含む電子メールメッセージが削除される</span><span class="sxs-lookup"><span data-stu-id="9df6a-156">Email messages containing malware are removed after delivery</span></span>
- <span data-ttu-id="9df6a-157">配信後にフィッシング Url を含む電子メールメッセージが削除される</span><span class="sxs-lookup"><span data-stu-id="9df6a-157">Email messages containing phish URLs are removed after delivery</span></span>
- <span data-ttu-id="9df6a-158">疑わしい電子メール送信パターンが検出される</span><span class="sxs-lookup"><span data-stu-id="9df6a-158">Suspicious email sending patterns are detected</span></span>
- <span data-ttu-id="9df6a-159">ユーザーが電子メールの送信を制限されている</span><span class="sxs-lookup"><span data-stu-id="9df6a-159">A user is restricted from sending email</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="9df6a-160">空気機能を使用するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9df6a-160">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="9df6a-161">アクセス許可は、次の表に記載されているような特定の役割によって付与されます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-161">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="9df6a-162">タスク</span><span class="sxs-lookup"><span data-stu-id="9df6a-162">Task</span></span> |<span data-ttu-id="9df6a-163">必要な役割</span><span class="sxs-lookup"><span data-stu-id="9df6a-163">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="9df6a-164">エア機能を設定するには</span><span class="sxs-lookup"><span data-stu-id="9df6a-164">To set up AIR features</span></span> |<span data-ttu-id="9df6a-165">次のいずれかの役割:</span><span class="sxs-lookup"><span data-stu-id="9df6a-165">One of the following roles:</span></span> <br/><span data-ttu-id="9df6a-166">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="9df6a-166">- Global Administrator</span></span><br/><span data-ttu-id="9df6a-167">-セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="9df6a-167">- Security Administrator</span></span> <br/><span data-ttu-id="9df6a-168">これらのロールは、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) または [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-168">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="9df6a-169">推奨されるアクションを承認または拒否するには</span><span class="sxs-lookup"><span data-stu-id="9df6a-169">To approve or reject recommended actions</span></span>|<span data-ttu-id="9df6a-170">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てられている次のいずれかの役割。</span><span class="sxs-lookup"><span data-stu-id="9df6a-170">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="9df6a-171">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="9df6a-171">- Global Administrator</span></span> <br/><span data-ttu-id="9df6a-172">-セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="9df6a-172">- Security Administrator</span></span><br/><span data-ttu-id="9df6a-173">-セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="9df6a-173">- Security Reader</span></span> <br/><span data-ttu-id="9df6a-174">--- さらに ---</span><span class="sxs-lookup"><span data-stu-id="9df6a-174">--- and ---</span></span><br/><span data-ttu-id="9df6a-175">-検索と削除 (この役割は [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)のみで割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9df6a-175">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="9df6a-176">そこで新しい役割グループを作成し、その新しい役割グループに検索役割と削除役割を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9df6a-176">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

## <a name="required-licenses"></a><span data-ttu-id="9df6a-177">必要なライセンス</span><span class="sxs-lookup"><span data-stu-id="9df6a-177">Required licenses</span></span>

<span data-ttu-id="9df6a-178">[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ライセンスは次のものに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df6a-178">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="9df6a-179">セキュリティ管理者 (全体管理者を含む)</span><span class="sxs-lookup"><span data-stu-id="9df6a-179">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="9df6a-180">組織のセキュリティ運用チーム (セキュリティ閲覧者と、検索と削除の役割を含む)</span><span class="sxs-lookup"><span data-stu-id="9df6a-180">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="9df6a-181">エンド ユーザー</span><span class="sxs-lookup"><span data-stu-id="9df6a-181">End users</span></span>


## <a name="next-steps"></a><span data-ttu-id="9df6a-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="9df6a-182">Next steps</span></span>

- [<span data-ttu-id="9df6a-183">自動化された調査の詳細と結果を参照する</span><span class="sxs-lookup"><span data-stu-id="9df6a-183">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="9df6a-184">保留中のアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="9df6a-184">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="9df6a-185">関連記事</span><span class="sxs-lookup"><span data-stu-id="9df6a-185">Related articles</span></span>

- [<span data-ttu-id="9df6a-186">エンドポイントの Microsoft Defender での自動化された調査と修復</span><span class="sxs-lookup"><span data-stu-id="9df6a-186">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="9df6a-187">Microsoft 365 Defender での自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="9df6a-187">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
