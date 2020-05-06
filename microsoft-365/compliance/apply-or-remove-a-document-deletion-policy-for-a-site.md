---
title: サイトのドキュメント削除ポリシーを適用または削除する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
ms.custom:
- seo-marvel-apr2020
description: Office 365 サイトコレクションでドキュメント削除ポリシーを作成、削除、および管理する方法について説明します。
ms.openlocfilehash: 7a9cbec25349de02da35f0aaf0cc206774a9b59a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034341"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="3192b-103">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="3192b-103">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="3192b-104">多くの場合、組織は一定期間、ドキュメントの保持が要求されるコンプライアンス、法的要件、その他の規制を受けます。</span><span class="sxs-lookup"><span data-stu-id="3192b-104">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="3192b-105">しかし、必要以上にドキュメントを長く保持すると、組織が法的なリスクにさらされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-105">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="3192b-106">このため、組織でサイト&mdash;用のドキュメント削除ポリシーが作成されている場合があります。たとえば、一般的なビジネスドキュメントは作成後5年間で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-106">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="3192b-107">組織に応じて、ドキュメント削除ポリシーには次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3192b-107">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="3192b-108">**必須**サイト所有者は必須ポリシーから脱退できません。これは、サイトに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3192b-108">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="3192b-109">**既定** 既定のポリシーがサイトに自動的に適用されますが、サイトの所有者には次の選択肢がある。</span><span class="sxs-lookup"><span data-stu-id="3192b-109">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="3192b-110">利用可能な場合は、別のポリシーを選択する。</span><span class="sxs-lookup"><span data-stu-id="3192b-110">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="3192b-111">サイトのコンテンツに関連していない場合は、ポリシーを完全にオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="3192b-111">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="3192b-112">**必須でも既定でもない** この場合、サイトにはどのポリシーも自動的に適用されず、サイトの所有者はポリシーを適用するためにアクションが必要。</span><span class="sxs-lookup"><span data-stu-id="3192b-112">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="3192b-113">ドキュメント削除ポリシーには、複数のルール&mdash;が含まれている場合があります。たとえば、作成後1年後にドキュメントを削除するとします。ただし、別のルールは、最後に変更された後1年後にドキュメントを削除する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-113">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="3192b-114">ポリシーに複数のルールが含まれている場合は、自分のサイトに最も適したルールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3192b-114">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="3192b-115">削除ルールは、サイト内のすべてのライブラリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3192b-115">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="3192b-116">1 つのサイトに一度に有効にできるのは、1 つのポリシーおよび 1 つのルールのみです。</span><span class="sxs-lookup"><span data-stu-id="3192b-116">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="3192b-117">ポリシーと同様に、ルールを既定として設定して、ポリシーが適用されたときにルールが自動的に適用されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3192b-117">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="3192b-p103">最後に、ドキュメント削除ポリシーは継承されます。サイトにポリシーやルールを選択すると、その選択はすべてのサブサイトに継承されますが、サブサイトの所有者は別のポリシーやルールを選択することにより、継承を止めることができます。ポリシーやルールを選択する際には、サイトの下位にあるすべてのサブサイトのコンテンツを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3192b-p103">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="3192b-121">サイト コレクションで使用できるドキュメント削除ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="3192b-121">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="3192b-p104">組織は、異なるサイト コレクションに異なるポリシーを割り当てる場合があります。サイト コレクション レベルでは、サイト コレクションの所有者は、そのサイト コレクションで使用可能なすべてのドキュメント削除ポリシーを表示できます。ポリシーはサイト コレクション テンプレート (そしてそのテンプレートから作成されたすべてのサイト コレクション) で使用できるようになっている場合も、その特定のサイト コレクションで使用できるようになっている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3192b-p104">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="3192b-125">サイトコレクションのトップレベルサイトで、右上隅の [**設定**] [歯車アイコン] [ \> **サイトの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3192b-125">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="3192b-126">[**サイトコレクションの管理** \> **ドキュメント削除ポリシー**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="3192b-126">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3192b-127">サイトコレクションにポリシーが割り当てられていない場合、[**ドキュメント削除ポリシー**のリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3192b-127">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="3192b-128">また、リンクは、ポリシーがサイトに割り当てられた直後には表示されず、[**ドキュメント削除ポリシー** ] リンクが表示されるときにポリシーが割り当てられると、最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3192b-128">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="3192b-129">このページでは次のものが確認できます。</span><span class="sxs-lookup"><span data-stu-id="3192b-129">On this page you can view:</span></span>
    
  - <span data-ttu-id="3192b-p106">現在割り当てられているポリシーおよび関連するルール。右側のウィンドウで、ルールを表示するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3192b-p106">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="3192b-132">既定のポリシーがある場合、[**既定**] 列に [**はい**] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3192b-132">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="3192b-133">ポリシーが [**必須**] として割り当てられている場合は、リストの下にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3192b-133">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="3192b-p107">このリストは表示専用であり、サイト コレクションの所有者に、使用可能なすべてのポリシーとルールが表示されます。ポリシーを適用するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3192b-p107">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![サイト コレクションに割り当てられているドキュメント削除ポリシーの表示](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="3192b-137">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="3192b-137">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="3192b-138">サイト所有者またはサイト コレクション所有者が自分のサイトに適用するか、まったく適用しないかを選択できるポリシーを組織が作成してある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-138">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="3192b-139">右上隅で、[**設定**] [歯車アイコン] [サイト\>の**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3192b-139">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="3192b-140">[**サイト管理** \>の**ドキュメント削除ポリシー**] の下。</span><span class="sxs-lookup"><span data-stu-id="3192b-140">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3192b-141">サイトコレクションにポリシーが割り当てられていない場合、[**ドキュメント削除ポリシー**のリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3192b-141">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="3192b-142">また、リンクは、ポリシーがサイトに割り当てられた直後には表示されず、[**ドキュメント削除ポリシー** ] リンクが表示されるときにポリシーが割り当てられると、最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3192b-142">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="3192b-143">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="3192b-143">Do one of the following:</span></span>
    
  - <span data-ttu-id="3192b-144">**ポリシーを適用するには**ポリシー \>の選択そのポリシー \>の [**保存**] でルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3192b-144">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="3192b-p109">1 つのサイトに一度に有効にできるのは、1 つのポリシーおよび 1 つのルールのみです。組織は複数のポリシーとルールを用意して選択できるようにする場合も、ポリシーやルールを 1 つだけ用意する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3192b-p109">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![ポリシーオプションの選択](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="3192b-148">**ポリシーからオプトアウトするに**は[**オプトアウト: Do Note Delete** \> **Save**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3192b-148">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="3192b-149">サイトの所有者は、ポリシーがサイトのコンテンツに適用できないと判断した場合は、ドキュメント削除ポリシーをオプトアウトできます。</span><span class="sxs-lookup"><span data-stu-id="3192b-149">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="3192b-150">ただし、**必須**としてマークされているポリシーからオプトアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3192b-150">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![オプトアウトオプション](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="3192b-152">ドキュメント削除ポリシーによる、他のポリシーの上書き</span><span class="sxs-lookup"><span data-stu-id="3192b-152">Document deletion policies override other policies</span></span>

<span data-ttu-id="3192b-153">コンテンツの保持と削除のために、サイトでは別のポリシーを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-153">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="3192b-154">サイト コレクションのコンテンツ タイプ ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3192b-154">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="3192b-155">リストまたはライブラリの情報管理ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3192b-155">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="3192b-156">リストまたはライブラリ用に既にコンテンツ タイプ ポリシーまたは情報管理ポリシーを使用しているサイトにドキュメント削除ポリシーを適用した場合、前者のポリシーは無視され、ドキュメント削除ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="3192b-156">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="3192b-157">他のポリシーが無視されると、"このサイトのコンテンツは、ドキュメント削除ポリシーを使用しています。" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3192b-157">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="3192b-158">つまり、構造化コンテンツ (情報管理ポリシーとコンテンツ タイプ ポリシー) 用か、非構造化コンテンツ (ドキュメント削除ポリシー) 用のいずれかのポリシーのみを使用するサイトを計画する必要があり、両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3192b-158">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="3192b-159">ドキュメント削除ポリシーの設定を解除した場合、警告は表示されず、他の種類のポリシーが引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="3192b-159">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="3192b-160">サイト ポリシーはドキュメント削除ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="3192b-160">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="3192b-161">コンテンツ タイプ ポリシーが無視されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="3192b-161">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="3192b-162">サイトでコンテンツ タイプ ポリシーが使用されていたが、このメッセージが表示される場合、それらのポリシーはもう有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3192b-162">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="3192b-163">コンテンツタイプのポリシーを復元するには、使用可能なオプトアウトオプションがある場合は、前に説明したように、サイトからドキュメント削除ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3192b-163">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="3192b-164">オプトアウトするオプションがない場合は、ドキュメント削除ポリシーは必須であり、組織のコンプライアンス責任者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-164">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="3192b-165">右上隅で、[**設定**] [歯車アイコン] [サイト\>の**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3192b-165">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="3192b-166">[**サイト管理** \> **コンテンツタイプポリシーテンプレート**] の下。</span><span class="sxs-lookup"><span data-stu-id="3192b-166">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![サイト削除ポリシーが使用されていることを示す警告](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="3192b-168">情報管理ポリシーが無視されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="3192b-168">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="3192b-169">サイトで情報管理ポリシーが使用されていたが、このメッセージが表示される場合、それらのポリシーはもう有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3192b-169">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="3192b-170">情報管理ポリシーを復元するには、前に説明したように、使用可能なオプトアウトオプションがある場合は、ドキュメント削除ポリシーをサイトから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3192b-170">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="3192b-171">オプトアウトするオプションがない場合は、ドキュメント削除ポリシーは必須であり、組織のコンプライアンス責任者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3192b-171">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="3192b-172">\>リストまたはライブラリの場合、[**権限と管理** \> **情報管理ポリシーの設定**] の [リボン**ライブラリ**] タブ\> **ライブラリの設定** \> 。</span><span class="sxs-lookup"><span data-stu-id="3192b-172">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![サイト削除ポリシーが使用されていることを示す警告](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="3192b-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="3192b-174">See also</span></span>

[<span data-ttu-id="3192b-175">ドキュメント削除ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="3192b-175">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="3192b-176">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3192b-176">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

