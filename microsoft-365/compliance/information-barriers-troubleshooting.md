---
title: 情報バリアのトラブルシューティング
description: この記事は、情報障壁のトラブルシューティングのガイドとして使用します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126564"
---
# <a name="troubleshooting-information-barriers"></a><span data-ttu-id="6b56d-103">情報バリアのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6b56d-103">Troubleshooting information barriers</span></span>

<span data-ttu-id="6b56d-104">[情報障壁は、](information-barriers.md) 組織が法的要件や業界の規制に準拠し続けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-104">[Information barriers](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="6b56d-105">たとえば、情報バリアを使用すると、特定のユーザー グループ間の通信を制限して、利益の競合や他の問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="6b56d-106">(情報バリアを設定する方法の詳細については、「情報バリアのポリシーの定義」 [を参照してください](information-barriers-policies.md))。</span><span class="sxs-lookup"><span data-stu-id="6b56d-106">(To learn more about how to set up information barriers, see [Define policies for information barriers](information-barriers-policies.md).)</span></span>

<span data-ttu-id="6b56d-107">情報バリアが設定された後に予期しない問題が発生した場合は、それらの問題を解決するためにいくつかの手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="6b56d-108">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-108">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b56d-109">この記事で説明するタスクを実行するには、次のいずれかの適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="6b56d-110">- Microsoft 365 Enterprise グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6b56d-110">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="6b56d-111">- グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6b56d-111">- global administrator</span></span><br/><span data-ttu-id="6b56d-112">- コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6b56d-112">- Compliance Administrator</span></span><br/><span data-ttu-id="6b56d-113">-IB コンプライアンス管理 (これは新しい役割です)</span><span class="sxs-lookup"><span data-stu-id="6b56d-113">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="6b56d-114">情報バリアの前提条件の詳細については、「前提条件 (情報バリア ポリシーの [場合)」](information-barriers-policies.md#prerequisites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b56d-114">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="6b56d-115">セキュリティ センター [コンプライアンス センターの PowerShell &接続してください](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-115">Make sure to [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a><span data-ttu-id="6b56d-116">問題: Microsoft Teams の他のユーザーとの通信が予期せずブロックされる</span><span class="sxs-lookup"><span data-stu-id="6b56d-116">Issue: Users are unexpectedly blocked from communicating with others in Microsoft Teams</span></span> 

<span data-ttu-id="6b56d-117">この場合、Microsoft Teams で他のユーザーと通信する際に予期しない問題が報告されています。</span><span class="sxs-lookup"><span data-stu-id="6b56d-117">In this case, people are reporting unexpected issues communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="6b56d-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-118">Some examples are:</span></span>

- <span data-ttu-id="6b56d-119">ユーザーが Microsoft Teams で別のユーザーを検索しますが、見つからない場合。</span><span class="sxs-lookup"><span data-stu-id="6b56d-119">A user searches for, but is unable to find, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="6b56d-120">ユーザーは Microsoft Teams で別のユーザーを検索できますが、選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b56d-120">A user can find, but cannot select, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="6b56d-121">ユーザーは別のユーザーを表示できますが、Microsoft Teams で他のユーザーにメッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b56d-121">A user can see another user, but cannot send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="6b56d-122">操作</span><span class="sxs-lookup"><span data-stu-id="6b56d-122">What to do</span></span>

<span data-ttu-id="6b56d-123">ユーザーが情報バリア ポリシーの影響を受けるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-123">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="6b56d-124">ポリシーの構成方法によっては、情報バリアが期待通り動作している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-124">Depending on how policies are configured, information barriers might be working as expected.</span></span> <span data-ttu-id="6b56d-125">または、組織のポリシーを調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-125">Or, you might have to refine your organization's policies.</span></span>

1. <span data-ttu-id="6b56d-126">Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-126">Use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="6b56d-127">**構文**</span><span class="sxs-lookup"><span data-stu-id="6b56d-127">**Syntax**</span></span>|<span data-ttu-id="6b56d-128">**例**</span><span class="sxs-lookup"><span data-stu-id="6b56d-128">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> <span data-ttu-id="6b56d-129">名前、エイリアス、識別名 (DN)、正規 DN、電子メール アドレス、GUID など、各受信者を一意に識別する任意の ID 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-129">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> <span data-ttu-id="6b56d-130">この例では、Identity パラメーターにエイリアス (*meganb)* を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6b56d-130">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="6b56d-131">このコマンドレットは、ユーザーが情報バリア ポリシーの影響を受けるかどうかを示す情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-131">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="6b56d-132">(\*ExoPolicyId: を探します \<GUID> 。</span><span class="sxs-lookup"><span data-stu-id="6b56d-132">(Look for \*ExoPolicyId: \<GUID>.)</span></span> |

    <span data-ttu-id="6b56d-133">**ユーザーが情報バリア ポリシーに含まれていない場合は、サポートにお問い合わせください**。</span><span class="sxs-lookup"><span data-stu-id="6b56d-133">**If the users are not included in information barrier policies, contact support**.</span></span> <span data-ttu-id="6b56d-134">それ以外の場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="6b56d-134">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="6b56d-135">情報バリア ポリシーに含まれるセグメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-135">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="6b56d-136">これを行うには `Get-InformationBarrierPolicy` 、Identity パラメーターを指定してコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-136">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="6b56d-137">**構文**</span><span class="sxs-lookup"><span data-stu-id="6b56d-137">**Syntax**</span></span>|<span data-ttu-id="6b56d-138">**例**</span><span class="sxs-lookup"><span data-stu-id="6b56d-138">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> <span data-ttu-id="6b56d-139">前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を ID 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-139">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span> | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> <span data-ttu-id="6b56d-140">この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f* を持つ情報バリア ポリシーに関する詳細情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="6b56d-140">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span> |

    <span data-ttu-id="6b56d-141">コマンドレットを実行した後、結果で **AssignedSegment、SegmentsAllowed、\*\*\*\*および SegmentsBlocked** の値を探します。 </span><span class="sxs-lookup"><span data-stu-id="6b56d-141">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="6b56d-142">たとえば、コマンドレットの実行後 `Get-InformationBarrierPolicy` 、結果の一覧に次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-142">For example, after running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    <span data-ttu-id="6b56d-143">この場合、情報バリア ポリシーが Sales および Research セグメントに含まれるユーザーに影響を与えるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-143">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="6b56d-144">この場合、Sales のユーザーは Research のユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-144">In this case, people in Sales are prevented from communicating with people in Research.</span></span>

    <span data-ttu-id="6b56d-145">これが正しいと思われる場合、情報バリアは期待通り動作しています。</span><span class="sxs-lookup"><span data-stu-id="6b56d-145">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="6b56d-146">そうでない場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-146">If not, proceed to the next step.</span></span>

3. <span data-ttu-id="6b56d-147">セグメントが正しく定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-147">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="6b56d-148">これを行うには、コマンドレットを `Get-OrganizationSegment` 使用し、結果の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-148">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span>

    |<span data-ttu-id="6b56d-149">**構文**</span><span class="sxs-lookup"><span data-stu-id="6b56d-149">**Syntax**</span></span>|<span data-ttu-id="6b56d-150">**例**</span><span class="sxs-lookup"><span data-stu-id="6b56d-150">**Example**</span></span>|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> <span data-ttu-id="6b56d-151">このコマンドレットは Identity パラメーターと一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-151">Use this cmdlet with an Identity parameter.</span></span> | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> <span data-ttu-id="6b56d-152">この例では、GUID *が c96e0837-c232-4a8a-841e-ef45787d8fcd* であるセグメントに関する情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="6b56d-152">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span> |

    <span data-ttu-id="6b56d-153">セグメントの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-153">Review the details for the segment.</span></span> <span data-ttu-id="6b56d-154">必要に応 [じてセグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment)し、コマンドレットを再使用 `Start-InformationBarrierPoliciesApplication` します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-154">If necessary, [edit a segment](information-barriers-edit-segments-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="6b56d-155">**If you are still having issues with your information barrier policy, contact support**.</span><span class="sxs-lookup"><span data-stu-id="6b56d-155">**If you are still having issues with your information barrier policy, contact support**.</span></span>

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="6b56d-156">問題: Microsoft Teams でブロックする必要があるユーザー間の通信が許可されている</span><span class="sxs-lookup"><span data-stu-id="6b56d-156">Issue: Communications are allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="6b56d-157">この場合、情報バリアが定義され、アクティブで、適用されている場合でも、互いに通信を妨げる必要があるユーザーは、Microsoft Teams でチャットし、互いに通話することができます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-157">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other are somehow able to chat with and call each other in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="6b56d-158">操作</span><span class="sxs-lookup"><span data-stu-id="6b56d-158">What to do</span></span>

<span data-ttu-id="6b56d-159">該当するユーザーが情報バリア ポリシーに含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-159">Verify that the users in question are included in an information barrier policy.</span></span> 

1. <span data-ttu-id="6b56d-160">Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-160">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="6b56d-161">**構文** _</span><span class="sxs-lookup"><span data-stu-id="6b56d-161">**Syntax** _</span></span>|<span data-ttu-id="6b56d-162">_ *の例*\*</span><span class="sxs-lookup"><span data-stu-id="6b56d-162">_ *Example*\*</span></span>|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="6b56d-163">名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-163">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="6b56d-164">この例では、365 年 365 日に Office 2 つのユーザー アカウント *(megan* の場合は *meganb、Alex* の場合は *alexw)* を参照 *します*。</span><span class="sxs-lookup"><span data-stu-id="6b56d-164">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

    > [!TIP]
    > <span data-ttu-id="6b56d-165">このコマンドレットは、1 人のユーザーに対して使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="6b56d-165">You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`</span></span>

2. <span data-ttu-id="6b56d-166">結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-166">Review the findings.</span></span> <span data-ttu-id="6b56d-167">**Get-InformationBarrierRecipientStatus** コマンドレットは、属性値や適用されている情報バリア ポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-167">The **Get-InformationBarrierRecipientStatus** cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    <span data-ttu-id="6b56d-168">結果を確認し、次の表に示す手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-168">Review the results, and then take your next steps, as described in the following table:</span></span>

    |<span data-ttu-id="6b56d-169">**結果**</span><span class="sxs-lookup"><span data-stu-id="6b56d-169">**Results**</span></span>|<span data-ttu-id="6b56d-170">**次の操作**</span><span class="sxs-lookup"><span data-stu-id="6b56d-170">**What to do next**</span></span>|
    |:----------|:------------------|
    | <span data-ttu-id="6b56d-171">選択したユーザーのセグメントが一覧表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b56d-171">No segments are listed for the selected user(s)</span></span> | <span data-ttu-id="6b56d-172">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b56d-172">Do one of the following:</span></span><br/><span data-ttu-id="6b56d-173">- Azure Active Directory でユーザー プロファイルを編集して、既存のセグメントにユーザーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6b56d-173">- Assign users to an existing segment by editing their user profiles in Azure Active Directory.</span></span> <span data-ttu-id="6b56d-174">[(「365 PowerShell を使用してユーザー Officeを構成する」を参照](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)してください)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-174">(See [Configure user account properties with Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).)</span></span><br/><span data-ttu-id="6b56d-175">- 情報バリアでサポートされている [属性を使用してセグメントを定義します](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-175">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md).</span></span> <span data-ttu-id="6b56d-176">次に、新[しいポリシーを定義するか](information-barriers-policies.md#part-2-define-information-barrier-policies)[、既存のポリシーを編集して](information-barriers-edit-segments-policies.md#edit-a-policy)そのセグメントを含めるかのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="6b56d-176">Then, either [define a new policy](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit an existing policy](information-barriers-edit-segments-policies.md#edit-a-policy) to include that segment.</span></span> |
    | <span data-ttu-id="6b56d-177">セグメントが一覧表示されますが、それらのセグメントに情報バリア ポリシーが割り当てられていない</span><span class="sxs-lookup"><span data-stu-id="6b56d-177">Segments are listed but no information barrier policies are assigned to those segments</span></span> | <span data-ttu-id="6b56d-178">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6b56d-178">Do one of the following:</span></span><br/><span data-ttu-id="6b56d-179">- [問題のセグメントごとに新しい](information-barriers-policies.md#part-2-define-information-barrier-policies) 情報バリア ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="6b56d-179">- [Define a new information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span> <br/><span data-ttu-id="6b56d-180">- [既存の情報バリア ポリシーを編集して適切](information-barriers-edit-segments-policies.md#edit-a-policy) なセグメントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="6b56d-180">- [Edit an existing information barrier policy](information-barriers-edit-segments-policies.md#edit-a-policy) to assign it to the correct segment</span></span> |
    | <span data-ttu-id="6b56d-181">セグメントが一覧表示され、それぞれが情報バリア ポリシーに含まれる</span><span class="sxs-lookup"><span data-stu-id="6b56d-181">Segments are listed and each is included in an information barrier policy</span></span> | <span data-ttu-id="6b56d-182">- コマンドレットを `Get-InformationBarrierPolicy` 実行して情報バリア ポリシーがアクティブな状態を確認する</span><span class="sxs-lookup"><span data-stu-id="6b56d-182">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="6b56d-183">- コマンドレットを `Get-InformationBarrierPoliciesApplicationStatus` 実行してポリシーが適用されたのを確認する</span><span class="sxs-lookup"><span data-stu-id="6b56d-183">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="6b56d-184">- コマンドレットを実行 `Start-InformationBarrierPoliciesApplication` してすべてのアクティブな情報バリア ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="6b56d-184">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span> |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a><span data-ttu-id="6b56d-185">問題: 情報バリア ポリシーから 1 人のユーザーを削除する必要がある</span><span class="sxs-lookup"><span data-stu-id="6b56d-185">Issue: I need to remove a single user from an information barrier policy</span></span>

<span data-ttu-id="6b56d-186">この場合、情報バリア ポリシーが有効であり、1 人または複数のユーザーが Microsoft Teams の他のユーザーとの通信を予期せずブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-186">In this case, information barrier policies are in effect, and a one or more users are unexpectedly blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="6b56d-187">情報バリア ポリシーを完全に削除するのではなく、1 人または複数の個々のユーザーを情報バリア ポリシーから削除できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-187">Rather than remove information barrier policies altogether, you can remove one or more individual users from information barrier policies.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="6b56d-188">操作</span><span class="sxs-lookup"><span data-stu-id="6b56d-188">What to do</span></span>

<span data-ttu-id="6b56d-189">情報バリア ポリシーは、ユーザーのセグメントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-189">Information barrier policies are assigned to segments of users.</span></span> <span data-ttu-id="6b56d-190">セグメントは、ユーザー アカウント プロファイルの特定 [の属性を使用して定義されます](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-190">Segments are defined by using certain [attributes in user account profiles](information-barriers-attributes.md).</span></span> <span data-ttu-id="6b56d-191">1 人のユーザーからポリシーを削除する必要がある場合は、そのユーザーのプロファイルを Azure Active Directory で編集して、情報バリアの影響を受けるセグメントにユーザーが含めなくなるのを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6b56d-191">If you must remove a policy from a single user, consider editing that user's profile in Azure Active Directory such that the user is no longer included in a segment affected by information barriers.</span></span>

1. <span data-ttu-id="6b56d-192">Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-192">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <span data-ttu-id="6b56d-193">このコマンドレットは、属性値や適用されている情報バリア ポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-193">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    |<span data-ttu-id="6b56d-194">**構文**</span><span class="sxs-lookup"><span data-stu-id="6b56d-194">**Syntax**</span></span>|<span data-ttu-id="6b56d-195">**例**</span><span class="sxs-lookup"><span data-stu-id="6b56d-195">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="6b56d-196">名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-196">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="6b56d-197">この例では、365 年 365 日に Office 2 つのユーザー アカウント *(megan* の場合は *meganb、Alex* の場合は *alexw)* を参照 *します*。</span><span class="sxs-lookup"><span data-stu-id="6b56d-197">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> <span data-ttu-id="6b56d-198">名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-198">You can use any value that uniquely identifies the user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span>|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> <span data-ttu-id="6b56d-199">この例では、365 年 1 月 365 Officeアカウントを *参照します*。</span><span class="sxs-lookup"><span data-stu-id="6b56d-199">In this example, we refer to a single account in Office 365: *jeanp*.</span></span> |

2. <span data-ttu-id="6b56d-200">結果を確認して、情報バリア ポリシーが割り当てられているか、ユーザーが属するセグメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-200">Review the results to see if information barrier policies are assigned, and to which segment(s) the user(s) belong.</span></span>

3. <span data-ttu-id="6b56d-201">情報バリアの影響を受けるセグメントからユーザーを削除するには、Azure Active Directory でユーザーのプロファイル [情報を更新します](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-201">To remove a user from a segment affected by information barriers, [update the user's profile information in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

4. <span data-ttu-id="6b56d-202">FwdSync が発生するまで約 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-202">Wait about 30 minutes for FwdSync to occur.</span></span> <span data-ttu-id="6b56d-203">または、コマンドレットを実行 `Start-InformationBarrierPoliciesApplication` してすべてのアクティブな情報バリア ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-203">Or, run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies.</span></span>

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="6b56d-204">問題: 情報バリア アプリケーション プロセスに時間がかかっている</span><span class="sxs-lookup"><span data-stu-id="6b56d-204">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="6b56d-205">**Start-InformationBarrierPoliciesApplication** コマンドレットを実行した後、プロセスが完了するには非常に長い時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b56d-205">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="6b56d-206">操作</span><span class="sxs-lookup"><span data-stu-id="6b56d-206">What to do</span></span>

<span data-ttu-id="6b56d-207">ポリシー アプリケーションコマンドレットを実行すると、組織内のすべてのアカウントに対して、ユーザー別に情報バリア ポリシーが適用 (または削除) されます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-207">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="6b56d-208">ユーザーが多い場合は、処理に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-208">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="6b56d-209">(一般的なガイドラインとして、5,000 のユーザー アカウントの処理には約 1 時間かかる)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-209">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="6b56d-210">**Get-InformationBarrierPoliciesApplicationStatus** コマンドレットを使用して、最新のポリシー アプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-210">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    |<span data-ttu-id="6b56d-211">**最新のポリシー アプリケーションを表示するには**</span><span class="sxs-lookup"><span data-stu-id="6b56d-211">**To view the most recent policy application**</span></span>|<span data-ttu-id="6b56d-212">**すべてのポリシー アプリケーションの状態を表示するには**</span><span class="sxs-lookup"><span data-stu-id="6b56d-212">**To view status for all policy applications**</span></span>|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    <span data-ttu-id="6b56d-213">これにより、ポリシー アプリケーションが完了した、失敗した、または進行中かどうかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-213">This will display information about whether policy application completed, failed, or is in progress.</span></span>

2. <span data-ttu-id="6b56d-214">前の手順の結果に応じて、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-214">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="6b56d-215">**状態**</span><span class="sxs-lookup"><span data-stu-id="6b56d-215">**Status**</span></span>|<span data-ttu-id="6b56d-216">**次の手順**</span><span class="sxs-lookup"><span data-stu-id="6b56d-216">**Next step**</span></span>|
    |:---------|:------------|
    | <span data-ttu-id="6b56d-217">**開始されていない**</span><span class="sxs-lookup"><span data-stu-id="6b56d-217">**Not started**</span></span> | <span data-ttu-id="6b56d-218">**Start-InformationBarrierPoliciesApplication** コマンドレットの実行から 45 分以上経っている場合は、監査ログを確認して、ポリシー定義にエラーが発生していないか、またはアプリケーションが起動していない理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-218">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    | <span data-ttu-id="6b56d-219">**Failed**</span><span class="sxs-lookup"><span data-stu-id="6b56d-219">**Failed**</span></span> | <span data-ttu-id="6b56d-220">アプリケーションが失敗した場合は、監査ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-220">If the application has failed, review your audit log.</span></span> <span data-ttu-id="6b56d-221">また、セグメントとポリシーも確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-221">Also review your segments and policies.</span></span> <span data-ttu-id="6b56d-222">複数のセグメントに割り当てられているユーザーはいますか?</span><span class="sxs-lookup"><span data-stu-id="6b56d-222">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="6b56d-223">複数のポリシーが割り当てられているセグメントはありますか?</span><span class="sxs-lookup"><span data-stu-id="6b56d-223">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="6b56d-224">必要に応 [じて、セグメント](information-barriers-edit-segments-policies.md#edit-a-segment)の編集や [](information-barriers-edit-segments-policies.md#edit-a-policy)ポリシーの編集を行い **、Start-InformationBarrierPoliciesApplication** コマンドレットを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-224">If necessary, [edit segments](information-barriers-edit-segments-policies.md#edit-a-segment) and/or [edit policies](information-barriers-edit-segments-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span> |
    | <span data-ttu-id="6b56d-225">**処理中**</span><span class="sxs-lookup"><span data-stu-id="6b56d-225">**In progress**</span></span> | <span data-ttu-id="6b56d-226">アプリケーションがまだ進行中の場合は、完了までさらに時間を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-226">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="6b56d-227">数日が過ごした場合は、監査ログを収集し、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6b56d-227">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a><span data-ttu-id="6b56d-228">問題: 情報バリア ポリシーが適用されていない</span><span class="sxs-lookup"><span data-stu-id="6b56d-228">Issue: Information barrier policies are not being applied at all</span></span>

<span data-ttu-id="6b56d-229">この場合、セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーの適用を試みたとします。</span><span class="sxs-lookup"><span data-stu-id="6b56d-229">In this case, you have defined segments, defined information barrier policies, and have attempted to apply those policies.</span></span> <span data-ttu-id="6b56d-230">ただし、コマンドレットを実行すると `Get-InformationBarrierPoliciesApplicationStatus` 、ポリシー アプリケーションが失敗しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-230">However, when you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, you can see that policy application has failed.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="6b56d-231">操作</span><span class="sxs-lookup"><span data-stu-id="6b56d-231">What to do</span></span>

<span data-ttu-id="6b56d-232">組織に Exchange アドレス帳ポリシー [が設定されていないことを](/exchange/address-books/address-book-policies/address-book-policies) 確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-232">Make sure that your organization does not have [Exchange address book policies](/exchange/address-books/address-book-policies/address-book-policies) in place.</span></span> <span data-ttu-id="6b56d-233">このようなポリシーは、情報バリア ポリシーの適用を防止します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-233">Such policies will prevent information barrier policies from being applied.</span></span>

1. <span data-ttu-id="6b56d-234">[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する</span><span class="sxs-lookup"><span data-stu-id="6b56d-234">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6b56d-235">[Get-AddressBookPolicy コマンドレットを実行](/powershell/module/exchange/get-addressbookpolicy)し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-235">Run the [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet, and review the results.</span></span>

    |<span data-ttu-id="6b56d-236">**結果**</span><span class="sxs-lookup"><span data-stu-id="6b56d-236">**Results**</span></span>|<span data-ttu-id="6b56d-237">**次の手順**</span><span class="sxs-lookup"><span data-stu-id="6b56d-237">**Next step**</span></span>|
    |:----------|:------------|
    | <span data-ttu-id="6b56d-238">Exchange アドレス帳ポリシーが一覧表示される</span><span class="sxs-lookup"><span data-stu-id="6b56d-238">Exchange address book policies are listed</span></span> | [<span data-ttu-id="6b56d-239">アドレス帳ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6b56d-239">Remove address book policies</span></span>](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | <span data-ttu-id="6b56d-240">アドレス帳ポリシーが存在しない</span><span class="sxs-lookup"><span data-stu-id="6b56d-240">No address book policies exist</span></span> |<span data-ttu-id="6b56d-241">監査ログを確認して、ポリシー アプリケーションが失敗する理由を確認する</span><span class="sxs-lookup"><span data-stu-id="6b56d-241">Review your audit logs to find out why policy application is failing</span></span> |

3. <span data-ttu-id="6b56d-242">[ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示します](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-242">[View status of user accounts, segments, policies, or policy application](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).</span></span>

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a><span data-ttu-id="6b56d-243">問題: 指定されたユーザーに適用されない情報バリア ポリシー</span><span class="sxs-lookup"><span data-stu-id="6b56d-243">Issue: Information barrier policy not applied to all designated users</span></span>

<span data-ttu-id="6b56d-244">セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーを適用しようとすると、ポリシーが一部の受信者に適用されますが、他の受信者には適用されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-244">After you have defined segments, defined information barrier policies, and have attempted to apply those policies, you may find that the policy is applying to some recipients, but not to others.</span></span>
<span data-ttu-id="6b56d-245">コマンドレットを実行すると `Get-InformationBarrierPoliciesApplicationStatus` 、出力で次のようなテキストが検索されます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-245">When you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, search the output for text like this.</span></span>

> <span data-ttu-id="6b56d-246">ID: `<application guid>`</span><span class="sxs-lookup"><span data-stu-id="6b56d-246">Identity: `<application guid>`</span></span>
>
> <span data-ttu-id="6b56d-247">Total Recipients: 81527</span><span class="sxs-lookup"><span data-stu-id="6b56d-247">Total Recipients: 81527</span></span>
>
> <span data-ttu-id="6b56d-248">失敗した受信者: 2</span><span class="sxs-lookup"><span data-stu-id="6b56d-248">Failed Recipients: 2</span></span>
>
> <span data-ttu-id="6b56d-249">エラー カテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="6b56d-249">Failure Category: None</span></span>
>
> <span data-ttu-id="6b56d-250">状態: 完了</span><span class="sxs-lookup"><span data-stu-id="6b56d-250">Status: Complete</span></span>

### <a name="what-to-do"></a><span data-ttu-id="6b56d-251">操作</span><span class="sxs-lookup"><span data-stu-id="6b56d-251">What to do</span></span>

1. <span data-ttu-id="6b56d-252">監査ログで検索します `<application guid>` 。</span><span class="sxs-lookup"><span data-stu-id="6b56d-252">Search in the audit log for `<application guid>`.</span></span> <span data-ttu-id="6b56d-253">この PowerShell コードをコピーし、変数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-253">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. <span data-ttu-id="6b56d-254">監査ログからの詳細な出力で、フィールドの値を `"UserId"` 確認 `"ErrorDetails"` します。</span><span class="sxs-lookup"><span data-stu-id="6b56d-254">Check the detailed output from the audit log for the values of the `"UserId"` and `"ErrorDetails"` fields.</span></span> <span data-ttu-id="6b56d-255">これにより、エラーの理由が示されます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-255">This will give you the reason for the failure.</span></span> <span data-ttu-id="6b56d-256">この PowerShell コードをコピーし、変数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b56d-256">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
   $DetailedLogs[1] |fl
```

<span data-ttu-id="6b56d-257">例:</span><span class="sxs-lookup"><span data-stu-id="6b56d-257">For example:</span></span>

> <span data-ttu-id="6b56d-258">"UserId": User1</span><span class="sxs-lookup"><span data-stu-id="6b56d-258">"UserId":  User1</span></span>
>
><span data-ttu-id="6b56d-259">"ErrorDetails":"Status:IBPolicyConflict.</span><span class="sxs-lookup"><span data-stu-id="6b56d-259">"ErrorDetails":"Status: IBPolicyConflict.</span></span> <span data-ttu-id="6b56d-260">エラー: "segment id1" と"segment id2" の間に競合が発生し、受信者に割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="6b56d-260">Error: IB  segment "segment id1" and IB segment "segment id2" has conflict and cannot be assigned to the recipient.</span></span>

3. <span data-ttu-id="6b56d-261">通常、ユーザーが複数のセグメントに含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b56d-261">Usually, you will find that a user has been included in more than one segment.</span></span> <span data-ttu-id="6b56d-262">You can fix this by updating the `-UserGroupFilter` value in `OrganizationSegments` .</span><span class="sxs-lookup"><span data-stu-id="6b56d-262">You can fix this by updating the `-UserGroupFilter` value in `OrganizationSegments`.</span></span>

4. <span data-ttu-id="6b56d-263">これらの手順を使用して、情報バリア ポリシーを再 [適用します](information-barriers-policies.md#part-3-apply-information-barrier-policies)。</span><span class="sxs-lookup"><span data-stu-id="6b56d-263">Re-apply information barrier policies using these procedures [Information Barriers policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).</span></span>

## <a name="resources"></a><span data-ttu-id="6b56d-264">リソース</span><span class="sxs-lookup"><span data-stu-id="6b56d-264">Resources</span></span>

- [<span data-ttu-id="6b56d-265">Microsoft Teams での情報障壁のポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="6b56d-265">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="6b56d-266">情報障壁</span><span class="sxs-lookup"><span data-stu-id="6b56d-266">Information barriers</span></span>](information-barriers.md)
