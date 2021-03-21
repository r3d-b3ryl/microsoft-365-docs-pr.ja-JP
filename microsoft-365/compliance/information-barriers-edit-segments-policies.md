---
title: 情報バリア ポリシーの管理
description: 情報バリアのポリシーを編集または削除する方法について説明します。
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
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925553"
---
# <a name="manage-information-barrier-policies"></a><span data-ttu-id="19a18-103">情報バリア ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="19a18-103">Manage information barrier policies</span></span>

<span data-ttu-id="19a18-104">情報バリア[ポリシーを定義](information-barriers-policies.md)した後、トラブルシューティングの一環として、または定期的なメンテナンスとして、それらのポリシーまたはユーザー セグメントに変更[](information-barriers-troubleshooting.md)を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="19a18-105">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="19a18-106">目的に合ったトピックをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="19a18-106">What do you want to do?</span></span>

|<span data-ttu-id="19a18-107">**操作**</span><span class="sxs-lookup"><span data-stu-id="19a18-107">**Action**</span></span>|<span data-ttu-id="19a18-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="19a18-108">**Description**</span></span>|
|:---------|:--------------|
| [<span data-ttu-id="19a18-109">ユーザー アカウントの属性を編集する</span><span class="sxs-lookup"><span data-stu-id="19a18-109">Edit user account attributes</span></span>](#edit-user-account-attributes) | <span data-ttu-id="19a18-110">セグメントの定義に使用できる Azure Active Directory の属性を入力します。</span><span class="sxs-lookup"><span data-stu-id="19a18-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="19a18-111">ユーザーアカウントの属性を編集して、ユーザーがセグメントに含まれていない場合、ユーザーが所属するセグメントを変更したり、異なる属性を使用してセグメントを定義したりする場合。</span><span class="sxs-lookup"><span data-stu-id="19a18-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span> |
| [<span data-ttu-id="19a18-112">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="19a18-112">Edit a segment</span></span>](#edit-a-segment) | <span data-ttu-id="19a18-113">セグメントの定義方法を変更する場合は、セグメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="19a18-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="19a18-114">たとえば、Department を使用して最初にセグメントを定義し *、MemberOf* などの別の属性を使用 *する場合があります*。</span><span class="sxs-lookup"><span data-stu-id="19a18-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span> |
| [<span data-ttu-id="19a18-115">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="19a18-115">Edit a policy</span></span>](#edit-a-policy) | <span data-ttu-id="19a18-116">ポリシーの動作方法を変更する場合は、情報バリア ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="19a18-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="19a18-117">たとえば、2 つのセグメント間の通信をブロックする代わりに、特定のセグメント間でのみ通信を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span> |
| [<span data-ttu-id="19a18-118">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="19a18-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status) |<span data-ttu-id="19a18-119">ポリシーを変更する場合、またはポリシーを有効にしない場合は、ポリシーを非アクティブ状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="19a18-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span> |
| [<span data-ttu-id="19a18-120">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="19a18-120">Remove a policy</span></span>](#remove-a-policy) | <span data-ttu-id="19a18-121">特定のポリシーが不要になった場合は、情報バリア ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="19a18-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span> |
| [<span data-ttu-id="19a18-122">ポリシー アプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="19a18-122">Stop a policy application</span></span>](#stop-a-policy-application) | <span data-ttu-id="19a18-123">情報バリア ポリシーの適用プロセスを停止する場合は、このアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="19a18-123">Take this action when you want to stop the process of applying information barrier policies.</span></span><br/> <span data-ttu-id="19a18-124">ポリシー アプリケーションを停止しても、ユーザーに既に適用されているポリシーは元に戻されません。</span><span class="sxs-lookup"><span data-stu-id="19a18-124">Stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span> |
| [<span data-ttu-id="19a18-125">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="19a18-125">Define policies for information barriers</span></span>](information-barriers-policies.md) | <span data-ttu-id="19a18-126">このようなポリシーが設定されていない場合に情報バリア ポリシーを定義し、特定のユーザー グループ間の通信を制限または制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span> |
| [<span data-ttu-id="19a18-127">情報バリアのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="19a18-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md) | <span data-ttu-id="19a18-128">情報バリアで予期しない問題が発生した場合は、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a18-128">Refer to this article when you run into unexpected issues with information barriers.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="19a18-129">この記事で説明するタスクを実行するには、次のいずれかの適切な役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="19a18-130">- Microsoft 365 Enterprise Global Administrator</span><span class="sxs-lookup"><span data-stu-id="19a18-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="19a18-131">- グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="19a18-131">- Global Administrator</span></span><br/><span data-ttu-id="19a18-132">- コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="19a18-132">- Compliance Administrator</span></span><br/><span data-ttu-id="19a18-133">- IB コンプライアンス管理 (これは新しい役割です!</span><span class="sxs-lookup"><span data-stu-id="19a18-133">- IB Compliance Management (this is a new role!)</span></span><br><br><span data-ttu-id="19a18-134">情報バリアの前提条件の詳細については、「前提条件 (情報バリア ポリシーの場合 [)」を参照してください](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="19a18-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><br><br> <span data-ttu-id="19a18-135">コンプライアンス センター [PowerShell のセキュリティ &接続してください](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="19a18-135">Make sure to [connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="19a18-136">ユーザー アカウントの属性を編集する</span><span class="sxs-lookup"><span data-stu-id="19a18-136">Edit user account attributes</span></span>

<span data-ttu-id="19a18-137">セグメント化ユーザーに使用する属性を編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19a18-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> <span data-ttu-id="19a18-138">たとえば、Department 属性を使用している場合に、1 つ以上のユーザー アカウントに現在 Department の値が表示されていない場合は、それらのユーザー アカウントを編集して部署情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> <span data-ttu-id="19a18-139">ユーザー アカウントの属性は、情報バリア ポリシーを割り当て可能なセグメントを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="19a18-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="19a18-140">属性値や割り当てられたセグメントなど、特定のユーザー アカウントの詳細を表示するには、Identity パラメーターを使用して **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="19a18-141">**構文**</span><span class="sxs-lookup"><span data-stu-id="19a18-141">**Syntax**</span></span>|<span data-ttu-id="19a18-142">**例**</span><span class="sxs-lookup"><span data-stu-id="19a18-142">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="19a18-143">名前、エイリアス、識別名、標準ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19a18-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p> <span data-ttu-id="19a18-144">(このコマンドレットは、1 人のユーザーにも使用できます `Get-InformationBarrierRecipientStatus -Identity <value>` 。</span><span class="sxs-lookup"><span data-stu-id="19a18-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="19a18-145">この例では、365 の 2 つのユーザー アカウントを参照Office meganb for *Megan、alexw* を *示します*。  </span><span class="sxs-lookup"><span data-stu-id="19a18-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

2. <span data-ttu-id="19a18-146">ユーザー アカウント プロファイルに対して編集する属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="19a18-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="19a18-147">詳細については、「情報バリア ポリシー [の属性」を参照してください](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="19a18-147">For more information, see [Attributes for information barrier policies](information-barriers-attributes.md).</span></span> 

3. <span data-ttu-id="19a18-148">1 つ以上のユーザー アカウントを編集して、前の手順で選択した属性の値を含める。</span><span class="sxs-lookup"><span data-stu-id="19a18-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="19a18-149">このアクションを実行するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-149">To take this action, use one of the following procedures:</span></span>

    - <span data-ttu-id="19a18-150">1 つのアカウントを編集するには、「Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する [」を参照してください](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="19a18-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="19a18-151">複数のアカウントを編集する (または PowerShell を使用して 1 つのアカウントを編集する) には、「Configure user account properties with [Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a18-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="19a18-152">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="19a18-152">Edit a segment</span></span>

<span data-ttu-id="19a18-153">ユーザー セグメントの定義を編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19a18-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="19a18-154">たとえば、セグメントの名前や、セグメントに含まれるユーザーを特定するために使用されるフィルターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="19a18-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="19a18-155">既存のすべてのセグメントを表示するには **、Get-OrganizationSegment コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>

    <span data-ttu-id="19a18-156">構文: `Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="19a18-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="19a18-157">セグメントの種類、UserGroupFilter の値、作成または最後に変更したユーザー、GUID など、各セグメントと詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19a18-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="19a18-158">後で参照するために、セグメントのリストを印刷または保存します。</span><span class="sxs-lookup"><span data-stu-id="19a18-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="19a18-159">たとえば、セグメントを編集する場合は、その名前を知る必要があります。または値を識別する必要があります (これは Identity パラメーターと一緒に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="19a18-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="19a18-160">セグメントを編集するには、Identity パラメーターと関連する詳細を指定して **Set-OrganizationSegment** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span>

    |<span data-ttu-id="19a18-161">**構文**</span><span class="sxs-lookup"><span data-stu-id="19a18-161">**Syntax**</span></span>|<span data-ttu-id="19a18-162">**例**</span><span class="sxs-lookup"><span data-stu-id="19a18-162">**Example**</span></span>|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> <span data-ttu-id="19a18-163">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* を持つセグメントについて、部門名を "HRDept" に更新しました。</span><span class="sxs-lookup"><span data-stu-id="19a18-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span> |

<span data-ttu-id="19a18-164">組織のセグメントの編集が完了したら、情報バリア ポリシーを[定義](#edit-a-policy)または編集できます。 [](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="19a18-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="19a18-165">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="19a18-165">Edit a policy</span></span>

1. <span data-ttu-id="19a18-166">現在の情報バリア ポリシーの一覧を表示するには **、Get-InformationBarrierPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="19a18-167">構文: `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="19a18-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="19a18-168">結果の一覧で、変更するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="19a18-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="19a18-169">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="19a18-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="19a18-170">Identity パラメーター **と一緒に Set-InformationBarrierPolicy** コマンドレットを使用し、行う変更を指定します。 </span><span class="sxs-lookup"><span data-stu-id="19a18-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="19a18-171">例: Research セグメントが Sales セグメントおよび *Marketing* セグメントとの通信をブロックするポリシー *を定義した\*\*と* します。</span><span class="sxs-lookup"><span data-stu-id="19a18-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="19a18-172">ポリシーは、次のコマンドレットを使用して定義されています。 `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="19a18-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>

    <span data-ttu-id="19a18-173">リサーチ セグメントのユーザーが人事セグメントのユーザーとのみ通信できるよう *変更するとします*。</span><span class="sxs-lookup"><span data-stu-id="19a18-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="19a18-174">この変更を行う場合は、次のコマンドレットを使用します。 `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="19a18-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="19a18-175">この例では、"SegmentsBlocked" を "SegmentsAllowed" に変更し *、HR* セグメントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="19a18-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="19a18-176">ポリシーの編集が完了したら、必ず変更を適用してください。</span><span class="sxs-lookup"><span data-stu-id="19a18-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="19a18-177">(「 [情報バリア ポリシーの適用」を参照](information-barriers-policies.md#part-3-apply-information-barrier-policies)してください。</span><span class="sxs-lookup"><span data-stu-id="19a18-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="19a18-178">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="19a18-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="19a18-179">現在の情報バリア ポリシーの一覧を表示するには **、Get-InformationBarrierPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="19a18-180">構文: `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="19a18-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="19a18-181">結果の一覧で、変更 (または削除) するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="19a18-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="19a18-182">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="19a18-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="19a18-183">ポリシーの状態を非アクティブに設定するには、Identity パラメーターと State パラメーターを非アクティブに設定した **Set-InformationBarrierPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="19a18-184">**構文**</span><span class="sxs-lookup"><span data-stu-id="19a18-184">**Syntax**</span></span>|<span data-ttu-id="19a18-185">**例**</span><span class="sxs-lookup"><span data-stu-id="19a18-185">**Example**</span></span>|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> <span data-ttu-id="19a18-186">この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247* を非アクティブな状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="19a18-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span> |

3. <span data-ttu-id="19a18-187">変更を適用するには **、Start-InformationBarrierPoliciesApplication コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="19a18-188">構文: `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="19a18-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="19a18-189">変更は、組織に対してユーザー別に適用されます。</span><span class="sxs-lookup"><span data-stu-id="19a18-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="19a18-190">組織が大規模な場合、このプロセスが完了するには 24 時間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="19a18-191">(一般的なガイドラインとして、5,000 のユーザー アカウントを処理するのに約 1 時間かかる)。</span><span class="sxs-lookup"><span data-stu-id="19a18-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="19a18-192">この時点で、1 つ以上の情報バリア ポリシーが非アクティブ状態に設定されます。</span><span class="sxs-lookup"><span data-stu-id="19a18-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="19a18-193">ここから、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="19a18-193">From here, you can do any of the following actions:</span></span>

- <span data-ttu-id="19a18-194">この状態を維持します (ポリシー セットを非アクティブな状態に設定すると、ユーザーには影響しません)</span><span class="sxs-lookup"><span data-stu-id="19a18-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="19a18-195">ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="19a18-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="19a18-196">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="19a18-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="19a18-197">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="19a18-197">Remove a policy</span></span>

1. <span data-ttu-id="19a18-198">現在の情報バリア ポリシーの一覧を表示するには **、Get-InformationBarrierPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="19a18-199">構文: `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="19a18-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="19a18-200">結果の一覧で、削除するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="19a18-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="19a18-201">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="19a18-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="19a18-202">ポリシーが非アクティブ状態に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="19a18-203">Identity パラメーター **と一緒に Remove-InformationBarrierPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="19a18-204">**構文**</span><span class="sxs-lookup"><span data-stu-id="19a18-204">**Syntax**</span></span>|<span data-ttu-id="19a18-205">**例**</span><span class="sxs-lookup"><span data-stu-id="19a18-205">**Example**</span></span>|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> <span data-ttu-id="19a18-206">この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* を持つポリシーを削除しています。</span><span class="sxs-lookup"><span data-stu-id="19a18-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> |

    <span data-ttu-id="19a18-207">メッセージが表示されたら、変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="19a18-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="19a18-208">削除するポリシーごとに手順 1 ~ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="19a18-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="19a18-209">ポリシーの削除が完了したら、変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="19a18-210">このアクションを実行するには **、Start-InformationBarrierPoliciesApplication コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-210">To take this action, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="19a18-211">構文: `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="19a18-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="19a18-212">変更は、組織に対してユーザー別に適用されます。</span><span class="sxs-lookup"><span data-stu-id="19a18-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="19a18-213">組織が大規模な場合、このプロセスが完了するには 24 時間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="19a18-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="19a18-214">ポリシー アプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="19a18-214">Stop a policy application</span></span>

<span data-ttu-id="19a18-215">情報バリア ポリシーの適用を開始した後、それらのポリシーの適用を停止する場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-215">After you have started applying information barrier policies, if you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="19a18-216">プロセスが開始するには、約 30 ~ 35 分かかります。</span><span class="sxs-lookup"><span data-stu-id="19a18-216">It will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="19a18-217">最新の情報バリア ポリシー アプリケーションの状態を表示するには **、Get-InformationBarrierPoliciesApplicationStatus コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="19a18-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="19a18-218">構文: `Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="19a18-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="19a18-219">アプリケーションの GUID に注意してください。</span><span class="sxs-lookup"><span data-stu-id="19a18-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="19a18-220">Identity パラメーター **と共に Stop-InformationBarrierPoliciesApplication** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19a18-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="19a18-221">**構文**</span><span class="sxs-lookup"><span data-stu-id="19a18-221">**Syntax**</span></span>|<span data-ttu-id="19a18-222">**例**</span><span class="sxs-lookup"><span data-stu-id="19a18-222">**Example**</span></span>|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> <span data-ttu-id="19a18-223">この例では、情報バリア ポリシーの適用を停止しています。</span><span class="sxs-lookup"><span data-stu-id="19a18-223">In this example, we are stopping information barrier policies from being applied.</span></span> |

## <a name="resources"></a><span data-ttu-id="19a18-224">リソース</span><span class="sxs-lookup"><span data-stu-id="19a18-224">Resources</span></span>

- [<span data-ttu-id="19a18-225">情報バリアの概要を取得する</span><span class="sxs-lookup"><span data-stu-id="19a18-225">Get an overview of information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="19a18-226">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="19a18-226">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="19a18-227">Microsoft Teams の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="19a18-227">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="19a18-228">SharePoint Online の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="19a18-228">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="19a18-229">OneDrive の情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="19a18-229">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="19a18-230">情報障壁ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="19a18-230">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="19a18-231">情報障壁のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="19a18-231">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)