---
title: ATP の安全なリンク機能を使用して「書き換けないカスタム URL リストを設定する」
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
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
description: Office 365 ATP の安全なリンク ポリシーのユーザー グループに対して、ユーザーのブロック URL のカスタムのリストと書き換Officeのない URL のリストを設定する方法について説明します。
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825235"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="a19c7-103">ATP の安全なリンク機能を使用して「書き換けないカスタム URL リストを設定する」</span><span class="sxs-lookup"><span data-stu-id="a19c7-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a19c7-104">この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a19c7-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="a19c7-105">ホーム ユーザーで Outlook の安全なリンクに関する情報をお見しいとする場合は、「詳細設定またはセキュリティ [Outlook.comを参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="a19c7-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="a19c7-106">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP)[custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md)により、組織はユーザーがメール メッセージや特定の Office ドキュメントの Web アドレス (URL) をクリックした場合にそれらの URL に移動することが禁止されるので、カスタムのブロック URL を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="a19c7-107">また、組織では、組織内の特定のグループに対して、カスタムの「書き換えない」リストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="a19c7-108">「書き換えない」リストを使用すると、一部のユーザーは、他のユーザーがアクセス許可リストの ATP の安全なリンクによって [ブロックされている URL Officeを使用できます](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a19c7-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="a19c7-109">この記事では、ATP の安全なリンクのスキャンから除外される URL のリストを指定する方法と、注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a19c7-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

> [!NOTE]
> <span data-ttu-id="a19c7-110">組織で安全なリンク ポリシーを使用している場合、サード パーティのフィッシング テストでサポートされている方法は"書き換えない" リストのみです。</span><span class="sxs-lookup"><span data-stu-id="a19c7-110">If your organization use Safe Links policies, the "do not rewrite" list is the only supported method for third party phishing tests.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="a19c7-111">「書き換えない」の一覧を設定する</span><span class="sxs-lookup"><span data-stu-id="a19c7-111">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="a19c7-112">ATP の安全なリンク保護では、組織の禁止 URL リストや例外の「書き換えない」一覧など、いくつかのリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-112">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="a19c7-113">必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-113">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="a19c7-114">これは、組織内の特定の受信者に適用する安全なリンク ポリシーを追加または編集する場合に行います。</span><span class="sxs-lookup"><span data-stu-id="a19c7-114">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="a19c7-115">ATP ポリシーを編集 (または定義) するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a19c7-115">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="a19c7-116">次の表にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-116">The following table includes some examples.</span></span> <span data-ttu-id="a19c7-117">詳細については、コンプライアンス センター [の「アクセス許可」&を参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a19c7-117">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="a19c7-118">役割</span><span class="sxs-lookup"><span data-stu-id="a19c7-118">Role</span></span>|<span data-ttu-id="a19c7-119">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="a19c7-119">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="a19c7-120">全体管理者</span><span class="sxs-lookup"><span data-stu-id="a19c7-120">global administrator</span></span>|<span data-ttu-id="a19c7-121">Microsoft 365 を購入するためにサインアップするユーザーは、既定ではグローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="a19c7-121">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="a19c7-122">(詳細については [、Microsoft 365 の管理者ロール](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) の詳細を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a19c7-122">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="a19c7-123">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="a19c7-123">Security Administrator</span></span>|<span data-ttu-id="a19c7-124">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="a19c7-124">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="a19c7-125">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="a19c7-125">Exchange Online Organization Management</span></span>|<span data-ttu-id="a19c7-126">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="a19c7-126">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="a19c7-127">または</span><span class="sxs-lookup"><span data-stu-id="a19c7-127">or</span></span> <br>  <span data-ttu-id="a19c7-128">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="a19c7-128">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="a19c7-129">役割とアクセス許可の詳細については、「アクセス許可 [」コンプライアンス センターの&、「アクセス許可」を参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a19c7-129">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="a19c7-130">カスタム "書き換えない" URL リストを表示または編集するには</span><span class="sxs-lookup"><span data-stu-id="a19c7-130">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="a19c7-131">[https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a19c7-131">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="a19c7-132">左側のナビゲーションでは、[脅威**管理ポリシーの** \> **安全なリンク** \> **] の下に**</span><span class="sxs-lookup"><span data-stu-id="a19c7-132">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="a19c7-133">特定の **受信者に適用するポリシー セクション** で、[ **新規** 作成] を選択し (新しいボタンはプラス記号 ( **+** )) を選びます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-133">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="a19c7-134">既存のポリシーを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-134">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="a19c7-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="a19c7-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="a19c7-136">ポリシーの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-136">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="a19c7-137">URL **は** 書き換えられ、ユーザーがリンクをクリックすると既知の悪意のあるリンクの一覧と照合されます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-137">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="a19c7-138">[次の **URL を書き換えてはいけない** ] セクションで、[ **有効な URL を入力してください] ボックスを** オンにし、URL を入力して、プラス記号 (+) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-138">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="a19c7-139">[ **適用先]** セクションで **、[受信者がメンバーである**もの] を選択し、ポリシーに含めるグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-139">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="a19c7-140">**[Add]**(追加) を選び **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a19c7-140">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="a19c7-141">画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a19c7-142">ブロック URL の組織のカスタム リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-142">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="a19c7-143">[「ATP の安全なリンク」を使用して、カスタムのブロック URL リストを設定する方法を確認する](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="a19c7-143">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="a19c7-144">注意事項</span><span class="sxs-lookup"><span data-stu-id="a19c7-144">Important points to keep in mind</span></span>

- <span data-ttu-id="a19c7-145">「書き換えない」一覧に指定した URL は、指定した受信者に対する ATP の安全なリンク スキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-145">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="a19c7-146">一般的に使用される内部 URL を "書き換えない" リストに追加して、ユーザー エクスペリエンスを向上させることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a19c7-146">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="a19c7-147">たとえば、Skype for Business、Sharepoint などのオンプレミス サービスがある場合は、それらの URL をリストに追加してスキャンから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-147">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="a19c7-148">URL の一覧が既に "書き換えない" 一覧の場合は、該当する一覧を確認してワイルドカードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-148">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="a19c7-149">たとえば、既存のリストにエントリが含まれており、ポリシーに含めるような `https://contoso.com/a` `https://contoso.com/a/b` サブパスを含める場合は、エントリにワイルドカードを追加して、同様の外観を持つようにします `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="a19c7-149">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="a19c7-150">ATP の安全なリンク ポリシーに「書き換えない」リストを指定した場合、最大 3 \* つのワイルドカード (</span><span class="sxs-lookup"><span data-stu-id="a19c7-150">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="a19c7-151">ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a19c7-151">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="a19c7-152">たとえば、指定したドメインのサブドメインおよびパスにアクセスできるため、エントリは同 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` じには設定されません。</span><span class="sxs-lookup"><span data-stu-id="a19c7-152">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="a19c7-153">次の表に、入力できる項目と、それらのエントリの効果の例を示します。</span><span class="sxs-lookup"><span data-stu-id="a19c7-153">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="a19c7-154">エントリの例</span><span class="sxs-lookup"><span data-stu-id="a19c7-154">Example Entry</span></span>|<span data-ttu-id="a19c7-155">機能</span><span class="sxs-lookup"><span data-stu-id="a19c7-155">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="a19c7-156">受信者が、サブドメインやパスのような `https://contoso.com` サイトにアクセスできますが、サブドメインやパスはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a19c7-156">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="a19c7-157">受信者が、ドメイン、サブドメイン、パス (,、.. など) `https://www.contoso.com` にアクセス `https://www.contoso.com` `https://maps.contoso.com` できます `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a19c7-157">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="a19c7-158">このエントリは、不用のある可能性のあるサイトが含まれていないため、このエントリの値はかなり `*contoso.com*` 大きく優れ `https://www.falsecontoso.com` ており、 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="a19c7-158">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="a19c7-159">特定の受信者がたとえばのようなサイトにアクセス `https://contoso.com/a` できますが、次のようなサブパスはアクセスできません。 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="a19c7-159">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="a19c7-160">特定の受信者がいいね!や、次のような `https://contoso.com/a` サイトにアクセスできます。 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="a19c7-160">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
