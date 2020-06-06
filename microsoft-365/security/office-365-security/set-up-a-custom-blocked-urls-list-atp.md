---
title: ATP の安全なリンクを使用して、ブロックされたカスタムの Url リストを設定する
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Advanced Threat Protection を使用して、組織でブロックされている Url の一覧を設定する方法について説明します。
ms.openlocfilehash: 9bf4417044dab5488e2945ccea5fa30a7fd4113d
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588146"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="d7af3-103">ATP の安全なリンクを使用して、ブロックされたカスタムの Url リストを設定する</span><span class="sxs-lookup"><span data-stu-id="d7af3-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7af3-104">この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d7af3-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="d7af3-105">Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7af3-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="d7af3-p102">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織はブロックされている Web サイト アドレスのユーザー設定リストを所有することができます。URL がブロックされると、ブロックされた URL へのリンクをクリックしたユーザーは次の画像のような[警告ページ](atp-safe-links-warning-pages.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![このサイトはブロックされています](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="d7af3-109">禁止された Url の一覧は、組織の Microsoft 365 for business security teams によって定義されており、そのリストは、Office 365 ATP Safe Links ポリシーでカバーされている組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7af3-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="d7af3-110">この記事では、[Office 365 の ATP の安全なリンク](atp-safe-links.md)に、組織のユーザー設定のブロック URL リストを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7af3-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="d7af3-111">ユーザー設定のブロック URL リストを表示または編集する</span><span class="sxs-lookup"><span data-stu-id="d7af3-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="d7af3-p103">[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のユーザー設定のブロック URL リストなど、いくつかのリストを使用します。必要なアクセス許可があれば、組織のユーザー設定リストを設定できます。これを行うには、組織の既定の安全なリンクのポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="d7af3-115">ATP ポリシーを編集 (または定義) するには、次の表に示す役割の 1 つが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7af3-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="d7af3-116">役割</span><span class="sxs-lookup"><span data-stu-id="d7af3-116">Role</span></span>|<span data-ttu-id="d7af3-117">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="d7af3-117">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="d7af3-118">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="d7af3-118">global administrator</span></span>|<span data-ttu-id="d7af3-119">Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="d7af3-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="d7af3-120">(詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)てを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d7af3-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="d7af3-121">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="d7af3-121">Security Administrator</span></span>|<span data-ttu-id="d7af3-122">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="d7af3-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="d7af3-123">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="d7af3-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="d7af3-124">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="d7af3-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="d7af3-125">または</span><span class="sxs-lookup"><span data-stu-id="d7af3-125">or</span></span> <br>  <span data-ttu-id="d7af3-126">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="d7af3-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

> [!TIP]
> <span data-ttu-id="d7af3-127">役割とアクセス許可の詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7af3-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="d7af3-128">ユーザー設定のブロック URL リストを表示または編集するには</span><span class="sxs-lookup"><span data-stu-id="d7af3-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="d7af3-129">[https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="d7af3-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="d7af3-130">左側のナビゲーションの **[脅威の管理]** で **[ポリシー]** \> **[安全なリンク]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="d7af3-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="d7af3-131">**[組織全体に適用されるポリシー]** セクションで、**[既定]**、**[編集]** (編集ボタンは鉛筆に似ています) の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="d7af3-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="d7af3-132">![[編集] をクリックして安全なリンクの保護に関する既定のポリシーを編集する](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="d7af3-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="d7af3-p105">これにより、ブロック URL リストを表示することができます。最初は、URL のリストが表示されないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p105">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="d7af3-135">![既定の安全なリンク ポリシーに適用されるブロック URL リスト](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="d7af3-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="d7af3-136">**[有効な URL を入力します]** ボックスを選んで、「URL」と入力し、プラス記号 (**+**) を選びます。</span><span class="sxs-lookup"><span data-stu-id="d7af3-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="d7af3-137">画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7af3-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="d7af3-138">注意事項</span><span class="sxs-lookup"><span data-stu-id="d7af3-138">A few things to keep in mind</span></span>

<span data-ttu-id="d7af3-139">URL をリストに追加するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7af3-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="d7af3-p106">URL の最後にスラッシュ (**/**) を含めないでください。たとえば、「`https://www.contoso.com/`」と入力する代わりに、「`https://www.contoso.com`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p106">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="d7af3-p107">ドメイン専用の URL (`contoso.com` または `tailspintoys.com` など) を指定することができます。これにより、ドメインを含む URL のクリックがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p107">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="d7af3-p108">完全なドメイン (`contoso.com` など) はブロックせずにサブドメイン (`toys.contoso.com*` など) を指定することができます。これにより、サブドメインを含む URL のクリックはブロックされますが、完全ドメインを含む URL のクリックはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p108">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="d7af3-p109">URL ごとにワイルドカードのアスタリスク (\*) を 3 つまで含めることができます。次の表は、入力できる内容と、エントリにどのような効果があるかについていくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p109">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>

|<span data-ttu-id="d7af3-148">エントリの例</span><span class="sxs-lookup"><span data-stu-id="d7af3-148">Example Entry</span></span>|<span data-ttu-id="d7af3-149">機能</span><span class="sxs-lookup"><span data-stu-id="d7af3-149">What It Does</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7af3-150">`contoso.com` または `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="d7af3-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="d7af3-151">ドメイン、サブドメイン、パス (`https://www.contoso.com`、`https://sub.contoso.com`、`https://contoso.com/abc` など) をブロックします</span><span class="sxs-lookup"><span data-stu-id="d7af3-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="d7af3-152">サイト `https://contoso.com/a` をブロックしますが、`https://contoso.com/a/b` のような追加のサブパスはブロックしません</span><span class="sxs-lookup"><span data-stu-id="d7af3-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="d7af3-153">サイト `https://contoso.com/a`、`https://contoso.com/a/b` のような追加のサブパスをブロックします</span><span class="sxs-lookup"><span data-stu-id="d7af3-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="d7af3-154">サブドメイン (この場合は「toys」) をブロックしますが、他のドメイン URL (`https://contoso.com` や `https://home.contoso.com` など) のクリックを許可します。</span><span class="sxs-lookup"><span data-stu-id="d7af3-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="d7af3-155">組織の特定のユーザーに対して例外を定義する方法</span><span class="sxs-lookup"><span data-stu-id="d7af3-155">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="d7af3-p110">他のユーザーに対してブロックされる可能性のある URL を特定のグループが表示できるようにする場合、特定の受信者に適用される ATP の安全なリンクに関するポリシーを指定できます。「[ATP の安全なリンクを使用して、ユーザー設定の "書き換えない" URL リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7af3-p110">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
