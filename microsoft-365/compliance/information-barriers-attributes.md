---
title: 情報バリア ポリシーの属性
description: この記事は、情報バリア セグメントの定義に使用できる Azure Active Directory ユーザー アカウント属性のリファレンスです。
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
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919733"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="9499a-103">情報バリア ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="9499a-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="9499a-104">Azure Active Directory の特定の属性を使用して、ユーザーをセグメント化できます。</span><span class="sxs-lookup"><span data-stu-id="9499a-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="9499a-105">セグメントを定義すると、これらのセグメントを情報バリア ポリシーのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="9499a-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="9499a-106">たとえば、部門を使用して組織内の部署別にユーザーのセグメントを定義できます (2 つの部門で同時に 1 人の従業員が働かされていないと仮定します)。</span><span class="sxs-lookup"><span data-stu-id="9499a-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span>

<span data-ttu-id="9499a-107">この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="9499a-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="9499a-108">情報バリアの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9499a-108">To learn more about information barriers, see the following resources:</span></span>

- [<span data-ttu-id="9499a-109">情報障壁</span><span class="sxs-lookup"><span data-stu-id="9499a-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="9499a-110">Microsoft Teams で情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="9499a-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="9499a-111">情報バリア ポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="9499a-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="9499a-112">情報バリア ポリシーで属性を使用する方法</span><span class="sxs-lookup"><span data-stu-id="9499a-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="9499a-113">この記事に記載されている属性は、ユーザーのセグメントを定義または編集するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9499a-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="9499a-114">定義されたセグメントは、情報バリア ポリシーのパラメーター *(UserGroupFilter* 値と呼ばれる) [として機能します](information-barriers-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9499a-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="9499a-115">セグメントの定義に使用する属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="9499a-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="9499a-116">(この記事 [の「リファレンス](#reference) 」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9499a-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="9499a-117">手順 1 で選択した属性の値がユーザー アカウントに入力されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9499a-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="9499a-118">ユーザー アカウントの詳細を表示し、必要に応じてユーザー アカウントを編集して属性値を含めます。</span><span class="sxs-lookup"><span data-stu-id="9499a-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="9499a-119">複数のアカウントを編集する (または PowerShell を使用して 1 つのアカウントを編集する) には、「Configure user account properties with [Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9499a-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).</span></span>

    - <span data-ttu-id="9499a-120">1 つのアカウントを編集するには、「Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する [」を参照してください](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="9499a-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="9499a-121">[次の例に似た PowerShell](information-barriers-policies.md#define-segments-using-powershell)を使用してセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="9499a-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="9499a-122">**例**</span><span class="sxs-lookup"><span data-stu-id="9499a-122">**Example**</span></span>|<span data-ttu-id="9499a-123">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="9499a-123">**Cmdlet**</span></span>|
    |:----------|:---------|
    | <span data-ttu-id="9499a-124">Department 属性を使用して Segment1 というセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="9499a-124">Define a segment called Segment1 using the Department attribute</span></span> | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | <span data-ttu-id="9499a-125">MemberOf 属性を使用して SegmentA というセグメントを定義します (この属性に "BlueGroup" などのグループ名が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="9499a-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span> | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | <span data-ttu-id="9499a-126">ExtensionAttribute1 を使用して DayTraders というセグメントを定義します (この属性に "DayTrader" などのジョブ タイトルが含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="9499a-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span> | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="9499a-127">セグメントを定義する場合は、すべてのセグメントに同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9499a-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="9499a-128">たとえば、Department を使用して一部のセグメントを定義する場合は *、Department* を使用してすべてのセグメントを *定義します*。</span><span class="sxs-lookup"><span data-stu-id="9499a-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="9499a-129">MemberOf を使用して、Department および *他のセグメントを使用* して一部のセグメント *を定義しない*。</span><span class="sxs-lookup"><span data-stu-id="9499a-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="9499a-130">セグメントが重ならないようにします。各ユーザーは、1 つのセグメントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9499a-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span>

## <a name="reference"></a><span data-ttu-id="9499a-131">Reference</span><span class="sxs-lookup"><span data-stu-id="9499a-131">Reference</span></span>

<span data-ttu-id="9499a-132">次の表に、情報バリアで使用できる属性を示します。</span><span class="sxs-lookup"><span data-stu-id="9499a-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="9499a-133">**Azure Active Directory プロパティ名 <br/> (LDAP 表示名)**</span><span class="sxs-lookup"><span data-stu-id="9499a-133">**Azure Active Directory property name<br/>(LDAP display name)**</span></span>|<span data-ttu-id="9499a-134">**Exchange プロパティ名**</span><span class="sxs-lookup"><span data-stu-id="9499a-134">**Exchange property name**</span></span>|
|:---------------------------------------------------------------|:-------------------------|
| <span data-ttu-id="9499a-135">Co</span><span class="sxs-lookup"><span data-stu-id="9499a-135">Co</span></span> | <span data-ttu-id="9499a-136">Co</span><span class="sxs-lookup"><span data-stu-id="9499a-136">Co</span></span> |
| <span data-ttu-id="9499a-137">Company</span><span class="sxs-lookup"><span data-stu-id="9499a-137">Company</span></span> | <span data-ttu-id="9499a-138">Company</span><span class="sxs-lookup"><span data-stu-id="9499a-138">Company</span></span> |
| <span data-ttu-id="9499a-139">Department</span><span class="sxs-lookup"><span data-stu-id="9499a-139">Department</span></span> | <span data-ttu-id="9499a-140">Department</span><span class="sxs-lookup"><span data-stu-id="9499a-140">Department</span></span> |
| <span data-ttu-id="9499a-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="9499a-141">ExtensionAttribute1</span></span> | <span data-ttu-id="9499a-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="9499a-142">CustomAttribute1</span></span> |
| <span data-ttu-id="9499a-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="9499a-143">ExtensionAttribute2</span></span> | <span data-ttu-id="9499a-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="9499a-144">CustomAttribute2</span></span> |
| <span data-ttu-id="9499a-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="9499a-145">ExtensionAttribute3</span></span> | <span data-ttu-id="9499a-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="9499a-146">CustomAttribute3</span></span> |
| <span data-ttu-id="9499a-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="9499a-147">ExtensionAttribute4</span></span> | <span data-ttu-id="9499a-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="9499a-148">CustomAttribute4</span></span> |
| <span data-ttu-id="9499a-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="9499a-149">ExtensionAttribute5</span></span> | <span data-ttu-id="9499a-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="9499a-150">CustomAttribute5</span></span> |
| <span data-ttu-id="9499a-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="9499a-151">ExtensionAttribute6</span></span> | <span data-ttu-id="9499a-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="9499a-152">CustomAttribute6</span></span> |
| <span data-ttu-id="9499a-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="9499a-153">ExtensionAttribute7</span></span> | <span data-ttu-id="9499a-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="9499a-154">CustomAttribute7</span></span> |
| <span data-ttu-id="9499a-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="9499a-155">ExtensionAttribute8</span></span> | <span data-ttu-id="9499a-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="9499a-156">CustomAttribute8</span></span> |
| <span data-ttu-id="9499a-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="9499a-157">ExtensionAttribute9</span></span> | <span data-ttu-id="9499a-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="9499a-158">CustomAttribute9</span></span> |
| <span data-ttu-id="9499a-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="9499a-159">ExtensionAttribute10</span></span> | <span data-ttu-id="9499a-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="9499a-160">CustomAttribute10</span></span> |
| <span data-ttu-id="9499a-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="9499a-161">ExtensionAttribute11</span></span> | <span data-ttu-id="9499a-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="9499a-162">CustomAttribute11</span></span> |
| <span data-ttu-id="9499a-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="9499a-163">ExtensionAttribute12</span></span> | <span data-ttu-id="9499a-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="9499a-164">CustomAttribute12</span></span> |
| <span data-ttu-id="9499a-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="9499a-165">ExtensionAttribute13</span></span> | <span data-ttu-id="9499a-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="9499a-166">CustomAttribute13</span></span> |
| <span data-ttu-id="9499a-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="9499a-167">ExtensionAttribute14</span></span> | <span data-ttu-id="9499a-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="9499a-168">CustomAttribute14</span></span> |
| <span data-ttu-id="9499a-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="9499a-169">ExtensionAttribute15</span></span> | <span data-ttu-id="9499a-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="9499a-170">CustomAttribute15</span></span> |
| <span data-ttu-id="9499a-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="9499a-171">MSExchExtensionCustomAttribute1</span></span> | <span data-ttu-id="9499a-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="9499a-172">ExtensionCustomAttribute1</span></span> |
| <span data-ttu-id="9499a-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="9499a-173">MSExchExtensionCustomAttribute2</span></span> | <span data-ttu-id="9499a-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="9499a-174">ExtensionCustomAttribute2</span></span> |
| <span data-ttu-id="9499a-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="9499a-175">MSExchExtensionCustomAttribute3</span></span> | <span data-ttu-id="9499a-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="9499a-176">ExtensionCustomAttribute3</span></span> |
| <span data-ttu-id="9499a-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="9499a-177">MSExchExtensionCustomAttribute4</span></span> | <span data-ttu-id="9499a-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="9499a-178">ExtensionCustomAttribute4</span></span> |
| <span data-ttu-id="9499a-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="9499a-179">MSExchExtensionCustomAttribute5</span></span> | <span data-ttu-id="9499a-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="9499a-180">ExtensionCustomAttribute5</span></span> |
| <span data-ttu-id="9499a-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="9499a-181">MailNickname</span></span> | <span data-ttu-id="9499a-182">エイリアス</span><span class="sxs-lookup"><span data-stu-id="9499a-182">Alias</span></span> |
| <span data-ttu-id="9499a-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="9499a-183">PhysicalDeliveryOfficeName</span></span> | <span data-ttu-id="9499a-184">Office</span><span class="sxs-lookup"><span data-stu-id="9499a-184">Office</span></span> |
| <span data-ttu-id="9499a-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="9499a-185">PostalCode</span></span> | <span data-ttu-id="9499a-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="9499a-186">PostalCode</span></span> |
| <span data-ttu-id="9499a-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9499a-187">ProxyAddresses</span></span> | <span data-ttu-id="9499a-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="9499a-188">EmailAddresses</span></span> |
| <span data-ttu-id="9499a-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="9499a-189">StreetAddress</span></span> | <span data-ttu-id="9499a-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="9499a-190">StreetAddress</span></span> |
| <span data-ttu-id="9499a-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="9499a-191">TargetAddress</span></span> | <span data-ttu-id="9499a-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="9499a-192">ExternalEmailAddress</span></span> |
| <span data-ttu-id="9499a-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="9499a-193">UsageLocation</span></span> | <span data-ttu-id="9499a-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="9499a-194">UsageLocation</span></span> |
| <span data-ttu-id="9499a-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9499a-195">UserPrincipalName</span></span> | <span data-ttu-id="9499a-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9499a-196">UserPrincipalName</span></span> |
| <span data-ttu-id="9499a-197">メール</span><span class="sxs-lookup"><span data-stu-id="9499a-197">Mail</span></span> | <span data-ttu-id="9499a-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="9499a-198">WindowsEmailAddress</span></span> |
| <span data-ttu-id="9499a-199">説明</span><span class="sxs-lookup"><span data-stu-id="9499a-199">Description</span></span> | <span data-ttu-id="9499a-200">説明</span><span class="sxs-lookup"><span data-stu-id="9499a-200">Description</span></span> |
| <span data-ttu-id="9499a-201">MemberOf</span><span class="sxs-lookup"><span data-stu-id="9499a-201">MemberOf</span></span> | <span data-ttu-id="9499a-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="9499a-202">MemberOfGroup</span></span> |

## <a name="resources"></a><span data-ttu-id="9499a-203">リソース</span><span class="sxs-lookup"><span data-stu-id="9499a-203">Resources</span></span>

- [<span data-ttu-id="9499a-204">Microsoft Teams で情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="9499a-204">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="9499a-205">情報バリアのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9499a-205">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
- [<span data-ttu-id="9499a-206">情報障壁</span><span class="sxs-lookup"><span data-stu-id="9499a-206">Information barriers</span></span>](information-barriers.md)