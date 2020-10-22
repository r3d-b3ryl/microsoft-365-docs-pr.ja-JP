---
title: Contoso Corporation のトップシークレットプロジェクトの分離されたチーム
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社がトップシークレットプロジェクトのセキュリティ分離を備えたチームを使用して、新しいスイートの製品とサービスを開発する方法について説明します。'
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656071"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="e398c-103">Contoso Corporation のトップシークレットプロジェクトの分離されたチーム</span><span class="sxs-lookup"><span data-stu-id="e398c-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="e398c-104">上級管理職がオフサイトになると、Contoso 社の CEO は、今後5年間で Contoso 社の利益を2倍にすることができる新しいスイートの製品とサービスの開発を命じました。</span><span class="sxs-lookup"><span data-stu-id="e398c-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="e398c-105">ビジネス、エンジニアリング、マーケットプランを開発する最上位のプロジェクトは、 **Project 2x** という名前で、会社全体にわたる主なスタッフは recruited でした。</span><span class="sxs-lookup"><span data-stu-id="e398c-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="e398c-106">研究開発のタイムラインは厳しいものでした。つまり、共同作業を効率的に行い、セキュリティで保護された会議、継続的な会話、ファイルストレージを提供する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="e398c-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="e398c-107">プロジェクト2X の結果として得られる成果物は、ビジネスプラン、製品とエンジニアリングの仕様、およびマーケティング資料とスケジュールが、Word、Excel、および PowerPoint のファイルの形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e398c-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="e398c-108">機密情報のため、これらのファイルへのアクセスは次のようになりました。</span><span class="sxs-lookup"><span data-stu-id="e398c-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="e398c-109">プロジェクト2チームメンバーおよびシニアリーダーシップに制限されています。</span><span class="sxs-lookup"><span data-stu-id="e398c-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="e398c-110">セキュリティで保護されたフォルダーの外部でファイルが配布された場合でも、プロジェクト2X のチームメンバーおよびシニアリーダーシップにのみアクセスできるようにするためのアクセス許可によって暗号化および保護されます。</span><span class="sxs-lookup"><span data-stu-id="e398c-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="e398c-111">Contoso IT スタッフは、Project 2X の [セキュリティ分離を備えたチーム](secure-teams-security-isolation.md) を使用して、これらの手順を実行していました。</span><span class="sxs-lookup"><span data-stu-id="e398c-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="e398c-112">手順 1: プライベートチームを作成する</span><span class="sxs-lookup"><span data-stu-id="e398c-112">Step 1: Created a private team</span></span>

