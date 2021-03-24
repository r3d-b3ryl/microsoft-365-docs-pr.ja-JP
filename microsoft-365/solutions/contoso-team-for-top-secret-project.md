---
title: Contoso Corporation のトップシークレット プロジェクトの分離チーム
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
description: '概要: Contoso 社は、トップシークレット プロジェクトのセキュリティ分離を持つチームを使用して、新しい製品とサービスのスイートを開発する方法について説明します。'
ms.openlocfilehash: d5ab2808251ff6a53f8975ea868431691d3301e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051008"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="1c77c-103">Contoso Corporation のトップシークレット プロジェクトの分離チーム</span><span class="sxs-lookup"><span data-stu-id="1c77c-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="1c77c-104">エグゼクティブ オフサイトの後、Contoso の CEO は、次の 5 年間で Contoso の利益を倍増できる新しい製品とサービスの開発を命じた。</span><span class="sxs-lookup"><span data-stu-id="1c77c-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="1c77c-105">ビジネス、エンジニアリング、および市場計画を開発するトップ シークレット プロジェクトは **Project 2X** と名付け、会社全体の主要なスタッフが採用されました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="1c77c-106">研究開発のスケジュールは厳しく、共同作業を効率的に行い、安全な会議、継続的な会話、ファイルストレージを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c77c-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="1c77c-107">Project 2X の成果物は、ビジネス プラン、製品およびエンジニアリング仕様、および Word、Excel、および PowerPoint ファイルの形式でのマーケティング資料とスケジュールでした。</span><span class="sxs-lookup"><span data-stu-id="1c77c-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="1c77c-108">機密性の高い性質のため、これらのファイルへのアクセスは次の条件に従います。</span><span class="sxs-lookup"><span data-stu-id="1c77c-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="1c77c-109">Project 2X チーム メンバーとシニア リーダーシップに制限されています。</span><span class="sxs-lookup"><span data-stu-id="1c77c-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="1c77c-110">ファイルがセキュリティで保護されたフォルダーの外部に配布されている場合でも、Project 2X チーム メンバーとシニア リーダーシップへのアクセスのみを許可するアクセス許可を持つ暗号化と保護。</span><span class="sxs-lookup"><span data-stu-id="1c77c-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="1c77c-111">Contoso IT スタッフ[](secure-teams-security-isolation.md)は、Project 2X とこれらの手順にセキュリティ分離を持つチームを使用しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="1c77c-112">手順 1: プライベート チームを作成する</span><span class="sxs-lookup"><span data-stu-id="1c77c-112">Step 1: Created a private team</span></span>

