---
title: Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint Online サイト
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社が SharePoint Online サイトを非常に規制されたデータ用に実装し、研究チーム間のコラボレーションを容易にする方法について説明します。'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369528"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="88edd-103">Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="88edd-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="88edd-104">**概要:** 研究チーム間のコラボレーションを容易にするために、Contoso 社が SharePoint Online サイトを高規制データ用に実装した方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="88edd-105">Contoso 社の最も重要な資産は、独自の製造手法、開発中の製品の設計仕様など、企業秘密の形式での知的財産です。</span><span class="sxs-lookup"><span data-stu-id="88edd-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="88edd-106">これらのアセットはデジタル形式で、もともとは SharePoint Server 2016 サイトにファイルとして保存されています。</span><span class="sxs-lookup"><span data-stu-id="88edd-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="88edd-107">Contoso 社では、Microsoft 365 Enterprise を展開したときに、オンプレミスのデジタルアセットをクラウドに移行して、パリ、モスクワ、ニューヨーク、北京、Bangalore の研究チーム間で簡単にアクセスできるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="88edd-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="88edd-108">ただし、機密性の高い性質上、これらのファイルへのアクセスは次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88edd-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="88edd-109">SharePoint 管理者のみが管理するサイトに対する継続的なアクセス許可を持つ、それらのユーザーを表示または変更できるユーザーのセットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="88edd-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="88edd-110">データ損失防止 (DLP) を使用して保護することで、ユーザーがサイト外に配布するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="88edd-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="88edd-111">権限のないユーザーがサイト外に配布されている場合でも、そのコンテンツへのアクセスを許可しないように、アクセス制御リストで暗号化および保護します。</span><span class="sxs-lookup"><span data-stu-id="88edd-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="88edd-112">Contoso 社の IT 部門のセキュリティおよび SharePoint 管理者は、厳しく規制された[データ用に Sharepoint Online サイト](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="88edd-113">Contoso 社は、これらの手順を使用して、調査チームのために SharePoint Online チームサイトを作成してセキュリティ保護しています。</span><span class="sxs-lookup"><span data-stu-id="88edd-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="88edd-114">手順 1: 研究チームグループのメンバーをレビューおよび確認する</span><span class="sxs-lookup"><span data-stu-id="88edd-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="88edd-115">Contoso IT 管理者は、研究チームの一連のセキュリティグループの確認を行いました。</span><span class="sxs-lookup"><span data-stu-id="88edd-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="88edd-116">研究者以外のユーザーを削除したか、または研究資産にアクセスする必要がないユーザーを削除しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="88edd-117">また、これらの新しいセキュリティグループも作成しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="88edd-118">**研究-管理者** アクセス許可を変更する機能を含め、サイトを完全に制御できる SharePoint 管理者のセット。</span><span class="sxs-lookup"><span data-stu-id="88edd-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="88edd-119">**リサーチ-メンバー** 世界各地の研究チームの一連のセキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="88edd-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="88edd-120">**リサーチ閲覧**者 サイト上の資産のみを表示できる、研究組織のエグゼクティブなどの管理ユーザーのセット。</span><span class="sxs-lookup"><span data-stu-id="88edd-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="88edd-121">手順 2: 分離した SharePoint Online チームサイトを作成する</span><span class="sxs-lookup"><span data-stu-id="88edd-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="88edd-122">Contoso 社の SharePoint 管理者は、最初に**Research**という名前の新しいチームサイトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="88edd-123">その後、次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="88edd-123">They then configured:</span></span>

