---
title: ATP の安全なリンクを使用して、リライトしないカスタムの Url リストを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 の ATP の安全なリンクポリシーでユーザーのブロックされたユーザーの Url を設定する方法と、ユーザーのグループの Url のリストを書き換えない方法について説明します。
ms.openlocfilehash: 7d7c8ad3f5ae0f6a79bd839151ed09628e7f2dfd
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517475"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="233b9-103">ATP の安全なリンクを使用して、リライトしないカスタムの Url リストを設定する</span><span class="sxs-lookup"><span data-stu-id="233b9-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="233b9-104">この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="233b9-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="233b9-105">Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="233b9-106">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織に[カスタムのブロック](set-up-a-custom-blocked-urls-list-atp.md)された url を設定できます。これにより、ユーザーが電子メールメッセージや特定の Office ドキュメント内の web アドレス (url) をクリックしたときに、それらの url にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="233b9-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="233b9-107">組織では、組織内の特定のグループに対してカスタムの "書き換え不可" リストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="233b9-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="233b9-108">[書き換えない] リストを使用すると、一部のユーザーは、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)によってブロックされている url にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="233b9-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="233b9-109">この記事では、ATP の安全なリンクスキャンから除外する Url の一覧を指定する方法と、注意すべき重要な点について説明します。</span><span class="sxs-lookup"><span data-stu-id="233b9-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="233b9-110">「書き換えない」リストを設定する</span><span class="sxs-lookup"><span data-stu-id="233b9-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="233b9-111">ATP の安全なリンク保護では、組織のブロックされた Url のリストや例外の「書き換えない」リストを含むいくつかのリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="233b9-111">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="233b9-112">必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストを設定できます。</span><span class="sxs-lookup"><span data-stu-id="233b9-112">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="233b9-113">この操作は、組織内の特定の受信者に適用する安全なリンクポリシーを追加または編集するときに行います。</span><span class="sxs-lookup"><span data-stu-id="233b9-113">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="233b9-114">ATP ポリシーを編集 (または定義) するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="233b9-114">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="233b9-115">次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="233b9-115">The following table includes some examples.</span></span> <span data-ttu-id="233b9-116">詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-116">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="233b9-117">役割</span><span class="sxs-lookup"><span data-stu-id="233b9-117">Role</span></span>  |<span data-ttu-id="233b9-118">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="233b9-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="233b9-119">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="233b9-119">global administrator</span></span> |<span data-ttu-id="233b9-120">Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="233b9-120">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="233b9-121">(詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)てを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="233b9-121">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="233b9-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="233b9-122">Security Administrator</span></span> |<span data-ttu-id="233b9-123">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="233b9-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="233b9-124">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="233b9-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="233b9-125">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="233b9-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="233b9-126">または</span><span class="sxs-lookup"><span data-stu-id="233b9-126">or</span></span> <br>  <span data-ttu-id="233b9-127">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="233b9-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="233b9-128">役割とアクセス許可の詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-128">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="233b9-129">ユーザー設定の「リライトしない」 Url リストを表示または編集するには</span><span class="sxs-lookup"><span data-stu-id="233b9-129">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="233b9-130">[https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="233b9-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="233b9-131">左側のナビゲーションで、[**脅威管理** \> **ポリシー** \> **セーフリンク**] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="233b9-131">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="233b9-132">[**特定の受信者に適用するポリシー** ] セクションで、[**新規**作成] (新しいボタンはプラス記号 () に似ています) を選択して、 **+** 新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="233b9-132">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="233b9-133">(または、既存のポリシーを編集することもできます)。</span><span class="sxs-lookup"><span data-stu-id="233b9-133">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="233b9-134">![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="233b9-134">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="233b9-135">ポリシーの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="233b9-135">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="233b9-136">ユーザーがリンクをクリックしたときに、url**を**有効にして、既知の悪意のあるリンクの一覧に対して書き換えて確認します。</span><span class="sxs-lookup"><span data-stu-id="233b9-136">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="233b9-137">[**次の url を書き換えない**] セクションで、[**有効な url を入力**してください] ボックスを選択し、url を入力して、プラス記号 (+) を選択します。</span><span class="sxs-lookup"><span data-stu-id="233b9-137">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="233b9-138">[**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="233b9-138">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="233b9-139">[**追加**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="233b9-139">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="233b9-140">画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="233b9-140">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="233b9-141">組織の禁止された Url のカスタムリストを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-141">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="233b9-142">「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-142">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="233b9-143">留意すべき重要な点</span><span class="sxs-lookup"><span data-stu-id="233b9-143">Important points to keep in mind</span></span>

- <span data-ttu-id="233b9-144">[書き換えない] ボックスの一覧で指定したすべての Url は、指定した受信者の ATP の安全なリンクスキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="233b9-144">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="233b9-145">ユーザーの操作を改善するために、よく使用される内部 Url を "リライトしない" リストに追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-145">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="233b9-146">たとえば、Skype for Business や Sharepoint などのオンプレミスのサービスがある場合は、それらの Url をリストに追加してスキャンから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="233b9-146">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="233b9-147">「書き換えない」リスト内に既に Url のリストがある場合は、そのリストを確認し、必要に応じてワイルドカードを追加してください。</span><span class="sxs-lookup"><span data-stu-id="233b9-147">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="233b9-148">たとえば、既存のリストにそのようなエントリがあり、 `https://contoso.com/a` ポリシーにそのようなサブパスを含める場合は、 `https://contoso.com/a/b` エントリにワイルドカードを追加して、次のように `https://contoso.com/a/*` します。</span><span class="sxs-lookup"><span data-stu-id="233b9-148">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="233b9-149">ATP の安全なリンクポリシーの "書き込み不可" リストを指定する場合は、最大3つのワイルドカード () を含めることができ \* ます。</span><span class="sxs-lookup"><span data-stu-id="233b9-149">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="233b9-150">ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="233b9-150">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="233b9-151">たとえば、エントリ `contoso.com` はと同じではありません `*.contoso.com/*` 。これに `*.contoso.com/*` より、ユーザーは指定したドメインのサブドメインとパスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="233b9-151">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="233b9-152">次の表に、入力できる内容と、それらのエントリの影響についての例を示します。</span><span class="sxs-lookup"><span data-stu-id="233b9-152">The following table lists examples of what you can enter and what effect those entries have.</span></span>

|<span data-ttu-id="233b9-153">エントリの例</span><span class="sxs-lookup"><span data-stu-id="233b9-153">Example Entry</span></span>|<span data-ttu-id="233b9-154">機能</span><span class="sxs-lookup"><span data-stu-id="233b9-154">What It Does</span></span>|
|:-----|:-----|
|`contoso.com`|<span data-ttu-id="233b9-155">受信者がサブドメインやパスではなく、サイトにアクセスできるように `https://contoso.com` します。</span><span class="sxs-lookup"><span data-stu-id="233b9-155">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="233b9-156">受信者が、、、またはなどのドメイン、サブドメイン、およびパスにアクセスできるようにし `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` ます。</span><span class="sxs-lookup"><span data-stu-id="233b9-156">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="233b9-157">このエントリには、次のように、 `*contoso.com*` 偽装している可能性のあるサイトが含まれていないため、 `https://www.falsecontoso.com` またはのようになります。`https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="233b9-157">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="233b9-158">特定の受信者が、次のようなサブパスではなく、サイトにアクセスできるようにし `https://contoso.com/a` ます。`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="233b9-158">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="233b9-159">特定の受信者が、次のようなサブパスでサイトにアクセスできるようにします。 `https://contoso.com/a``https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="233b9-159">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
