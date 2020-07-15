---
title: Exchange Online および セキュリティ/コンプライアンス センターを使用して米国証券取引委員会規則 17a-4 (SEC Rule 17a-4) に準拠する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: CFTC ルール 1.31 (c)-(d)、FINRA ルール 4511、および SEC ルール 17a-4 の規制要件を満たすのに役立つように Exchange Online/コンプライアンスセンターを構成します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127304"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="02cc0-103">Exchange Online および セキュリティ/コンプライアンス センターを使用して米国証券取引委員会規則 17a-4 (SEC Rule 17a-4) に準拠する</span><span class="sxs-lookup"><span data-stu-id="02cc0-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="02cc0-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="02cc0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="02cc0-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="02cc0-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="02cc0-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="02cc0-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="02cc0-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="02cc0-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="02cc0-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="02cc0-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="02cc0-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="02cc0-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="02cc0-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="02cc0-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="02cc0-111">セキュリティ/コンプライアンス センターを活用して Exchange Online での規制上の義務 (特に、規則 17a-4 の要件に関する義務) を遵守することができ、これをこれらの組織でもっと知っていただくために、Microsoft は Cohasset Associates と協力して評価をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="02cc0-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="02cc0-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="02cc0-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="02cc0-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="02cc0-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="02cc0-114">Cohasset 評価をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="02cc0-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="02cc0-115">[Cohasset 評価はこちらからダウンロード](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)できます。</span><span class="sxs-lookup"><span data-stu-id="02cc0-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![ダウンロード可能な Cohasset Associates による評価のタイトル ページ](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="02cc0-117">この評価は、Exchange Online に固有のものです</span><span class="sxs-lookup"><span data-stu-id="02cc0-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="02cc0-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="02cc0-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="02cc0-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="02cc0-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="02cc0-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="02cc0-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="02cc0-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="02cc0-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="02cc0-122">推奨構成の鍵は保持ロックを使用することです</span><span class="sxs-lookup"><span data-stu-id="02cc0-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="02cc0-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="02cc0-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="02cc0-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="02cc0-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="02cc0-125">記録は義務づけられた保持期間保持される必要があります。保持期間を短縮することはできず、延長のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="02cc0-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="02cc0-126">記録は不変である必要があります。つまり、保持期間中は記録の上書き、消去、または変更をすることができません。</span><span class="sxs-lookup"><span data-stu-id="02cc0-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="02cc0-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="02cc0-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="02cc0-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="02cc0-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="02cc0-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="02cc0-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="02cc0-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="02cc0-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="02cc0-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="02cc0-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="02cc0-132">ポリシーの保持期間は延長のみが可能で、短縮することはできません。</span><span class="sxs-lookup"><span data-stu-id="02cc0-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="02cc0-133">ユーザーをポリシーに追加することはできますが、ユーザーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="02cc0-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="02cc0-134">アイテム保持ポリシーを管理者が削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="02cc0-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="02cc0-135">保持ロックを使用して、米国証券取引委員会規則 17a-4 の規制要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="02cc0-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="02cc0-136">保持ロックを設定する方法</span><span class="sxs-lookup"><span data-stu-id="02cc0-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="02cc0-137">アイテム保持ポリシーは、PowerShell を使用してロックできます。</span><span class="sxs-lookup"><span data-stu-id="02cc0-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="02cc0-138">詳細については、「[[保持ロック] を使用して規制要件に準拠する](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02cc0-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="02cc0-139">既知の制限</span><span class="sxs-lookup"><span data-stu-id="02cc0-139">Known limitations</span></span>

<span data-ttu-id="02cc0-140">現在、Exchange Online にはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="02cc0-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="02cc0-141">スレッド形式の通信は、Teams チャットおよびチャンネル メッセージでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02cc0-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="02cc0-142">Teams チャットおよびチャンネル メッセージでの "いいね" は保持されません。</span><span class="sxs-lookup"><span data-stu-id="02cc0-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="02cc0-143">アイテム レベルの監査は Microsoft 365 グループのメールボックスで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="02cc0-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="02cc0-144">詳細については、「[メールボックスの監査を管理する](enable-mailbox-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02cc0-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
