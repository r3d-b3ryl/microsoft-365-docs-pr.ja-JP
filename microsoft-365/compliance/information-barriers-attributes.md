---
title: 情報障壁ポリシーの属性
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
description: この記事は、情報バリアポリシーで使用できるさまざまな属性の参照として使用します。
ms.openlocfilehash: ff7b6e22370c086f6b685fce4de8b61396017bf9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600624"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="d62b3-103">情報障壁ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="d62b3-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="d62b3-104">Azure Active Directory の特定の属性を使用して、ユーザーをセグメントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d62b3-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="d62b3-105">セグメントが定義されると、それらのセグメントは情報バリアポリシーのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="d62b3-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="d62b3-106">たとえば **、部署を使用し**て、組織内の部署別のユーザーのセグメントを定義することができます (2 つの部署に対して1人の従業員が同時に働くことは想定されていません)。</span><span class="sxs-lookup"><span data-stu-id="d62b3-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="d62b3-107">この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="d62b3-108">情報バリアの詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d62b3-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="d62b3-109">情報障壁</span><span class="sxs-lookup"><span data-stu-id="d62b3-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="d62b3-110">Microsoft Teams の情報障壁に関するポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="d62b3-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="d62b3-111">情報バリアポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="d62b3-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="d62b3-112">情報バリアポリシーで属性を使用する方法</span><span class="sxs-lookup"><span data-stu-id="d62b3-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="d62b3-113">この記事に記載されている属性は、ユーザーのセグメントを定義または編集するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d62b3-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="d62b3-114">定義済みのセグメントは、[情報バリアポリシー](information-barriers-policies.md)でパラメーター ( *usergroupfilter*値と呼ばれる) として機能します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="d62b3-115">セグメントを定義するために使用する属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="d62b3-116">(この記事の[参照](#reference)セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d62b3-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="d62b3-117">手順1で選択した属性に対して、ユーザーアカウントに値が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="d62b3-118">ユーザーアカウントの詳細を表示し、必要に応じて、属性値を含めるようにユーザーアカウントを編集します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="d62b3-119">複数のアカウントを編集する (または PowerShell を使用して1つのアカウントを編集する) には、「 [Office 365 powershell でユーザーアカウントのプロパティを構成](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d62b3-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

    - <span data-ttu-id="d62b3-120">単一のアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d62b3-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="d62b3-121">次の例に示すように、 [PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="d62b3-122">例</span><span class="sxs-lookup"><span data-stu-id="d62b3-122">Example</span></span>  |<span data-ttu-id="d62b3-123">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d62b3-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="d62b3-124">Department 属性を使用して、Segment1 というセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="d62b3-125">MemberOf 属性を使用して SegmentA と呼ばれるセグメントを定義します (この属性には "BlueGroup" などのグループ名が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="d62b3-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="d62b3-126">ExtensionAttribute1 を使用して、DayTraders という名前のセグメントを定義します (この属性には "Daytraders" のような役職が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="d62b3-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="d62b3-127">セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="d62b3-128">たとえば、*部門*を使用してセグメントを定義する場合、 *department*を使用してすべてのセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="d62b3-129">*部署*を使用したセグメントと、 *MemberOf*を使用しているセグメントを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="d62b3-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="d62b3-130">セグメントが重ならないようにします。各ユーザーは、1つのセグメントにのみ割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d62b3-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="d62b3-131">リファレンス</span><span class="sxs-lookup"><span data-stu-id="d62b3-131">Reference</span></span>

<span data-ttu-id="d62b3-132">次の表に、情報バリアで使用できる属性を示します。</span><span class="sxs-lookup"><span data-stu-id="d62b3-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="d62b3-133">Azure Active Directory のプロパティ名</span><span class="sxs-lookup"><span data-stu-id="d62b3-133">Azure Active Directory property name</span></span><br/><span data-ttu-id="d62b3-134">(LDAP 表示名)</span><span class="sxs-lookup"><span data-stu-id="d62b3-134">(LDAP display name)</span></span>  |<span data-ttu-id="d62b3-135">Exchange のプロパティ名</span><span class="sxs-lookup"><span data-stu-id="d62b3-135">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="d62b3-136">産品</span><span class="sxs-lookup"><span data-stu-id="d62b3-136">Co</span></span>       | <span data-ttu-id="d62b3-137">産品</span><span class="sxs-lookup"><span data-stu-id="d62b3-137">Co</span></span>        |
|<span data-ttu-id="d62b3-138">Company</span><span class="sxs-lookup"><span data-stu-id="d62b3-138">Company</span></span>     |<span data-ttu-id="d62b3-139">Company</span><span class="sxs-lookup"><span data-stu-id="d62b3-139">Company</span></span>         |
|<span data-ttu-id="d62b3-140">Department</span><span class="sxs-lookup"><span data-stu-id="d62b3-140">Department</span></span>     |<span data-ttu-id="d62b3-141">Department</span><span class="sxs-lookup"><span data-stu-id="d62b3-141">Department</span></span>         |
|<span data-ttu-id="d62b3-142">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="d62b3-142">ExtensionAttribute1</span></span> |<span data-ttu-id="d62b3-143">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="d62b3-143">CustomAttribute1</span></span>  |
|<span data-ttu-id="d62b3-144">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="d62b3-144">ExtensionAttribute2</span></span> |<span data-ttu-id="d62b3-145">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="d62b3-145">CustomAttribute2</span></span>  |
|<span data-ttu-id="d62b3-146">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="d62b3-146">ExtensionAttribute3</span></span> |<span data-ttu-id="d62b3-147">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="d62b3-147">CustomAttribute3</span></span>  |
|<span data-ttu-id="d62b3-148">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="d62b3-148">ExtensionAttribute4</span></span> |<span data-ttu-id="d62b3-149">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="d62b3-149">CustomAttribute4</span></span>  |
|<span data-ttu-id="d62b3-150">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="d62b3-150">ExtensionAttribute5</span></span> |<span data-ttu-id="d62b3-151">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="d62b3-151">CustomAttribute5</span></span>  |
|<span data-ttu-id="d62b3-152">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="d62b3-152">ExtensionAttribute6</span></span> |<span data-ttu-id="d62b3-153">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="d62b3-153">CustomAttribute6</span></span>  |
|<span data-ttu-id="d62b3-154">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="d62b3-154">ExtensionAttribute7</span></span> |<span data-ttu-id="d62b3-155">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="d62b3-155">CustomAttribute7</span></span>  |
|<span data-ttu-id="d62b3-156">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="d62b3-156">ExtensionAttribute8</span></span> |<span data-ttu-id="d62b3-157">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="d62b3-157">CustomAttribute8</span></span>  |
|<span data-ttu-id="d62b3-158">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="d62b3-158">ExtensionAttribute9</span></span> |<span data-ttu-id="d62b3-159">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="d62b3-159">CustomAttribute9</span></span>  |
|<span data-ttu-id="d62b3-160">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="d62b3-160">ExtensionAttribute10</span></span> |<span data-ttu-id="d62b3-161">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="d62b3-161">CustomAttribute10</span></span>  |
|<span data-ttu-id="d62b3-162">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="d62b3-162">ExtensionAttribute11</span></span> |<span data-ttu-id="d62b3-163">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="d62b3-163">CustomAttribute11</span></span>  |
|<span data-ttu-id="d62b3-164">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="d62b3-164">ExtensionAttribute12</span></span> |<span data-ttu-id="d62b3-165">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="d62b3-165">CustomAttribute12</span></span>  |
|<span data-ttu-id="d62b3-166">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="d62b3-166">ExtensionAttribute13</span></span> |<span data-ttu-id="d62b3-167">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="d62b3-167">CustomAttribute13</span></span>  |
|<span data-ttu-id="d62b3-168">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="d62b3-168">ExtensionAttribute14</span></span> |<span data-ttu-id="d62b3-169">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="d62b3-169">CustomAttribute14</span></span>  |
|<span data-ttu-id="d62b3-170">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="d62b3-170">ExtensionAttribute15</span></span> |<span data-ttu-id="d62b3-171">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="d62b3-171">CustomAttribute15</span></span>  |
|<span data-ttu-id="d62b3-172">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="d62b3-172">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="d62b3-173">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="d62b3-173">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="d62b3-174">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="d62b3-174">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="d62b3-175">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="d62b3-175">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="d62b3-176">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="d62b3-176">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="d62b3-177">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="d62b3-177">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="d62b3-178">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="d62b3-178">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="d62b3-179">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="d62b3-179">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="d62b3-180">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="d62b3-180">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="d62b3-181">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="d62b3-181">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="d62b3-182">MailNickname</span><span class="sxs-lookup"><span data-stu-id="d62b3-182">MailNickname</span></span> |<span data-ttu-id="d62b3-183">Alias</span><span class="sxs-lookup"><span data-stu-id="d62b3-183">Alias</span></span> |
|<span data-ttu-id="d62b3-184">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="d62b3-184">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="d62b3-185">Office</span><span class="sxs-lookup"><span data-stu-id="d62b3-185">Office</span></span> |
|<span data-ttu-id="d62b3-186">郵便</span><span class="sxs-lookup"><span data-stu-id="d62b3-186">PostalCode</span></span> |<span data-ttu-id="d62b3-187">郵便</span><span class="sxs-lookup"><span data-stu-id="d62b3-187">PostalCode</span></span> |
|<span data-ttu-id="d62b3-188">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="d62b3-188">ProxyAddresses</span></span> |<span data-ttu-id="d62b3-189">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="d62b3-189">EmailAddresses</span></span> |
|<span data-ttu-id="d62b3-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="d62b3-190">StreetAddress</span></span> |<span data-ttu-id="d62b3-191">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="d62b3-191">StreetAddress</span></span> |
|<span data-ttu-id="d62b3-192">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="d62b3-192">TargetAddress</span></span> |<span data-ttu-id="d62b3-193">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="d62b3-193">ExternalEmailAddress</span></span> |
|<span data-ttu-id="d62b3-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="d62b3-194">UsageLocation</span></span> |<span data-ttu-id="d62b3-195">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="d62b3-195">UsageLocation</span></span> |
|<span data-ttu-id="d62b3-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d62b3-196">UserPrincipalName</span></span>  |<span data-ttu-id="d62b3-197">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d62b3-197">UserPrincipalName</span></span>  |
|<span data-ttu-id="d62b3-198">メール</span><span class="sxs-lookup"><span data-stu-id="d62b3-198">Mail</span></span>   |<span data-ttu-id="d62b3-199">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="d62b3-199">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="d62b3-200">説明</span><span class="sxs-lookup"><span data-stu-id="d62b3-200">Description</span></span>    |<span data-ttu-id="d62b3-201">説明</span><span class="sxs-lookup"><span data-stu-id="d62b3-201">Description</span></span>    |
|<span data-ttu-id="d62b3-202">所属</span><span class="sxs-lookup"><span data-stu-id="d62b3-202">MemberOf</span></span>   |<span data-ttu-id="d62b3-203">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="d62b3-203">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="d62b3-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="d62b3-204">Related topics</span></span>

[<span data-ttu-id="d62b3-205">Microsoft Teams の情報障壁に関するポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="d62b3-205">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)

[<span data-ttu-id="d62b3-206">情報障壁のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d62b3-206">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="d62b3-207">情報障壁</span><span class="sxs-lookup"><span data-stu-id="d62b3-207">Information barriers</span></span>](information-barriers.md)



