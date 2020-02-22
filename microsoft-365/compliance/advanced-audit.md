---
title: Microsoft 365 の高度な監査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 の高度な監査は、新しい監査機能を提供し、組織におけるフォレンシックおよびコンプライアンスの調査を支援します。
ms.openlocfilehash: 79c7e24349d3b6603e82946fda4a3c1f0c0ae6ff
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170517"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="1a5aa-103">Microsoft 365 の高度な監査</span><span class="sxs-lookup"><span data-stu-id="1a5aa-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="1a5aa-104">Microsoft 365 の[統合監査機能](search-the-audit-log-in-security-and-compliance.md)を使用すると、組織は Microsoft 365 のさまざまなサービスにわたって、さまざまな種類の監査済みアクティビティを可視化できます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="1a5aa-105">Microsoft 365 の高度な監査のリリースにより、組織におけるフォレンシックおよびコンプライアンスの調査を支援できる新しい監査機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-105">Now with the release of Advanced Audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.</span></span>

> [!NOTE]
> <span data-ttu-id="1a5aa-106">高度な監査は、Office 365 または Microsoft 365 Enterprise E5 サブスクリプションを持つ組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-106">Advanced Audit is available for organizations with an Office 365 or Microsoft 365 Enterprise E5 subscription.</span></span> <span data-ttu-id="1a5aa-107">さらに、Microsoft 365 E5 コンプライアンス アドオン サブスクリプションは、監査ログの長期保持や調査のための重要なイベントへのアクセスと同様に、高度な監査機能にユーザーごとのライセンスが必要な場合に、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-107">Additionally, a Microsoft 365 E5 Compliance add-on subscription can be assigned to users for when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span>

<span data-ttu-id="1a5aa-108">この記事では、これらの高度な監査機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-108">This article provides an overview of these Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="1a5aa-109">監査ログの長期保持</span><span class="sxs-lookup"><span data-stu-id="1a5aa-109">Long-term retention of audit logs</span></span>

<span data-ttu-id="1a5aa-110">高度な監査は、Exchange、SharePoint、および Azure Active Directory の監査レコードを 1 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-110">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="1a5aa-111">これは、アクティビティが発生したサービスを示す**ワークロード** プロパティの**Exchange**、**SharePoint**、または **AzureActiveDirectory** の値を含む任意の監査レコードを 1 年間保持する既定の監査ログの保持ポリシーによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-111">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="1a5aa-112">これは、フォレンシックまたはコンプライアンスに関する継続的な調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-112">This can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="1a5aa-113">詳細については、「監査ログの保持ポリシーの管理」の「[既定の監査ログの保持ポリシー](audit-log-retention-policies.md#default-audit-log-retention-policy)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-113">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

## <a name="audit-log-retention-policies"></a><span data-ttu-id="1a5aa-114">監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="1a5aa-114">Audit log retention policies</span></span>

<span data-ttu-id="1a5aa-115">(前のセクションで説明した) 既定の監査ログの保持ポリシーが適用されていない他のサービスで生成されたすべての監査レコードは、90 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-115">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="1a5aa-116">ただし、カスタマイズした監査ログの保持ポリシーを作成して、最大 1 年間他の監査レコードを保持できます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-116">However, now you can create customized audit log retention policies to retain other audit records for up to one year.</span></span> <span data-ttu-id="1a5aa-117">次の 1 つ以上の基準に基づいて、監査レコードを保持するポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-117">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="1a5aa-118">監査されたアクティビティが発生する Microsoft 365 サービス</span><span class="sxs-lookup"><span data-stu-id="1a5aa-118">The Microsoft 365 service where the audited activities occur</span></span>

- <span data-ttu-id="1a5aa-119">特定の監査済みアクティビティ</span><span class="sxs-lookup"><span data-stu-id="1a5aa-119">Specific audited activities</span></span>

- <span data-ttu-id="1a5aa-120">監査済みアクティビティを実行するユーザー</span><span class="sxs-lookup"><span data-stu-id="1a5aa-120">The user who performs an audited activity</span></span>

<span data-ttu-id="1a5aa-121">特定のポリシーが他のポリシーよりも優先されるように、ポリシーおよび優先度のレベルに一致する監査レコードを保持する期間を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-121">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="1a5aa-122">また、組織の一部またはすべてのユーザーに対して Exchange、SharePoint、または Azure Active Directory 監査レコードを 1 年未満で保持する必要がある場合は、カスタム監査ログの保持ポリシーが既定の監査保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-122">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year for some or all the users in your organization.</span></span> <span data-ttu-id="1a5aa-123">詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-123">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="1a5aa-124">調査のための重要なイベントへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1a5aa-124">Access to crucial events for investigations</span></span>

