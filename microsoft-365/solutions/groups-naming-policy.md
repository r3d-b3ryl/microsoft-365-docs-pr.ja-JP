---
title: Microsoft 365 グループの名前付けポリシー
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Microsoft 365 グループの名前付けポリシーを作成する方法について説明します。
ms.openlocfilehash: 15fcbace737398c6edd2062e72622e8551ebd222
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613504"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="5a169-103">Microsoft 365 グループの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="5a169-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="5a169-104">グループの名前付けポリシーを使用して、組織内のユーザーによって作成されたグループに一貫した名前付け戦略を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="5a169-105">名前付けポリシーにより、お客様とユーザーがグループの機能、メンバーシップ、地域、グループの作成者を特定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5a169-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="5a169-106">名前付けポリシーは、アドレス帳のグループの分類にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a169-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="5a169-107">ポリシーを使用して、特定の単語をグループの名前やエイリアスで使われないようにブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="5a169-108">名前付けポリシーは、すべてのグループのワークロードに対して作成されたグループ (Outlook、Microsoft Teams、SharePoint、Planner、Yammer など) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="5a169-109">グループ名とグループのエイリアスの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="5a169-110">名前付けポリシーは、ユーザーによるグループの作成時、または既存のグループのグループ名やエイリアスの編集時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="5a169-111">Microsoft 365 グループの名前付けポリシーは、Microsoft 365 グループにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="5a169-112">Exchange Online で作成された配布グループには適用されません。</span><span class="sxs-lookup"><span data-stu-id="5a169-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="5a169-113">配布グループの名前付けポリシーを作成するには、「 [配布グループ名前付けポリシーを作成](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a169-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="5a169-114">グループの名前付けポリシーは、次の機能で構成されています。</span><span class="sxs-lookup"><span data-stu-id="5a169-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="5a169-115">**プレフィックス/サフィックスの名前付けポリシー**: グループの名前付け規則を定義するには、プレフィックスまたはサフィックスを使用できます (例: "US \_ My Group \_ Engineering")。</span><span class="sxs-lookup"><span data-stu-id="5a169-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="5a169-116">プレフィックス/サフィックスは、固定文字列、またはグループを作成しているユーザーに基づいて置換される [Department] などのユーザー属性のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="5a169-117">ユーザー **設定のブロック** された単語: 組織に固有で、ユーザーが作成したグループでブロックされるブロックされる単語のセットをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5a169-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="5a169-118">(例: "CEO, Payroll, HR")。</span><span class="sxs-lookup"><span data-stu-id="5a169-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5a169-119">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="5a169-119">Licensing requirements</span></span>

<span data-ttu-id="5a169-120">Microsoft 365 グループの Azure AD 名前付けポリシーを使用するには、1つ以上の Microsoft 365 グループのメンバーである一意のユーザー (ゲストを含む) ごとに、Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU ライセンスを所有している必要がありますが、必ずしも割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a169-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="5a169-121">これは、グループの名前付けポリシーを作成する管理者にも必要になります。</span><span class="sxs-lookup"><span data-stu-id="5a169-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="5a169-122">Prefix-Suffix 名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="5a169-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="5a169-123">プレフィックスとサフィックスは、固定文字列またはユーザー属性のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="5a169-124">固定文字列</span><span class="sxs-lookup"><span data-stu-id="5a169-124">Fixed strings</span></span>

<span data-ttu-id="5a169-125">短い文字列を使用して、GAL とグループワークロードの左側のナビゲーションでグループを区別するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a169-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="5a169-126">一般的なプレフィックスのサフィックスには、' Grp \_ Name '、' \# name '、' \_ name ' などのキーワードがあります。</span><span class="sxs-lookup"><span data-stu-id="5a169-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="5a169-127">属性</span><span class="sxs-lookup"><span data-stu-id="5a169-127">Attributes</span></span>

<span data-ttu-id="5a169-128">属性を使って、[Department] のようにグループを作成したユーザー、および [Country] のように作成された場所を識別するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="5a169-129">例:</span><span class="sxs-lookup"><span data-stu-id="5a169-129">Examples:</span></span>

- <span data-ttu-id="5a169-130">Policy = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="5a169-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="5a169-131">User's department = Engineering</span><span class="sxs-lookup"><span data-stu-id="5a169-131">User's department = Engineering</span></span>
- <span data-ttu-id="5a169-132">Created group name = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="5a169-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="5a169-133">サポートされている Azure Active Directory (Azure AD) 属性は、[部署]、[会社]、[Office]、[StateOrProvince]、[CountryOrRegion]、[Title] です。</span><span class="sxs-lookup"><span data-stu-id="5a169-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="5a169-134">サポートされていないユーザー属性は、[郵便番号] などの固定文字列と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5a169-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="5a169-135">拡張属性とカスタム属性はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5a169-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="5a169-136">組織のすべてのユーザーに対して、値が設定された属性を使用することをお勧めします。長い値が設定された属性は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a169-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="5a169-137">次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a169-137">Things to look out for</span></span>

