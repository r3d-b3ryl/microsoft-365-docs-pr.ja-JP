---
title: 組織内の Power BI
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: 組織のユーザー Power BIこのビジネス分析サービスを使用する方法について詳しくは、こちらをご覧ください。
ms.openlocfilehash: 6da25932e1813744aa38bab2b399d6ac30c3429a
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683369"
---
# <a name="power-bi-in-your-organization"></a><span data-ttu-id="b8eda-103">組織内の Power BI</span><span class="sxs-lookup"><span data-stu-id="b8eda-103">Power BI in your organization</span></span>

<span data-ttu-id="b8eda-104">このページでは、組織のユーザーが Power BI を使う方法と、組織でこのサービスを取得する手順を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-104">This page describes how users in your organization can use Power BI and how you can control how your organization acquires this service.</span></span>

## <a name="what-is-power-bi"></a><span data-ttu-id="b8eda-105">Power BI とは</span><span class="sxs-lookup"><span data-stu-id="b8eda-105">What is Power BI?</span></span>

<span data-ttu-id="b8eda-p101">Microsoft Power BI は、直感的な新しい方法でデータの可視化、発見の共有、共同作業を実現します。 詳細については、[Power BI Web サイト](https://powerbi.microsoft.com/en-us/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p101">Microsoft Power BI enables users to visualize data, share discoveries, and collaborate in intuitive new ways. To learn more, see the [Power BI Web site](https://powerbi.microsoft.com/en-us/).</span></span>
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a><span data-ttu-id="b8eda-108">国内Power BI、業界固有のコンプライアンス要件を満たしているか。</span><span class="sxs-lookup"><span data-stu-id="b8eda-108">Does Power BI meet national, regional, and industry-specific compliance requirements?</span></span>

<span data-ttu-id="b8eda-109">コンプライアンスの詳細についてはPower BI Microsoft Trust Center[を参照してください](https://go.microsoft.com/fwlink/?LinkId=785324)。</span><span class="sxs-lookup"><span data-stu-id="b8eda-109">To learn more about Power BI compliance, see the [Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkId=785324).</span></span>
  
## <a name="how-do-users-sign-up-for-power-bi"></a><span data-ttu-id="b8eda-110">ユーザーが Power BI にサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-110">How do users sign up for Power BI?</span></span>

<span data-ttu-id="b8eda-111">管理者であるユーザーは、[Power BI Web サイト](https://powerbi.microsoft.com/en-us/)を通じて Power BI にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-111">As an administrator, you can sign up for Power BI through the [Power BI web site](https://powerbi.microsoft.com/en-us/).</span></span> <span data-ttu-id="b8eda-112">管理センターの [購入サービス] ページからサインアップMicrosoft 365することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-112">You can also sign up through the purchase services page on the Microsoft 365 admin center.</span></span> <span data-ttu-id="b8eda-113">管理者が Power BI にサインアップすると、アクセス権が必要なユーザーにユーザー サブスクリプション ライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-113">When an administrator signs up for Power BI, they can assign user subscription licenses to users who should have access.</span></span>
  
<span data-ttu-id="b8eda-p103">また、組織の個々のユーザーは、[Power BI Web サイト](https://powerbi.microsoft.com/en-us/)を通じて Power BI にサインアップできる場合もあります。 組織のユーザーが Power BI にサインアップする場合、そのユーザーには Power BI ライセンスが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p103">Additionally, individual users in your organization may be able to sign up for Power BI through the [Power BI web site](https://powerbi.microsoft.com/en-us/). When a user in your organization signs up for Power BI, that user is assigned a Power BI license automatically.</span></span>
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a><span data-ttu-id="b8eda-116">組織の個々のユーザーがサインアップする方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-116">How do individual users in my organization sign up?</span></span>

<span data-ttu-id="b8eda-117">組織のユーザーには、以下のように 3 種類のシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-117">There are three scenarios that might apply to users in your organization:</span></span>
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-a-microsoft-365-account"></a><span data-ttu-id="b8eda-118">シナリオ 1: 組織に既に既存のMicrosoft 365環境が存在し、ユーザーが既存の Power BIアカウントをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-118">Scenario 1: Your organization already has an existing Microsoft 365 environment and the user signing up for Power BI already has a Microsoft 365 account.</span></span>

<span data-ttu-id="b8eda-119">このシナリオでは、テナント (たとえば、contoso.com) 内で、ユーザーには職場や学校のアカウントが既にあり、まだ Power BI を使っていない場合、マイクロソフトが単にそのアカウントのプランをライセンス認証することになります。ユーザーには、Power BI サービスの使い方が自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-119">In this scenario, if a user already has a work or school account in the tenant (for example, contoso.com) but does not yet have Power BI, Microsoft will simply activate the plan for that account, and the user will automatically be notified of how to use the Power BI service.</span></span>
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-a-microsoft-365-account"></a><span data-ttu-id="b8eda-120">シナリオ 2: 組織に既存の Microsoft 365環境が存在し、ユーザーが Power BIアカウントを持Microsoft 365はありません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-120">Scenario 2: Your organization has an existing Microsoft 365 environment and the user signing up for Power BI doesn't have a Microsoft 365 account.</span></span>

<span data-ttu-id="b8eda-121">このシナリオでは、ユーザーは組織のドメイン (contoso.com など) に電子メール アドレスを持っていますが、Microsoft 365 アカウントを持っていません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-121">In this scenario, the user has an email address in your organization's domain (for example, contoso.com) but does not yet have a Microsoft 365 account.</span></span> <span data-ttu-id="b8eda-122">この場合、ユーザーは Power BI にサインアップすることができ、自動的にアカウントが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-122">In this case, the user can sign up for Power BI and will automatically be given an account.</span></span> <span data-ttu-id="b8eda-123">この手順で、ユーザーは Power BI サービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-123">This lets the user access the Power BI service.</span></span> <span data-ttu-id="b8eda-124">たとえば、Nancy という名前の従業員が自分の仕事用メール アドレス (Nancy@contoso.com など) を使用してサインアップした場合、Microsoft は自動的に Contoso Microsoft 365 環境で Nancy をユーザーとして追加し、そのアカウントの Power BI をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="b8eda-124">For example, if an employee named Nancy uses her work email address (for example, Nancy@contoso.com) to sign up, Microsoft will automatically add Nancy as a user in the Contoso Microsoft 365 environment and activate Power BI for that account.</span></span>
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a><span data-ttu-id="b8eda-125">シナリオ 3: 組織にメール ドメインにMicrosoft 365環境はありません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-125">Scenario 3: Your organization does not have a Microsoft 365 environment connected to your email domain.</span></span>

<span data-ttu-id="b8eda-126">組織がサービスを利用するために必要な管理Power BI。</span><span class="sxs-lookup"><span data-stu-id="b8eda-126">There are no administrative actions your organization needs to take advantage of Power BI.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b8eda-127">組織にメール ドメインが複数あり、すべてのメール アドレスの拡張子を同じテナントに含める場合は、ユーザーがプライマリ テナントを作成する前に、そのテナントにすべてのメール アドレス ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-127">If your organization has multiple email domains and you prefer all email address extensions to be in the same tenant, before any users create your primary tenant, add all email address domains to that tenant before any users create your primary tenant.</span></span> <span data-ttu-id="b8eda-128">テナントが作成された後で、ユーザーをテナント間で自動的に移動する方法は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-128">There is no automated mechanism to move users across tenants after they have been created.</span></span> <span data-ttu-id="b8eda-129">このプロセスの詳細については、「複数のドメインがある場合、ユーザーが追加されるテナントを制御できますか[?」](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to)および「Add a domain to Office 365 online」[を参照](../setup/add-domain.md)してください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-129">For more information on this process, see [If I have multiple domains, can I control the tenant that users are added to?](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) later in this article and [Add a domain to Office 365](../setup/add-domain.md) online.</span></span>
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a><span data-ttu-id="b8eda-130">組織側での現在のユーザー ID の管理方法は、どのように変わりますか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-130">How will this change the way I manage identities for users in my organization today?</span></span>

<span data-ttu-id="b8eda-131">組織に既存の環境が既に存在Microsoft 365、組織内のすべてのユーザーにアカウントMicrosoft 365がある場合、ID 管理は変更されません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-131">If your organization already has an existing Microsoft 365 environment and all users in your organization have Microsoft 365 accounts, identity management will not change.</span></span>
  
<span data-ttu-id="b8eda-132">組織に既に既存の Microsoft 365 環境がありますが、組織内のすべてのユーザーが Microsoft 365 アカウントを持っている場合は、テナントにユーザーを作成し、ユーザーの仕事または学校の電子メール アドレスに基づいてライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-132">If your organization already has an existing Microsoft 365 environment but not all users in your organization have Microsoft 365 accounts, we will create a user in the tenant and assign licenses based on the user's work or school email address.</span></span> <span data-ttu-id="b8eda-133">これは、特定の時間に管理するユーザー数は、組織内のユーザーが当該サービスにサインアップするに従って増えていくことを表しています。</span><span class="sxs-lookup"><span data-stu-id="b8eda-133">This means that the number of users you are managing at any particular time will grow as users in your organization sign up for the service.</span></span>
  
<span data-ttu-id="b8eda-134">ディレクトリをオンプレミスで管理しており、Active Directory フェデレーション サービス (AD FS) を使っている場合、マイクロソフトはテナントにユーザーを追加しません。テナントに参加しようとするユーザーは、組織の管理者に連絡するように求めるメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-134">If you are managing your directory on-premises, and use Active Directory Federation Services (AD FS), Microsoft will not add users to your tenant, and users attempting to join your tenant will receive a message to contact their organization's admin.</span></span>
  
<span data-ttu-id="b8eda-135">組織にメール ドメインに接続Microsoft 365環境がない場合、ID の管理方法に変更はありません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-135">If your organization does not have a Microsoft 365 environment connected to your email domain, there will be no change in how you manage identity.</span></span> <span data-ttu-id="b8eda-136">ユーザーは、クラウドのみを使用する新しいユーザー ディレクトリに追加され、組織の管理者はテナントの管理者としての役割を引き継いで、ユーザーを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-136">Users will be added to a new, cloud-only user directory, and you will have the option to elect to take over as the tenant admin and manage them.</span></span>
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a><span data-ttu-id="b8eda-137">ユーザー用にマイクロソフトによって作成されたテナントを管理するためのプロセス</span><span class="sxs-lookup"><span data-stu-id="b8eda-137">What is the process to manage a tenant created by Microsoft for my users?</span></span>

<span data-ttu-id="b8eda-138">Microsoft によってテナントが作成されたら、次の手順に従って、そのテナントが自分の管理対象であることを宣言して管理できます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-138">If a tenant was created by Microsoft, you can claim and manage that tenant by following these steps:</span></span>
  
1. <span data-ttu-id="b8eda-p108">テナントに参加するには、管理するテナントのドメインと同じメール アドレス ドメインを使って [Power BI にサインアップ](https://go.microsoft.com/fwlink/?LinkId=522448)します。たとえば、contoso.com というテナントが作成された場合は、@contoso.com で終わるメール アドレスを使って、テナントに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p108">Join the tenant by [signing up for Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) using an email address domain that matches the tenant domain you want to manage. For example, if Microsoft created the contoso.com tenant, you will need to join the tenant with an email address ending with @contoso.com.</span></span>

1. <span data-ttu-id="b8eda-p109">ドメインの所有者を検証して管理者コントロールを宣言します。テナントに参加したら、ドメインの所有者を検証して、自分自身を管理者の役割に昇格させることができます。この操作を行うには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p109">Claim admin control by verifying domain ownership: once you are in the tenant, you can promote yourself to the admin role by verifying domain ownership. To do so, follow these steps:</span></span>

::: moniker range="o365-worldwide"

3. <span data-ttu-id="b8eda-143"><a href="https://admin.microsoft.com" target="_blank">https://admin.microsoft.com</a> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b8eda-143">Go to <a href="https://admin.microsoft.com" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

3. <span data-ttu-id="b8eda-144"><a href="https://portal.office.de" target="_blank">https://portal.office.de</a> に移動します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-144">Go to <a href="https://portal.office.de" target="_blank">https://portal.office.de</a></span></span>

::: moniker-end

::: moniker range="o365-21vianet"

3. <span data-ttu-id="b8eda-145"><a href="https://portal.partner.microsoftonline.cn" target="_blank">https://portal.partner.microsoftonline.cn</a> に移動します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-145">Go to <a href="https://portal.partner.microsoftonline.cn" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end

4. <span data-ttu-id="b8eda-146">左上にあるアプリ起動ツールのアイコンを選択して、**[管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8eda-146">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

    ![管理アプリが強調表示されたアプリ起動ツール](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. <span data-ttu-id="b8eda-148">[管理者になる] ページの **手順を** 読み、[はい] を選択 **します。管理者になる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="b8eda-148">Read the instructions on the **Become the admin** page and then select **Yes, I want to be the admin**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b8eda-149">このオプションが表示されない場合は、既に管理者が配置されています。</span><span class="sxs-lookup"><span data-stu-id="b8eda-149">If this option doesn't appear, there is already an administrator in place.</span></span>
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a><span data-ttu-id="b8eda-150">複数のドメインがある場合、ユーザーが追加されるテナントを制御できますか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-150">If I have multiple domains, can I control the tenant that users are added to?</span></span>

<span data-ttu-id="b8eda-151">何の操作も行わない場合、テナントはユーザーのメール ドメインとサブドメインごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-151">If you do nothing, a tenant will be created for each user email domain and subdomain.</span></span>
  
<span data-ttu-id="b8eda-152">メール アドレスの拡張子に関係なく、すべてのユーザーを同じテナントに入れたい場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b8eda-152">If you want all users to be in the same tenant regardless of their email address extensions:</span></span>
  
- <span data-ttu-id="b8eda-p110">目的のテナントをあらかじめ作成しておくか、または既存のテナントを使って、1 つにまとめたい既存のドメインとサブドメインを目的のテナントに追加します。この操作で、それらのドメインおよびサブドメインで終わるメール アドレスを持つすべてのユーザーは、サインアップ時に目的のテナントに自動的に参加するようになります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p110">Create a target tenant ahead of time or use an existing tenant, and add all the existing domains and subdomains that you want consolidated within that tenant. Then all the users with email addresses ending in those domains and subdomains will automatically join the target tenant when they sign up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8eda-155">テナントが作成された後にユーザーをテナント間で自動的に移動する仕組みは、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-155">There is no supported automated mechanism to move users across tenants once they have been created.</span></span> <span data-ttu-id="b8eda-156">1 つのテナントにドメインを追加する方法Microsoft 365、「ドメインをドメインに追加する」[をOffice 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="b8eda-156">To learn about adding domains to a single Microsoft 365 tenant, see [Add a domain to Office 365](../setup/add-domain.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8eda-157">テナントの管理に関する詳細とガイダンスについては、「管理とは[」をPower BIしてください](/power-bi/service-admin-administering-power-bi-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="b8eda-157">For more information and guidance on managing tenants, see [What is Power BI administration?](/power-bi/service-admin-administering-power-bi-in-your-organization).</span></span>
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a><span data-ttu-id="b8eda-158">ユーザーが既存のテナントに参加するのを防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-158">How can I prevent users from joining my existing tenant?</span></span>

<span data-ttu-id="b8eda-159">ユーザーが既存のテナントに参加するのを防ぐため、管理者として実行できる手順があります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-159">There are steps you can take as an admin to prevent users from joining your existing tenant.</span></span> <span data-ttu-id="b8eda-160">ユーザーがテナントに参加するのをブロックすると、ユーザーのサインイン試行は失敗し、組織の管理者に連絡する指示が表示されます。以前にライセンスの自動配布を既に無効にしている場合は、このプロセスを繰り返す必要があります (たとえば、学生、教職員、およびスタッフのOffice 365 Educationなど)。</span><span class="sxs-lookup"><span data-stu-id="b8eda-160">If you block users from joining the tenant, users' attempts to sign in will fail and they will be directed to contact their organization's admin. You do not need to repeat this process if you have already disabled automatic license distribution before (for example, Office 365 Education for Students, Faculty, and Staff).</span></span>
  
<span data-ttu-id="b8eda-p113">これらの手順では、Windows PowerShell を使う必要があります。 Windows PowerShell を使い始める場合は、「[PowerShell ファースト ステップ ガイド](/powershell/scripting/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p113">These steps require the use of Windows PowerShell. To get started with Windows PowerShell, see the [PowerShell getting started guide](/powershell/scripting/overview).</span></span>
  
<span data-ttu-id="b8eda-163">次の手順を実行するには、V2 PowerShell モジュールの最新の 64 ビット バージョンをインストールAzure Active Directory[する必要があります](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5)。</span><span class="sxs-lookup"><span data-stu-id="b8eda-163">To perform the following steps, you must install the latest 64-bit version of the [Azure Active Directory V2 PowerShell Module](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5).</span></span>
  
<span data-ttu-id="b8eda-164">リンクを選択したら、[**実行**] を選択して、インストーラー パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-164">After you select the link, select **Run** to run the installer package.</span></span>
  
<span data-ttu-id="b8eda-165">**テナントの自動参加を無効にする**: 新規ユーザーが管理対象テナントに参加できないようにするには、次に示す Windows PowerShell コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="b8eda-165">**Disable automatic tenant join**: Use this Windows PowerShell command to prevent new users from joining a managed tenant:</span></span>
  
<span data-ttu-id="b8eda-166">新規ユーザーに対してテナントの自動参加を無効にする場合:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`</span><span class="sxs-lookup"><span data-stu-id="b8eda-166">To disable automatic tenant join for new users:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`</span></span>
  
<span data-ttu-id="b8eda-167">新規ユーザーに対してテナントの自動参加を有効にする場合:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`</span><span class="sxs-lookup"><span data-stu-id="b8eda-167">To enable automatic tenant join for new users:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8eda-168">このブロックの設定で、組織の新しいユーザーは Power BI にサインアップできなくなります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-168">This blocking prevents new users in your organization from signing up for Power BI.</span></span> <span data-ttu-id="b8eda-169">組織内の新しいサインアップを無効にする前に Power BI にサインアップしていたユーザーは、それ以降もライセンスを与えられたままになります。</span><span class="sxs-lookup"><span data-stu-id="b8eda-169">Users that sign up for Power BI prior to disabling new signups for your organization will still retain their licenses.</span></span> <span data-ttu-id="b8eda-170">以前に[サービス](#how-do-i-remove-power-bi-for-users-that-already-signed-up)にサインアップしたユーザーの Power BI へのアクセスを削除する方法については、「既にサインアップしたユーザーの Power BI を削除する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-170">See the [How do I remove Power BI for users that already signed up?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) for instructions on how you can remove access to Power BI for users that had previously signed up for the service.</span></span>
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a><span data-ttu-id="b8eda-171">ユーザーに既存のテナントへの参加を許可する方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-171">How can I allow users to join my existing tenant?</span></span>

<span data-ttu-id="b8eda-172">To allow users to join your tenant, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`</span><span class="sxs-lookup"><span data-stu-id="b8eda-172">To allow users to join your tenant, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`</span></span>
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a><span data-ttu-id="b8eda-173">テナントでブロックが設定されているかどうかを確認する方法を教えてください</span><span class="sxs-lookup"><span data-stu-id="b8eda-173">How do I verify if I have the block on in the tenant?</span></span>

<span data-ttu-id="b8eda-174">次の PowerShell スクリプトを使用します:  `Get-MsolCompanyInformation | fl allow*`</span><span class="sxs-lookup"><span data-stu-id="b8eda-174">Use the following PowerShell script:  `Get-MsolCompanyInformation | fl allow*`</span></span>
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a><span data-ttu-id="b8eda-175">既存のユーザーが Power BI を使い始めることを防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-175">How can I prevent my existing users from starting to use Power BI?</span></span>

<span data-ttu-id="b8eda-176">**ライセンスの自動配布を無効にする**: 既存ユーザーに対してライセンスの自動配布を無効にするには、次に示す Windows PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-176">**Disable automatic license distribution:** Use this Windows PowerShell script to disable automatic license distributions for existing users.</span></span> <span data-ttu-id="b8eda-177">以前にライセンスの自動配布を既に無効にしている場合は、このプロセスを繰り返す必要があります (たとえば、学生、教職員、およびスタッフのOffice 365 Educationなど)。</span><span class="sxs-lookup"><span data-stu-id="b8eda-177">You do not need to repeat this process if you have already disabled automatic license distribution before (for example, Office 365 Education for Students, Faculty, and Staff).</span></span>
  
<span data-ttu-id="b8eda-178">既存ユーザーに対してライセンスの自動配布を無効にする場合:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`</span><span class="sxs-lookup"><span data-stu-id="b8eda-178">To disable automatic license distribution for existing users:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`</span></span>
  
<span data-ttu-id="b8eda-179">既存ユーザーに対してライセンスの自動配布を有効にする場合:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`</span><span class="sxs-lookup"><span data-stu-id="b8eda-179">To enable automatic license distribution for existing users:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8eda-180">*AllowAdHocSubscriptions* フラグは、ユーザーが Azure Rights Management Service にサインアップする機能など、組織内のいくつかのユーザー機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-180">The *AllowAdHocSubscriptions* flag is used to control several user capabilities in your organization, including the ability for users to sign up for the Azure Rights Management Service.</span></span> <span data-ttu-id="b8eda-181">このフラグを変更すると、これらのすべての機能に影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-181">Changing this flag will affect all of these capabilities.</span></span>
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a><span data-ttu-id="b8eda-182">既存のユーザーが Power BI にサインアップできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-182">How can I allow my existing users to sign up for Power BI?</span></span>

<span data-ttu-id="b8eda-183">To allow your existing users to sign up for Power BI, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`</span><span class="sxs-lookup"><span data-stu-id="b8eda-183">To allow your existing users to sign up for Power BI, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`</span></span>
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a><span data-ttu-id="b8eda-184">既にサインアップしたユーザーの Power BI を削除する方法</span><span class="sxs-lookup"><span data-stu-id="b8eda-184">How do I remove Power BI for users that already signed up?</span></span>

<span data-ttu-id="b8eda-185">ユーザーが Power BI にサインアップしたが、Power BI へのアクセス権を持たなくなった場合は、そのユーザーの Power BI ライセンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-185">If a user signed up for Power BI, but you no longer want them to have access to Power BI, you can remove the Power BI license for that user.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8eda-186">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-186">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b8eda-187">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-187">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b8eda-188">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-188">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="b8eda-189">ライセンスを削除するユーザーを見つけて、そのユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-189">Find the user you want to remove the license for, then select their name.</span></span>

3. <span data-ttu-id="b8eda-190">[ライセンスと **アプリ] タブで\*\*\*\*、[Microsoft** のライセンスとアプリ] チェック Power BIをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b8eda-190">On the **Licenses and Apps** tab, clear the **Microsoft Power BI** check box.</span></span>

4. <span data-ttu-id="b8eda-191">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-191">Select **Save changes**.</span></span>

## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a><span data-ttu-id="b8eda-192">新しいユーザーがテナントに参加したことは、どのようにしてわかりますか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-192">How do I know when new users have joined my tenant?</span></span>

<span data-ttu-id="b8eda-193">このプログラムの一員として、あなたのテナントに参加したユーザーには、一意のライセンスが割り当てられます。このライセンスは、管理者ダッシュボードの [アクティブ ユーザー] ウィンドウでフィルタリングできます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-193">Users who have joined your tenant as part of this program are assigned a unique license that you can filter on within your active user pane in the admin dashboard.</span></span>
  
<span data-ttu-id="b8eda-194">この新しいビューを作成するには、管理センターで、「カスタム ユーザー ビューを作成する [」の手順に従います](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view)。</span><span class="sxs-lookup"><span data-stu-id="b8eda-194">To create this new view, in the admin center, follow the steps to in [Create a custom user view](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view).</span></span> <span data-ttu-id="b8eda-195">[割 **り当てられた製品ライセンス] で\*\*\*\*、[Microsoft ライセンス] をPower BI。**</span><span class="sxs-lookup"><span data-stu-id="b8eda-195">Under **Assigned product license**, select **Microsoft Power BI**.</span></span> <span data-ttu-id="b8eda-196">新しいビューが作成されると、このプログラムに登録したテナント内のすべてのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-196">After the new view has been created, you will be able to see all the users in your tenant who have enrolled in this program.</span></span>
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a><span data-ttu-id="b8eda-197">事前に準備しておく必要のあるものが、他にもありますか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-197">Are there any additional things I should be prepared for?</span></span>

<span data-ttu-id="b8eda-p118">パスワード再設定の依頼が増えることがあります。 このプロセスの詳細については、「[ユーザーのパスワードを再設定する](../add-users/reset-passwords.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p118">You might experience an increase in password reset requests. For information about this process, see [Reset a user's password](../add-users/reset-passwords.md).</span></span>
  
<span data-ttu-id="b8eda-200">管理センターの標準プロセスを使用して、テナントからユーザーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-200">You can remove a user from your tenant via the standard process in the admin center.</span></span> <span data-ttu-id="b8eda-201">ただし、ユーザーが組織のアクティブなメール アドレスをまだ持っている場合、すべてのユーザーの参加がブロックされていない限り、そのユーザーは再び参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-201">However, if the user still has an active email address from your organization, they will be able to rejoin unless you block all users from joining.</span></span>
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a><span data-ttu-id="b8eda-202">Microsoft サービスのライセンスが 100 万件Power BIテナントに表示された理由</span><span class="sxs-lookup"><span data-stu-id="b8eda-202">Why did 1 million licenses for Microsoft Power BI show up in my tenant?</span></span>

<span data-ttu-id="b8eda-203">対象となる組織では、組織内のユーザーが Microsoft Power BI サービスを使用する資格を持ち、これらのライセンスはテナント内の新しいユーザーのPower BI容量を表します。</span><span class="sxs-lookup"><span data-stu-id="b8eda-203">As a qualifying organization, users in your organization are eligible to use the Microsoft Power BI service and these licenses represent the available capacity for new Power BI users in your tenant.</span></span> <span data-ttu-id="b8eda-204">これらのライセンスの料金は発生しません。</span><span class="sxs-lookup"><span data-stu-id="b8eda-204">There is no charge for these licenses.</span></span> <span data-ttu-id="b8eda-205">ユーザーが自分で Power BI へのサインアップを許可する場合は、サインアップ プロセスが完了すると、これらの利用可能な無料ライセンスの 1 つが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-205">If you've chosen to allow users to sign up for Power BI themselves, they will be assigned one of these available free licenses when they complete the sign up process.</span></span> <span data-ttu-id="b8eda-206">これらのライセンスを管理センターからユーザー自身に割り当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b8eda-206">You can also choose to assign these licenses to users yourself through the admin center.</span></span>
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a><span data-ttu-id="b8eda-p121">料金はかかりますか? ライセンス料は請求されますか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-p121">Is this free? Will I be charged for these licenses?</span></span>

<span data-ttu-id="b8eda-p122">これらのライセンスは Power BI の無料版で使えます。 機能を拡張したい場合は、Power BI Pro 版を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-p122">These licenses are for the free version of Power BI. If you're interested in additional capabilities, take a look at the Power BI Pro version.</span></span>
  
## <a name="why-1-million-licenses"></a><span data-ttu-id="b8eda-211">ライセンス数が 100 万件なのは、なぜですか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-211">Why 1 million licenses?</span></span>

<span data-ttu-id="b8eda-212">大多数の組織がユーザーにこの利点を提供するのに十分なライセンスを持つ十分な大きな数を選択しました。</span><span class="sxs-lookup"><span data-stu-id="b8eda-212">We chose a number that was large enough that the majority of organizations would have ample licenses to provide this benefit without delay to their users.</span></span>
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a><span data-ttu-id="b8eda-213">100 万件を超えるライセンスが必要な場合は、どうしたらよいですか?</span><span class="sxs-lookup"><span data-stu-id="b8eda-213">What if I need more than 1 million licenses?</span></span>

<span data-ttu-id="b8eda-214">追加のライセンスが必要な場合は、マイクロソフトのアカウント担当者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="b8eda-214">Contact your Microsoft account representative for more information if you will need to acquire additional licenses.</span></span>