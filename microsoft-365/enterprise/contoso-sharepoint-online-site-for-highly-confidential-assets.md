---
title: Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint サイト
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: 研究チーム間の共同作業を容易にするために、Contoso 社が非常に規制されたデータに対して SharePoint サイトを実装した方法を示します。'
ms.openlocfilehash: 0a4bc2f685cf015611da62ebbed000218f37f31e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634254"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="a98a6-103">Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="a98a6-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="a98a6-104">Contoso 社の最も重要な資産は、独自の製造手法、開発中の製品の設計仕様など、企業秘密の形式での知的財産です。</span><span class="sxs-lookup"><span data-stu-id="a98a6-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="a98a6-105">これらのアセットはデジタル形式で、もともとは SharePoint Server 2016 サイトにファイルとして保存されていました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="a98a6-106">Contoso 社では、Microsoft 365 Enterprise を展開したときに、オンプレミスのデジタルアセットをクラウドに移行して、パリ、モスクワ、ニューヨーク、北京、Bangalore の研究チーム間で簡単にアクセスできるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="a98a6-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="a98a6-107">ただし、機密性の高い性質上、これらのファイルへのアクセスは次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a98a6-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="a98a6-108">アクセスが許可されているユーザーのセットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="a98a6-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="a98a6-109">データ損失防止 (DLP) ポリシーで保護され、ユーザーがサイト外に配布することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="a98a6-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="a98a6-110">アクセス許可を使用して保護され、権限のないユーザーがサイト外に配布されている場合でも、そのコンテンツにアクセスするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="a98a6-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="a98a6-111">Contoso 社の IT 部門のセキュリティおよび SharePoint 管理者は、[高度な規制データ用に sharepoint サイト](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="a98a6-112">Contoso 社は、これらの手順を使用して、調査チームのために SharePoint チームサイトを作成してセキュリティ保護しています。</span><span class="sxs-lookup"><span data-stu-id="a98a6-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="a98a6-113">手順 1: プライベート SharePoint チームサイトを作成する</span><span class="sxs-lookup"><span data-stu-id="a98a6-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="a98a6-114">SharePoint サイトへのアクセスを保護するために、Contoso 社は推奨される[sharepoint アクセスポリシー](sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="a98a6-115">次に Contoso IT 管理者は、パリ、モスクワ、ニューヨーク、北京、Bangalore オフィスの研究者のユーザーアカウントの一覧をコンパイルしていました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="a98a6-116">次に、Contoso IT 管理者は**Research**という名前の新しいプライベートチームサイトを作成し、その研究者のすべてのユーザーアカウントを追加しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="a98a6-117">その後、調査者がサイトへのアクセスを共有したり、研究者以外がサイトへのアクセスを要求したりできないように、サイトの追加のアクセス許可設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="a98a6-118">手順 2: 制限付き DLP ポリシー用にサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="a98a6-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="a98a6-119">最初に、Contoso 管理者は、既存の**高機密**保持ラベルを**Research**サイトのドキュメントフォルダーに適用しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="a98a6-120">次に、 **Research**という名前の新しい DLP ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-120">Next, they created a new DLP policy named **Research** that:</span></span>

