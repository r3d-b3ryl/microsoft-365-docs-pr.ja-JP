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
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="028a8-103">Exchange Online および セキュリティ/コンプライアンス センターを使用して米国証券取引委員会規則 17a-4 (SEC Rule 17a-4) に準拠する</span><span class="sxs-lookup"><span data-stu-id="028a8-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="028a8-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="028a8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="028a8-p101">データ保持に関する規制基準への準拠が組織で必要な場合に、セキュリティ/コンプライアンス センターは Exchange Online 上のデータのライフサイクル管理機能を提供します。これには、データを保持、監査、検索、およびエクスポートする機能が含まれます。これらの機能は、ほとんどの組織でのニーズを満たすために十分な機能です。</span><span class="sxs-lookup"><span data-stu-id="028a8-p101">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="028a8-p102">ただし、規制が厳しい業界の一部の組織は、より厳格な規制要件を遵守する必要があります。たとえば、銀行や株式仲介業者などの金融機関は、証券取引委員会 (SEC) が発行する規則 17a-4 を遵守する必要があります。規則 17a-4 には、記録保持の期間、形式、品質、可用性、および責任などの記録の管理に関する多くの側面を含む、電子データの記憶域に関する特定の要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="028a8-p102">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="028a8-111">セキュリティ/コンプライアンス センターを活用して Exchange Online での規制上の義務 (特に、規則 17a-4 の要件に関する義務) を遵守することができ、これをこれらの組織でもっと知っていただくために、Microsoft は Cohasset Associates と協力して評価をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="028a8-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="028a8-p103">Exchange Online および セキュリティ/コンプライアンス センターは、推奨通りに構成した場合、米国商品先物取引委員会規則 1.31(c)-(d) (CFTC Rule 1.31(c)-(d) )、米国金融取引業規制機構規則 4511 (FINRA Rule 4511)、および米国証券取引委員会規則 17a-4 (SEC Rule 17a-4) における記憶域に関する該当要件に準拠することが、Cohasset により検証されました。これらの規則を検証の対象とした理由は、これらの規則は金融機関における記録保持に関する世界的に最も影響力のある規範のガイダンスであるためです。</span><span class="sxs-lookup"><span data-stu-id="028a8-p103">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="028a8-114">Cohasset 評価をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="028a8-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="028a8-115">[Cohasset 評価はこちらからダウンロード](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)できます。</span><span class="sxs-lookup"><span data-stu-id="028a8-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![ダウンロード可能な Cohasset Associates による評価のタイトル ページ](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="028a8-117">この評価は、Exchange Online に固有のものです</span><span class="sxs-lookup"><span data-stu-id="028a8-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="028a8-p104">この評価は Exchange Online に固有のものであることにご留意ください。将来的には SharePoint Online や OneDrive for Business などの他の Microsoft 365 サービスでも米国証券取引委員会規則 17a-4 (SEC Rule 17a-4) に関するサポートを予定していますが、これらのサービスは本評価には含まれません。</span><span class="sxs-lookup"><span data-stu-id="028a8-p104">Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="028a8-p105">Skype for Business および Teams も Exchange Online にデータを保存します。そのため、Skype for Business メッセージおよび Teams からのチャンネル メッセージおよびチャット メッセージも評価対象に含まれます。</span><span class="sxs-lookup"><span data-stu-id="028a8-p105">It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="028a8-122">推奨構成の鍵は保持ロックを使用することです</span><span class="sxs-lookup"><span data-stu-id="028a8-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="028a8-p106">規制が厳しい業界では多くの場合、WORM (書き込みは一度だけ、読み取りは何度でも) 要件に準拠するために電子通信の保存が義務づけられます。WORM 要件に準拠するストレージ ソリューションでは、記録に関して次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="028a8-p106">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="028a8-125">記録は義務づけられた保持期間保持される必要があります。保持期間を短縮することはできず、延長のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="028a8-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="028a8-126">記録は不変である必要があります。つまり、保持期間中は記録の上書き、消去、または変更をすることができません。</span><span class="sxs-lookup"><span data-stu-id="028a8-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="028a8-p107">Exchange Online では、ユーザーのメール ボックスに[アイテム保持ポリシー](retention.md)が適用された場合、ポリシーの条件に基づきユーザーのすべてのコンテンツが保持されます。実際に、ユーザーがメールの削除または変更を試みると、変更される前のメールのコピーがユーザーのメール ボックス内の保護された、非表示の場所に保存されます。アイテム保持ポリシーは組織での電子通信の保持を可能にしますが、それらのポリシーは変更することができます。</span><span class="sxs-lookup"><span data-stu-id="028a8-p107">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="028a8-p108">保持ロックをアイテム保持ポリシーに配置することにより、組織はポリシーの変更ができないようにすることができます。実際に、保持ロックがアイテム保持ポリシーに適用されると、次の操作が制限されます。</span><span class="sxs-lookup"><span data-stu-id="028a8-p108">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="028a8-132">ポリシーの保持期間は延長のみが可能で、短縮することはできません。</span><span class="sxs-lookup"><span data-stu-id="028a8-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="028a8-133">ユーザーをポリシーに追加することはできますが、ユーザーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="028a8-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="028a8-134">アイテム保持ポリシーを管理者が削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="028a8-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="028a8-135">保持ロックを使用して、米国証券取引委員会規則 17a-4 の規制要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="028a8-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="028a8-136">保持ロックを設定する方法</span><span class="sxs-lookup"><span data-stu-id="028a8-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="028a8-137">アイテム保持ポリシーは、PowerShell を使用してロックできます。</span><span class="sxs-lookup"><span data-stu-id="028a8-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="028a8-138">詳細については、「[[保持ロック] を使用して規制要件に準拠する](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="028a8-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="028a8-139">既知の制限</span><span class="sxs-lookup"><span data-stu-id="028a8-139">Known limitations</span></span>

<span data-ttu-id="028a8-140">現在、Exchange Online にはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="028a8-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="028a8-141">スレッド形式の通信は、Teams チャットおよびチャンネル メッセージでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="028a8-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="028a8-142">Teams チャットおよびチャンネル メッセージでの "いいね" は保持されません。</span><span class="sxs-lookup"><span data-stu-id="028a8-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="028a8-143">アイテム レベルの監査は Microsoft 365 グループのメールボックスで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="028a8-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="028a8-144">詳細については、「[メールボックスの監査を管理する](enable-mailbox-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="028a8-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
