---
title: 特権アクセス管理の詳細
description: この記事では、よく寄せられる質問 (FAQ) への回答など、Microsoft 365 の特権アクセス管理の概要について説明します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126606"
---
# <a name="learn-about-privileged-access-management"></a><span data-ttu-id="ad023-103">特権アクセス管理の詳細</span><span class="sxs-lookup"><span data-stu-id="ad023-103">Learn about privileged access management</span></span>

<span data-ttu-id="ad023-104">特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-104">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="ad023-105">これは、機密データや重要な構成設定への継続的なアクセス権を持つ既存の特権管理アカウントが使用される違反から組織を保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad023-105">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="ad023-106">特権アクセス管理では、ユーザーは、高度にスコープが設定され、時間にバインドされた承認ワークフローを通じて昇格されたタスクと特権タスクを完了するために、Just-In-Time アクセスを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad023-106">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="ad023-107">この構成では、機密性の高いデータや重要な構成の設定を危険にさらすことなくタスクが行えるように、ユーザーに十分なアクセス権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="ad023-107">This configuration gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="ad023-108">Microsoft 365 で特権アクセス管理を有効にすると、組織は無防備な特権で運用し、管理アクセスの脆弱性に対する防御層を提供できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-108">Enabling privileged access management in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="ad023-109">統合カスタマー ロックボックスと特権アクセス管理ワークフローの簡単な概要については、このカスタマー ロックボックスと特権アクセス管理のビデオ [を参照してください](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="ad023-109">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="ad023-110">保護レイヤー</span><span class="sxs-lookup"><span data-stu-id="ad023-110">Layers of protection</span></span>

<span data-ttu-id="ad023-111">特権アクセス管理は、Microsoft 365 セキュリティ アーキテクチャ内の他のデータとアクセス機能の保護を補完します。</span><span class="sxs-lookup"><span data-stu-id="ad023-111">Privileged access management complements other data and access feature protections within the Microsoft 365 security architecture.</span></span> <span data-ttu-id="ad023-112">セキュリティに対する統合されたレイヤー化されたアプローチの一部として特権アクセス管理を含めて、機密情報と Microsoft 365 構成設定の保護を最大化するセキュリティ モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad023-112">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Microsoft 365 configuration settings.</span></span> <span data-ttu-id="ad023-113">図に示すように、特権アクセス管理は、Microsoft 365 データのネイティブ暗号化と、Microsoft 365 サービスのロールベースのアクセス制御セキュリティ モデルによって提供される保護に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="ad023-113">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Microsoft 365 data and the role-based access control security model of Microsoft 365 services.</span></span> <span data-ttu-id="ad023-114">[Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)と一緒に使用する場合、これらの 2 つの機能は、さまざまなスコープで Just-in-Time アクセスを使用してアクセス制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad023-114">When used with [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Microsoft 365 のレイヤー保護](../media/pam-layered-protection.png)

<span data-ttu-id="ad023-116">特権アクセス管理はタスク レベルで定義およびスコープ設定され、Azure AD Privileged Identity Management は複数のタスクを実行できる役割レベルで保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="ad023-116">Privileged access management is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="ad023-117">Azure AD Privileged Identity Management では、主に AD の役割および役割グループへのアクセスを管理できます。また、Microsoft 365 の特権アクセス管理はタスク レベルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-117">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Microsoft 365 applies only at the task level.</span></span>

- <span data-ttu-id="ad023-118">Azure AD Privileged Identity Management を使用している間に特権 **アクセス管理を有効にする:** 特権アクセス管理を追加すると、Microsoft 365 データへの特権アクセスに対する保護と監査機能の別の詳細なレイヤーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-118">**Enabling privileged access management while already using Azure AD Privileged Identity Management:** Adding privileged access management provides another granular layer of protection and audit capabilities for privileged access to Microsoft 365 data.</span></span>

- <span data-ttu-id="ad023-119">Azure AD 365 で既に特権アクセス管理を使用している間に **Privileged Identity Management Office有効にする:** Azure AD Privileged Identity Management を特権アクセス管理に追加すると、主にユーザー ロールまたは ID によって定義される Microsoft 365 外のデータへの特権アクセスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management can extend privileged access to data outside of Microsoft 365 that's primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="ad023-120">特権アクセス管理アーキテクチャとプロセス フロー</span><span class="sxs-lookup"><span data-stu-id="ad023-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="ad023-121">次の各プロセス フローは、特権アクセスのアーキテクチャと、Microsoft 365 の基点、監査、および Exchange 管理の実行空間との対話方法の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad023-121">Each of the following process flows outline the architecture of privileged access and how it interacts with the Microsoft 365 substrate, auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="ad023-122">手順 1: 特権アクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="ad023-122">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="ad023-123">[Microsoft 365](https://admin.microsoft.com)管理センターまたは Exchange Management PowerShell を使用して特権アクセス ポリシーを構成する場合は、Microsoft 365 の管理センターで、ポリシーと特権アクセス機能プロセス、およびポリシー属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad023-123">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Microsoft 365 substrate.</span></span> <span data-ttu-id="ad023-124">アクティビティはセキュリティ コンプライアンス センターに &amp; 記録されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-124">The activities are logged in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ad023-125">ポリシーが有効になり、承認の受信要求を処理する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="ad023-125">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![手順 1: ポリシーの作成](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="ad023-127">手順 2: アクセス要求</span><span class="sxs-lookup"><span data-stu-id="ad023-127">Step 2: Access request</span></span>

<span data-ttu-id="ad023-128">Microsoft [365](https://admin.microsoft.com) 管理センターまたは Exchange Management PowerShell を使用して、ユーザーは昇格されたタスクまたは特権タスクへのアクセスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-128">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="ad023-129">特権アクセス機能は、構成された特権アクセス ポリシーに対して処理を行う要求を Microsoft 365 の基点に送信し、セキュリティ コンプライアンス センターのログにアクティビティ &amp; を記録します。</span><span class="sxs-lookup"><span data-stu-id="ad023-129">The privileged access feature sends the request to the Microsoft 365 substrate for processing against the configured privilege access policy and records the Activity in the Security &amp; Compliance Center logs.</span></span>

![手順 2: アクセス要求](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="ad023-131">手順 3: アクセスの承認</span><span class="sxs-lookup"><span data-stu-id="ad023-131">Step 3: Access approval</span></span>

<span data-ttu-id="ad023-132">承認要求が生成され、保留中の要求通知が承認者にメールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-132">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="ad023-133">承認された場合、特権アクセス要求は承認として処理され、タスクを完了する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="ad023-133">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="ad023-134">拒否された場合、タスクはブロックされ、要求者へのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="ad023-134">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="ad023-135">アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-135">The requestor is notified of the request approval or denial via email message.</span></span>

![手順 3: アクセスの承認](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="ad023-137">手順 4: アクセスの処理</span><span class="sxs-lookup"><span data-stu-id="ad023-137">Step 4: Access processing</span></span>

<span data-ttu-id="ad023-138">承認された要求の場合、タスクは Exchange 管理実行空間によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-138">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="ad023-139">承認は、特権アクセス ポリシーに対してチェックされ、Microsoft 365 サブストレートによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-139">The approval is checked against the privileged access policy and processed by the Microsoft 365 substrate.</span></span> <span data-ttu-id="ad023-140">タスクのすべてのアクティビティがセキュリティ コンプライアンス センターに &amp; 記録されます。</span><span class="sxs-lookup"><span data-stu-id="ad023-140">All activity for the task is logged in the Security &amp; Compliance Center.</span></span>

![手順 4: アクセスの処理](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="ad023-142">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ad023-142">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="ad023-143">Office 365 で特権アクセスを使用できる SKU は何ですか?</span><span class="sxs-lookup"><span data-stu-id="ad023-143">What SKUs can use privileged access in Office 365?</span></span>

<span data-ttu-id="ad023-144">特権アクセス管理は、Microsoft 365 および 365 サブスクリプションとアドオンOffice種類のお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-144">Privileged access management is available for customers for a wide selection of Microsoft 365 and Office 365 subscriptions and add-ons.</span></span> <span data-ttu-id="ad023-145">詳細 [については、「特権アクセス管理の使用を開始する](privileged-access-management-configuration.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad023-145">See [Get started with privileged access management](privileged-access-management-configuration.md) for details.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="ad023-146">特権アクセスが Exchange 以外の 365 Officeをサポートする場合</span><span class="sxs-lookup"><span data-stu-id="ad023-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>

<span data-ttu-id="ad023-147">特権アクセス管理は、他の 365 ワークロードOffice間もなく利用できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="ad023-148">詳細については [、Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad023-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="ad023-149">組織には 30 を超える特権アクセス ポリシーが必要ですが、この制限は増えますか?</span><span class="sxs-lookup"><span data-stu-id="ad023-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>

<span data-ttu-id="ad023-150">はい。組織ごとに 30 の特権アクセス ポリシーの現在の制限を引き上げることは、機能ロードマップに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad023-150">Yes, raising the current limit of 30 privileged access policies per organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="ad023-151">Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="ad023-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>

<span data-ttu-id="ad023-152">いいえ。Exchange 365 で特権アクセスを管理するアカウントには、Exchange 役割管理の役割Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="ad023-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="ad023-153">役割管理の役割をスタンドアロン アカウントのアクセス許可として構成しない場合、グローバル管理者の役割には既定でこの役割が含まれるので、特権アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ad023-153">If you don't want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="ad023-154">承認者のグループに含まれるユーザーは、グローバル管理者である必要や、PowerShell で要求を確認および承認するために役割管理の役割が割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad023-154">Users included in an approvers' group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests with PowerShell.</span></span>

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a><span data-ttu-id="ad023-155">カスタマー ロックボックスに関連する特権アクセス管理の方法</span><span class="sxs-lookup"><span data-stu-id="ad023-155">How is privileged access management related to Customer Lockbox?</span></span>

<span data-ttu-id="ad023-156">[カスタマー ロックボックスを使用](/office365/admin/manage/customer-lockbox-requests) すると、Microsoft がデータにアクセスするときに、組織に対してレベルのアクセス制御が可能になります。</span><span class="sxs-lookup"><span data-stu-id="ad023-156">[Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="ad023-157">特権アクセス管理を使用すると、組織内のすべての Microsoft 365 特権タスクに対して詳細なアクセス制御が可能になります。</span><span class="sxs-lookup"><span data-stu-id="ad023-157">Privileged access management allows granular access control within an organization for all Microsoft 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="ad023-158">始める準備はいいですか。</span><span class="sxs-lookup"><span data-stu-id="ad023-158">Ready to get started?</span></span>

<span data-ttu-id="ad023-159">特権 [アクセス管理用に組織の構成を開始します](privileged-access-management-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="ad023-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="ad023-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ad023-160">Learn more</span></span>

[<span data-ttu-id="ad023-161">対話型ガイド: 特権アクセス管理を使用して管理者タスクを監視および制御する</span><span class="sxs-lookup"><span data-stu-id="ad023-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
