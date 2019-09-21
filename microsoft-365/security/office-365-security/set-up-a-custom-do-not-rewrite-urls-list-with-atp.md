---
title: Office 365 の ATP の安全なリンクを使用して、リライトしないカスタムの Url リストを設定する
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: ATP の安全なリンクポリシーを設定するときに、組織内の一部のユーザーがリストに含まれているサイトにアクセスできるようにするために、Url の書き換え不可のリストを含めることができます。
ms.openlocfilehash: 7debc03fd11ddcdf6fd930779c56d686e30fb389
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086330"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="70995-103">Office 365 の ATP の安全なリンクを使用して、リライトしないカスタムの Url リストを設定する</span><span class="sxs-lookup"><span data-stu-id="70995-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70995-104">この記事は、 [Office 365 Advanced Threat Protection](office-365-atp.md)を使用しているビジネスのお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="70995-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="70995-105">Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70995-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="70995-106">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織に[カスタムのブロック](set-up-a-custom-blocked-urls-list-wtih-atp.md)された url を設定できます。これにより、ユーザーが電子メールメッセージや特定の Office ドキュメント内の web アドレス (url) をクリックしたときに、それらの url にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="70995-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="70995-107">組織では、組織内の特定のグループに対してカスタムの "書き換え不可" リストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="70995-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="70995-108">[書き換えない] リストを使用すると、一部のユーザーは、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)によってブロックされている url にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="70995-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="70995-109">この記事では、ATP の安全なリンクスキャンから除外する Url の一覧を指定する方法と、注意すべき重要な点について説明します。</span><span class="sxs-lookup"><span data-stu-id="70995-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="70995-110">「書き換えない」リストを設定する</span><span class="sxs-lookup"><span data-stu-id="70995-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="70995-111">ATP の安全なリンク保護では、組織のブロックされた Url のリストや例外の「書き換えない」リストを含むいくつかのリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="70995-111">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="70995-112">必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストを設定できます。</span><span class="sxs-lookup"><span data-stu-id="70995-112">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="70995-113">この操作は、組織内の特定の受信者に適用する安全なリンクポリシーを追加または編集するときに行います。</span><span class="sxs-lookup"><span data-stu-id="70995-113">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 

