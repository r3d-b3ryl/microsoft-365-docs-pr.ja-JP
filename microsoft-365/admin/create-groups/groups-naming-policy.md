---
title: Office 365 グループの名前付けポリシー
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Office 365 グループの名前付けポリシーを作成する方法について説明します。
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241392"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="304d4-103">Office 365 グループの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="304d4-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="304d4-104">グループの名前付けポリシーを使用して、組織内のユーザーによって作成されたグループに一貫した名前付け戦略を適用します。</span><span class="sxs-lookup"><span data-stu-id="304d4-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="304d4-105">名前付けポリシーにより、お客様とユーザーがグループの機能、メンバーシップ、地域、グループの作成者を特定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="304d4-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="304d4-106">名前付けポリシーは、アドレス帳のグループの分類にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="304d4-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="304d4-107">ポリシーを使用して、特定の単語をグループの名前やエイリアスで使われないようにブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="304d4-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="304d4-p102">名前付けポリシーは、すべてのグループのワークロード (Outlook、Microsoft Teams、SharePoint、Planner、Yammer など) で作成されたグループに適用されます。グループ名とグループのエイリアスのどちらにも適用されます。名前付けポリシーは、ユーザーによるグループの作成時、または既存のグループのグループ名やエイリアスの編集時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-p102">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc). It gets applied to both the group name and group alias. It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="304d4-111">Office 365 グループの名前付けポリシーは Office 365 グループにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="304d4-112">Exchange Online で作成された配布グループには適用されません。</span><span class="sxs-lookup"><span data-stu-id="304d4-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="304d4-113">配布グループの名前付けポリシーを作成するには、「[配布グループ名前付けポリシーを作成](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="304d4-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="304d4-114">グループの名前付けポリシーは、次の機能で構成されています。</span><span class="sxs-lookup"><span data-stu-id="304d4-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="304d4-115">**プレフィックス/サフィックスの名前付けポリシー**: グループの名前付け規則を定義するには、プレフィックスまたはサフィックスを使用\_でき\_ます (\_例: "GRP US My Group Engineering")。</span><span class="sxs-lookup"><span data-stu-id="304d4-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="304d4-116">プレフィックス/サフィックスは、固定文字列、またはグループを作成しているユーザーに基づいて置換される [Department] などのユーザー属性のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="304d4-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="304d4-117">ユーザー**設定のブロック**された単語: 組織に固有で、ユーザーが作成したグループでブロックされるブロックされる単語のセットをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="304d4-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="304d4-118">(例: "CEO, Payroll, HR")。</span><span class="sxs-lookup"><span data-stu-id="304d4-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="304d4-119">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="304d4-119">Licensing requirements</span></span>

<span data-ttu-id="304d4-120">Office 365 グループに Azure AD の名前付けポリシーを使用するには、1つ以上の Office 365 グループのメンバーである一意のユーザー (ゲストを含む) ごとに、Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU ライセンスが割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="304d4-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="304d4-121">これは、グループの名前付けポリシーを作成する管理者にも必要になります。</span><span class="sxs-lookup"><span data-stu-id="304d4-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="304d4-122">プレフィックスサフィックスの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="304d4-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="304d4-123">プレフィックスとサフィックスは、固定文字列またはユーザー属性のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="304d4-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="304d4-124">固定文字列</span><span class="sxs-lookup"><span data-stu-id="304d4-124">Fixed strings</span></span>

<span data-ttu-id="304d4-125">短い文字列を使って、GAL およびグループのワークロードの左のナビゲーションでグループを区別するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="304d4-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="304d4-126">一般的なプレフィックスのサフィックスには、' Grp\_Name '、'\#name '、'\_name ' などのキーワードがあります。</span><span class="sxs-lookup"><span data-stu-id="304d4-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="304d4-127">属性</span><span class="sxs-lookup"><span data-stu-id="304d4-127">Attributes</span></span>

<span data-ttu-id="304d4-128">属性を使って、[Department] のようにグループを作成したユーザー、および [Country] のように作成された場所を識別するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="304d4-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="304d4-129">**例**</span><span class="sxs-lookup"><span data-stu-id="304d4-129">**Examples**</span></span>|<span data-ttu-id="304d4-130">Policy = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="304d4-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="304d4-131">User's department = Engineering</span><span class="sxs-lookup"><span data-stu-id="304d4-131">User's department = Engineering</span></span>|
||<span data-ttu-id="304d4-132">Created group name = "GRP My Group Engineering"</span><span class="sxs-lookup"><span data-stu-id="304d4-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="304d4-133">サポートされている Azure Active Directory (Azure AD) 属性は [部署]、[会社]、[Office]、[StateOrProvince]、[CountryOrRegion]、[Title]</span><span class="sxs-lookup"><span data-stu-id="304d4-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="304d4-p108">サポートされていないユーザー属性は、固定文字列と見なされます。例: "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="304d4-p108">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="304d4-137">拡張属性とカスタム属性はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="304d4-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="304d4-138">組織のすべてのユーザーに対して、値が設定された属性を使用することをお勧めします。長い値が設定された属性は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="304d4-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="304d4-139">次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="304d4-139">Things to look out for</span></span>

- <span data-ttu-id="304d4-140">ポリシーを作成するときは、プレフィックスとサフィックスの合計文字数は 53 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="304d4-p109">プレフィックスとサフィックスには、グループ名とグループのエイリアスでサポートされている特殊文字を含めることができます。プレフィックスとサフィックスに、グループのエイリアスで許可されていない特殊文字が含まれている場合は、それらは削除されてグループのエイリアスに適用されます。そのため、この場合は、グループ名に適用されているプレフィックスとサフィックスは、グループのエイリアスに適用されているものとは異なります。</span><span class="sxs-lookup"><span data-stu-id="304d4-p109">Prefixes and suffixes can contain special characters supported in group name and group alias. When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias. So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="304d4-144">Yammer Office 365 に接続されたグループを使用している場合は、名前付けポリシーで、 \#@ \[、 \]、 \<、、 \>、およびの文字を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="304d4-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="304d4-145">これらの文字が名前付けポリシーに含まれている場合、正規の Yammer ユーザーはグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="304d4-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="304d4-146">ユーザー設定のブロックされた単語</span><span class="sxs-lookup"><span data-stu-id="304d4-146">Custom blocked words</span></span>

<span data-ttu-id="304d4-147">ブロックされた単語のリストをコンマ区切りで入力できます。これは、グループの名前とエイリアスでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="304d4-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="304d4-148">ブロックされた単語チェックは、ユーザーが入力したグループ名に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="304d4-149">このため、ユーザーが ' darnit ' と '\_prefix ' を入力すると、名前\_付けポリシーになります。 ' prefix darnit ' は失敗します。</span><span class="sxs-lookup"><span data-stu-id="304d4-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="304d4-150">サブ文字列検索は実行されません。具体的には、エラーを発生させるには、ユーザーが入力した名前とカスタムのブロックされた単語が完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="304d4-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="304d4-151">サブ文字列の検索は行われないので、ユーザーは ' 「をブロックする」の単語であっても、' Class ' のような一般的な単語を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="304d4-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="304d4-152">次**の点に注目して**ください。</span><span class="sxs-lookup"><span data-stu-id="304d4-152">**Things to look out for**:</span></span>

- <span data-ttu-id="304d4-153">ブロックする単語は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="304d4-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="304d4-154">ユーザーがブロックする単語を入力すると、グループ クライアントによって、ブロックされた単語を含むエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="304d4-155">ブロックする単語で使用する文字に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="304d4-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="304d4-156">ブロックする単語として設定できる、上限は5000単語に制限されています。</span><span class="sxs-lookup"><span data-stu-id="304d4-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="304d4-157">管理者による上書き</span><span class="sxs-lookup"><span data-stu-id="304d4-157">Admin override</span></span>

<span data-ttu-id="304d4-p113">管理者はブロックする単語と必要な名前付け規則を使ってグループを作成できるように、選択された管理者は、これらのポリシー、すべてのグループのワークロードおよびエンドポイントの適用から除外されます。グループの名前付けポリシーの適用から除外される管理者の役割リストは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="304d4-p113">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="304d4-160">全体管理者</span><span class="sxs-lookup"><span data-stu-id="304d4-160">Global admin</span></span>

- <span data-ttu-id="304d4-161">パートナー レベル 1 のサポート</span><span class="sxs-lookup"><span data-stu-id="304d4-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="304d4-162">パートナー レベル 2 のサポート</span><span class="sxs-lookup"><span data-stu-id="304d4-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="304d4-163">ユーザー アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="304d4-163">User account admin</span></span>

- <span data-ttu-id="304d4-164">ディレクトリ製作者</span><span class="sxs-lookup"><span data-stu-id="304d4-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="304d4-165">名前付けポリシーをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="304d4-165">How to set up the naming policy</span></span>

<span data-ttu-id="304d4-166">名前付けポリシーをセットアップするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="304d4-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="304d4-167">[Azure Active Directory](https://aad.portal.azure.com)の [**管理**] で、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="304d4-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="304d4-168">[**設定**] の [**名前付けポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="304d4-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="304d4-169">[**グループの名前付けポリシー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="304d4-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="304d4-170">[**現在のポリシー**] で、プレフィックスかサフィックス、あるいはその両方を要求するかどうかを選択し、適切なチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="304d4-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="304d4-171">各行の**属性**と**文字列**を選択してから、属性または文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="304d4-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="304d4-172">必要なプレフィックスとサフィックスを追加したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="304d4-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory のグループの名前付けポリシーの設定のスクリーンショット](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="304d4-174">Office 365 アプリ全体の名前付けポリシーの操作環境</span><span class="sxs-lookup"><span data-stu-id="304d4-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="304d4-p114">ユーザーがグループの名前とエイリアスを入力すると、Office 365 アプリが更新され、(プレフィックスとサフィックスと共に) 名前付けポリシーのグループ名のプレビューが表示されます。ユーザーがブロックされた単語を入力すると、ブロックされた単語を削除できるように、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-p114">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias. When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="304d4-177">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="304d4-177">Outlook on the web</span></span>

<span data-ttu-id="304d4-178">Web 上の outlook (旧称: Outlook Web App または OWA) は、ユーザーがグループ名またはグループエイリアスを入力したときに表示される名前付けポリシーの装飾名を示しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="304d4-179">ユーザーがカスタムのブロックする単語を入力すると、ユーザーがその単語を削除できるように、エラー メッセージがブロックされた単語と共に UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="304d4-180">Outlook on the web experience のスナップショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="304d4-180">Outlook on the web experience snapshots are shown below.</span></span>

![Office 365 グループのグループの名前付けポリシーの並べて表示](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="304d4-182">Outlook デスクトップ</span><span class="sxs-lookup"><span data-stu-id="304d4-182">Outlook Desktop</span></span>

<span data-ttu-id="304d4-183">Outlook デスクトップで作成されたグループは、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="304d4-184">Outlook デスクトップアプリは、まだ名前付けポリシーのプレビューを表示せず、ユーザーがグループ名を入力したときに、ユーザー設定のブロックされた word エラーを返しません。</span><span class="sxs-lookup"><span data-stu-id="304d4-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="304d4-185">ただし、グループ名またはエイリアスにユーザー設定のブロックされた単語がある場合、[作成/編集] を選択すると名前付けポリシーが自動的に適用され、ユーザーにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="304d4-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="304d4-186">Microsoft Teams</span></span>

<span data-ttu-id="304d4-p117">ユーザーがチーム名を入力すると、Microsoft Teams に名前付けポリシーを修飾した名前が表示されます。ユーザーがカスタムのブロックする単語を入力すると、ユーザーがその単語を削除できるように、エラー メッセージがブロックされた単語と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-p117">Microsoft Teams shows the naming policy decorated name when the user types a team name. When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Microsoft Teams のグループ名前付けポリシーのブロック例](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="304d4-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="304d4-190">SharePoint</span></span>

<span data-ttu-id="304d4-191">ユーザーがサイト名またはグループの電子メールアドレスを入力すると、SharePoint によって名前付けポリシー名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="304d4-192">ユーザーがカスタムのブロックする単語を入力すると、ユーザーがその単語を削除できるように、エラー メッセージがブロックされた単語と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![グループの名前付けポリシー-SharePoint サイトのブロックされた名前](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="304d4-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="304d4-194">Microsoft Stream</span></span>

<span data-ttu-id="304d4-p119">ユーザーがグループ名またはグループのエイリアスを入力すると、Microsoft Stream で名前付けポリシーを修飾した名前が表示されます。ユーザーがカスタムのブロックする単語を入力すると、ユーザーがその単語を削除できるように、エラー メッセージがブロックされた単語と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-p119">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias. When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Microsoft Stream のグループ名前付けポリシーのブロック例](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="304d4-198">iOS と Android の Outlook アプリ</span><span class="sxs-lookup"><span data-stu-id="304d4-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="304d4-199">Outlook アプリで作成されたグループは、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="304d4-200">Outlook mobile では、グループ名を入力するときに名前付けポリシーのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="304d4-201">ユーザーがカスタムのブロックされた単語を入力すると、グループの作成時にエラーメッセージが表示され、ユーザーはブロックされた単語を削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="304d4-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="304d4-202">Planner</span><span class="sxs-lookup"><span data-stu-id="304d4-202">Planner</span></span>

<span data-ttu-id="304d4-203">Planner は、名前付けポリシーに準拠します。</span><span class="sxs-lookup"><span data-stu-id="304d4-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="304d4-204">Planner には、プラン名を入力するときの名前付けポリシーのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="304d4-205">ユーザーがカスタムのブロックされた単語を入力すると、プランを作成するときにエラーメッセージが表示されるので、ユーザーはブロックされた単語を削除できます。</span><span class="sxs-lookup"><span data-stu-id="304d4-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![グループの名前付けポリシー-新しいプランの作成のブロックされた例](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="304d4-207">顧客契約のための Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="304d4-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="304d4-208">顧客契約の Dynamics 365 は、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="304d4-209">Dynamics 365 は、ユーザーがグループ名またはグループの電子メールエイリアスを入力したときに表示される名前付けポリシーの装飾名を示しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="304d4-210">ユーザーがカスタムのブロックされた単語を入力すると、ユーザーが削除できるように、エラーメッセージがブロックされた単語と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="304d4-212">School Data Sync (SDS)</span><span class="sxs-lookup"><span data-stu-id="304d4-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="304d4-p123">SDS を使って作成されたグループは名前付けポリシーに準拠しますが、名前付けポリシーは自動的に適用されません。SDS 管理者は、グループを作成する必要があるクラス名にプレフィックスとサフィックスを追加し、SDS にアップロードする必要があります。それ以外の場合は、グループの作成または編集は失敗します。</span><span class="sxs-lookup"><span data-stu-id="304d4-p123">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically. SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS. Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="304d4-216">Outlook カスタマーマネージャー (OCM)</span><span class="sxs-lookup"><span data-stu-id="304d4-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="304d4-217">Outlook カスタマーマネージャーは、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="304d4-218">名前付けポリシーは、Outlook カスタマーマネージャーで作成したグループに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="304d4-219">「すべての営業チーム」内の単語のいずれかがカスタムのブロックされた単語として定義されている場合、OCM でのグループの作成はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="304d4-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="304d4-220">ユーザーは OCM グループを作成できなくなり、OCM アプリの使用が禁止されます。 "</span><span class="sxs-lookup"><span data-stu-id="304d4-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="304d4-221">Classroom アプリ</span><span class="sxs-lookup"><span data-stu-id="304d4-221">Classroom App</span></span>

<span data-ttu-id="304d4-p125">Classroom アプリで作成されたグループは、名前付けポリシーに準拠しますが、名前付けポリシーが自動的に適用されるわけではありません。また、名前付けポリシーのプレビューは、教室グループの名前を入力するときにユーザーに表示されません。そのため、ユーザーはプレフィックスとサフィックスで修飾された教室グループ名を入力する必要があります。それ以外の場合、教室グループの作成または編集は失敗し、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-p125">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name. So users would have to enter the decorated classroom group name with prefixes and suffixes. Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="304d4-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="304d4-225">Power BI</span></span>

<span data-ttu-id="304d4-226">Power BI ワークスペースで作成されたグループは、名前付けポリシーに準拠していますが、名前付けポリシーは自動的には適用されません。</span><span class="sxs-lookup"><span data-stu-id="304d4-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="304d4-227">また、ユーザーが Power BI ワークスペース名を入力するときに、名前付けポリシーのプレビューは表示されません。</span><span class="sxs-lookup"><span data-stu-id="304d4-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="304d4-228">推奨される名前 (名前付けポリシーを適用済み) は、「create or edit workspace」のエラーの詳細に示されています。</span><span class="sxs-lookup"><span data-stu-id="304d4-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="304d4-229">これは、ユーザーが、修飾されたワークスペース名にプレフィックスとサフィックスを入力する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="304d4-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="304d4-230">それ以外の場合、ワークスペースの作成または編集はエラーが発生して失敗します。</span><span class="sxs-lookup"><span data-stu-id="304d4-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="304d4-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="304d4-231">Yammer</span></span>

<span data-ttu-id="304d4-232">ユーザーが Azure Active Directory アカウントを使用して Yammer にサインインすると、グループが作成されるか、グループ名が編集されると、グループ名は名前付けポリシーに準拠します。</span><span class="sxs-lookup"><span data-stu-id="304d4-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="304d4-233">これは、Office 365 接続グループとその他すべての Yammer グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="304d4-234">名前付けポリシーが設定される前に Office 365 接続グループを作成した場合、グループ名は自動的に命名ポリシーに従いません。</span><span class="sxs-lookup"><span data-stu-id="304d4-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="304d4-235">ユーザーがグループ名を編集すると、プレフィックスとサフィックスを追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="304d4-236">名前付けポリシーに Yammer グループ名にできない文字が含まれている場合、管理者のみが Yammer に接続されたグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="304d4-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="304d4-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="304d4-237">StaffHub</span></span>

<span data-ttu-id="304d4-238">StaffHub teams は、名前付けポリシーに従いませんが、基礎となる Office 365 グループになります。</span><span class="sxs-lookup"><span data-stu-id="304d4-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="304d4-239">StaffHub チーム名は、プレフィックスとサフィックスを適用せず、カスタムのブロックされた単語をチェックしません。</span><span class="sxs-lookup"><span data-stu-id="304d4-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="304d4-240">ただし、StaffHub はプレフィックスとサフィックスを適用し、基になる Office 365 グループからブロックされた単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="304d4-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="304d4-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="304d4-241">Exchange PowerShell</span></span>

<span data-ttu-id="304d4-p131">Exchange PowerShell コマンドレットは、名前付けポリシーに準拠します。名前付け規則がグループの名前とグループのエイリアスで使用されない場合、ユーザーは候補のプレフィックスとサフィックスを含む、カスタムのブロックする単語に対する適切なエラー メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="304d4-p131">Exchange PowerShell cmdlets are compliant with naming policy. Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="304d4-244">Azure Active Directory PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="304d4-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="304d4-245">Azure Active Directory PowerShell コマンドレットは、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="304d4-246">名前付け規則がグループの名前とグループのエイリアスで使用されない場合、ユーザーは候補のプレフィックスとサフィックスを含む、カスタムのブロックする単語に対する適切なエラー メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="304d4-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="304d4-247">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="304d4-247">Exchange admin center</span></span>

<span data-ttu-id="304d4-248">Exchange 管理センター (EAC) は、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="304d4-249">作成または編集のアクションでは、名前付け規則がグループの名前とグループのエイリアスで使用されない場合、ユーザーは候補のプレフィックスとサフィックスを含む、カスタムのブロックする単語に対する適切なエラー メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="304d4-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="304d4-250">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="304d4-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="304d4-251">Microsoft 365 管理センターは、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="304d4-252">[アクションの作成または編集] では、名前付けポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="304d4-253">ユーザーがカスタムのブロックする単語を入力すると、適切なエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="304d4-254">Microsoft 365 管理センターでは、名前付けポリシーのプレビューは表示されず、ユーザーがグループ名を入力したときに、ユーザー設定のブロックされた word エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="304d4-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="304d4-255">Azure Active Directory ポータル</span><span class="sxs-lookup"><span data-stu-id="304d4-255">Azure Active Directory portal</span></span>

<span data-ttu-id="304d4-256">Azure Active Directory ポータルは、名前付けポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="304d4-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="304d4-257">Azure Active Directory ポータルには、グループ名を入力するときの名前付けポリシーのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="304d4-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="304d4-258">ユーザーがカスタムのブロックされた単語を入力すると、グループの作成時にエラーメッセージが表示され、ユーザーはブロックされた単語を削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="304d4-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="304d4-259">名前付けポリシーに関するその他の記事</span><span class="sxs-lookup"><span data-stu-id="304d4-259">More articles on naming policy</span></span>

[<span data-ttu-id="304d4-260">Azure Active Directory での Office 365 グループの名前付けポリシーの強制</span><span class="sxs-lookup"><span data-stu-id="304d4-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="304d4-261">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="304d4-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
