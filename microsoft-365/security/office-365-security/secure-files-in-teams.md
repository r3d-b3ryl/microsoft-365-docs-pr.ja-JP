---
title: Microsoft Teams のファイルを保護する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: '概要: Microsoft Teams 内のファイルを保護するために推奨されている構成を取り上げます。'
ms.openlocfilehash: e177f290dff22943e282080652326dfb65cd07cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638478"
---
# <a name="secure-files-in-microsoft-teams"></a><span data-ttu-id="09f5e-103">Microsoft Teams のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="09f5e-103">Secure files in Microsoft Teams</span></span>

<span data-ttu-id="09f5e-104">この記事では、ファイルを保護するために、Microsoft Teams のチームとその基礎となる SharePoint サイトを、セキュリティとコラボレーションのしやすさのバランスを取りながら構成するための推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-104">This article provides recommendations for configuring teams in Microsoft Teams and their underlying SharePoint sites for file protection that balances security with ease of collaboration.</span></span> <span data-ttu-id="09f5e-105">この記事では、4 種類の構成を定義しています。最初の構成は組織内の公開サイトで、最も開放的な共有ポリシーが与えられます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-105">This article defines four different configurations, starting with a public site within your organization with the most open sharing policies.</span></span> <span data-ttu-id="09f5e-106">追加の構成はいずれも、保護において意味のある強化となりますが、Teams 内に保存されているファイルにアクセスし、共同作業を行う能力がチーム メンバーの一部の関係者に限定されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-106">Each additional configuration represents a meaningful step up in protection, but the ability to access and collaborate on files stored within Teams is reduced to the relevant set of team members.</span></span> <span data-ttu-id="09f5e-107">推奨事項を出発点として利用し、組織のニーズに合わせて構成を調整してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-107">Use these recommendations as a starting point and adjust the configurations to meet the needs of your organization.</span></span>

<span data-ttu-id="09f5e-108">この記事の構成は、3 つの保護層 (データ、ID、デバイス) に関する Microsoft の推奨事項に沿っています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-108">The configurations in this article align with Microsoft's recommendations for three tiers of protection for data, identities, and devices:</span></span>

- <span data-ttu-id="09f5e-109">基準の保護</span><span class="sxs-lookup"><span data-stu-id="09f5e-109">Baseline protection</span></span>

- <span data-ttu-id="09f5e-110">機密の保護</span><span class="sxs-lookup"><span data-stu-id="09f5e-110">Sensitive protection</span></span>

- <span data-ttu-id="09f5e-111">非常に機密性の高い社外秘の保護</span><span class="sxs-lookup"><span data-stu-id="09f5e-111">Highly confidential protection</span></span>

<span data-ttu-id="09f5e-112">以上の層と各層に推奨される機能については、次の情報源をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-112">For more information about these tiers and capabilities recommended for each tier, see the following resources.</span></span>

