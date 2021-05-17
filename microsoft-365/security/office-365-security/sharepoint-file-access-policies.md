---
title: 推奨されるセキュリティで保護されたドキュメント ポリシー - エンタープライズ Microsoft 365の|Microsoft Docs
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
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="98143-103">SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="98143-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="98143-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="98143-104">**Applies to**</span></span>
- [<span data-ttu-id="98143-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="98143-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="98143-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="98143-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- <span data-ttu-id="98143-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98143-107">SharePoint Online</span></span> 


<span data-ttu-id="98143-108">この記事では、推奨される ID ポリシーとデバイス アクセス ポリシーを実装して、ユーザーとユーザーを保護するSharePoint説明OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="98143-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="98143-109">このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーを基にしています](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="98143-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="98143-110">これらの推奨事項は、ニーズの粒度に基づいて適用できる SharePoint ファイルのセキュリティと保護の 3 つの層に基づいて行います。ベースライン、機密性の高い、高度に規制 **されています**。</span><span class="sxs-lookup"><span data-stu-id="98143-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="98143-111">これらのセキュリティ層と、これらの推奨事項で参照される推奨クライアント オペレーティング システムの詳細については、「概要」 [を参照してください](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="98143-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="98143-112">このガイダンスの実装に加えて、機密および規制の厳しいコンテンツに対する適切なアクセス許可の設定など、適切な保護SharePointサイトを構成してください。</span><span class="sxs-lookup"><span data-stu-id="98143-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="98143-113">一般的なポリシーを更新して、SharePointとOneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="98143-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="98143-114">次の図は、SharePointおよび OneDriveのファイルを保護するために、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="98143-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="98143-115">[![サービスとその依存サービスへのアクセスを保護するためのTeamsの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="98143-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

<span data-ttu-id="98143-116">共通ポリシーをSharePointに追加した場合は、新しいポリシーのみを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98143-116">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="98143-117">条件付きアクセス ポリシーの場合、SharePointがOneDrive。</span><span class="sxs-lookup"><span data-stu-id="98143-117">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="98143-118">新しいポリシーでは、指定したサイトに特定のアクセス要件を適用することで、機密性の高い規制のSharePointデバイス保護を実装します。</span><span class="sxs-lookup"><span data-stu-id="98143-118">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="98143-119">次の表に、新しいポリシーを確認および更新または作成する必要があるポリシーを示SharePoint。</span><span class="sxs-lookup"><span data-stu-id="98143-119">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="98143-120">共通ポリシーは、「共通 ID とデバイス アクセス ポリシー」の記事に関連付けられた構成 [手順にリンク](identity-access-policies.md) します。</span><span class="sxs-lookup"><span data-stu-id="98143-120">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="98143-121">保護レベル</span><span class="sxs-lookup"><span data-stu-id="98143-121">Protection level</span></span>|<span data-ttu-id="98143-122">ポリシー</span><span class="sxs-lookup"><span data-stu-id="98143-122">Policies</span></span>|<span data-ttu-id="98143-123">詳細情報</span><span class="sxs-lookup"><span data-stu-id="98143-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="98143-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="98143-124">**Baseline**</span></span>|[<span data-ttu-id="98143-125">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="98143-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="98143-126">クラウド SharePoint割り当てにアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="98143-126">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="98143-127">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="98143-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="98143-128">クラウド SharePoint割り当てにアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="98143-128">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="98143-129">APP データ保護ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="98143-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="98143-130">すべての推奨アプリがアプリの一覧に含まれているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="98143-130">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="98143-131">各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。</span><span class="sxs-lookup"><span data-stu-id="98143-131">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="98143-132">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="98143-132">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="98143-133">クラウド SharePointリストにアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="98143-133">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="98143-134">アプリで適用される制限を使用SharePoint</span><span class="sxs-lookup"><span data-stu-id="98143-134">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="98143-135">この新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="98143-135">Add this new policy.</span></span> <span data-ttu-id="98143-136">これにより、Azure Active Directory (Azure AD) で指定された設定を使用SharePoint。</span><span class="sxs-lookup"><span data-stu-id="98143-136">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="98143-137">このポリシーは、すべてのユーザーに適用されますが、アクセス ポリシーに含まれるサイトSharePoint影響します。</span><span class="sxs-lookup"><span data-stu-id="98143-137">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="98143-138">**機密**</span><span class="sxs-lookup"><span data-stu-id="98143-138">**Sensitive**</span></span>|[<span data-ttu-id="98143-139">サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="98143-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="98143-140">クラウド SharePoint割り当てにアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="98143-140">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="98143-141">準拠している PC とモバイル *デバイスを* 要求する</span><span class="sxs-lookup"><span data-stu-id="98143-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="98143-142">クラウド SharePointリストにアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="98143-142">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="98143-143">[SharePointアクセス制御ポリシー](#sharepoint-access-control-policies): 管理されていないデバイスから特定のサイトへのブラウザー SharePointアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="98143-143">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="98143-144">これにより、ファイルの編集とダウンロードが防止されます。</span><span class="sxs-lookup"><span data-stu-id="98143-144">This prevents edit and download of files.</span></span> <span data-ttu-id="98143-145">PowerShell を使用してサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="98143-145">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="98143-146">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="98143-146">**Highly regulated**</span></span>|[<span data-ttu-id="98143-147">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="98143-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="98143-148">クラウド SharePoint割り当てにアプリを含める。</span><span class="sxs-lookup"><span data-stu-id="98143-148">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="98143-149">[SharePointアクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 管理されていないデバイスから特定のSharePointサイトへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="98143-149">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="98143-150">PowerShell を使用してサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="98143-150">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="98143-151">アプリで適用される制限を使用SharePoint</span><span class="sxs-lookup"><span data-stu-id="98143-151">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="98143-152">SharePoint でアクセス制御を実装する場合は、Azure AD でこの条件付きアクセス ポリシーを作成して、SharePoint で構成したポリシーを適用するように Azure AD に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="98143-152">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="98143-153">このポリシーはすべてのユーザーに適用されますが、PowerShell を使用して指定したサイトへのアクセスに影響を与えるのは、PowerShell でアクセス制御を作成するときにのみSharePoint。</span><span class="sxs-lookup"><span data-stu-id="98143-153">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="98143-154">このポリシーを構成するには、「管理されていないデバイスからのアクセスを制御する」の「SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」[を参照してください](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="98143-154">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="98143-155">SharePointアクセス制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="98143-155">SharePoint access control policies</span></span>

<span data-ttu-id="98143-156">Microsoft では、デバイス アクセス制御を使用してSharePoint規制の厳しいコンテンツを使用して、サイト内のコンテンツを保護することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="98143-156">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="98143-157">これを行うには、保護のレベルと保護を適用するサイトを指定するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="98143-157">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="98143-158">機密性の高いサイト: ブラウザー専用のアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="98143-158">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="98143-159">これにより、ユーザーはファイルを編集およびダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="98143-159">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="98143-160">高度に規制されたサイト: 管理されていないデバイスからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="98143-160">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="98143-161">「管理されていないデバイスからのアクセスを制御する」の「SharePointサイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」[を参照してください](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="98143-161">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="98143-162">これらのポリシーの動作</span><span class="sxs-lookup"><span data-stu-id="98143-162">How these policies work together</span></span>

<span data-ttu-id="98143-163">通常、サイトのアクセス許可のSharePointは、サイトへのアクセスに関するビジネス上の必要性に基づいて行なう必要があります。</span><span class="sxs-lookup"><span data-stu-id="98143-163">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="98143-164">これらのアクセス許可は、サイトの所有者によって管理され、非常に動的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="98143-164">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="98143-165">デバイス SharePoint ポリシーを使用すると、ベースライン保護、機密性の高い保護、または厳しく規制された保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかに関係なく、これらのサイトを保護できます。</span><span class="sxs-lookup"><span data-stu-id="98143-165">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="98143-166">次の図は、デバイス アクセス ポリシーを使用SharePointサイトへのアクセスを保護する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="98143-166">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="98143-167">[![デバイス アクセス ポリシー SharePoint保護する方法の例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="98143-167">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="98143-168">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="98143-168">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="98143-169">James には基準となる条件付きアクセス ポリシーが割り当て済みですが、機密性の高い保護または高度に規制されたSharePointサイトへのアクセス権を与えられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98143-169">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="98143-170">James が自分の PC を使用するメンバーである機密性の高い、または規制の厳しいサイトにアクセスした場合、自分の PC が準拠している限り、アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="98143-170">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="98143-171">James が管理されていない電話を使用するメンバーである機密性の高いサイトにアクセスした場合、このサイト用に構成されたデバイス アクセス ポリシーにより、機密性の高いサイトへのブラウザー専用アクセスを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="98143-171">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="98143-172">James が管理されていない電話を使用するメンバーである規制の厳しいサイトにアクセスすると、このサイト用に構成されたアクセス ポリシーが原因でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="98143-172">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="98143-173">このサイトにアクセスできるのは、管理および準拠している PC を使用する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="98143-173">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="98143-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="98143-174">Next step</span></span>

![手順 4: クラウド アプリMicrosoft 365ポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="98143-176">次の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="98143-176">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="98143-177">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98143-177">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="98143-178">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="98143-178">Exchange Online</span></span>](secure-email-recommended-policies.md)