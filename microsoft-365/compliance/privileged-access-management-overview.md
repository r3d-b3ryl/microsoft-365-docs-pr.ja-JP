---
title: 特権アクセス管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
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
ms.assetid: ''
description: この記事では、よく寄せられる質問 (Faq) に対する回答を含む、Microsoft 365 での特権アクセス管理の概要について説明します。
ms.openlocfilehash: a1bcf1fbe767b4657be8a8ebcc8bf7b101c498d8
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341235"
---
# <a name="privileged-access-management"></a><span data-ttu-id="98655-103">特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="98655-103">Privileged access management</span></span>

<span data-ttu-id="98655-104">特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。</span><span class="sxs-lookup"><span data-stu-id="98655-104">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="98655-105">これは、機密データや重要な構成設定への継続的なアクセス権を持つ既存の特権管理アカウントが使用される違反から組織を保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98655-105">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="98655-106">特権アクセス管理では、ユーザーはジャストインタイムアクセスを要求して、高度に範囲指定された、時間の制限のある承認ワークフローを通じて、昇格された権限のあるタスクを完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="98655-106">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="98655-107">この構成では、機密性の高いデータや重要な構成の設定を危険にさらすことなくタスクが行えるように、ユーザーに十分なアクセス権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="98655-107">This configuration gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="98655-108">Microsoft 365 で特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、管理者アクセスの脆弱性に対する防御層を提供できます。</span><span class="sxs-lookup"><span data-stu-id="98655-108">Enabling privileged access management in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="98655-109">統合された顧客ロックボックスおよび特権アクセス管理ワークフローの簡単な概要については、この「 [customer のロックボックス」および「privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98655-109">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="98655-110">保護レイヤー</span><span class="sxs-lookup"><span data-stu-id="98655-110">Layers of protection</span></span>

<span data-ttu-id="98655-111">特権アクセス管理は、Microsoft 365 セキュリティアーキテクチャ内の他のデータおよびアクセス機能の保護を補完します。</span><span class="sxs-lookup"><span data-stu-id="98655-111">Privileged access management complements other data and access feature protections within the Microsoft 365 security architecture.</span></span> <span data-ttu-id="98655-112">セキュリティに対する統合および階層化アプローチの一部としての特権アクセス管理を含むセキュリティモデルを使用すると、機密情報の保護を強化し、Microsoft 365 の構成設定を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="98655-112">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Microsoft 365 configuration settings.</span></span> <span data-ttu-id="98655-113">図に示されているように、特権アクセス管理は、microsoft 365 データのネイティブ暗号化と、Microsoft 365 services の役割ベースのアクセス制御セキュリティモデルによって提供される保護に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="98655-113">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Microsoft 365 data and the role-based access control security model of Microsoft 365 services.</span></span> <span data-ttu-id="98655-114">[AZURE AD 特権 Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と共に使用する場合、この2つの機能により、さまざまなスコープでジャストインタイムのアクセスを使用してアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="98655-114">When used with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Microsoft 365 での階層型の保護](../media/pam-layered-protection.png)

<span data-ttu-id="98655-116">特権アクセス管理は **タスク** レベルで定義され、スコープが設定されていますが、Azure AD 特権 id 管理は、複数のタスクを実行する機能を使用して、 **役割** レベルで保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="98655-116">Privileged access management is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="98655-117">Azure AD Privileged Identity Management では、主に AD の役割および役割グループへのアクセスを管理できます。また、Microsoft 365 の特権アクセス管理はタスク レベルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="98655-117">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Microsoft 365 applies only at the task level.</span></span>

- <span data-ttu-id="98655-118">**既に AZURE AD 特権 Id 管理を使用しているときに、特権アクセス管理を有効にします。** 特権アクセス管理を追加すると、Microsoft 365 データへの特権アクセスのための、より詳細な保護および監査機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="98655-118">**Enabling privileged access management while already using Azure AD Privileged Identity Management:** Adding privileged access management provides another granular layer of protection and audit capabilities for privileged access to Microsoft 365 data.</span></span>