- <span data-ttu-id="a98a6-121">**高機密**保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a98a6-121">Uses the **Highly Confidential** retention label.</span></span> 
- <span data-ttu-id="a98a6-122">ユーザーが Contoso 外の**Research**サイトでデジタルアセットを共有しようとすると、ユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a98a6-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="a98a6-123">構成の詳細については、「 [SharePoint ファイルを保持ラベルおよび DLP で保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a98a6-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="a98a6-124">手順 3: サイトの機密 sublabel を作成する</span><span class="sxs-lookup"><span data-stu-id="a98a6-124">Step 3: Created a sensitivity sublabel for the site</span></span>

<span data-ttu-id="a98a6-125">Contoso 管理者は、次のような**高機密**ラベルの**研究チーム**という名前の新しい機密 sublabel を作成しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-125">Contoso admins created a new sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="a98a6-126">暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="a98a6-126">Requires encryption.</span></span>
- <span data-ttu-id="a98a6-127">**リサーチ**Microsoft 365 グループに対して共同編集者の権限を許可する</span><span class="sxs-lookup"><span data-stu-id="a98a6-127">Allows Co-Author permissions for the **Research** Microsoft 365 group</span></span>
- <span data-ttu-id="a98a6-128">**Research** Microsoft 365 グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a98a6-128">Applies to the **Research** Microsoft 365 group</span></span>

<span data-ttu-id="a98a6-129">以下は、非常に機密性の高い資産を対象とした**研究**チームサイトの構成結果です。</span><span class="sxs-lookup"><span data-stu-id="a98a6-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![非常に機密性の高い資産を検索するための研究チームサイトの構成結果。](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="a98a6-131">**リサーチ**サイトのフォルダー内のファイルは、次の方法で保護されます。</span><span class="sxs-lookup"><span data-stu-id="a98a6-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="a98a6-132">サイト権限。 **Research** Microsoft 365 グループのメンバーにのみアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="a98a6-132">The site permissions, which only allow access to members of the **Research** Microsoft 365 group.</span></span>
- <span data-ttu-id="a98a6-133">**リサーチ**DLP ポリシー。**高機密**保持ラベルと、ファイルを外部ユーザーと共有できないようにする設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a98a6-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="a98a6-134">**研究サイトから**移動またはコピーされた場合に、ファイルと共に移動する暗号化とアクセス許可を持つ、**調査チーム**の感度 sublabel。</span><span class="sxs-lookup"><span data-stu-id="a98a6-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="a98a6-135">**Research サイトに**保存されているファイルの例として、 **research Teams**の感度 sublabel が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="a98a6-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![非常に機密性の高い資産を検索するための研究チームサイトの構成結果。](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="a98a6-137">手順 4: オンプレミスの SharePoint リサーチデータを移行する</span><span class="sxs-lookup"><span data-stu-id="a98a6-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="a98a6-138">Contoso admins は、オンプレミスの SharePoint Server 2016 サイト内のすべてのオンプレミスの研究ファイルを新しい**research** sharepoint サイト内のフォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="a98a6-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="a98a6-139">手順 5: 自分の研究者をトレーニングする</span><span class="sxs-lookup"><span data-stu-id="a98a6-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="a98a6-140">Contoso のセキュリティスタッフは、次に示す必須のコースで、 **Research** Microsoft 365 グループのメンバーをトレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="a98a6-140">Contoso security staff trained the members of the **Research** Microsoft 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="a98a6-141">新しい**リサーチ**サイトとその既存のファイルにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a98a6-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="a98a6-142">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="a98a6-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="a98a6-143">**リサーチ**DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="a98a6-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="a98a6-144">**リサーチ Teams**の感度 sublabel でファイルにラベルを付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a98a6-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="a98a6-145">サイトからリークが生じた場合でも、 **Research Teams**のサブラベルがファイルを保護する方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="a98a6-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="a98a6-146">最終的には、研究情報が含まれるファイルのセキュリティで保護された環境で、研究者が Contoso を越えて共同作業を行うことのできる安全な環境が得られます。</span><span class="sxs-lookup"><span data-stu-id="a98a6-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="a98a6-147">Research **Teams**を使用した research ドキュメントが**research**サイトを離れた場合、sublabel は暗号化され、有効なユーザーアカウントの資格情報を持つ**research** Microsoft 365 グループのメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a98a6-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Microsoft 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="a98a6-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="a98a6-148">Next step</span></span>

<span data-ttu-id="a98a6-149">[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="a98a6-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="a98a6-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="a98a6-150">See also</span></span>

<span data-ttu-id="a98a6-151">[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="a98a6-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
