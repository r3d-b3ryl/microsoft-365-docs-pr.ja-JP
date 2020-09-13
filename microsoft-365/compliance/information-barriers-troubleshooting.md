---
title: 情報バリアのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e19c7d22e2b34d3f8083bcf5b8fb7297dbf86229
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545671"
---
# <a name="troubleshooting-information-barriers"></a><span data-ttu-id="8e1bf-103">情報バリアのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8e1bf-103">Troubleshooting information barriers</span></span>

<span data-ttu-id="8e1bf-104">[情報バリア](information-barriers.md) は、組織が法的な要件や業界の規制に準拠していることを支援します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-104">[Information barriers](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="8e1bf-105">たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="8e1bf-106">(情報障壁の設定方法の詳細については、「 [Define policies for information バリア](information-barriers-policies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-106">(To learn more about how to set up information barriers, see [Define policies for information barriers](information-barriers-policies.md).)</span></span>

<span data-ttu-id="8e1bf-107">情報の障壁が設定された後に予期しない問題が発生した場合は、それらの問題を解決するために実行できるいくつかの手順があります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="8e1bf-108">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-108">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e1bf-109">この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="8e1bf-110">-Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8e1bf-110">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="8e1bf-111">-全体管理者</span><span class="sxs-lookup"><span data-stu-id="8e1bf-111">- global administrator</span></span><br/><span data-ttu-id="8e1bf-112">-コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8e1bf-112">- Compliance Administrator</span></span><br/><span data-ttu-id="8e1bf-113">-IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="8e1bf-113">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="8e1bf-114">情報障壁の前提条件の詳細については、「 [必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-114">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="8e1bf-115">[セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-115">Make sure to [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a><span data-ttu-id="8e1bf-116">問題: ユーザーが予期せず Microsoft Teams の他のユーザーとの通信をブロックされている</span><span class="sxs-lookup"><span data-stu-id="8e1bf-116">Issue: Users are unexpectedly blocked from communicating with others in Microsoft Teams</span></span> 

<span data-ttu-id="8e1bf-117">この場合、ユーザーは、Microsoft Teams の他のユーザーとの間で予期しない問題を報告しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-117">In this case, people are reporting unexpected issues communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="8e1bf-118">例:</span><span class="sxs-lookup"><span data-stu-id="8e1bf-118">Examples:</span></span>
- <span data-ttu-id="8e1bf-119">ユーザーがを検索しましたが、Microsoft Teams の別のユーザーを検索できません。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-119">A user searches for, but is unable to find, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="8e1bf-120">ユーザーは、Microsoft Teams の別のユーザーを検索できますが、選択できません。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-120">A user can find, but cannot select, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="8e1bf-121">ユーザーは別のユーザーを表示できますが、Microsoft Teams 内の他のユーザーにメッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-121">A user can see another user, but cannot send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8e1bf-122">操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-122">What to do</span></span>

<span data-ttu-id="8e1bf-123">ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-123">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="8e1bf-124">ポリシーの構成方法によっては、情報の障壁が期待どおりに機能している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-124">Depending on how policies are configured, information barriers might be working as expected.</span></span> <span data-ttu-id="8e1bf-125">または、組織のポリシーを調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-125">Or, you might have to refine your organization's policies.</span></span>

1. <span data-ttu-id="8e1bf-126">Identity パラメーターを指定して **InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-126">Use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="8e1bf-127">構文</span><span class="sxs-lookup"><span data-stu-id="8e1bf-127">Syntax</span></span>  |<span data-ttu-id="8e1bf-128">例</span><span class="sxs-lookup"><span data-stu-id="8e1bf-128">Example</span></span>  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p><span data-ttu-id="8e1bf-129">名前、エイリアス、識別名 (DN)、標準 DN、電子メールアドレス、GUID など、各受信者を一意に識別する任意の id 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-129">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p><span data-ttu-id="8e1bf-130">この例では、Identity パラメーターに alias (*meガント b*) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-130">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="8e1bf-131">このコマンドレットは、ユーザーが情報バリアポリシーの影響を受けているかどうかを示す情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-131">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="8e1bf-132">(\* ExoPolicyId を検索 \<GUID> します。)</span><span class="sxs-lookup"><span data-stu-id="8e1bf-132">(Look for \*ExoPolicyId: \<GUID>.)</span></span>         |

    <span data-ttu-id="8e1bf-133">**ユーザーが情報バリアポリシーに含まれていない場合は、サポートにお問い合わせください**。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-133">**If the users are not included in information barrier policies, contact support**.</span></span> <span data-ttu-id="8e1bf-134">それ以外の場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-134">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="8e1bf-135">情報バリアポリシーに含まれるセグメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-135">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="8e1bf-136">これを行うには、 `Get-InformationBarrierPolicy` Identity パラメーターを指定したコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-136">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="8e1bf-137">構文</span><span class="sxs-lookup"><span data-stu-id="8e1bf-137">Syntax</span></span>  |<span data-ttu-id="8e1bf-138">例</span><span class="sxs-lookup"><span data-stu-id="8e1bf-138">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p><span data-ttu-id="8e1bf-139">前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を identity 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-139">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p><span data-ttu-id="8e1bf-140">この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*を持つ情報バリアポリシーに関する詳細情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-140">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>         |

    <span data-ttu-id="8e1bf-141">コマンドレットを実行した後、結果で **AssignedSegment**、 **SegmentsAllowed**、および **SegmentsBlocked** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-141">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="8e1bf-142">たとえば、コマンドレットを実行した後、 `Get-InformationBarrierPolicy` 結果の一覧で次のように表示されています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-142">For example, after running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="8e1bf-143">この場合、情報バリアポリシーが [営業] および [リサーチ] セグメントにあるユーザーに影響を与えることがわかります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-143">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="8e1bf-144">この場合、営業担当者は研究中の人々とコミュニケーションすることができません。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-144">In this case, people in Sales are prevented from communicating with people in Research.</span></span> 
    
    <span data-ttu-id="8e1bf-145">これが正しいように思われる場合は、情報バリアが期待どおりに機能しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-145">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="8e1bf-146">そうでない場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-146">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="8e1bf-147">セグメントが正しく定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-147">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="8e1bf-148">これを行うには、 `Get-OrganizationSegment` コマンドレットを使用して、結果の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-148">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    |<span data-ttu-id="8e1bf-149">構文</span><span class="sxs-lookup"><span data-stu-id="8e1bf-149">Syntax</span></span>  |<span data-ttu-id="8e1bf-150">例</span><span class="sxs-lookup"><span data-stu-id="8e1bf-150">Example</span></span>  |
    |---------|---------|
    |`Get-OrganizationSegment`<p><span data-ttu-id="8e1bf-151">このコマンドレットを Identity パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-151">Use this cmdlet with an Identity parameter.</span></span>     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p><span data-ttu-id="8e1bf-152">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントについての情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-152">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>         |

    <span data-ttu-id="8e1bf-153">セグメントの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-153">Review the details for the segment.</span></span> <span data-ttu-id="8e1bf-154">必要に応じて、 [セグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment)してから、コマンドレットを再度使用し `Start-InformationBarrierPoliciesApplication` ます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-154">If necessary, [edit a segment](information-barriers-edit-segments-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="8e1bf-155">**情報バリアポリシーに問題がある場合は、サポートにお問い合わせください**。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-155">**If you are still having issues with your information barrier policy, contact support**.</span></span>

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="8e1bf-156">問題: Microsoft Teams でブロックする必要があるユーザー間で通信が許可されている</span><span class="sxs-lookup"><span data-stu-id="8e1bf-156">Issue: Communications are allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="8e1bf-157">この場合、情報バリアは定義、アクティブ、および適用されますが、相互に通信できないようにする必要があるユーザーは、Microsoft Teams で互いにチャットして通話することができます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-157">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other are somehow able to chat with and call each other in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8e1bf-158">操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-158">What to do</span></span>

<span data-ttu-id="8e1bf-159">該当するユーザーが情報バリアポリシーに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-159">Verify that the users in question are included in an information barrier policy.</span></span> 

1. <span data-ttu-id="8e1bf-160">Identity パラメーターを使用して **InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-160">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="8e1bf-161">構文</span><span class="sxs-lookup"><span data-stu-id="8e1bf-161">Syntax</span></span>  |<span data-ttu-id="8e1bf-162">例</span><span class="sxs-lookup"><span data-stu-id="8e1bf-162">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p><span data-ttu-id="8e1bf-163">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-163">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span>     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p><span data-ttu-id="8e1bf-164">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-164">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>          |

    
    > [!TIP]
    > <span data-ttu-id="8e1bf-165">1人のユーザーに対してこのコマンドレットを使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="8e1bf-165">You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`</span></span>
    
2. <span data-ttu-id="8e1bf-166">結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-166">Review the findings.</span></span> <span data-ttu-id="8e1bf-167">**InformationBarrierRecipientStatus**コマンドレットでは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-167">The **Get-InformationBarrierRecipientStatus** cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span> 

    <span data-ttu-id="8e1bf-168">結果を確認し、次の表に示すように、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-168">Review the results, and then take your next steps, as described in the following table:</span></span>
    
    |<span data-ttu-id="8e1bf-169">結果</span><span class="sxs-lookup"><span data-stu-id="8e1bf-169">Results</span></span>  |<span data-ttu-id="8e1bf-170">次の操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-170">What to do next</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8e1bf-171">選択したユーザーのセグメントが表示されません</span><span class="sxs-lookup"><span data-stu-id="8e1bf-171">No segments are listed for the selected user(s)</span></span>     |<span data-ttu-id="8e1bf-172">以下のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-172">Do one of the following:</span></span><br/><span data-ttu-id="8e1bf-173">-Azure Active Directory でユーザープロファイルを編集して、ユーザーを既存のセグメントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-173">- Assign users to an existing segment by editing their user profiles in Azure Active Directory.</span></span> <span data-ttu-id="8e1bf-174">(「 [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する」を](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-174">(See [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).)</span></span><br/><span data-ttu-id="8e1bf-175">- [情報バリアに対してサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-175">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md).</span></span> <span data-ttu-id="8e1bf-176">次に、 [新しいポリシーを定義](information-barriers-policies.md#part-2-define-information-barrier-policies) するか、 [既存のポリシーを編集](information-barriers-edit-segments-policies.md#edit-a-policy) してそのセグメントを含めます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-176">Then, either [define a new policy](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit an existing policy](information-barriers-edit-segments-policies.md#edit-a-policy) to include that segment.</span></span>  |
    |<span data-ttu-id="8e1bf-177">セグメントは表示されますが、これらのセグメントに情報バリアポリシーが割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="8e1bf-177">Segments are listed but no information barrier policies are assigned to those segments</span></span>     |<span data-ttu-id="8e1bf-178">以下のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-178">Do one of the following:</span></span><br/><span data-ttu-id="8e1bf-179">- 対象のセグメントごとに[新しい情報バリアポリシーを定義する](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="8e1bf-179">- [Define a new information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span><br/><span data-ttu-id="8e1bf-180">- [既存の情報バリアポリシーを編集](information-barriers-edit-segments-policies.md#edit-a-policy) して正しいセグメントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8e1bf-180">- [Edit an existing information barrier policy](information-barriers-edit-segments-policies.md#edit-a-policy) to assign it to the correct segment</span></span>         |
    |<span data-ttu-id="8e1bf-181">セグメントがリストされ、それぞれが情報バリアポリシーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-181">Segments are listed and each is included in an information barrier policy</span></span>     |<span data-ttu-id="8e1bf-182">-コマンドレットを実行して、 `Get-InformationBarrierPolicy` 情報バリアポリシーがアクティブであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-182">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="8e1bf-183">- `Get-InformationBarrierPoliciesApplicationStatus` コマンドレットを実行してポリシーが適用されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8e1bf-183">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="8e1bf-184">-すべての `Start-InformationBarrierPoliciesApplication` アクティブ情報バリアポリシーを適用するには、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-184">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span>          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a><span data-ttu-id="8e1bf-185">問題: 情報バリアポリシーから1人のユーザーを削除する必要がある</span><span class="sxs-lookup"><span data-stu-id="8e1bf-185">Issue: I need to remove a single user from an information barrier policy</span></span>

<span data-ttu-id="8e1bf-186">この場合、情報バリアポリシーが有効になっており、1人以上のユーザーが予期せず Microsoft Teams 内の他のユーザーとの通信をブロックされています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-186">In this case, information barrier policies are in effect, and a one or more users are unexpectedly blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="8e1bf-187">情報バリアポリシーを完全に削除するのではなく、1人または複数の個別のユーザーを情報バリアポリシーから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-187">Rather than remove information barrier policies altogether, you can remove one or more individual users from information barrier policies.</span></span> 

### <a name="what-to-do"></a><span data-ttu-id="8e1bf-188">操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-188">What to do</span></span>

<span data-ttu-id="8e1bf-189">情報バリアポリシーは、ユーザーのセグメントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-189">Information barrier policies are assigned to segments of users.</span></span> <span data-ttu-id="8e1bf-190">セグメントは、 [ユーザーアカウントプロファイルの特定の属性](information-barriers-attributes.md)を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-190">Segments are defined by using certain [attributes in user account profiles](information-barriers-attributes.md).</span></span> <span data-ttu-id="8e1bf-191">単一のユーザーからポリシーを削除する必要がある場合は、そのユーザーのプロファイルを Azure Active Directory で編集することを検討してください。これは、ユーザーが情報障壁の影響を受けるセグメントに含まれなくなったことです。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-191">If you must remove a policy from a single user, consider editing that user's profile in Azure Active Directory such that the user is no longer included in a segment affected by information barriers.</span></span>

1. <span data-ttu-id="8e1bf-192">Identity パラメーターを使用して **InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-192">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <span data-ttu-id="8e1bf-193">このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-193">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    |<span data-ttu-id="8e1bf-194">構文</span><span class="sxs-lookup"><span data-stu-id="8e1bf-194">Syntax</span></span>  |<span data-ttu-id="8e1bf-195">例</span><span class="sxs-lookup"><span data-stu-id="8e1bf-195">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p><span data-ttu-id="8e1bf-196">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-196">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span>     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p><span data-ttu-id="8e1bf-197">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-197">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p><span data-ttu-id="8e1bf-198">ユーザーを一意に識別する任意の値 (名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-198">You can use any value that uniquely identifies the user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span>|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p><span data-ttu-id="8e1bf-199">この例では、Office 365: *jeanp*で1つのアカウントを参照します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-199">In this example, we refer to a single account in Office 365: *jeanp*.</span></span> |

2. <span data-ttu-id="8e1bf-200">結果を確認して、情報バリアポリシーが割り当てられているかどうか、およびユーザーが属するセグメントがどれかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-200">Review the results to see if information barrier policies are assigned, and to which segment(s) the user(s) belong.</span></span> 

3. <span data-ttu-id="8e1bf-201">情報バリアの影響を受けるセグメントからユーザーを削除するには、 [Azure Active Directory でユーザーのプロファイル情報を更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-201">To remove a user from a segment affected by information barriers, [update the user's profile information in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

4. <span data-ttu-id="8e1bf-202">FwdSync が実行されるまで30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-202">Wait about 30 minutes for FwdSync to occur.</span></span> <span data-ttu-id="8e1bf-203">または、コマンドレットを実行して、 `Start-InformationBarrierPoliciesApplication` すべてのアクティブな情報バリアポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-203">Or, run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies.</span></span>

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="8e1bf-204">問題: 情報バリアアプリケーションプロセスで時間がかかりすぎています</span><span class="sxs-lookup"><span data-stu-id="8e1bf-204">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="8e1bf-205">**InformationBarrierPoliciesApplication**コマンドレットを実行した後、プロセスが完了するまでに長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-205">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8e1bf-206">操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-206">What to do</span></span>

<span data-ttu-id="8e1bf-207">Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-207">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="8e1bf-208">ユーザー数が多い場合は、処理に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-208">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="8e1bf-209">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-209">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="8e1bf-210">最新のポリシーアプリケーションの状態を確認するには、 **InformationBarrierPoliciesApplicationStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-210">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    |<span data-ttu-id="8e1bf-211">最新のポリシーアプリケーションを表示するには</span><span class="sxs-lookup"><span data-stu-id="8e1bf-211">To view the most recent policy application</span></span>  |<span data-ttu-id="8e1bf-212">すべてのポリシーアプリケーションの状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="8e1bf-212">To view status for all policy applications</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    <span data-ttu-id="8e1bf-213">これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-213">This will display information about whether policy application completed, failed, or is in progress.</span></span>

2. <span data-ttu-id="8e1bf-214">前の手順の結果に応じて、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-214">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="8e1bf-215">状態</span><span class="sxs-lookup"><span data-stu-id="8e1bf-215">Status</span></span>  |<span data-ttu-id="8e1bf-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="8e1bf-216">Next step</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8e1bf-217">**未開始**</span><span class="sxs-lookup"><span data-stu-id="8e1bf-217">**Not started**</span></span>     |<span data-ttu-id="8e1bf-218">**InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを調べて、ポリシー定義にエラーがないかどうか、またはアプリケーションが開始されていない理由を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-218">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    |<span data-ttu-id="8e1bf-219">**失敗**</span><span class="sxs-lookup"><span data-stu-id="8e1bf-219">**Failed**</span></span>     |<span data-ttu-id="8e1bf-220">アプリケーションに障害が発生した場合は、監査ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-220">If the application has failed, review your audit log.</span></span> <span data-ttu-id="8e1bf-221">また、セグメントとポリシーも確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-221">Also review your segments and policies.</span></span> <span data-ttu-id="8e1bf-222">複数のセグメントに割り当てられているユーザーはいますか?</span><span class="sxs-lookup"><span data-stu-id="8e1bf-222">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="8e1bf-223">セグメントに複数の poliicy が割り当てられているかどうか。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-223">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="8e1bf-224">必要に応じて、 [セグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment) するか、または [ポリシーを編集](information-barriers-edit-segments-policies.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication** コマンドレットを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-224">If necessary, [edit segments](information-barriers-edit-segments-policies.md#edit-a-segment) and/or [edit policies](information-barriers-edit-segments-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>  |
    |<span data-ttu-id="8e1bf-225">**処理中**</span><span class="sxs-lookup"><span data-stu-id="8e1bf-225">**In progress**</span></span>     |<span data-ttu-id="8e1bf-226">アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-226">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="8e1bf-227">数日経過した場合は、監査ログを収集し、サポートに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-227">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a><span data-ttu-id="8e1bf-228">問題: 情報バリアポリシーがまったく適用されていない</span><span class="sxs-lookup"><span data-stu-id="8e1bf-228">Issue: Information barrier policies are not being applied at all</span></span>

<span data-ttu-id="8e1bf-229">この例では、セグメントを定義し、情報のバリアポリシーを定義し、それらのポリシーを適用しようとしました。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-229">In this case, you have defined segments, defined information barrier policies, and have attempted to apply those policies.</span></span> <span data-ttu-id="8e1bf-230">ただし、コマンドレットを実行すると、 `Get-InformationBarrierPoliciesApplicationStatus` ポリシーアプリケーションが失敗したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-230">However, when you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, you can see that policy application has failed.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8e1bf-231">操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-231">What to do</span></span>

<span data-ttu-id="8e1bf-232">組織に [Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) が設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-232">Make sure that your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in place.</span></span> <span data-ttu-id="8e1bf-233">このようなポリシーにより、情報バリアポリシーが適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-233">Such policies will prevent information barrier policies from being applied.</span></span>

1. <span data-ttu-id="8e1bf-234">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) に接続する</span><span class="sxs-lookup"><span data-stu-id="8e1bf-234">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> 

2. <span data-ttu-id="8e1bf-235">[AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy)コマンドレットを実行し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-235">Run the [Get-AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy) cmdlet, and review the results.</span></span>

    |<span data-ttu-id="8e1bf-236">結果</span><span class="sxs-lookup"><span data-stu-id="8e1bf-236">Results</span></span>  |<span data-ttu-id="8e1bf-237">次の手順</span><span class="sxs-lookup"><span data-stu-id="8e1bf-237">Next step</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8e1bf-238">Exchange アドレス帳ポリシーの一覧</span><span class="sxs-lookup"><span data-stu-id="8e1bf-238">Exchange address book policies are listed</span></span>     |[<span data-ttu-id="8e1bf-239">アドレス帳ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="8e1bf-239">Remove address book policies</span></span>](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |<span data-ttu-id="8e1bf-240">アドレス帳ポリシーが存在しません</span><span class="sxs-lookup"><span data-stu-id="8e1bf-240">No address book policies exist</span></span> |<span data-ttu-id="8e1bf-241">ポリシーアプリケーションが失敗している理由を確認するには、監査ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-241">Review your audit logs to find out why policy application is failing</span></span> |

3. <span data-ttu-id="8e1bf-242">[ユーザーアカウント、セグメント、ポリシー、またはポリシーアプリケーションの状態を表示](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-242">[View status of user accounts, segments, policies, or policy application](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).</span></span>

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a><span data-ttu-id="8e1bf-243">問題: 情報バリアポリシーが指定したすべてのユーザーに適用されない</span><span class="sxs-lookup"><span data-stu-id="8e1bf-243">Issue: Information barrier policy not applied to all designated users</span></span>

<span data-ttu-id="8e1bf-244">セグメントを定義し、定義された情報バリアポリシーを適用した後、それらのポリシーを適用しようとすると、そのポリシーは一部の受信者に適用されますが、他の受信者には適用されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-244">After you have defined segments, defined information barrier policies, and have attempted to apply those policies, you may find that the policy is applying to some recipients, but not to others.</span></span>
<span data-ttu-id="8e1bf-245">コマンドレットを実行するときは `Get-InformationBarrierPoliciesApplicationStatus` 、次のようなテキストの出力を検索します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-245">When you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, search the output for text like this.</span></span>

> <span data-ttu-id="8e1bf-246">独自性 `<application guid>`</span><span class="sxs-lookup"><span data-stu-id="8e1bf-246">Identity: `<application guid>`</span></span>
>
> <span data-ttu-id="8e1bf-247">受信者の合計: 81527</span><span class="sxs-lookup"><span data-stu-id="8e1bf-247">Total Recipients: 81527</span></span>
>
> <span data-ttu-id="8e1bf-248">失敗した受信者: 2</span><span class="sxs-lookup"><span data-stu-id="8e1bf-248">Failed Recipients: 2</span></span>
>
> <span data-ttu-id="8e1bf-249">エラーのカテゴリ: なし</span><span class="sxs-lookup"><span data-stu-id="8e1bf-249">Failure Category: None</span></span>
>
> <span data-ttu-id="8e1bf-250">状態: 完了</span><span class="sxs-lookup"><span data-stu-id="8e1bf-250">Status: Complete</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8e1bf-251">操作</span><span class="sxs-lookup"><span data-stu-id="8e1bf-251">What to do</span></span>

1. <span data-ttu-id="8e1bf-252">の監査ログで検索 `<application guid>` します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-252">Search in the audit log for `<application guid>`.</span></span> <span data-ttu-id="8e1bf-253">この PowerShell コードをコピーして、変数に対して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-253">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. <span data-ttu-id="8e1bf-254">およびフィールドの値について、監査ログからの詳細な出力を確認し `"UserId"` `"ErrorDetails"` ます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-254">Check the detailed output from the audit log for the values of the `"UserId"` and `"ErrorDetails"` fields.</span></span> <span data-ttu-id="8e1bf-255">これにより、エラーが発生した理由がわかります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-255">This will give you the reason for the failure.</span></span> <span data-ttu-id="8e1bf-256">この PowerShell コードをコピーして、変数に対して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-256">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
   $DetailedLogs[1] |fl
```
 <span data-ttu-id="8e1bf-257">例:</span><span class="sxs-lookup"><span data-stu-id="8e1bf-257">For example:</span></span>

> <span data-ttu-id="8e1bf-258">"UserId": User1</span><span class="sxs-lookup"><span data-stu-id="8e1bf-258">"UserId":  User1</span></span>
> 
><span data-ttu-id="8e1bf-259">"ErrorDetails": "Status: IBPolicyConflict"。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-259">"ErrorDetails":"Status: IBPolicyConflict.</span></span> <span data-ttu-id="8e1bf-260">エラー: IB segment "segment id1" および IB segment "segment id2" が競合しており、受信者に割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-260">Error: IB  segment               "segment id1" and IB segment "segment id2" has conflict and cannot be assigned to the recipient.</span></span> 

3. <span data-ttu-id="8e1bf-261">通常、ユーザーが複数のセグメントに含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-261">Usually, you will find that a user has been included in more than one segment.</span></span> <span data-ttu-id="8e1bf-262">これを修正するには、 `-UserGroupFilter` の値を更新し `OrganizationSegments` ます。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-262">You can fix this by updating the `-UserGroupFilter` value in `OrganizationSegments`.</span></span>

4. <span data-ttu-id="8e1bf-263">これらの手順 [情報障壁ポリシー](information-barriers-policies.md#part-3-apply-information-barrier-policies)を使用して、情報バリアポリシーを再適用します。</span><span class="sxs-lookup"><span data-stu-id="8e1bf-263">Re-apply information barrier policies using these procedures [Information Barriers policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e1bf-264">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8e1bf-264">Related topics</span></span>

[<span data-ttu-id="8e1bf-265">Microsoft Teams の情報障壁に関するポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="8e1bf-265">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)

[<span data-ttu-id="8e1bf-266">情報障壁</span><span class="sxs-lookup"><span data-stu-id="8e1bf-266">Information barriers</span></span>](information-barriers.md)