<span data-ttu-id="70995-114">ATP ポリシーを編集 (または定義) するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70995-114">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="70995-115">次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="70995-115">The following table includes some examples.</span></span> <span data-ttu-id="70995-116">詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70995-116">To learn more, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="70995-117">役割</span><span class="sxs-lookup"><span data-stu-id="70995-117">Role</span></span>  |<span data-ttu-id="70995-118">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="70995-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="70995-119">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="70995-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="70995-p105">Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70995-p105">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="70995-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="70995-122">Security Administrator</span></span> |<span data-ttu-id="70995-123">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="70995-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="70995-124">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="70995-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="70995-125">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="70995-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="70995-126">または</span><span class="sxs-lookup"><span data-stu-id="70995-126">or</span></span> <br>  <span data-ttu-id="70995-127">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="70995-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="70995-128">役割とアクセス許可の詳細については、「[Office 365 セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70995-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="70995-129">ユーザー設定の「リライトしない」 Url リストを表示または編集するには</span><span class="sxs-lookup"><span data-stu-id="70995-129">To view or edit a custom "do not rewrite" URLs list</span></span>
  
1. <span data-ttu-id="70995-130">[https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="70995-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="70995-131">左側のナビゲーションで、[**脅威管理** \> **ポリシー** \> **セーフリンク**] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="70995-131">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="70995-132">[**特定の受信者に適用するポリシー** ] セクションで、[**新規**作成] (新しいボタンは**+** プラス記号 () に似ています) を選択して、新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="70995-132">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="70995-133">(または、既存のポリシーを編集することもできます)。</span><span class="sxs-lookup"><span data-stu-id="70995-133">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="70995-134">![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="70995-134">![Choose New to add a Safe Links policy for specific email recipients](../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="70995-135">ポリシーの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="70995-135">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="70995-136">[**次の url を書き換えない**] セクションで、[**有効な url を入力**してください] ボックスを選択し、url を入力して、プラス記号 (+) を選択します。</span><span class="sxs-lookup"><span data-stu-id="70995-136">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="70995-137">[**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="70995-137">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="70995-138">[**追加**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70995-138">Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="70995-139">画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70995-139">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="70995-140">組織の禁止された Url のカスタムリストを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="70995-140">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="70995-141">「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-wtih-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70995-141">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="70995-142">留意すべき重要な点</span><span class="sxs-lookup"><span data-stu-id="70995-142">Important points to keep in mind</span></span>

- <span data-ttu-id="70995-143">[書き換えない] ボックスの一覧で指定したすべての Url は、指定した受信者の ATP の安全なリンクスキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="70995-143">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="70995-144">「書き換えない」リスト内に既に Url のリストがある場合は、そのリストを確認し、必要に応じてワイルドカードを追加してください。</span><span class="sxs-lookup"><span data-stu-id="70995-144">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="70995-145">たとえば、既存のリストにそのよう`http://contoso.com/a`なエントリがあり、ポリシーにそのような`http://contoso.com/a/b`サブパスを含める場合は、エントリにワイルドカードを追加`http://contoso.com/a*`して、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="70995-145">For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="70995-146">「書き換えない」の一覧で指定した Url にスラッシュ (/) を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="70995-146">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list.</span></span> <span data-ttu-id="70995-147">たとえば、「リライトしない`contoso.com/` 」の一覧で入力するのではなく`contoso.com`、を入力します。</span><span class="sxs-lookup"><span data-stu-id="70995-147">For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>

- <span data-ttu-id="70995-148">ATP の安全なリンクポリシーの "書き込み不可" リストを指定する場合は、最大3つのワイルドカードのアスタリスク\*() を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="70995-148">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*).</span></span> <span data-ttu-id="70995-149">ワイルドカード\*() を使用して、または`http://` `https://`などのプレフィックスまたはサブドメインを明示的に含めます。</span><span class="sxs-lookup"><span data-stu-id="70995-149">Wildcards (\*) are used to explicitly include prefixes or subdomains, like `http://` or `https://`.</span></span> <span data-ttu-id="70995-150">などのエントリ`contoso.com`は、"リライトしない" `*contoso.com*`リストの場合と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="70995-150">An entry, such as `contoso.com` is not the same as `*contoso.com*` for your "do not rewrite" list.</span></span> <span data-ttu-id="70995-151">ドメインおよびその`*contoso.com*`サブドメインおよびパスへのアクセスをユーザーに許可する場合は、必要があります。</span><span class="sxs-lookup"><span data-stu-id="70995-151">You must have `*contoso.com*` if you want to allow people to visit a domain and its subdomains and paths.</span></span>
    
<span data-ttu-id="70995-152">次の表に、入力できる内容と、それらのエントリの影響についての例を示します。</span><span class="sxs-lookup"><span data-stu-id="70995-152">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="70995-153">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="70995-153">**Example Entry**</span></span>|<span data-ttu-id="70995-154">**機能**</span><span class="sxs-lookup"><span data-stu-id="70995-154">**What It Does**</span></span>|
|:-----|:-----|
|`contoso.com`|<span data-ttu-id="70995-155">受信者がサブドメインやパス`http://contoso.com`ではなく、サイトにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="70995-155">Allows recipients to visit a site like `http://contoso.com` but not subdomains or paths.</span></span>|
|`*contoso.com*`  <br/> |<span data-ttu-id="70995-156">受信者が`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、、などのドメイン、サブドメイン、およびパスにアクセスできるようにします。`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="70995-156">Allows recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="70995-157">特定の受信者が、次`http://contoso.com/a`のようなサブパスではなく、サイトにアクセスできるようにします。`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="70995-157">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="70995-158">特定の受信者が、次`http://contoso.com/a`のようなサブパスでサイトにアクセスできるようにします。`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="70995-158">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 