- <span data-ttu-id="5a169-138">ポリシーを作成するときは、プレフィックスとサフィックスの合計文字数は 53 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="5a169-139">プレフィックスとサフィックスには、グループ名とグループのエイリアスでサポートされている特殊文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="5a169-140">プレフィックスとサフィックスに、グループエイリアスで許可されていない特殊文字が含まれている場合、それらはグループ名にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="5a169-141">そのため、この場合は、グループ名に適用されているプレフィックスとサフィックスは、グループのエイリアスに適用されているものとは異なります。</span><span class="sxs-lookup"><span data-stu-id="5a169-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5a169-142">グループ名の任意の場所にピリオド (.) またはハイフン (-) を使用できます。ただし、名前の先頭または末尾にある場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="5a169-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="5a169-143">グループ名の任意の場所にアンダースコア (_) を使用できます。名前の先頭または末尾を含むこともできます。</span><span class="sxs-lookup"><span data-stu-id="5a169-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="5a169-144">Yammer Office 365 に接続されたグループを使用している場合は、名前付けポリシーで次の文字を使用しないでください。 @、 \# 、 \[ 、、 \] \<, and \> 。</span><span class="sxs-lookup"><span data-stu-id="5a169-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="5a169-145">これらの文字が名前付けポリシーに含まれている場合、正規の Yammer ユーザーはグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="5a169-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="5a169-146">短い文字列をサフィックスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="5a169-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="5a169-147">値が指定された属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a169-147">Use attributes with values.</span></span>
> - <span data-ttu-id="5a169-148">創造的なので、名前の長さの合計は264文字までです。</span><span class="sxs-lookup"><span data-stu-id="5a169-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="5a169-149">使用制限する組織固有の禁止単語をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5a169-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="5a169-150">ユーザー設定のブロックされた単語</span><span class="sxs-lookup"><span data-stu-id="5a169-150">Custom blocked words</span></span>

<span data-ttu-id="5a169-151">ブロックされた単語のリストをコンマ区切りで入力できます。これは、グループの名前とエイリアスでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5a169-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="5a169-152">サブ文字列検索は実行されません。具体的には、エラーを発生させるには、ユーザーが入力した名前とカスタムのブロックされた単語が完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a169-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="5a169-153">次 **の点に注目して** ください。</span><span class="sxs-lookup"><span data-stu-id="5a169-153">**Things to look out for**:</span></span>

- <span data-ttu-id="5a169-154">ブロックする単語は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="5a169-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="5a169-155">ユーザーがブロックする単語を入力すると、グループ クライアントによって、ブロックされた単語を含むエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a169-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="5a169-156">ブロックする単語で使用する文字に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5a169-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="5a169-157">ブロックされた単語として設定できる単語数の制限は5000です。</span><span class="sxs-lookup"><span data-stu-id="5a169-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="5a169-158">管理者による上書き</span><span class="sxs-lookup"><span data-stu-id="5a169-158">Admin override</span></span>

<span data-ttu-id="5a169-159">一部の管理者は、これらのポリシーから除外され、それらのグループのワークロードおよびエンドポイント全体で、これらのブロックされた単語を使用してグループを作成したり、必要な名前付け規則を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a169-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="5a169-160">グループの名前付けポリシーの適用から除外される管理者の役割リストは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a169-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="5a169-161">全体管理者</span><span class="sxs-lookup"><span data-stu-id="5a169-161">Global admin</span></span>

- <span data-ttu-id="5a169-162">パートナー レベル 1 のサポート</span><span class="sxs-lookup"><span data-stu-id="5a169-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="5a169-163">パートナー レベル 2 のサポート</span><span class="sxs-lookup"><span data-stu-id="5a169-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="5a169-164">ユーザー アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="5a169-164">User account admin</span></span>

- <span data-ttu-id="5a169-165">ディレクトリ製作者</span><span class="sxs-lookup"><span data-stu-id="5a169-165">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="5a169-166">名前付けポリシーをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="5a169-166">How to set up the naming policy</span></span>

<span data-ttu-id="5a169-167">名前付けポリシーをセットアップするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5a169-167">To set up a naming policy:</span></span>

1. <span data-ttu-id="5a169-168">[Azure Active Directory](https://aad.portal.azure.com)の [**管理**] で、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a169-168">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="5a169-169">[ **設定**] の [ **名前付けポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a169-169">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="5a169-170">[ **グループの名前付けポリシー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a169-170">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="5a169-171">[ **現在のポリシー**] で、プレフィックスかサフィックス、あるいはその両方を要求するかどうかを選択し、適切なチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5a169-171">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="5a169-172">各行の **属性** と **文字列** を選択してから、属性または文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a169-172">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="5a169-173">必要なプレフィックスとサフィックスを追加したら、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a169-173">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory のグループの名前付けポリシーの設定のスクリーンショット](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="5a169-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a169-175">Related topics</span></span>

[<span data-ttu-id="5a169-176">コラボレーションガバナンスの計画のステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="5a169-176">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="5a169-177">コラボレーションのガバナンス計画を作成する</span><span class="sxs-lookup"><span data-stu-id="5a169-177">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="5a169-178">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5a169-178">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
