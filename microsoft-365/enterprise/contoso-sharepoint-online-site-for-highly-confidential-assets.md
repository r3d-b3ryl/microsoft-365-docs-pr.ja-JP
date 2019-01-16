---
title: コントソ株式会社のデジタル資産の機密性の高い SharePoint Online サイト
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: '概要: contoso 社が高度の SharePoint Online サイトを実装する方法の研究の間で簡単に共同作業のための規制対象のデータがチームです。'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869590"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="52af4-103">コントソ株式会社のデジタル資産の機密性の高い SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="52af4-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="52af4-104">**の概要:** Contoso 社の研究チームの間で簡単に共同作業のための規制の厳しいデータを SharePoint Online サイトの実装方法です。</span><span class="sxs-lookup"><span data-stu-id="52af4-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="52af4-p101">Contoso 社の最も貴重な資産はある知的財産が企業秘密は、独自の製造技術などの形で、設計、開発中の製品仕様サーバー 2016 の SharePoint サイト上のファイルとして保存された元のデジタル形式では、これらの資産です。Contoso 社では、Microsoft 365 エンタープライズを展開するときパリ、モスクワ、ニューヨーク、北京、バンガロールに研究チーム間で、設置型のデジタル資産を簡単にアクセスしより多くのコラボレーションのクラウドに移行するつもりでした。</span><span class="sxs-lookup"><span data-stu-id="52af4-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="52af4-108">ただし、その機密性のためこれらのファイルへのアクセスを必要があります。</span><span class="sxs-lookup"><span data-stu-id="52af4-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="52af4-109">表示または SharePoint 管理者によってのみ管理サイトの継続的なアクセス許可を使用して、変更を許可されているユーザーのセットに制限されています。</span><span class="sxs-lookup"><span data-stu-id="52af4-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="52af4-110">データ損失防止 (DLP) ユーザーがサイトの外部に配布することを防ぐために保護されています。</span><span class="sxs-lookup"><span data-stu-id="52af4-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="52af4-111">暗号化され保護されているアクセスは、サイトの外部ユーザーに配布されている場合でも、その内容にアクセスする権限のないユーザーを防ぐためにリストを制御します。</span><span class="sxs-lookup"><span data-stu-id="52af4-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="52af4-112">Contoso 社のセキュリティと SharePoint の管理者の IT 部門は[の SharePoint Online サイト規制の厳しいデータ](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することにしました。</span><span class="sxs-lookup"><span data-stu-id="52af4-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="52af4-113">Contoso 社では、次の手順を使用して作成し、研究チームの SharePoint Online のチーム サイトをセキュリティで保護されました。</span><span class="sxs-lookup"><span data-stu-id="52af4-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="52af4-114">手順 1: レビューし、研究チームのグループのメンバーを確認</span><span class="sxs-lookup"><span data-stu-id="52af4-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="52af4-p102">Contoso の IT 管理者は、研究チームのセキュリティ グループのセットのレビューを実行します。これらの削除人が、研究者または研究資産へのアクセスを必要はありませんでした。</span><span class="sxs-lookup"><span data-stu-id="52af4-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="52af4-117">これらの新しいセキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="52af4-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="52af4-118">**研究管理者** 一連のアクセス許可を変更する機能を含め、サイトに対するフル コントロールを持つ SharePoint 管理者です。</span><span class="sxs-lookup"><span data-stu-id="52af4-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="52af4-119">**研究メンバー** 研究チームが世界中のセキュリティ グループのセット。</span><span class="sxs-lookup"><span data-stu-id="52af4-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="52af4-120">**視聴者の調査** サイトに、アセットを表示することができる研究組織の経営幹部などの管理のユーザーのセットです。</span><span class="sxs-lookup"><span data-stu-id="52af4-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="52af4-121">手順 2: SharePoint Online の分離のチーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="52af4-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="52af4-p103">Contoso 社の SharePoint 管理者が最初に作成された新しいチーム サイトでは、**研究**という名前です。それらをし、構成します。</span><span class="sxs-lookup"><span data-stu-id="52af4-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="52af4-124">**研究 Admins**セキュリティ グループをメンバーとしての研究の所有者 SharePoint グループを使用するのにはフル コントロール アクセス許可のレベル</span><span class="sxs-lookup"><span data-stu-id="52af4-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="52af4-125">編集アクセス許可のレベル、メンバーとして、**研究メンバー**のセキュリティ グループを持っている研究のメンバー SharePoint グループを使用するには</span><span class="sxs-lookup"><span data-stu-id="52af4-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="52af4-126">**リサーチ ビューアー**のセキュリティ グループをメンバーとして、研究の訪問者の SharePoint グループを使用するのには読み取りアクセス許可のレベル</span><span class="sxs-lookup"><span data-stu-id="52af4-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="52af4-127">結果の SharePoint アクセス許可レベル、SharePoint グループ、およびそのメンバーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="52af4-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="52af4-128">次に、これらのサイトの追加の制限を構成します。</span><span class="sxs-lookup"><span data-stu-id="52af4-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="52af4-129">構成の詳細については、[分離のオンラインの SharePoint チーム サイトの展開](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52af4-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="52af4-130">手順 3: 制限された Office 365 ラベル DLP ポリシーについては、サイトの構成</span><span class="sxs-lookup"><span data-stu-id="52af4-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="52af4-131">まず、Contoso の管理者では、**リサーチ**サイトに**機密性の高い**Office 365 のラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="52af4-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="52af4-132">新しいを作成する次に、Office 365 の DLP ポリシーという名前の**研究**。</span><span class="sxs-lookup"><span data-stu-id="52af4-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="52af4-133">**機密性の高い**Office 365 のラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="52af4-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="52af4-134">**リサーチ**サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="52af4-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="52af4-135">ドキュメントを共有できないようにします。</span><span class="sxs-lookup"><span data-stu-id="52af4-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="52af4-136">構成の詳細については、 [Office 365 のラベルと DLP を SharePoint Online を保護するためのファイル](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52af4-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="52af4-137">ステップ 4: サイトの情報保護の Azure サブ ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="52af4-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="52af4-138">Azure の情報保護のサブの新しいラベルを作成した Contoso 管理者という名前のスコープ指定ポリシーの既定の**機密度の高い**ラベルの**研究**。</span><span class="sxs-lookup"><span data-stu-id="52af4-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="52af4-139">暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="52af4-139">Requires encryption.</span></span>
- <span data-ttu-id="52af4-140">**研究メンバー**のセキュリティ グループのメンバーが完全にアクセスをできます。</span><span class="sxs-lookup"><span data-stu-id="52af4-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="52af4-141">**研究のあるユーザー**のセキュリティ グループのメンバーでの読み取りアクセスを許可するには。</span><span class="sxs-lookup"><span data-stu-id="52af4-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="52af4-142">次に、研究チームのメンバーのデバイスへの Azure の情報保護のクライアントが展開されました。</span><span class="sxs-lookup"><span data-stu-id="52af4-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="52af4-143">構成の詳細については、 [Azure の情報保護を保護するための SharePoint Online ファイル](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52af4-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="52af4-144">ここでは、機密性の高い資産の**リサーチ**サイトの結果として得られる構成です。</span><span class="sxs-lookup"><span data-stu-id="52af4-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="52af4-145">手順 5: は、設置型の SharePoint の研究データを移行します。</span><span class="sxs-lookup"><span data-stu-id="52af4-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="52af4-146">Contoso の管理者は、施設内でのすべての調査**研究**の SharePoint Online サイトにフォルダーを設置型の SharePoint サーバーの 2016年サイト内のファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="52af4-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="52af4-147">手順 6: ユーザーのトレーニング</span><span class="sxs-lookup"><span data-stu-id="52af4-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="52af4-148">Contoso 社のセキュリティ スタッフには、必須のコースを使用してステップ実行での調査チームがトレーニングを受けた。</span><span class="sxs-lookup"><span data-stu-id="52af4-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="52af4-149">新しい**研究**SharePoint Online サイトとその既存のファイルにアクセスする方法です。</span><span class="sxs-lookup"><span data-stu-id="52af4-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="52af4-150">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="52af4-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="52af4-151">DLP ポリシーが外部で共有されているファイルをブロックする方法のデモンストレーションです。</span><span class="sxs-lookup"><span data-stu-id="52af4-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="52af4-152">Azure 情報保護クライアントを使用して、調査**研究**サブ ラベル ファイルにラベルを付ける方法です。</span><span class="sxs-lookup"><span data-stu-id="52af4-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="52af4-153">方法のデモ**研究**サブのラベルは、サイトからリークしている場合でもにファイルを保護します。</span><span class="sxs-lookup"><span data-stu-id="52af4-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="52af4-154">最終的な結果は、セキュリティで保護された環境、研究者がセキュリティで保護された環境で組織全体にわたる共同作業が可能です。</span><span class="sxs-lookup"><span data-stu-id="52af4-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="52af4-155">**研究**サブのラベルを持つ研究文書がリーク**研究**サイトから、暗号化され、有効な資格情報の**リサーチ メンバー**および**研究のあるユーザー**のセキュリティ グループのメンバーだけにアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="52af4-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="52af4-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="52af4-156">Next step</span></span>

<span data-ttu-id="52af4-157">組織に Microsoft 365 Enterprise を[展開](deploy-microsoft-365-enterprise.md)します。</span><span class="sxs-lookup"><span data-stu-id="52af4-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