- <span data-ttu-id="98655-119">**Office 365 で既に特権アクセス管理を使用しているときに、AZURE AD 特権 Id 管理を有効にする:**  特権アクセス管理に Azure AD 特権 Id 管理を追加すると、主にユーザーロールまたは id によって定義された Microsoft 365 外部のデータへの特権アクセスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="98655-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management can extend privileged access to data outside of Microsoft 365 that's primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="98655-120">特権アクセス管理アーキテクチャとプロセスフロー</span><span class="sxs-lookup"><span data-stu-id="98655-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="98655-121">次の各プロセスフローは、特権アクセスのアーキテクチャと、それが Microsoft 365 のサブストレート、監査、および Exchange 管理実行空間とどのように連携するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="98655-121">Each of the following process flows outline the architecture of privileged access and how it interacts with the Microsoft 365 substrate, auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="98655-122">手順 1: 特権アクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="98655-122">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="98655-123">[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して特権アクセスポリシーを構成する場合は、ポリシーおよび特権アクセス機能のプロセスおよびポリシー属性を microsoft 365 のサブストレートに定義します。</span><span class="sxs-lookup"><span data-stu-id="98655-123">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Microsoft 365 substrate.</span></span> <span data-ttu-id="98655-124">アクティビティは、セキュリティコンプライアンスセンターに記録され &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="98655-124">The activities are logged in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="98655-125">ポリシーが有効になり、承認の受信要求を処理する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="98655-125">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![手順 1: ポリシーの作成](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="98655-127">手順 2: アクセス要求</span><span class="sxs-lookup"><span data-stu-id="98655-127">Step 2: Access request</span></span>

<span data-ttu-id="98655-128">[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して、ユーザーは昇格されたタスクまたは権限のあるタスクへのアクセスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="98655-128">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="98655-129">特権アクセス機能は、構成された特権アクセスポリシーに対して処理するために、Microsoft 365 のサブストレートに要求を送信し、セキュリティコンプライアンスセンターのログにアクティビティを記録し &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="98655-129">The privileged access feature sends the request to the Microsoft 365 substrate for processing against the configured privilege access policy and records the Activity in the Security &amp; Compliance Center logs.</span></span>

![手順 2: アクセス要求](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="98655-131">手順 3: アクセスの承認</span><span class="sxs-lookup"><span data-stu-id="98655-131">Step 3: Access approval</span></span>

<span data-ttu-id="98655-132">承認要求が生成され、保留中の要求通知が承認者にメールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="98655-132">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="98655-133">承認された場合、特権アクセス要求は承認として処理され、タスクを完了する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="98655-133">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="98655-134">拒否された場合、タスクはブロックされ、要求者へのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="98655-134">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="98655-135">アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。</span><span class="sxs-lookup"><span data-stu-id="98655-135">The requestor is notified of the request approval or denial via email message.</span></span>

![手順 3: アクセスの承認](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="98655-137">手順 4: アクセスの処理</span><span class="sxs-lookup"><span data-stu-id="98655-137">Step 4: Access processing</span></span>

<span data-ttu-id="98655-138">承認された要求の場合、タスクは Exchange 管理実行空間によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="98655-138">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="98655-139">承認は、特権アクセス ポリシーに対してチェックされ、Microsoft 365 サブストレートによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="98655-139">The approval is checked against the privileged access policy and processed by the Microsoft 365 substrate.</span></span> <span data-ttu-id="98655-140">タスクのすべてのアクティビティは、セキュリティコンプライアンスセンターに記録され &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="98655-140">All activity for the task is logged in the Security &amp; Compliance Center.</span></span>

![手順 4: アクセスの処理](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="98655-142">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="98655-142">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="98655-143">Office 365 では、どの Sku で特権アクセスを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="98655-143">What SKUs can use privileged access in Office 365?</span></span>

<span data-ttu-id="98655-144">特権アクセス管理は、Microsoft 365 および Office 365 のサブスクリプションとアドオンを幅広く選択しているお客様に利用できます。</span><span class="sxs-lookup"><span data-stu-id="98655-144">Privileged access management is available for customers for a wide selection of Microsoft 365 and Office 365 subscriptions and add-ons.</span></span> <span data-ttu-id="98655-145">詳細については [、「特権アクセス管理の概要](privileged-access-management-configuration.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98655-145">See [Get started with privileged access management](privileged-access-management-configuration.md) for details.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="98655-146">特権アクセスが Exchange を超えて Office 365 ワークロードをサポートするのはいつですか?</span><span class="sxs-lookup"><span data-stu-id="98655-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>

<span data-ttu-id="98655-147">権限のあるアクセス管理は、近日中に他の Office 365 ワークロードで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="98655-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="98655-148">詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98655-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="98655-149">自分の組織では30以上の特権アクセスポリシーが必要ですが、この制限は増加しますか?</span><span class="sxs-lookup"><span data-stu-id="98655-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>

<span data-ttu-id="98655-150">はい。組織ごとの特権アクセスポリシーの現在の制限は、機能のロードマップにあります。</span><span class="sxs-lookup"><span data-stu-id="98655-150">Yes, raising the current limit of 30 privileged access policies per organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="98655-151">Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="98655-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>

<span data-ttu-id="98655-152">いいえ。 Office 365 で特権アクセスを管理するアカウントには、Exchange 役割管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="98655-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="98655-153">役割管理役割をスタンドアロンのアカウントアクセス許可として構成しない場合は、グローバル管理者の役割に既定でこの役割が含まれ、特権アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="98655-153">If you don't want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="98655-154">承認者のグループに含まれるユーザーは、グローバル管理者である必要がありません。または、PowerShell を使用して要求を確認して承認するための役割管理役割が割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="98655-154">Users included in an approvers' group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests with PowerShell.</span></span>

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a><span data-ttu-id="98655-155">カスタマーロックボックスに関連する特権アクセス管理の方法</span><span class="sxs-lookup"><span data-stu-id="98655-155">How is privileged access management related to Customer Lockbox?</span></span>

<span data-ttu-id="98655-156">[カスタマーロックボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) Microsoft がデータにアクセスするときに、組織に対してレベルのアクセス制御を許可します。</span><span class="sxs-lookup"><span data-stu-id="98655-156">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="98655-157">特権アクセス管理を使用すると、Microsoft 365 のすべての特権タスクに対して、組織内で詳細なアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="98655-157">Privileged access management allows granular access control within an organization for all Microsoft 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="98655-158">始める準備はいいですか。</span><span class="sxs-lookup"><span data-stu-id="98655-158">Ready to get started?</span></span>

<span data-ttu-id="98655-159">[権限のあるアクセス管理の組織の構成を](privileged-access-management-configuration.md)開始します。</span><span class="sxs-lookup"><span data-stu-id="98655-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="98655-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="98655-160">Learn more</span></span>

[<span data-ttu-id="98655-161">対話型ガイド: 特権アクセス管理を使用して管理者タスクを監視および制御する</span><span class="sxs-lookup"><span data-stu-id="98655-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
