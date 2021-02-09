---
title: 推奨されるセキュリティ保護されたドキュメント ポリシー - エンタープライズ向け Microsoft 365 |Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 5c739a47ccab79561277436812c36f842b6b578c
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142815"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="ec570-103">SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="ec570-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="ec570-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ec570-104">**Applies to**</span></span>
- [<span data-ttu-id="ec570-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ec570-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ec570-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ec570-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- <span data-ttu-id="ec570-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ec570-107">SharePoint Online</span></span> 


<span data-ttu-id="ec570-108">この記事では、推奨される ID ポリシーとデバイス アクセス ポリシーを実装して SharePoint と OneDrive for Business を保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec570-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="ec570-109">このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーに基っています](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ec570-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="ec570-110">これらの推奨事項は、ニーズの粒度に基づいて適用できる SharePoint ファイルの 3 つの異なる層のセキュリティと保護に基づいており、ベースライン、機密、厳しく規制 **されています**。</span><span class="sxs-lookup"><span data-stu-id="ec570-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="ec570-111">これらのセキュリティ層と、これらの推奨事項で参照されている推奨クライアント オペレーティング システムの詳細については、概要を [参照してください](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="ec570-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="ec570-112">このガイダンスの実装に加えて、機密性の高い厳しく規制されたコンテンツに対する適切なアクセス許可の設定など、適切な保護を備えて SharePoint サイトを構成してください。</span><span class="sxs-lookup"><span data-stu-id="ec570-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="ec570-113">SharePoint と OneDrive for Business を含む一般的なポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="ec570-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="ec570-114">SharePoint と OneDrive のファイルを保護するために、次の図は、共通の ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="ec570-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="ec570-115">[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="ec570-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="ec570-116">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="ec570-116">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="ec570-117">共通ポリシーの作成時に SharePoint を含める場合は、新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec570-117">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="ec570-118">条件付きアクセス ポリシーの場合、SharePoint には OneDrive が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec570-118">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="ec570-119">新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することで、機密性の高い厳しく規制されたコンテンツのデバイス保護を実装します。</span><span class="sxs-lookup"><span data-stu-id="ec570-119">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="ec570-120">次の表に、SharePoint の確認と更新、または新規の作成に必要なポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="ec570-120">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="ec570-121">共通ポリシーは、共通 ID とデバイス アクセス ポリシーの記事に関連する構成手順 [にリンク](identity-access-policies.md) しています。</span><span class="sxs-lookup"><span data-stu-id="ec570-121">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="ec570-122">保護レベル</span><span class="sxs-lookup"><span data-stu-id="ec570-122">Protection level</span></span>|<span data-ttu-id="ec570-123">Policies</span><span class="sxs-lookup"><span data-stu-id="ec570-123">Policies</span></span>|<span data-ttu-id="ec570-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ec570-124">More information</span></span>|
|---|---|---|
|<span data-ttu-id="ec570-125">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="ec570-125">**Baseline**</span></span>|[<span data-ttu-id="ec570-126">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="ec570-126">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="ec570-127">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="ec570-127">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="ec570-128">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="ec570-128">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="ec570-129">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="ec570-129">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="ec570-130">アプリ のデータ保護ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="ec570-130">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="ec570-131">推奨されるアプリすべてがアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec570-131">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="ec570-132">各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。</span><span class="sxs-lookup"><span data-stu-id="ec570-132">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="ec570-133">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="ec570-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="ec570-134">クラウド アプリの一覧に SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="ec570-134">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="ec570-135">SharePoint でアプリによって適用される制限を使用する</span><span class="sxs-lookup"><span data-stu-id="ec570-135">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="ec570-136">この新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ec570-136">Add this new policy.</span></span> <span data-ttu-id="ec570-137">これにより、Azure Active Directory (Azure AD) に、SharePoint で指定された設定を使用するように指示します。</span><span class="sxs-lookup"><span data-stu-id="ec570-137">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="ec570-138">このポリシーはすべてのユーザーに適用されますが、SharePoint アクセス ポリシーに含まれるサイトへのアクセスにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ec570-138">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="ec570-139">**機密**</span><span class="sxs-lookup"><span data-stu-id="ec570-139">**Sensitive**</span></span>|[<span data-ttu-id="ec570-140">サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*</span><span class="sxs-lookup"><span data-stu-id="ec570-140">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="ec570-141">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="ec570-141">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="ec570-142">準拠した PC とモバイル *デバイスが* 必要</span><span class="sxs-lookup"><span data-stu-id="ec570-142">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="ec570-143">クラウド アプリの一覧に SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="ec570-143">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="ec570-144">[SharePoint アクセス制御ポリシー](#sharepoint-access-control-policies): 非管理対象デバイスから特定の SharePoint サイトへのブラウザー専用アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="ec570-144">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="ec570-145">これにより、ファイルの編集とダウンロードが防止されます。</span><span class="sxs-lookup"><span data-stu-id="ec570-145">This prevents edit and download of files.</span></span> <span data-ttu-id="ec570-146">PowerShell を使用してサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec570-146">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="ec570-147">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="ec570-147">**Highly regulated**</span></span>|[<span data-ttu-id="ec570-148">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="ec570-148">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="ec570-149">クラウド アプリの割り当てに SharePoint を含める。</span><span class="sxs-lookup"><span data-stu-id="ec570-149">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="ec570-150">[SharePoint アクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 非管理対象デバイスからの特定の SharePoint サイトへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ec570-150">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="ec570-151">PowerShell を使用してサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec570-151">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="ec570-152">SharePoint でアプリによって適用される制限を使用する</span><span class="sxs-lookup"><span data-stu-id="ec570-152">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="ec570-153">SharePoint にアクセス制御を実装する場合は、Azure AD でこの条件付きアクセス ポリシーを作成して、SharePoint で構成したポリシーを適用するように Azure AD に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec570-153">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="ec570-154">このポリシーはすべてのユーザーに適用されますが、SharePoint でアクセス制御を作成するときに PowerShell を使用して指定したサイトへのアクセスにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ec570-154">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="ec570-155">このポリシーを構成するには、「管理されていないデバイスからのアクセスを制御する」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは [制限する」を参照してください](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="ec570-155">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="ec570-156">SharePoint アクセス制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="ec570-156">SharePoint access control policies</span></span>

<span data-ttu-id="ec570-157">デバイス アクセス制御を使用して、機密性の高い厳しく規制されたコンテンツを使用して SharePoint サイトのコンテンツを保護することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="ec570-157">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="ec570-158">これを行うには、保護のレベルと、保護を適用するサイトを指定するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec570-158">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="ec570-159">機密性の高いサイト: ブラウザー専用アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="ec570-159">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="ec570-160">これにより、ユーザーはファイルを編集およびダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ec570-160">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="ec570-161">厳しく規制されたサイト: 非管理対象デバイスからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ec570-161">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="ec570-162">非管理対象デバイスからのアクセスの制御の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」 [を参照してください](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="ec570-162">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="ec570-163">これらのポリシーの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="ec570-163">How these policies work together</span></span>

<span data-ttu-id="ec570-164">SharePoint サイトのアクセス許可は、通常、サイトへのアクセスに関するビジネス 上の必要性に基づくと理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ec570-164">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="ec570-165">これらのアクセス許可はサイトの所有者によって管理され、動的にできます。</span><span class="sxs-lookup"><span data-stu-id="ec570-165">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="ec570-166">SharePoint デバイス アクセス ポリシーを使用すると、ベースライン、機密、または厳しく規制された保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかに関係なく、これらのサイトを保護できます。</span><span class="sxs-lookup"><span data-stu-id="ec570-166">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="ec570-167">次の図は、SharePoint デバイス アクセス ポリシーがユーザーのサイトへのアクセスを保護する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ec570-167">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="ec570-168">[![SharePoint デバイス アクセス ポリシーがサイトを保護する方法の例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="ec570-168">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="ec570-169">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="ec570-169">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="ec570-170">James には、ベースラインの条件付きアクセス ポリシーが割り当てらたっていますが、機密性の高い保護または厳しく規制された保護を持つ SharePoint サイトへのアクセス権を与えられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec570-170">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="ec570-171">彼が PC を使用するメンバーである機密性の高いサイトまたは厳しく規制されたサイトにアクセスする場合、彼の PC が準拠している限り、アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="ec570-171">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="ec570-172">ベースライン ユーザーに許可されている管理されていない電話を使用するメンバーである機密性の高いサイトにアクセスする場合、このサイト用に構成されたデバイス アクセス ポリシーにより、機密サイトへのブラウザー専用アクセスを受け取る予定です。</span><span class="sxs-lookup"><span data-stu-id="ec570-172">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="ec570-173">管理されていない電話を使用しているメンバーである厳しく規制されたサイトにアクセスした場合、このサイトに対して構成されたアクセス ポリシーが原因でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ec570-173">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="ec570-174">このサイトには、管理対象の準拠 PC を使用してしかアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ec570-174">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="ec570-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="ec570-175">Next step</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="ec570-177">次の条件に合ったアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ec570-177">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="ec570-178">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec570-178">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="ec570-179">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ec570-179">Exchange Online</span></span>](secure-email-recommended-policies.md)