- <span data-ttu-id="88edd-124">リサーチの所有者の SharePoint グループを使用して、**研究管理者**のセキュリティグループをメンバーとして持つ、フルコントロールアクセス許可レベル。</span><span class="sxs-lookup"><span data-stu-id="88edd-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="88edd-125">**Research メンバーのセキュリティグループ**をメンバーとして持つ research メンバーの SharePoint グループを使用するための編集アクセス許可レベル。</span><span class="sxs-lookup"><span data-stu-id="88edd-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="88edd-126">リサーチ閲覧者の SharePoint グループを使用してリサーチ閲覧者**のセキュリティグループ**をメンバーとして持つ、読み取りアクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="88edd-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="88edd-127">その結果、SharePoint アクセス許可レベル、SharePoint グループ、およびそれらのメンバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88edd-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![SharePoint アクセス許可レベル、SharePoint グループ、およびそれらのメンバー](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="88edd-129">次に、サイトに対する追加の制限を構成しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-129">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="88edd-130">構成の詳細については、「[分離した SharePoint Online チームサイトを展開する](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88edd-130">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="88edd-131">手順 3: 制限付き DLP ポリシー用にサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="88edd-131">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="88edd-132">最初に、Contoso 管理者は**高機密**Office 365 保持ラベルを**Research**サイトに適用しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-132">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="88edd-133">次に、 **Research**という名前の新しい OFFICE 365 DLP ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-133">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="88edd-134">非常に**機密性の高い**Office 365 保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="88edd-134">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="88edd-135">**リサーチ**サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="88edd-135">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="88edd-136">ユーザーが Contoso 外の**Research**サイトでデジタルアセットを共有しようとすると、ユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="88edd-136">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="88edd-137">構成の詳細については、「[保持ラベルおよび DLP を使用して SharePoint Online ファイルを保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88edd-137">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="88edd-138">手順 4: サイトの Azure Information Protection サブラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="88edd-138">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="88edd-139">Contoso 管理者は、次のようなスコープ付きポリシーで、既定の**高機密**ラベルの**リサーチ**という新しい Azure Information Protection サブラベルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-139">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="88edd-140">暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="88edd-140">Requires encryption.</span></span>
- <span data-ttu-id="88edd-141">**リサーチメンバー**セキュリティグループのメンバーによるフルアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="88edd-141">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="88edd-142">**リサーチ閲覧**者セキュリティグループのメンバーによる読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="88edd-142">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="88edd-143">次に、Azure Information Protection クライアントを研究チームメンバーのデバイスに展開しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-143">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="88edd-144">構成の詳細については、「 [Azure Information Protection で SharePoint Online ファイルを保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88edd-144">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="88edd-145">非常に機密性の高い資産に対する**調査**サイトの構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88edd-145">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![非常に機密性の高い資産に対して、\* \* Research \* \* サイトの構成の結果として得られる構成](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="88edd-147">**リサーチ**サイトのフォルダー内のファイルは、次の方法で保護されます。</span><span class="sxs-lookup"><span data-stu-id="88edd-147">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="88edd-148">**Research** Azure Information Protection sublabel は、**リサーチ**サイトから移動またはコピーされたときに、ファイルと共に移動する各ファイルに暗号化と permssions を適用します。</span><span class="sxs-lookup"><span data-stu-id="88edd-148">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="88edd-149">**リサーチ**DLP ポリシー。非常に機密性の**高い**保持ラベルと、ファイルを外部ユーザーと共有できないようにする設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="88edd-149">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="88edd-150">サイトのアクセス許可のセット。 research-Admins セキュリティグループのメンバーには、リサーチ**メンバー**およびリサーチ**閲覧\*\*\*\*者**のセキュリティグループのメンバーへのアクセスのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="88edd-150">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="88edd-151">手順 5: オンプレミスの SharePoint リサーチデータを移行する</span><span class="sxs-lookup"><span data-stu-id="88edd-151">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="88edd-152">Contoso admins は、オンプレミスの SharePoint Server 2016 サイト内のすべてのオンプレミスの研究ファイルを新しい**research** sharepoint Online サイト内のフォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="88edd-152">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="88edd-153">手順 6: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="88edd-153">Step 6: Trained their users</span></span> 

<span data-ttu-id="88edd-154">Contoso のセキュリティスタッフは、次の手順を実行する必須コースで研究チームをトレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="88edd-154">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="88edd-155">新しい**Research** SharePoint Online サイトと既存のファイルにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88edd-155">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="88edd-156">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="88edd-156">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="88edd-157">DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="88edd-157">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="88edd-158">Azure Information Protection クライアントを使用し**てリサーチファイルにリサーチサブラベル**を付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88edd-158">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="88edd-159">サイトからリークが生じた場合でも、**リサーチ**サブラベルがファイルを保護する方法についてのデモ。</span><span class="sxs-lookup"><span data-stu-id="88edd-159">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="88edd-160">最終的には、セキュリティで保護された環境で研究者が組織全体で共同作業を行える安全な環境が得られます。</span><span class="sxs-lookup"><span data-stu-id="88edd-160">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="88edd-161">**Research サブラベル**を持つ research ドキュメントが**research**サイトから**漏洩した**場合、そのドキュメントは暗号化され、有効な資格情報を持つ research および**research**のセキュリティグループのメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="88edd-161">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="88edd-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="88edd-162">Next step</span></span>

<span data-ttu-id="88edd-163">[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="88edd-163">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

