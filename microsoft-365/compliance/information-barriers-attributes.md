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
ms.openlocfilehash: 5e7815dbcfc6129685322a250351276476f8a9e3
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980051"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="7ab2e-103">情報バリア ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="7ab2e-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="7ab2e-104">Azure Active Directory の特定の属性を使用して、ユーザーをセグメント化できます。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="7ab2e-105">セグメントを定義すると、それらのセグメントを情報バリア ポリシーのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="7ab2e-106">たとえば、部門を使用して、組織内の部署別にユーザーのセグメントを定義できます (同時に 2 つの部署に 1 人の従業員が働かされていないと仮定します)。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span>

<span data-ttu-id="7ab2e-107">この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="7ab2e-108">情報バリアの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-108">To learn more about information barriers, see the following resources:</span></span>

- [<span data-ttu-id="7ab2e-109">情報障壁</span><span class="sxs-lookup"><span data-stu-id="7ab2e-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="7ab2e-110">Microsoft Teams で情報障壁のポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="7ab2e-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="7ab2e-111">情報バリア ポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="7ab2e-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="7ab2e-112">情報バリア ポリシーで属性を使用する方法</span><span class="sxs-lookup"><span data-stu-id="7ab2e-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="7ab2e-113">この記事に記載されている属性を使用して、ユーザーのセグメントを定義または編集できます。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="7ab2e-114">定義されたセグメントは、情報バリア ポリシーのパラメーター *(UserGroupFilter* 値と呼ばれる) [として機能します](information-barriers-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="7ab2e-115">セグメントの定義に使用する属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="7ab2e-116">(この記事 [の「リファレンス](#reference) 」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="7ab2e-117">手順 1 で選択した属性の値がユーザー アカウントに入力されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="7ab2e-118">ユーザー アカウントの詳細を表示し、必要に応じてユーザー アカウントを編集して属性値を含めます。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="7ab2e-119">複数のアカウントを編集する (または、PowerShell を使用して 1 つのアカウントを編集する) には、「Office [365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)でユーザー アカウントのプロパティを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).</span></span>

    - <span data-ttu-id="7ab2e-120">単一のアカウントを編集するには [、「Azure Active Directory を](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)使用してユーザーのプロファイル情報を追加または更新する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="7ab2e-121">[PowerShell を使用して、次の](information-barriers-policies.md#define-segments-using-powershell)例のようなセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="7ab2e-122">**例**</span><span class="sxs-lookup"><span data-stu-id="7ab2e-122">**Example**</span></span>|<span data-ttu-id="7ab2e-123">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="7ab2e-123">**Cmdlet**</span></span>|
    |:----------|:---------|
    | <span data-ttu-id="7ab2e-124">Department 属性を使用して Segment1 というセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="7ab2e-124">Define a segment called Segment1 using the Department attribute</span></span> | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | <span data-ttu-id="7ab2e-125">MemberOf 属性を使用して SegmentA というセグメントを定義します (この属性に "BlueGroup" などのグループ名が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span> | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | <span data-ttu-id="7ab2e-126">ExtensionAttribute1 を使用して DayTraders というセグメントを定義します (この属性に "DayTrader" などのジョブ タイトルが含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span> | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="7ab2e-127">セグメントを定義する場合は、すべてのセグメントに同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="7ab2e-128">たとえば、Department を使用していくつかのセグメントを定義する場合 *は、Department* を使用してすべてのセグメントを定義 *します*。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="7ab2e-129">Department を使用して一部のセグメントを定義し *、MemberOf* を使用する他のセグメント *は定義しない*。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="7ab2e-130">セグメントが重ならないようにします。各ユーザーは、1 つのセグメントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span>

## <a name="reference"></a><span data-ttu-id="7ab2e-131">リファレンス</span><span class="sxs-lookup"><span data-stu-id="7ab2e-131">Reference</span></span>

<span data-ttu-id="7ab2e-132">次の表に、情報バリアで使用できる属性を示します。</span><span class="sxs-lookup"><span data-stu-id="7ab2e-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="7ab2e-133">**Azure Active Directory プロパティ名 <br/> (LDAP 表示名)**</span><span class="sxs-lookup"><span data-stu-id="7ab2e-133">**Azure Active Directory property name<br/>(LDAP display name)**</span></span>|<span data-ttu-id="7ab2e-134">**Exchange プロパティ名**</span><span class="sxs-lookup"><span data-stu-id="7ab2e-134">**Exchange property name**</span></span>|
|:---------------------------------------------------------------|:-------------------------|
| <span data-ttu-id="7ab2e-135">Co</span><span class="sxs-lookup"><span data-stu-id="7ab2e-135">Co</span></span> | <span data-ttu-id="7ab2e-136">Co</span><span class="sxs-lookup"><span data-stu-id="7ab2e-136">Co</span></span> |
| <span data-ttu-id="7ab2e-137">Company</span><span class="sxs-lookup"><span data-stu-id="7ab2e-137">Company</span></span> | <span data-ttu-id="7ab2e-138">Company</span><span class="sxs-lookup"><span data-stu-id="7ab2e-138">Company</span></span> |
| <span data-ttu-id="7ab2e-139">Department</span><span class="sxs-lookup"><span data-stu-id="7ab2e-139">Department</span></span> | <span data-ttu-id="7ab2e-140">Department</span><span class="sxs-lookup"><span data-stu-id="7ab2e-140">Department</span></span> |
| <span data-ttu-id="7ab2e-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="7ab2e-141">ExtensionAttribute1</span></span> | <span data-ttu-id="7ab2e-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7ab2e-142">CustomAttribute1</span></span> |
| <span data-ttu-id="7ab2e-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="7ab2e-143">ExtensionAttribute2</span></span> | <span data-ttu-id="7ab2e-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7ab2e-144">CustomAttribute2</span></span> |
| <span data-ttu-id="7ab2e-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="7ab2e-145">ExtensionAttribute3</span></span> | <span data-ttu-id="7ab2e-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7ab2e-146">CustomAttribute3</span></span> |
| <span data-ttu-id="7ab2e-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="7ab2e-147">ExtensionAttribute4</span></span> | <span data-ttu-id="7ab2e-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7ab2e-148">CustomAttribute4</span></span> |
| <span data-ttu-id="7ab2e-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="7ab2e-149">ExtensionAttribute5</span></span> | <span data-ttu-id="7ab2e-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7ab2e-150">CustomAttribute5</span></span> |
| <span data-ttu-id="7ab2e-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="7ab2e-151">ExtensionAttribute6</span></span> | <span data-ttu-id="7ab2e-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="7ab2e-152">CustomAttribute6</span></span> |
| <span data-ttu-id="7ab2e-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="7ab2e-153">ExtensionAttribute7</span></span> | <span data-ttu-id="7ab2e-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="7ab2e-154">CustomAttribute7</span></span> |
| <span data-ttu-id="7ab2e-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="7ab2e-155">ExtensionAttribute8</span></span> | <span data-ttu-id="7ab2e-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="7ab2e-156">CustomAttribute8</span></span> |
| <span data-ttu-id="7ab2e-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="7ab2e-157">ExtensionAttribute9</span></span> | <span data-ttu-id="7ab2e-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="7ab2e-158">CustomAttribute9</span></span> |
| <span data-ttu-id="7ab2e-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="7ab2e-159">ExtensionAttribute10</span></span> | <span data-ttu-id="7ab2e-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="7ab2e-160">CustomAttribute10</span></span> |
| <span data-ttu-id="7ab2e-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="7ab2e-161">ExtensionAttribute11</span></span> | <span data-ttu-id="7ab2e-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="7ab2e-162">CustomAttribute11</span></span> |
| <span data-ttu-id="7ab2e-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="7ab2e-163">ExtensionAttribute12</span></span> | <span data-ttu-id="7ab2e-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="7ab2e-164">CustomAttribute12</span></span> |
| <span data-ttu-id="7ab2e-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="7ab2e-165">ExtensionAttribute13</span></span> | <span data-ttu-id="7ab2e-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="7ab2e-166">CustomAttribute13</span></span> |
| <span data-ttu-id="7ab2e-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="7ab2e-167">ExtensionAttribute14</span></span> | <span data-ttu-id="7ab2e-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="7ab2e-168">CustomAttribute14</span></span> |
| <span data-ttu-id="7ab2e-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="7ab2e-169">ExtensionAttribute15</span></span> | <span data-ttu-id="7ab2e-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="7ab2e-170">CustomAttribute15</span></span> |
| <span data-ttu-id="7ab2e-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7ab2e-171">MSExchExtensionCustomAttribute1</span></span> | <span data-ttu-id="7ab2e-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7ab2e-172">ExtensionCustomAttribute1</span></span> |
| <span data-ttu-id="7ab2e-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7ab2e-173">MSExchExtensionCustomAttribute2</span></span> | <span data-ttu-id="7ab2e-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7ab2e-174">ExtensionCustomAttribute2</span></span> |
| <span data-ttu-id="7ab2e-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7ab2e-175">MSExchExtensionCustomAttribute3</span></span> | <span data-ttu-id="7ab2e-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7ab2e-176">ExtensionCustomAttribute3</span></span> |
| <span data-ttu-id="7ab2e-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7ab2e-177">MSExchExtensionCustomAttribute4</span></span> | <span data-ttu-id="7ab2e-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7ab2e-178">ExtensionCustomAttribute4</span></span> |
| <span data-ttu-id="7ab2e-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7ab2e-179">MSExchExtensionCustomAttribute5</span></span> | <span data-ttu-id="7ab2e-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7ab2e-180">ExtensionCustomAttribute5</span></span> |
| <span data-ttu-id="7ab2e-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="7ab2e-181">MailNickname</span></span> | <span data-ttu-id="7ab2e-182">エイリアス</span><span class="sxs-lookup"><span data-stu-id="7ab2e-182">Alias</span></span> |
| <span data-ttu-id="7ab2e-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="7ab2e-183">PhysicalDeliveryOfficeName</span></span> | <span data-ttu-id="7ab2e-184">Office</span><span class="sxs-lookup"><span data-stu-id="7ab2e-184">Office</span></span> |
| <span data-ttu-id="7ab2e-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="7ab2e-185">PostalCode</span></span> | <span data-ttu-id="7ab2e-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="7ab2e-186">PostalCode</span></span> |
| <span data-ttu-id="7ab2e-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7ab2e-187">ProxyAddresses</span></span> | <span data-ttu-id="7ab2e-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="7ab2e-188">EmailAddresses</span></span> |
| <span data-ttu-id="7ab2e-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="7ab2e-189">StreetAddress</span></span> | <span data-ttu-id="7ab2e-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="7ab2e-190">StreetAddress</span></span> |
| <span data-ttu-id="7ab2e-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="7ab2e-191">TargetAddress</span></span> | <span data-ttu-id="7ab2e-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="7ab2e-192">ExternalEmailAddress</span></span> |
| <span data-ttu-id="7ab2e-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="7ab2e-193">UsageLocation</span></span> | <span data-ttu-id="7ab2e-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="7ab2e-194">UsageLocation</span></span> |
| <span data-ttu-id="7ab2e-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7ab2e-195">UserPrincipalName</span></span> | <span data-ttu-id="7ab2e-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7ab2e-196">UserPrincipalName</span></span> |
| <span data-ttu-id="7ab2e-197">メール</span><span class="sxs-lookup"><span data-stu-id="7ab2e-197">Mail</span></span> | <span data-ttu-id="7ab2e-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="7ab2e-198">WindowsEmailAddress</span></span> |
| <span data-ttu-id="7ab2e-199">説明</span><span class="sxs-lookup"><span data-stu-id="7ab2e-199">Description</span></span> | <span data-ttu-id="7ab2e-200">説明</span><span class="sxs-lookup"><span data-stu-id="7ab2e-200">Description</span></span> |
| <span data-ttu-id="7ab2e-201">MemberOf</span><span class="sxs-lookup"><span data-stu-id="7ab2e-201">MemberOf</span></span> | <span data-ttu-id="7ab2e-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="7ab2e-202">MemberOfGroup</span></span> |

## <a name="resources"></a><span data-ttu-id="7ab2e-203">リソース</span><span class="sxs-lookup"><span data-stu-id="7ab2e-203">Resources</span></span>

- [<span data-ttu-id="7ab2e-204">Microsoft Teams で情報障壁のポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="7ab2e-204">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="7ab2e-205">情報バリアのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7ab2e-205">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
- [<span data-ttu-id="7ab2e-206">情報障壁</span><span class="sxs-lookup"><span data-stu-id="7ab2e-206">Information barriers</span></span>](information-barriers.md)
