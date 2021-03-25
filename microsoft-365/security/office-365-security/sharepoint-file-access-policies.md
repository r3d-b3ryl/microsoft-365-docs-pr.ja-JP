---
title: 推奨されるセキュリティで保護されたドキュメント ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204976"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="7c4e0-103">SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="7c4e0-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="7c4e0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7c4e0-104">**Applies to**</span></span>
- [<span data-ttu-id="7c4e0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7c4e0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7c4e0-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7c4e0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- <span data-ttu-id="7c4e0-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c4e0-107">SharePoint Online</span></span> 


<span data-ttu-id="7c4e0-108">この記事では、SharePoint と OneDrive for Business を保護するために推奨される ID ポリシーとデバイス アクセス ポリシーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="7c4e0-109">このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーを基にしています](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="7c4e0-110">これらの推奨事項は、ニーズの粒度に基づいて適用できる SharePoint ファイルのセキュリティと保護の 3 つの層に基づいて行います。ベースライン、機密性の高い、高度に規制 **されています**。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="7c4e0-111">これらのセキュリティ層と、これらの推奨事項で参照される推奨クライアント オペレーティング システムの詳細については、「概要」 [を参照してください](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="7c4e0-112">このガイダンスの実装に加えて、機密性の高い規制が厳しいコンテンツに対して適切なアクセス許可を設定するなど、適切な保護を備えて SharePoint サイトを構成してください。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="7c4e0-113">SharePoint と OneDrive for Business を含む一般的なポリシーを更新する</span><span class="sxs-lookup"><span data-stu-id="7c4e0-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="7c4e0-114">SharePoint と OneDrive のファイルを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="7c4e0-115">[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="7c4e0-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

<span data-ttu-id="7c4e0-116">共通ポリシーの作成時に SharePoint を含める場合は、新しいポリシーのみを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-116">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="7c4e0-117">条件付きアクセス ポリシーの場合、SharePoint には OneDrive が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-117">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="7c4e0-118">新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することで、機密性の高い高度に規制されたコンテンツのデバイス保護を実装します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-118">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="7c4e0-119">次の表に、SharePoint のレビューと更新、または新しい作成を行う必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-119">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="7c4e0-120">共通ポリシーは、「共通 ID とデバイス アクセス ポリシー」の記事に関連付けられた構成 [手順にリンク](identity-access-policies.md) します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-120">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="7c4e0-121">保護レベル</span><span class="sxs-lookup"><span data-stu-id="7c4e0-121">Protection level</span></span>|<span data-ttu-id="7c4e0-122">ポリシー</span><span class="sxs-lookup"><span data-stu-id="7c4e0-122">Policies</span></span>|<span data-ttu-id="7c4e0-123">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7c4e0-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="7c4e0-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="7c4e0-124">**Baseline**</span></span>|[<span data-ttu-id="7c4e0-125">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="7c4e0-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c4e0-126">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-126">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="7c4e0-127">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="7c4e0-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="7c4e0-128">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-128">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="7c4e0-129">APP データ保護ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="7c4e0-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="7c4e0-130">すべての推奨アプリがアプリの一覧に含まれているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-130">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="7c4e0-131">各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-131">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="7c4e0-132">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="7c4e0-132">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="7c4e0-133">クラウド アプリの一覧に SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-133">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="7c4e0-134">SharePoint でアプリに適用される制限を使用する</span><span class="sxs-lookup"><span data-stu-id="7c4e0-134">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="7c4e0-135">この新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-135">Add this new policy.</span></span> <span data-ttu-id="7c4e0-136">これにより、Azure Active Directory (Azure AD) に、SharePoint で指定された設定を使用するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-136">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="7c4e0-137">このポリシーはすべてのユーザーに適用されますが、SharePoint アクセス ポリシーに含まれるサイトへのアクセスにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-137">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="7c4e0-138">**機密**</span><span class="sxs-lookup"><span data-stu-id="7c4e0-138">**Sensitive**</span></span>|[<span data-ttu-id="7c4e0-139">サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="7c4e0-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c4e0-140">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-140">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="7c4e0-141">準拠している PC とモバイル *デバイスを* 要求する</span><span class="sxs-lookup"><span data-stu-id="7c4e0-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="7c4e0-142">クラウド アプリの一覧に SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-142">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="7c4e0-143">[SharePoint アクセス制御ポリシー](#sharepoint-access-control-policies): 管理されていないデバイスから特定の SharePoint サイトへのブラウザー専用アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-143">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="7c4e0-144">これにより、ファイルの編集とダウンロードが防止されます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-144">This prevents edit and download of files.</span></span> <span data-ttu-id="7c4e0-145">PowerShell を使用してサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-145">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="7c4e0-146">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="7c4e0-146">**Highly regulated**</span></span>|[<span data-ttu-id="7c4e0-147">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="7c4e0-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c4e0-148">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-148">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="7c4e0-149">[SharePoint アクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 管理されていないデバイスからの特定の SharePoint サイトへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-149">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="7c4e0-150">PowerShell を使用してサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-150">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="7c4e0-151">SharePoint でのアプリによる制限の使用</span><span class="sxs-lookup"><span data-stu-id="7c4e0-151">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="7c4e0-152">SharePoint でアクセス制御を実装する場合は、Azure AD でこの条件付きアクセス ポリシーを作成して、SharePoint で構成したポリシーを適用するように Azure AD に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-152">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="7c4e0-153">このポリシーはすべてのユーザーに適用されますが、SharePoint でアクセス制御を作成するときに PowerShell を使用して指定したサイトへのアクセスにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-153">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="7c4e0-154">このポリシーを構成するには、「管理されていないデバイスからのアクセスを制御する」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」 [を参照してください](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-154">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="7c4e0-155">SharePoint アクセス制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="7c4e0-155">SharePoint access control policies</span></span>

<span data-ttu-id="7c4e0-156">Microsoft では、デバイス アクセス制御を使用して、機密性の高い規制の高いコンテンツを使用して SharePoint サイト内のコンテンツを保護することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-156">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="7c4e0-157">これを行うには、保護のレベルと保護を適用するサイトを指定するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-157">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="7c4e0-158">機密性の高いサイト: ブラウザー専用のアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-158">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="7c4e0-159">これにより、ユーザーはファイルを編集およびダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-159">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="7c4e0-160">高度に規制されたサイト: 管理されていないデバイスからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-160">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="7c4e0-161">「管理されていないデバイスからのアクセスを制御する」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは [制限する」を参照してください](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-161">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="7c4e0-162">これらのポリシーの動作</span><span class="sxs-lookup"><span data-stu-id="7c4e0-162">How these policies work together</span></span>

<span data-ttu-id="7c4e0-163">SharePoint サイトのアクセス許可は、通常、サイトへのアクセスに対するビジネス上の必要性に基づいて行なう必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-163">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="7c4e0-164">これらのアクセス許可は、サイトの所有者によって管理され、非常に動的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-164">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="7c4e0-165">SharePoint デバイス アクセス ポリシーを使用すると、ベースライン保護、機密性の高い保護、または厳しく規制された保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかに関係なく、これらのサイトを保護できます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-165">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="7c4e0-166">次の図は、SharePoint デバイス アクセス ポリシーがユーザーのサイトへのアクセスを保護する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-166">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="7c4e0-167">[![SharePoint デバイス アクセス ポリシーがサイトを保護する方法の例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="7c4e0-167">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="7c4e0-168">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="7c4e0-168">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="7c4e0-169">James には基準となる条件付きアクセス ポリシーが割り当て済みですが、機密性の高い保護または高度に規制された保護を備え、SharePoint サイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-169">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="7c4e0-170">James が自分の PC を使用するメンバーである機密性の高い、または規制の厳しいサイトにアクセスした場合、自分の PC が準拠している限り、アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-170">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="7c4e0-171">James が管理されていない電話を使用するメンバーである機密性の高いサイトにアクセスした場合、このサイト用に構成されたデバイス アクセス ポリシーにより、機密性の高いサイトへのブラウザー専用アクセスを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-171">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="7c4e0-172">James が管理されていない電話を使用するメンバーである規制の厳しいサイトにアクセスすると、このサイト用に構成されたアクセス ポリシーが原因でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-172">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="7c4e0-173">このサイトにアクセスできるのは、管理および準拠している PC を使用する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-173">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c4e0-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="7c4e0-174">Next step</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="7c4e0-176">次の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7c4e0-176">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="7c4e0-177">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c4e0-177">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="7c4e0-178">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7c4e0-178">Exchange Online</span></span>](secure-email-recommended-policies.md)