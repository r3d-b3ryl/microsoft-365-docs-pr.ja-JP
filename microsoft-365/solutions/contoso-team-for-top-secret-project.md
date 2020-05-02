---
title: Contoso Corporation のトップシークレットプロジェクトの分離されたチーム
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社がトップシークレットプロジェクトのセキュリティ分離を備えたチームを使用して、新しいスイートの製品とサービスを開発する方法について説明します。'
ms.openlocfilehash: 2da51890001a2890b2d65bc6b71537b51c335eb4
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003213"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="2dad5-103">Contoso Corporation のトップシークレットプロジェクトの分離されたチーム</span><span class="sxs-lookup"><span data-stu-id="2dad5-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="2dad5-104">上級管理職がオフサイトになると、Contoso 社の CEO は、今後5年間で Contoso 社の利益を2倍にすることができる新しいスイートの製品とサービスの開発を命じました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="2dad5-105">ビジネス、エンジニアリング、マーケットプランを開発する最上位のプロジェクトは、 **Project 2x**という名前で、会社全体にわたる主なスタッフは recruited でした。</span><span class="sxs-lookup"><span data-stu-id="2dad5-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="2dad5-106">研究開発のタイムラインは厳しいものでした。つまり、共同作業を効率的に行い、セキュリティで保護された会議、継続的な会話、ファイルストレージを提供する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="2dad5-107">プロジェクト2X の結果として得られる成果物は、ビジネスプラン、製品とエンジニアリングの仕様、およびマーケティング資料とスケジュールが、Word、Excel、および PowerPoint のファイルの形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dad5-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="2dad5-108">機密情報のため、これらのファイルへのアクセスは次のようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="2dad5-109">プロジェクト2チームメンバーに制限されます。</span><span class="sxs-lookup"><span data-stu-id="2dad5-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="2dad5-110">セキュリティで保護されたフォルダーの外部でファイルが配布された場合でも、Project 2X のチームメンバーにのみアクセスを許可するためのアクセス許可で暗号化および保護されます。</span><span class="sxs-lookup"><span data-stu-id="2dad5-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="2dad5-111">Contoso IT スタッフは、Project 2X の[セキュリティ分離を備えたチーム](secure-teams-security-isolation.md)を使用して、これらの手順を実行していました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="2dad5-112">手順 1: プライベートチームを作成する</span><span class="sxs-lookup"><span data-stu-id="2dad5-112">Step 1: Created a private team</span></span>

<span data-ttu-id="2dad5-113">最初に、チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が[推奨する sharepoint アクセスポリシー](../enterprise/sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="2dad5-114">次に Contoso IT 管理者は、Project 2X という名前の新しいプライベートチームを作成し、Project 2X スタッフのユーザーアカウントをメンバーとして追加しました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="2dad5-115">構成の詳細については、「 [Create a private team](secure-teams-security-isolation.md#create-a-private-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dad5-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="2dad5-116">手順 2: Project 2X チームの機密ラベルを作成しました</span><span class="sxs-lookup"><span data-stu-id="2dad5-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="2dad5-117">Contoso admins は、 **Project 2x**という名前の新しい機密ラベルを作成しました。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2dad5-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="2dad5-118">暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="2dad5-118">Requires encryption.</span></span>
- <span data-ttu-id="2dad5-119">Project 2 の Microsoft 365 グループに対して共同編集権限を許可します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="2dad5-120">基になる Project 2X SharePoint サイトの [**ドキュメント**] セクションにあるファイルは、次の方法で保護されています。</span><span class="sxs-lookup"><span data-stu-id="2dad5-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="2dad5-121">サイトのアクセス許可。これは、Project 2X Microsoft 365 グループのメンバーにのみアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="2dad5-122">プロジェクトがサイトから移動またはコピーされた場合に、ファイルと共に送信される、暗号化とアクセス許可を持つ2つのプロジェクトの機密ラベル。</span><span class="sxs-lookup"><span data-stu-id="2dad5-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="2dad5-123">構成の詳細については、「 [Create a 機密ラベル](secure-teams-security-isolation.md#create-a-sensitivity-label)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dad5-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="2dad5-124">手順 3: 基になる SharePoint サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="2dad5-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="2dad5-125">最初に、チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が[推奨する sharepoint アクセスポリシー](../enterprise/sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="2dad5-126">次に、プロジェクト2X がサイトへのアクセスを共有しないようにするために、サイトの追加のアクセス許可設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="2dad5-127">構成の詳細については、「 [SharePoint の設定 (セキュリティの分離を使用したチーム向け](secure-teams-security-isolation.md#sharepoint-settings))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dad5-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="2dad5-128">プロジェクト2チームの最終的な構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-128">Here is the resulting configuration of the Project 2X team.</span></span>

![プロジェクト2チームの最終的な構成](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="2dad5-130">手順 4: トレーニングを受けた Project 2X チームメンバー</span><span class="sxs-lookup"><span data-stu-id="2dad5-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="2dad5-131">Contoso のセキュリティスタッフは、次の手順に従ってステップ実行する必須のコースで、Project 2X のチームメンバーをトレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="2dad5-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="2dad5-132">新しい Project 2X teams にアクセスする方法、会議とチャットを使用する方法、およびチームファイルで共同作業する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="2dad5-133">チーム内で新しいファイルを作成し、ローカルに作成された新しいファイルをアップロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="2dad5-134">DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。</span><span class="sxs-lookup"><span data-stu-id="2dad5-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="2dad5-135">Project 2X 機密ラベルを使用してファイルにラベルを付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="2dad5-136">プロジェクトの2つのラベルがチームを離れたときでもファイルを保護する方法についてのデモ。</span><span class="sxs-lookup"><span data-stu-id="2dad5-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="2dad5-137">最終的には、セキュリティで保護された環境で、Project 2X のチームメンバーがチャット、会議、およびファイルのセキュリティで保護された環境で共同作業を行うことができました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="2dad5-138">以下は、プロジェクト2x 機密ラベルが割り当てられた、基になる Project 2X サイトに保存されているファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="2dad5-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![基になる Project 2X サイトに保存されているファイルの例](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="2dad5-140">いくつかのインスタンスでは、Project 2X のチームメンバーは、オフライン作業のために Project 2X ラベルで保護されたファイルをローカルドライブにダウンロードしていました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="2dad5-141">ただし、資格情報を開くときに資格情報の入力を求められた後で、それらの間違いを認識して削除しました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="2dad5-142">Teams のグループ作業環境と Microsoft 365 のセキュリティ機能により、project 2X の詳細はプロジェクトの期間中に機密情報として保持されていました。</span><span class="sxs-lookup"><span data-stu-id="2dad5-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="2dad5-143">Contoso 社はプランを発表し、新しい製品とサービスを顧客や投資家の成功および競合他社の chagrin に展開する過程にあります。</span><span class="sxs-lookup"><span data-stu-id="2dad5-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="2dad5-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="2dad5-144">Next step</span></span>

<span data-ttu-id="2dad5-145">組織内で[セキュリティの分離を使用してチームを展開](secure-teams-security-isolation.md)します。</span><span class="sxs-lookup"><span data-stu-id="2dad5-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