<span data-ttu-id="1c77c-113">まず、チームの基になる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が推奨される SharePoint アクセス ポリシー [を構成しました](../security/defender-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1c77c-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="1c77c-114">次に、Contoso IT 管理者が Project 2X という名前の新しいプライベート チームを作成し、Project 2X スタッフのユーザー アカウントをメンバーとして追加しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="1c77c-115">また、Project 2X チームの所有者だけがプライベート チャネルを作成できるようチームを構成しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="1c77c-116">構成の詳細については、「プライベート チームの [作成」を参照してください](secure-teams-security-isolation.md#create-a-private-team)。</span><span class="sxs-lookup"><span data-stu-id="1c77c-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="1c77c-117">手順 2: Project 2X チームの感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="1c77c-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="1c77c-118">Contoso 管理者は、Project 2X という名前の新しい **感度ラベルを作成** しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="1c77c-119">暗号化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c77c-119">Enabled encryption.</span></span>
- <span data-ttu-id="1c77c-120">Project 2X Co-Author 365 グループのアクセス許可を許可します。</span><span class="sxs-lookup"><span data-stu-id="1c77c-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="1c77c-121">シニア リーダーシップ グループに対して許可された閲覧者のアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="1c77c-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="1c77c-122">管理されていないデバイスへのアクセスがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="1c77c-123">基になる **Project** 2X SharePoint サイトの [ドキュメント] セクションのファイルは、次の方法で保護されています。</span><span class="sxs-lookup"><span data-stu-id="1c77c-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="1c77c-124">Project 2X Microsoft 365 グループのメンバーに対する完全なアクセス許可とシニア リーダーシップ グループへの読み取りアクセス許可のみを許可するサイトのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="1c77c-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="1c77c-125">サイトから移動またはコピーされた場合にファイルと一緒に移動する暗号化とアクセス許可を含む Project 2X の感度ラベル。</span><span class="sxs-lookup"><span data-stu-id="1c77c-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="1c77c-126">構成の詳細については、「感度ラベルを作成 [する」を参照してください](secure-teams-security-isolation.md#create-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="1c77c-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="1c77c-127">手順 3: 基になる SharePoint サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="1c77c-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="1c77c-128">まず、チームの基になる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が推奨される SharePoint アクセス ポリシー [を構成しました](../security/defender-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1c77c-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="1c77c-129">次に、サイトの追加のアクセス許可設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="1c77c-130">Project 2X グループ メンバーがサイトへのアクセスを共有しなけれな</span><span class="sxs-lookup"><span data-stu-id="1c77c-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="1c77c-131">構成の詳細については、「 [セキュリティ分離を使用するチームの SharePoint 設定」を参照してください](secure-teams-security-isolation.md#sharepoint-settings)。</span><span class="sxs-lookup"><span data-stu-id="1c77c-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="1c77c-132">シニア リーダーシップ グループの読み取りアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="1c77c-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="1c77c-133">次に、Project 2X グループ メンバーがサイトへのアクセスを共有しなかぐために、サイトの追加のアクセス許可設定を構成しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="1c77c-134">Project 2X のプライベート チャネルが作成されると、グループ所有者はゲスト共有を無効にし、既定の共有リンクを [特定のユーザー] **の値に設定** します。</span><span class="sxs-lookup"><span data-stu-id="1c77c-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="1c77c-135">セキュリティを分離した Project 2X チームの構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1c77c-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Project 2X チームの結果の構成](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="1c77c-137">手順 4: トレーニング済みの Project 2X チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="1c77c-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="1c77c-138">Contoso のセキュリティ スタッフは、Project 2X チーム メンバーを必須コースでトレーニングし、次のステップを踏み出しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="1c77c-139">新しい Project 2X チームにアクセスする方法、会議とチャットを使用する方法、およびチーム ファイルで共同作業する方法。</span><span class="sxs-lookup"><span data-stu-id="1c77c-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="1c77c-140">チーム内に新しいファイルを作成し、ローカルで作成された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="1c77c-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="1c77c-141">Project 2X の感度ラベルを使用してファイルにラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="1c77c-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="1c77c-142">Project 2X ラベルがチームを離れる場合でもファイルを保護する方法のデモンストレーション。</span><span class="sxs-lookup"><span data-stu-id="1c77c-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="1c77c-143">最後の結果は、Project 2X チーム メンバーがチャット、会議、ファイルの安全な環境で共同作業を行う安全な環境でした。</span><span class="sxs-lookup"><span data-stu-id="1c77c-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="1c77c-144">Project 2X の感度ラベルが割り当てられている基になる Project 2X サイトに保存されているファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1c77c-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![基になる Project 2X サイトに格納されているファイルの例](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="1c77c-146">いくつかのインスタンスで、Project 2X チーム メンバーは、Project 2X ラベルで保護されたファイルをローカル ドライブにダウンロードしてオフライン作業を行いました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="1c77c-147">ただし、資格情報を開く際に資格情報の入力を求めるメッセージが表示された後、間違いを気付いて削除しました。</span><span class="sxs-lookup"><span data-stu-id="1c77c-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="1c77c-148">Teams のコラボレーション環境と Microsoft 365 のセキュリティ機能のため、Project 2X の詳細はプロジェクト期間中秘密に保たれ続けでした。</span><span class="sxs-lookup"><span data-stu-id="1c77c-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="1c77c-149">Contoso 社は計画を発表し、顧客と投資家の喜びと競合他社のチャグリンに新しい製品とサービスを展開中です。</span><span class="sxs-lookup"><span data-stu-id="1c77c-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c77c-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="1c77c-150">Next step</span></span>

<span data-ttu-id="1c77c-151">[組織にセキュリティの分離を持つ](secure-teams-security-isolation.md) チームを展開します。</span><span class="sxs-lookup"><span data-stu-id="1c77c-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

