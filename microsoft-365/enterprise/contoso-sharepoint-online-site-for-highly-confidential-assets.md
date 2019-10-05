---
title: Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint サイト
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: 研究チーム間の共同作業を容易にするために、Contoso 社が非常に規制されたデータに対して SharePoint サイトを実装した方法を示します。'
ms.openlocfilehash: bb3c178ee64d5925f82aef9887c06ceafe51f4ee
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403228"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="a0ae2-103">Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="a0ae2-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="a0ae2-104">**概要:** 研究チーム間のコラボレーションを容易にするために、Contoso 社が高度な規制データ用の SharePoint サイトを実装しています。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-104">**Summary:** How Contoso implemented a SharePoint site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="a0ae2-105">Contoso 社の最も重要な資産は、独自の製造手法、開発中の製品の設計仕様など、企業秘密の形式での知的財産です。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="a0ae2-106">これらのアセットはデジタル形式で、もともとは SharePoint Server 2016 サイトにファイルとして保存されていました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-106">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="a0ae2-107">Contoso 社では、Microsoft 365 Enterprise を展開したときに、オンプレミスのデジタルアセットをクラウドに移行して、パリ、モスクワ、ニューヨーク、北京、Bangalore の研究チーム間で簡単にアクセスできるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="a0ae2-108">ただし、機密性の高い性質上、これらのファイルへのアクセスは次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="a0ae2-109">アクセスが許可されているユーザーのセットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-109">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="a0ae2-110">データ損失防止 (DLP) ポリシーで保護され、ユーザーがサイト外に配布することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-110">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="a0ae2-111">アクセス許可を使用して保護され、権限のないユーザーがサイト外に配布されている場合でも、そのコンテンツにアクセスするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-111">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="a0ae2-112">Contoso 社の IT 部門のセキュリティおよび SharePoint 管理者は、[高度な規制データ用に sharepoint サイト](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="a0ae2-113">Contoso 社は、これらの手順を使用して、調査チームのために SharePoint チームサイトを作成してセキュリティ保護しています。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-113">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="a0ae2-114">手順 1: プライベート SharePoint チームサイトを作成する</span><span class="sxs-lookup"><span data-stu-id="a0ae2-114">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="a0ae2-115">SharePoint サイトへのアクセスを保護するために、Contoso 社は推奨される[sharepoint アクセスポリシー](sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-115">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="a0ae2-116">次に Contoso IT 管理者は、パリ、モスクワ、ニューヨーク、北京、Bangalore オフィスの研究者のユーザーアカウントの一覧をコンパイルしていました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-116">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="a0ae2-117">次に、Contoso IT 管理者は**Research**という名前の新しいプライベートチームサイトを作成し、その研究者のすべてのユーザーアカウントを追加しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-117">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="a0ae2-118">その後、調査者がサイトへのアクセスを共有したり、研究者以外がサイトへのアクセスを要求したりできないように、サイトの追加のアクセス許可設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-118">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="a0ae2-119">手順 2: 制限付き DLP ポリシー用にサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="a0ae2-119">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="a0ae2-120">最初に、Contoso 管理者は、**リサーチ**サイトの Documents フォルダーに既存の**高機密**Office 365 保持ラベルを適用しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-120">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="a0ae2-121">次に、 **Research**という名前の新しい OFFICE 365 DLP ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-121">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="a0ae2-122">非常に**機密性の高い**Office 365 保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-122">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="a0ae2-123">ユーザーが Contoso 外の**Research**サイトでデジタルアセットを共有しようとすると、ユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-123">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="a0ae2-124">構成の詳細については、「 [SharePoint ファイルを保持ラベルおよび DLP で保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-124">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="a0ae2-125">手順 4: サイト用の Office 365 機密 sublabel を作成する</span><span class="sxs-lookup"><span data-stu-id="a0ae2-125">Step 4: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="a0ae2-126">Contoso 管理者は、次のような**高機密**ラベルの**研究チーム**という名前の新しい Office 365 機密 sublabel を作成しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-126">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="a0ae2-127">暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-127">Requires encryption.</span></span>
- <span data-ttu-id="a0ae2-128">**リサーチ**Office 365 グループに対して共同編集者の権限を許可する</span><span class="sxs-lookup"><span data-stu-id="a0ae2-128">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="a0ae2-129">**Research** Office 365 グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-129">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="a0ae2-130">以下は、非常に機密性の高い資産を対象とした**研究**チームサイトの構成結果です。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-130">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![非常に機密性の高い資産を検索するための研究チームサイトの構成結果。](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="a0ae2-132">**リサーチ**サイトのフォルダー内のファイルは、次の方法で保護されます。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-132">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="a0ae2-133">サイトのアクセス許可。 **Research** Office 365 グループのメンバーにのみアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-133">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="a0ae2-134">**リサーチ**DLP ポリシー。**高機密**保持ラベルと、ファイルを外部ユーザーと共有できないようにする設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-134">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="a0ae2-135">**研究サイトから**移動またはコピーされた場合に、ファイルと共に移動する暗号化とアクセス許可を持つ、**調査チーム**の感度 sublabel。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-135">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="a0ae2-136">**Research サイトに**保存されているファイルの例として、 **research Teams**の感度 sublabel が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-136">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![非常に機密性の高い資産を検索するための研究チームサイトの構成結果。](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="a0ae2-138">手順 5: オンプレミスの SharePoint リサーチデータを移行する</span><span class="sxs-lookup"><span data-stu-id="a0ae2-138">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="a0ae2-139">Contoso admins は、オンプレミスの SharePoint Server 2016 サイト内のすべてのオンプレミスの研究ファイルを新しい**research** sharepoint サイト内のフォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-139">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-6-trained-their-researchers"></a><span data-ttu-id="a0ae2-140">手順 6: 自分の研究者をトレーニングする</span><span class="sxs-lookup"><span data-stu-id="a0ae2-140">Step 6: Trained their researchers</span></span>

<span data-ttu-id="a0ae2-141">Contoso のセキュリティスタッフは、 **Research** Office 365 グループのメンバーに、次の手順に従ってステップインした必須コースをトレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-141">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="a0ae2-142">新しい**リサーチ**サイトとその既存のファイルにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-142">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="a0ae2-143">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-143">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="a0ae2-144">**リサーチ**DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-144">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="a0ae2-145">**リサーチ Teams**の感度 sublabel でファイルにラベルを付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-145">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="a0ae2-146">サイトからリークが生じた場合でも、 **Research Teams**のサブラベルがファイルを保護する方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-146">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="a0ae2-147">最終的には、研究情報が含まれるファイルのセキュリティで保護された環境で、研究者が Contoso を越えて共同作業を行うことのできる安全な環境が得られます。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-147">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="a0ae2-148">Research **Teams**を使用した research ドキュメントが**research**サイトを離れた場合、その sublabel は暗号化され、有効なユーザーアカウントの資格情報を持つ**research** Office 365 グループのメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-148">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 groups with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="a0ae2-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="a0ae2-149">Next step</span></span>

<span data-ttu-id="a0ae2-150">[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="a0ae2-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0ae2-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0ae2-151">See also</span></span>

<span data-ttu-id="a0ae2-152">[Microsoft 365 プロダクティビティライブラリ](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="a0ae2-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