<span data-ttu-id="1a5aa-125">重要なセキュリティ - セキュリティ関連の重要な監査イベントおよびコンプライアンス関連の監査イベントは、違反の可能性やその他のフォレンジック調査の調査に役立つイベントです。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-125">Crucial security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations.</span></span> <span data-ttu-id="1a5aa-126">リリースする最初の重要なイベントは、*MailItemsAccessed* メールボックスの監査イベントです。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-126">The first crucial event that we're releasing is the *MailItemsAccessed* mailbox auditing event.</span></span> <span data-ttu-id="1a5aa-127">このイベントは、メール プロトコルとクライアントがメール データにアクセスしたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-127">This event is trigger when mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="1a5aa-128">MailItemsAccessed イベントは、調査者がデータ違反を識別し、侵害された可能性があるメッセージの範囲を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-128">The MailItemsAccessed event can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="1a5aa-129">攻撃者がメール メッセージにアクセスすると、MailItemsAccessed イベントは、実際に読み取られたことを示す明示的な信号がない場合でもトリガーされます (つまり、バインドや同期などのアクセスの種類が監査レコードに記録されます)。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-129">If an attacker gained access to email messages, MailItemsAccessed event will be triggered even if there is no explicit signal that it was actually read (in other words, the type of access such as via bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="1a5aa-130">新しい MailItemsAccessed メールボックス アクションは、Exchange Online のメールボックスの監査ログインの MessageBind を置き換え、次の改良点を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-130">The new MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="1a5aa-131">MessageBind は、AuditAdmin ユーザー ログインの種類に対してのみ構成でき、委任または所有者のアクションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-131">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="1a5aa-132">MailItemsAccessed は、すべてのログインの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-132">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="1a5aa-133">MessageBind は、メール クライアントによるアクセスのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-133">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="1a5aa-134">同期アクティビティには適用されませんでした。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-134">It didn't apply to sync activities.</span></span> <span data-ttu-id="1a5aa-135">MailItemsAccessed イベントは、バインド アクセスの種類と同期アクセスの種類の両方によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-135">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="1a5aa-136">MessageBind アクションによって、同じメール メッセージにアクセスしたときに複数の監査レコードが作成され、「ノイズ」が監査されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-136">MessageBind actions would trigger multiple audit records to be created when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="1a5aa-137">一方、MailItemsAccessed イベントは、少数の監査レコードに集約されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-137">In contrast, MailItemsAccessed events are aggregated in fewer audit records.</span></span>

<span data-ttu-id="1a5aa-138">メールボックスの監査ログインの詳細については、「[メールボックスの監査を管理する](enable-mailbox-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-138">For more information about mailbox auditing logging, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="1a5aa-139">Office 365 管理アクティビティ API への高帯域幅アクセス</span><span class="sxs-lookup"><span data-stu-id="1a5aa-139">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="1a5aa-140">Office 365 管理アクティビティ API を使用して監査ログにアクセスする組織は、発行者レベルの調整制限により制限されていました。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-140">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="1a5aa-141">つまり、発行者が複数のお客様に代わってデータをプルする場合、制限はそれらすべてのお客様で共有されていました。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-141">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="1a5aa-142">高度な監査のリリースにより、発行者レベルの制限からテナント レベルの制限に移行しています。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-142">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="1a5aa-143">その結果、各組織は、監査データにアクセスするために独自に完全に割り当てられた帯域幅を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-143">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="1a5aa-144">帯域幅は静的な定義済みの制限ではありませんが、組織内のシート数などの要因の組み合わせでモデル化され、E5 組織は E5 以外よりも多くの帯域幅を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-144">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="1a5aa-145">すべての組織には、最初に 1 分あたり 2,000 件の要求のベースラインが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-145">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="1a5aa-146">この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-146">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="1a5aa-147">E5 組織は、E5 以外の組織の約 2 倍の帯域幅を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-147">E5 organizations will get approximately twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="1a5aa-148">また、サービスの正常性を保護するために、最大帯域幅の上限も設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-148">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="1a5aa-149">詳細については、「[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)」の「API 調整」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a5aa-149">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>