<span data-ttu-id="e398c-113">最初に、チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が [推奨する sharepoint アクセスポリシー](../security/office-365-security/sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="e398c-114">次に Contoso IT 管理者は、Project 2X という名前の新しいプライベートチームを作成し、Project 2X スタッフのユーザーアカウントをメンバーとして追加しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="e398c-115">また、Project 2X チームの所有者のみがプライベートチャネルを作成できるように、チームを構成しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="e398c-116">構成の詳細については、「 [Create a private team](secure-teams-security-isolation.md#create-a-private-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e398c-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="e398c-117">手順 2: Project 2X チームの機密ラベルを作成しました</span><span class="sxs-lookup"><span data-stu-id="e398c-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="e398c-118">Contoso admins は、 **Project 2x** という名前の新しい機密ラベルを作成しました。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e398c-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="e398c-119">暗号化を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="e398c-119">Enabled encryption.</span></span>
- <span data-ttu-id="e398c-120">Project 2X Microsoft 365 グループのアクセス許可 Co-Author 許可されます。</span><span class="sxs-lookup"><span data-stu-id="e398c-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="e398c-121">上級指導者グループに対して許可されたビューアーのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="e398c-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="e398c-122">非管理対象デバイスへのアクセスをブロックしました。</span><span class="sxs-lookup"><span data-stu-id="e398c-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="e398c-123">基になる Project 2X SharePoint サイトの [ **ドキュメント** ] セクションにあるファイルは、次の方法で保護されています。</span><span class="sxs-lookup"><span data-stu-id="e398c-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="e398c-124">サイトのアクセス許可。これは、Project 2X Microsoft 365 グループのメンバーに対する完全なアクセス許可と、シニアリーダーシップグループに対する読み取りアクセス許可のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="e398c-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="e398c-125">プロジェクトがサイトから移動またはコピーされた場合に、ファイルと共に送信される、暗号化とアクセス許可を持つ2つのプロジェクトの機密ラベル。</span><span class="sxs-lookup"><span data-stu-id="e398c-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="e398c-126">構成の詳細については、「 [Create a 機密ラベル](secure-teams-security-isolation.md#create-a-sensitivity-label)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e398c-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="e398c-127">手順 3: 基になる SharePoint サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="e398c-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="e398c-128">最初に、チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が [推奨する sharepoint アクセスポリシー](../security/office-365-security/sharepoint-file-access-policies.md)を構成しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="e398c-129">次に、サイトに対する追加のアクセス許可の設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="e398c-130">Project 2X グループのメンバーがサイトへのアクセスを共有できないようにする。</span><span class="sxs-lookup"><span data-stu-id="e398c-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="e398c-131">構成の詳細については、「 [SharePoint の設定 (セキュリティの分離を使用したチーム向け](secure-teams-security-isolation.md#sharepoint-settings))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e398c-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="e398c-132">上級リーダーシップグループの読み取りアクセス許可について。</span><span class="sxs-lookup"><span data-stu-id="e398c-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="e398c-133">次に、Project 2X グループのメンバーがサイトへのアクセスを共有できないようにするために、サイトの追加のアクセス許可設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="e398c-134">プロジェクト2X のプライベートチャネルが作成されると、グループの所有者はゲスト共有を無効にし、既定の共有リンクを **特定のユーザー** の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="e398c-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="e398c-135">以下に、セキュリティ分離を使用した Project 2X チームの構成結果を示します。</span><span class="sxs-lookup"><span data-stu-id="e398c-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![プロジェクト2チームの最終的な構成](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="e398c-137">手順 4: トレーニングを受けた Project 2X チームメンバー</span><span class="sxs-lookup"><span data-stu-id="e398c-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="e398c-138">Contoso のセキュリティスタッフは、次の手順に従ってステップ実行する必須のコースで、Project 2X のチームメンバーをトレーニングしています。</span><span class="sxs-lookup"><span data-stu-id="e398c-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="e398c-139">新しい Project 2X teams にアクセスする方法、会議とチャットを使用する方法、およびチームファイルで共同作業する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e398c-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="e398c-140">チーム内で新しいファイルを作成し、ローカルに作成された新しいファイルをアップロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e398c-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="e398c-141">Project 2X 機密ラベルを使用してファイルにラベルを付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e398c-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="e398c-142">プロジェクトの2つのラベルがチームを離れたときでもファイルを保護する方法についてのデモ。</span><span class="sxs-lookup"><span data-stu-id="e398c-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="e398c-143">最終的には、セキュリティで保護された環境で、Project 2X のチームメンバーがチャット、会議、およびファイルのセキュリティで保護された環境で共同作業を行うことができました。</span><span class="sxs-lookup"><span data-stu-id="e398c-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="e398c-144">以下は、プロジェクト2x 機密ラベルが割り当てられた、基になる Project 2X サイトに保存されているファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="e398c-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![基になる Project 2X サイトに保存されているファイルの例](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="e398c-146">いくつかのインスタンスでは、Project 2X のチームメンバーは、オフライン作業のために Project 2X ラベルで保護されたファイルをローカルドライブにダウンロードしていました。</span><span class="sxs-lookup"><span data-stu-id="e398c-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="e398c-147">ただし、資格情報を開くときに資格情報の入力を求められた後で、それらの間違いを認識して削除しました。</span><span class="sxs-lookup"><span data-stu-id="e398c-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="e398c-148">Teams のグループ作業環境と Microsoft 365 のセキュリティ機能により、project 2X の詳細はプロジェクトの期間中に機密情報として保持されていました。</span><span class="sxs-lookup"><span data-stu-id="e398c-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="e398c-149">Contoso 社はプランを発表し、新しい製品とサービスを顧客や投資家の成功および競合他社の chagrin に展開する過程にあります。</span><span class="sxs-lookup"><span data-stu-id="e398c-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="e398c-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="e398c-150">Next step</span></span>

<span data-ttu-id="e398c-151">組織内で[セキュリティの分離を使用してチームを展開](secure-teams-security-isolation.md)します。</span><span class="sxs-lookup"><span data-stu-id="e398c-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

