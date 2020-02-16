---
title: Contoso 社の極秘プロジェクトのチーム
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
description: '概要: Contoso 社がトップ機密プロジェクトの高度な規制データに対してチームを使用して、新しいスイートの製品とサービスを開発する方法について説明します。'
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068030"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="e8f97-103">Contoso 社の極秘プロジェクトのチーム</span><span class="sxs-lookup"><span data-stu-id="e8f97-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="e8f97-104">上級管理職がオフサイトになると、Contoso 社の CEO は、今後5年間で Contoso 社の利益を2倍にすることができる新しいスイートの製品とサービスの開発を命じました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="e8f97-105">ビジネス、エンジニアリング、マーケットプランを開発する最上位のプロジェクトは、 **Project 2x**という名前で、会社全体にわたる主なスタッフは recruited でした。</span><span class="sxs-lookup"><span data-stu-id="e8f97-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="e8f97-106">研究開発のタイムラインは厳しいものでした。つまり、共同作業を効率的に行い、セキュリティで保護された会議、継続的な会話、ファイルストレージを提供する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="e8f97-107">プロジェクト2X の結果として得られる成果物は、ビジネスプラン、製品とエンジニアリングの仕様、およびマーケティング資料とスケジュールが、Word、Excel、および PowerPoint のファイルの形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f97-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="e8f97-108">機密情報のため、これらのファイルへのアクセスは次のようになりました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="e8f97-109">プロジェクト2チームメンバーに制限されます。</span><span class="sxs-lookup"><span data-stu-id="e8f97-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="e8f97-110">データ損失防止 (DLP) ポリシーによって保護され、Project 2X チームメンバーがチーム外で共有できないようにします。</span><span class="sxs-lookup"><span data-stu-id="e8f97-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="e8f97-111">ファイルが Contoso 外に配布された場合でも、Project 2X のチームメンバーにのみアクセスを許可するためのアクセス許可によって暗号化および保護されます。</span><span class="sxs-lookup"><span data-stu-id="e8f97-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="e8f97-112">Contoso IT スタッフは、Project 2X の[高度な規制データにチーム](secure-teams-highly-regulated-data-scenario.md)を使用して、これらの手順を実行していました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="e8f97-113">手順 1: プライベートチームを作成し、基盤となる SharePoint サイトをロックした</span><span class="sxs-lookup"><span data-stu-id="e8f97-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="e8f97-114">チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が[推奨する sharepoint アクセスポリシー](sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="e8f97-115">次に Contoso IT 管理者は、Project 2X という名前の新しいプライベートチームを作成し、Project 2X スタッフのユーザーアカウントをメンバーとして追加しました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="e8f97-116">次に、プロジェクト2X がサイトへのアクセスを共有したり、他のユーザーがサイトへのアクセスを要求できないようにするために、サイトの追加のアクセス許可の設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="e8f97-117">構成の詳細については、「[高度な規制チームの SharePoint 設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f97-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="e8f97-118">手順 2: DLP ポリシーと、保持ラベルの基礎となるサイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="e8f97-119">最初に、Contoso 管理者は、Project 2X team の基礎となる SharePoint サイトの**ドキュメント**セクションに、既存の**非常に機密性の高い**Office 365 保持ラベルを適用しました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="e8f97-120">次に、 **Project 2x**という新しい OFFICE 365 DLP ポリシーを作成しました。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e8f97-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="e8f97-121">非常に機密性の高い Office 365 保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="e8f97-122">ユーザーが Contoso の外部のプロジェクト2X チーム内のファイルを共有しようとすると、ユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e8f97-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="e8f97-123">構成の詳細については、「[保持ラベルおよび DLP を使用した teams でファイルを保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f97-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="e8f97-124">手順 3: Project 2X チームの Office 365 機密ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="e8f97-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="e8f97-125">Contoso 管理者は、 **Project 2x**という名前の新しい Office 365 機密ラベルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="e8f97-126">暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8f97-126">Requires encryption.</span></span>
- <span data-ttu-id="e8f97-127">Project 2X Office 365 グループに対して共同編集権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="e8f97-128">プロジェクト2チームの最終的な構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-128">Here is the resulting configuration of the Project 2X team.</span></span>

![プロジェクト2チームの最終的な構成](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="e8f97-130">基になる Project 2X SharePoint サイトの [ドキュメント] セクションにあるファイルは、次の方法で保護されています。</span><span class="sxs-lookup"><span data-stu-id="e8f97-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="e8f97-131">サイトのアクセス許可。これは、Project 2X Office 365 グループのメンバーにのみアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="e8f97-132">新しいファイルに自動的に割り当てられる、高機密保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="e8f97-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="e8f97-133">高機密保持ラベルと、そのファイルを外部ユーザーと共有することをブロックする設定を使用する DLP ポリシー。</span><span class="sxs-lookup"><span data-stu-id="e8f97-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="e8f97-134">プロジェクトがサイトから移動またはコピーされた場合に、ファイルと共に送信される、暗号化とアクセス許可を持つ2つのプロジェクトの機密ラベル。</span><span class="sxs-lookup"><span data-stu-id="e8f97-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="e8f97-135">ここでは、基本となる Project 2X サイトに保存されているファイルのうち、高度な規制保持ラベルと Project 2X 機密ラベルが割り当てられているファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![基になる Project 2X サイトに保存されているファイルの例](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="e8f97-137">手順 4: トレーニングを受けた Project 2X チームメンバー</span><span class="sxs-lookup"><span data-stu-id="e8f97-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="e8f97-138">Contoso のセキュリティスタッフは、次の手順に従ってステップ実行する必須のコースで、Project 2X のチームメンバーをトレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="e8f97-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="e8f97-139">新しい Project 2X teams にアクセスする方法、会議とチャットを使用する方法、およびチームファイルで共同作業する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="e8f97-140">チーム内で新しいファイルを作成し、ローカルに作成された新しいファイルをアップロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="e8f97-141">DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="e8f97-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="e8f97-142">Project 2X 機密ラベルを使用してファイルにラベルを付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8f97-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="e8f97-143">プロジェクトの2つのラベルがチームを離れたときでもファイルを保護する方法についてのデモ。</span><span class="sxs-lookup"><span data-stu-id="e8f97-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="e8f97-144">最終的には、セキュリティで保護された環境で、Project 2X のチームメンバーがチャット、会議、およびファイルのセキュリティで保護された環境で共同作業を行うことができました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="e8f97-145">いくつかのインスタンスでは、Project 2X のチームメンバーは、オフライン作業のために Project 2X ラベルで保護されたファイルをローカルドライブにダウンロードしていました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="e8f97-146">ただし、資格情報を開くときに資格情報の入力を求められた後で、それらの間違いを認識して削除しました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="e8f97-147">Teams のグループ作業環境と Microsoft 365 のセキュリティ機能により、project 2X の詳細はプロジェクトの期間中に機密情報として保持されていました。</span><span class="sxs-lookup"><span data-stu-id="e8f97-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="e8f97-148">Contoso 社はプランを発表し、新しい製品とサービスを顧客や投資家の成功および競合他社の chagrin に展開する過程にあります。</span><span class="sxs-lookup"><span data-stu-id="e8f97-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8f97-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="e8f97-149">Next step</span></span>

<span data-ttu-id="e8f97-150">[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="e8f97-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8f97-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8f97-151">See also</span></span>

<span data-ttu-id="e8f97-152">[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="e8f97-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