- [<span data-ttu-id="09f5e-113">Office 365 の ID とデバイス保護</span><span class="sxs-lookup"><span data-stu-id="09f5e-113">Identity and Device Protection for Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [<span data-ttu-id="09f5e-114">Office 365 のファイル保護ソリューション</span><span class="sxs-lookup"><span data-stu-id="09f5e-114">File Protection Solutions in Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="capability-overview"></a><span data-ttu-id="09f5e-115">機能の概要</span><span class="sxs-lookup"><span data-stu-id="09f5e-115">Capability overview</span></span>

<span data-ttu-id="09f5e-116">セキュリティで保護されたチームの推奨事項は、Microsoft 365 のさまざまな機能に基づいています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-116">Recommendations for secured teams draw on a variety of Microsoft 365 capabilities.</span></span> <span data-ttu-id="09f5e-117">次の図は、推奨されている構成を示してます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-117">The following illustration shows the recommended configurations.</span></span>

![チームの推奨構成](../../media/secure-team-configurations.png)

<span data-ttu-id="09f5e-119">次の点が示されています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-119">As illustrated:</span></span>

- <span data-ttu-id="09f5e-120">ベースライン保護には、パブリック チームとプライベート チームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-120">Baseline protection includes a public team and private team.</span></span> <span data-ttu-id="09f5e-121">パブリック チームは、組織内のだれでも検出およびアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-121">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="09f5e-122">プライベート チームは、チームのメンバーのみが検出とアクセスを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-122">Private teams can only be discovered and accessed by members of the team.</span></span> <span data-ttu-id="09f5e-123">これらの構成はいずれも、ファイルがチーム グループ外に保存されている基礎となる SharePoint サイトを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-123">Both of these configurations allow for sharing of the underlying SharePoint site on which files are stored outside the team group.</span></span>

- <span data-ttu-id="09f5e-124">機密および高機密の保護のチームはプライベート チームで、基礎となるサイトへのアクセスの共有および要求は制限されています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-124">Teams for sensitive and highly confidential protection are private teams in which sharing and the requesting of access for the underlying site is limited.</span></span>

- <span data-ttu-id="09f5e-125">[保持ラベル](../../compliance/labels.md)は、基礎となる SharePoint サイト内のファイルを分類する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-125">[Retention labels](../../compliance/labels.md) provide a way to classify files within the underlying SharePoint sites.</span></span> <span data-ttu-id="09f5e-126">基礎となる SharePoint サイトはそれぞれ、ドキュメント ライブラリのファイルに既定の保持ラベルを自動的に付けるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-126">Each of the underlying SharePoint sites are configured to automatically label files in document libraries with a default retention label.</span></span> <span data-ttu-id="09f5e-127">4 つのチーム構成に合わせて、このサンプルのラベルは「内部パブリック」、「プライベート」、「機密」、「非常に機密性の高い社外秘」になっています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-127">Corresponding to the four team configurations, the labels in this example are Internal Public, Private, Sensitive, and Highly Confidential.</span></span> <span data-ttu-id="09f5e-128">ユーザーは個々のファイルのラベルを変更できますが、この構成ですべてのファイルに既定のラベルが確実に与えられます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-128">Users can change the labels on the individual files, but this configuration ensures all files receive a default label.</span></span>

- <span data-ttu-id="09f5e-129">[データ損失防止](../../compliance/data-loss-prevention-policies.md) (DLP) ポリシーは、機密および高機密の保持ラベル向けに構成されており、これらのタイプのファイルをユーザーが組織外に送信しようとすると警告を表示したり、その処理を防止したりします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-129">[Data loss prevention](../../compliance/data-loss-prevention-policies.md) (DLP) policies are configured for the Sensitive and Highly Confidential retention labels to either warn or prevent users when they attempt to send these types of files outside the organization.</span></span>

- <span data-ttu-id="09f5e-130">シナリオの必要に応じて、[機密ラベル](../../compliance/sensitivity-labels.md)を使用して、暗号化やアクセス許可によって機密性の高いファイルを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-130">If needed for your scenario, you can use [sensitivity labels](../../compliance/sensitivity-labels.md) to protect highly confidential files with encryption and permissions.</span></span> <span data-ttu-id="09f5e-131">Azure Information Protection のお客様は、Microsoft 365 コンプライアンス センターで、Azure Information Protection ラベルを使用することができ、追加の構成や高度な構成を行うように選択すると、ラベルは Azure portal と同期されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-131">For Azure Information Protection customers, you can use your Azure Information Protection labels in the Microsoft 365 compliance center, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration.</span></span> <span data-ttu-id="09f5e-132">Azure Information Protection ラベルと秘密度ラベルは、互いに完全な互換性があります。</span><span class="sxs-lookup"><span data-stu-id="09f5e-132">Azure Information Protection labels and sensitivity labels are fully compatible with each other.</span></span> <span data-ttu-id="09f5e-133">そのため、たとえば、Azure Information Protection でラベル付けされたコンテンツがある場合、そのコンテンツの分類やラベル付けをやり直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-133">This means, for example, if you have content labeled by Azure Information Protection, you won't need to reclassify or relabel your content.</span></span> <span data-ttu-id="09f5e-134">このレベルの保護がすべてのお客様に求められているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-134">Not all customers need this level of protection.</span></span>

## <a name="organization-wide-settings-for-sharepoint-and-onedrive"></a><span data-ttu-id="09f5e-135">SharePoint と OneDrive の組織全体の設定</span><span class="sxs-lookup"><span data-stu-id="09f5e-135">Organization-wide settings for SharePoint and OneDrive</span></span>

<span data-ttu-id="09f5e-136">SharePoint と OneDrive には、すべてのサイトとユーザーに影響を与える組織全体の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-136">SharePoint and OneDrive include organization-wide settings that affect all sites and users.</span></span> <span data-ttu-id="09f5e-137">このような設定の一部はサイト レベルで調整し、さらに限定的にすることもできます (限定性を下げることはできません)。</span><span class="sxs-lookup"><span data-stu-id="09f5e-137">Some of these settings can also be adjusted at the site level to be more restrictive (but not less).</span></span> <span data-ttu-id="09f5e-138">このセクションでは、セキュリティと共同作業に影響を与えるテナント全体の設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-138">This section discusses tenant-wide settings that affect security and collaboration.</span></span>

### <a name="sharing"></a><span data-ttu-id="09f5e-139">共有</span><span class="sxs-lookup"><span data-stu-id="09f5e-139">Sharing</span></span>

<span data-ttu-id="09f5e-140">このソリューションでは、次の組織全体設定を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="09f5e-140">For this solution, we recommend the following organization-wide settings:</span></span>

- <span data-ttu-id="09f5e-141">匿名の共有を含む、あらゆるアカウント タイプとのあらゆる共有を許可する既定の共有ポリシーを維持します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-141">Keep the default sharing policy that allows all sharing with all account types, including anonymous sharing.</span></span>

- <span data-ttu-id="09f5e-142">必要に応じて、匿名リンクの有効期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-142">Set anonymous links to expire, if desired.</span></span>

- <span data-ttu-id="09f5e-p107">既定のリンクの種類を「内部」に変更します。これにより、組織外で意図せずデータが漏洩する事態を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p107">Change the default link type for sharing to Internal. This helps prevent accidental data leakage outside your organization.</span></span>

<span data-ttu-id="09f5e-145">外部共有を許可することは直観に反することに思われるかもしれませんが、この手法では、メールでファイルを送信する方法に比べ、ファイル共有に対する管理が強化されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-145">While it might seem counterintuitive to allow external sharing, this approach provides more control over file sharing compared to sending files in email.</span></span> <span data-ttu-id="09f5e-146">SharePoint と Outlook の連動により、安全な方法でファイルに共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-146">SharePoint and Outlook work together to provide secure collaboration on files.</span></span>

- <span data-ttu-id="09f5e-147">既定では、Outlook は、電子メールでファイルを送信する代わりに、ファイルへのリンクを共有します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-147">By default, Outlook shares a link to a file instead of sending the file in email.</span></span>

- <span data-ttu-id="09f5e-148">SharePoint と OneDrive を使用すると、組織の内部と外部の共同作成者にファイルへのリンクを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-148">SharePoint and OneDrive make it easy to share links to files with contributors who are both inside and outside your organization</span></span>

<span data-ttu-id="09f5e-p109">また、外部共有を管理することもできます。たとえば、以下の事柄が可能です。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p109">You also have controls to help govern external sharing. For example, you can:</span></span>

- <span data-ttu-id="09f5e-151">匿名ゲスト リンクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-151">Disable an anonymous guest link.</span></span>

- <span data-ttu-id="09f5e-152">サイトへのユーザー アクセスを取り消す。</span><span class="sxs-lookup"><span data-stu-id="09f5e-152">Revoke user access to a site.</span></span>

- <span data-ttu-id="09f5e-153">特定のサイトまたはドメインにアクセスできるユーザーを確認する。</span><span class="sxs-lookup"><span data-stu-id="09f5e-153">See who has access to a specific site or document.</span></span>

- <span data-ttu-id="09f5e-154">匿名の共有リンクに期限を設定する (テナント設定)。</span><span class="sxs-lookup"><span data-stu-id="09f5e-154">Set anonymous sharing links to expire (tenant setting).</span></span>

- <span data-ttu-id="09f5e-155">組織外で共有できるユーザーを制限する (テナント設定)。</span><span class="sxs-lookup"><span data-stu-id="09f5e-155">Limit who can share outside your organization (tenant setting).</span></span>

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a><span data-ttu-id="09f5e-156">データ損失防止 (DLP) を外部共有と併用します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-156">Use external sharing together with data loss prevention (DLP)</span></span>

<span data-ttu-id="09f5e-p110">外部共有を許可しない場合、ビジネスで必要なユーザーは、代替のツールと手段を使用することになります。Microsoft は、機密ファイルおよび高機密ファイルを保護するために DLP ポリシーと外部共有を組み合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p110">If you don't allow external sharing, users with a business need will find alternate tools and methods. Microsoft recommends you combine external sharing with DLP policies to protect sensitive and highly confidential files.</span></span>

### <a name="device-access-settings"></a><span data-ttu-id="09f5e-159">デバイス アクセスの設定</span><span class="sxs-lookup"><span data-stu-id="09f5e-159">Device access settings</span></span>

<span data-ttu-id="09f5e-160">SharePoint と OneDrive のデバイス アクセスの設定では、アクセスを参照のみ (ファイルのダウンロード不可) に限定するか、アクセスをブロックするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-160">Device access settings for SharePoint and OneDrive let you determine whether access is limited to browser only (files can't be downloaded) or if access is blocked.</span></span> <span data-ttu-id="09f5e-161">詳細については、「[非管理対象デバイスからのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-161">For more information, see [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

<span data-ttu-id="09f5e-162">Azure Active Directory で推奨される条件付きアクセス ポリシーで、デバイス アクセスの設定を使用するには、「[SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-162">To use device access settings with recommended conditional access policies in Azure Active Directory, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

<span data-ttu-id="09f5e-163">設定を見て、OneDrive サイトの既定の設定を変更するかどうか決定してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-163">Visit these settings to decide if you want to change the default settings for OneDrive sites.</span></span> <span data-ttu-id="09f5e-164">現在のところ、共有とデバイス アクセスの設定は SharePoint 管理センターから複製されており、両方の環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-164">Currently, the sharing and device access settings are duplicated from the SharePoint admin center and apply to both environments.</span></span>

## <a name="team-and-sharepoint-site-configuration"></a><span data-ttu-id="09f5e-165">チームおよび SharePoint サイトの構成</span><span class="sxs-lookup"><span data-stu-id="09f5e-165">Team and SharePoint site configuration</span></span>

<span data-ttu-id="09f5e-166">次の表は、この記事で先に説明した、各チームとその基礎となる SharePoint サイトの構成をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="09f5e-166">The following table summarizes the configuration for each of the teams and their underlying SharePoint site described earlier in this article.</span></span> <span data-ttu-id="09f5e-167">この構成を出発点として利用し、組織のニーズに合わせてサイトの種類と構成を調整してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-167">Use these configurations as starting point recommendations and adjust the site types and configurations to meet the needs of your organization.</span></span> <span data-ttu-id="09f5e-168">すべての組織があらゆる種類のチームを必要とするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-168">Not every organization needs every type of team.</span></span> <span data-ttu-id="09f5e-169">ごく一部の組織だけが高機密保護のチームを必要とします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-169">Only a small number of organizations require teams with highly confidential protection.</span></span>

||||||
|:-----|:-----|:-----|:-----|:-----|
||<span data-ttu-id="09f5e-170">**ベースライン保護 1**</span><span class="sxs-lookup"><span data-stu-id="09f5e-170">**Baseline protection #1**</span></span>|<span data-ttu-id="09f5e-171">**基準の保護 #2**</span><span class="sxs-lookup"><span data-stu-id="09f5e-171">**Baseline protection #2**</span></span>|<span data-ttu-id="09f5e-172">**機密の保護**</span><span class="sxs-lookup"><span data-stu-id="09f5e-172">**Sensitive protection**</span></span>|<span data-ttu-id="09f5e-173">**非常に機密性の高い社外秘**</span><span class="sxs-lookup"><span data-stu-id="09f5e-173">**Highly confidential**</span></span>|
|<span data-ttu-id="09f5e-174">説明</span><span class="sxs-lookup"><span data-stu-id="09f5e-174">Description</span></span>|<span data-ttu-id="09f5e-175">組織内でアクセスや共同作業が自由に行えるパブリック チーム。</span><span class="sxs-lookup"><span data-stu-id="09f5e-175">Public team with open discovery and collaboration within the organization.</span></span>|<span data-ttu-id="09f5e-176">グループ外で基礎となる SharePoint サイトを共有できるプライベート チーム。</span><span class="sxs-lookup"><span data-stu-id="09f5e-176">Private team with sharing of the underlying SharePoint site allowed outside the group.</span></span>|<span data-ttu-id="09f5e-177">基礎となる SharePoint サイトの共有がサイトのメンバーに限定されるプライベート チーム。</span><span class="sxs-lookup"><span data-stu-id="09f5e-177">Private team, but sharing of the underlying SharePoint site is only allowed to members of the site.</span></span> <span data-ttu-id="09f5e-178">組織外にファイルを送信しようとすると、DLP はユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-178">DLP warns users when attempting to send files outside the organization.</span></span>|<span data-ttu-id="09f5e-179">ファイルとともに送信されるファイルの暗号化およびアクセス許可用に機密ラベルが付いているプライベート チーム。</span><span class="sxs-lookup"><span data-stu-id="09f5e-179">Private team with sensitivity labels for file encryption and permissions that travel with the file.</span></span> <span data-ttu-id="09f5e-180">DLP は、組織の外にファイルを送信しようとする行為を禁止します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-180">DLP prevents users from sending files outside the organization.</span></span>|
|<span data-ttu-id="09f5e-181">チーム サイトはプライベートかパブリックか</span><span class="sxs-lookup"><span data-stu-id="09f5e-181">Private or public team site</span></span>|<span data-ttu-id="09f5e-182">パブリック</span><span class="sxs-lookup"><span data-stu-id="09f5e-182">Public</span></span>|<span data-ttu-id="09f5e-183">プライベート</span><span class="sxs-lookup"><span data-stu-id="09f5e-183">Private</span></span>|<span data-ttu-id="09f5e-184">プライベート</span><span class="sxs-lookup"><span data-stu-id="09f5e-184">Private</span></span>|<span data-ttu-id="09f5e-185">プライベート</span><span class="sxs-lookup"><span data-stu-id="09f5e-185">Private</span></span>|
|<span data-ttu-id="09f5e-186">誰にアクセス権が与えられるか</span><span class="sxs-lookup"><span data-stu-id="09f5e-186">Who has access?</span></span>|<span data-ttu-id="09f5e-187">B2B のユーザーを含む組織の全員。</span><span class="sxs-lookup"><span data-stu-id="09f5e-187">Everybody in the organization, including B2B users.</span></span>|<span data-ttu-id="09f5e-188">サイトのメンバーのみ。</span><span class="sxs-lookup"><span data-stu-id="09f5e-188">Members of the site only.</span></span> <span data-ttu-id="09f5e-189">他のユーザーは、アクセス権を要求できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-189">Others can request access.</span></span>|<span data-ttu-id="09f5e-190">チームのメンバーのみ。</span><span class="sxs-lookup"><span data-stu-id="09f5e-190">Members of the team only.</span></span> <span data-ttu-id="09f5e-191">他のユーザーは、チーム所有者によって承認されている基礎となるサイトへのアクセスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-191">Others can request access to the underlying site, which is approved by a team owner.</span></span>|<span data-ttu-id="09f5e-192">メンバーのみ。</span><span class="sxs-lookup"><span data-stu-id="09f5e-192">Members only.</span></span> <span data-ttu-id="09f5e-193">他のユーザーは基礎となるサイトへのアクセスを要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-193">Others cannot request access to the underlying site.</span></span>|
|<span data-ttu-id="09f5e-194">サイト レベルの共有制御</span><span class="sxs-lookup"><span data-stu-id="09f5e-194">Site-level sharing controls</span></span>|<span data-ttu-id="09f5e-p119">すべてのユーザーと共有できます。既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p119">Sharing allowed with anybody. Default settings.</span></span>|<span data-ttu-id="09f5e-p120">すべてのユーザーと共有できます。既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p120">Sharing allowed with anybody. Default settings.</span></span>|<span data-ttu-id="09f5e-199">メンバーはサイトへのアクセスを共有できません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-199">Members cannot share access to the site.</span></span> <br/> <span data-ttu-id="09f5e-200">メンバー以外の人はサイトへのアクセスを要求できますが、要求はチームのグループ所有者に対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="09f5e-200">Non-members can request access to the site, but these requests need to be addressed by a group owner for the team.</span></span>|<span data-ttu-id="09f5e-201">メンバーはサイトへのアクセスを共有できません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-201">Members cannot share access to the site.</span></span> <br/> <span data-ttu-id="09f5e-202">メンバー以外の人はサイトまたはそのコンテンツへのアクセスを要求できません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-202">Non-members cannot request access to the site or its contents.</span></span>|
|<span data-ttu-id="09f5e-203">サイトレベルのデバイス アクセス制御</span><span class="sxs-lookup"><span data-stu-id="09f5e-203">Site-level device access controls</span></span>|<span data-ttu-id="09f5e-204">付加的な制御はありません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-204">No additional controls.</span></span>|<span data-ttu-id="09f5e-205">付加的な制御はありません。</span><span class="sxs-lookup"><span data-stu-id="09f5e-205">No additional controls.</span></span>|<span data-ttu-id="09f5e-p121">ユーザーは、非準拠デバイスまたはドメインに参加していないデバイスにファイルをダウンロードできません。他のすべてのデバイスからは参照専用のアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p121">Prevents users from downloading files to non-compliant or non-domain joined devices. This allows browser-only access from all other devices.</span></span>|<span data-ttu-id="09f5e-208">非準拠デバイスまたはドメインに参加していないデバイスへのファイルのダウンロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-208">Block downloading of files to non-compliant or non-domain joined devices.</span></span>|
|<span data-ttu-id="09f5e-209">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="09f5e-209">Retention labels</span></span>|<span data-ttu-id="09f5e-210">内部パブリック</span><span class="sxs-lookup"><span data-stu-id="09f5e-210">Internal Public</span></span>|<span data-ttu-id="09f5e-211">プライベート</span><span class="sxs-lookup"><span data-stu-id="09f5e-211">Private</span></span>|<span data-ttu-id="09f5e-212">機密</span><span class="sxs-lookup"><span data-stu-id="09f5e-212">Sensitive</span></span>|<span data-ttu-id="09f5e-213">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="09f5e-213">Highly Confidential</span></span>|
|<span data-ttu-id="09f5e-214">DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="09f5e-214">DLP policies</span></span>|||<span data-ttu-id="09f5e-215">機密ラベルが付けられたファイルを組織の外に送信しようとするとユーザーに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-215">Warn users when sending files that are labeled as Sensitive outside the organization.</span></span> <br/> <span data-ttu-id="09f5e-216">クレジット カード番号や他の個人データなど、機密データの種類の外部共有をブロックするには、これらのデータの種類 (自分で構成したカスタム データの種類を含む) に追加の DLP ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-216">To block external sharing of sensitive data types, such as credit card numbers or other personal data, you can configure additional DLP policies for these data types (including custom data types you configure).</span></span>|<span data-ttu-id="09f5e-p122">ユーザーが高機密のラベルが付けられているファイルを組織の外部に送信できないようにします。ファイルの共有相手など、理由を提供することよって、ユーザーはこの設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p122">Block users from sending files that are labeled as highly confidential outside organization. Allow users to override this by providing justification, including who they are sharing the file with.</span></span>|
|<span data-ttu-id="09f5e-219">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="09f5e-219">Sensitivity labels</span></span>||||<span data-ttu-id="09f5e-220">機密ラベルを使用して、ファイルの暗号化とファイルへのアクセス許可の付与を行います。</span><span class="sxs-lookup"><span data-stu-id="09f5e-220">Use sensitivity labels to encrypt and grant permissions to files.</span></span> <span data-ttu-id="09f5e-221">ファイルが基礎となる SharePoint サイトから流出した場合も、こうした保護は維持されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-221">This protection travels with the files in case they are leaked from the underlying SharePoint site.</span></span>|

<span data-ttu-id="09f5e-222">このソリューションの 4 種類のチームを展開する手順については、「[ファイルの 3 層の保護用にチームを展開する](deploy-teams-three-tiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-222">For the steps to deploy the four different types of teams in this solution, see [Deploy teams for three tiers of protection for files](deploy-teams-three-tiers.md).</span></span>

## <a name="retention-labels"></a><span data-ttu-id="09f5e-223">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="09f5e-223">Retention labels</span></span>

<span data-ttu-id="09f5e-224">機密データが存在する環境には、保持ラベルの使用が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-224">Using retention labels is recommended for environments with sensitive data.</span></span> <span data-ttu-id="09f5e-225">保持ラベルの構成と発行が完了した後、次のことを行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="09f5e-225">After you configure and publish retention labels:</span></span>

- <span data-ttu-id="09f5e-226">チームの基礎となる SharePoint サイトのドキュメント ライブラリに既定のラベルを適用することにより、チームの **[ファイル]** セクション内のすべてのドキュメントに既定のラベルを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-226">You can apply a default label to a document library in the underlying SharePoint site for a team, so that all documents in the **Files** section of the team get the default label.</span></span>

- <span data-ttu-id="09f5e-227">コンテンツが特定の条件に一致するときには、ラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-227">You can apply labels to content automatically if it matches specific conditions.</span></span>

- <span data-ttu-id="09f5e-228">保持ラベルに基づいた DLP ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-228">You can apply DLP policies that are based on retention labels.</span></span>

- <span data-ttu-id="09f5e-229">組織のユーザーが Outlook on the web、Outlook​​ 2010 以降、OneDrive、SharePoint​​、Microsoft 365 グループ内のコンテンツにラベルを手動で適用できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-229">People in your organization can apply a label manually to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="09f5e-230">多くの場合、ユーザーは自分が操作するコンテンツの種類を最もよく知っているので、コンテンツを分類して適切な DLP ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-230">Users often know best what type of content they're working with, so they can classify it and have the appropriate DLP policy applied.</span></span>

<span data-ttu-id="09f5e-231">図に示されているように、このソリューションでは次の保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="09f5e-231">As illustrated, this solution includes creating the following retention labels:</span></span>

- <span data-ttu-id="09f5e-232">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="09f5e-232">Highly Confidential</span></span>

- <span data-ttu-id="09f5e-233">機密</span><span class="sxs-lookup"><span data-stu-id="09f5e-233">Sensitive</span></span>

- <span data-ttu-id="09f5e-234">プライベート</span><span class="sxs-lookup"><span data-stu-id="09f5e-234">Private</span></span>

- <span data-ttu-id="09f5e-235">内部パブリック</span><span class="sxs-lookup"><span data-stu-id="09f5e-235">Internal Public</span></span>

<span data-ttu-id="09f5e-p126">これらのラベルは、図で推奨されているサイトと、この記事で前述したグラフにマップされます。このソリューションでは、機密および高機密というラベルの付いたファイルの漏洩を防ぐために DLP ポリシーを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-p126">These labels are mapped to the recommended sites in the illustrations and charts earlier in this article. This solution recommends configuring DLP policies to help prevent the leakage of files labeled as Sensitive and Highly Confidential.</span></span>

<span data-ttu-id="09f5e-238">このソリューションで保持ラベルと DLP ポリシーを構成する手順については、「[保持ラベルと DLP を使用してチーム内のファイルを保護する](deploy-teams-retention-DLP.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-238">For the steps to configure retention labels and DLP policies in this solution, see [Protect files in teams with retention labels and DLP](deploy-teams-retention-DLP.md).</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="09f5e-239">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="09f5e-239">Sensitivity labels</span></span>

<span data-ttu-id="09f5e-240">セキュリティ シナリオで保証される場合には、機密ラベルを使用して、ファイルが移動する場所に関係なく、保護を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="09f5e-240">If warranted for your security scenario, you can use sensitivity labels to apply protections that follow the files wherever they go.</span></span> <span data-ttu-id="09f5e-241">Microsoft 365 コンプライアンス センターの機密ラベルと Azure Information Protection ラベルは同じです。</span><span class="sxs-lookup"><span data-stu-id="09f5e-241">Sensitivity labels in the Microsoft 365 compliance center and Azure Information Protection labels are the same.</span></span> <span data-ttu-id="09f5e-242">このソリューションでは、機密ラベルまたはサブラベルを使用して、最高レベルのセキュリティでの保護が必要なファイルを暗号化して、それらのファイルに対するアクセス許可を付与することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09f5e-242">For this solution, we recommend you use a sensitivity label or sublabel to encrypt and grant permissions to files that need to be protected with the highest level of security.</span></span>

<span data-ttu-id="09f5e-243">詳細については、「[機密ラベルの概要](../../compliance/sensitivity-labels.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-243">For more information, see [Overview of sensitivity labels](../../compliance/sensitivity-labels.md).</span></span>

<span data-ttu-id="09f5e-244">このソリューションで機密ラベルを構成する手順については、「[機密ラベルを使用してチーム内のファイルを保護する](deploy-teams-sensitivity-labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09f5e-244">For the steps to configure sensitivity labels in this solution, see [Protect files in teams with sensitivity labels](deploy-teams-sensitivity-labels.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09f5e-245">関連項目</span><span class="sxs-lookup"><span data-stu-id="09f5e-245">See also</span></span>

[<span data-ttu-id="09f5e-246">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="09f5e-246">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
