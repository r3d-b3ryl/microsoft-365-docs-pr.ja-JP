---
title: Microsoft Viva のトピックの計画
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva のプラントピックを計画する方法について説明します。
ms.openlocfilehash: d64e4b341fe96d7aa3636f58bffe3dd8f388838e
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957541"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="5ef65-103">Microsoft Viva のトピックの計画</span><span class="sxs-lookup"><span data-stu-id="5ef65-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="5ef65-104">組織でのトピックのエクスペリエンスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="5ef65-105">トピックの計画の決定により、高品質のトピックがユーザーに表示され、知識を使用して提供するための適切なアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="5ef65-106">この記事では、次の計画の決定について検討します。</span><span class="sxs-lookup"><span data-stu-id="5ef65-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="5ef65-107">トピックをクロールする SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="5ef65-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="5ef65-108">トピック エクスペリエンスから除外するトピック (存在する場合)</span><span class="sxs-lookup"><span data-stu-id="5ef65-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="5ef65-109">トピックを表示するユーザー</span><span class="sxs-lookup"><span data-stu-id="5ef65-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="5ef65-110">トピック センターでトピックを管理するためのアクセス許可を付与するユーザー</span><span class="sxs-lookup"><span data-stu-id="5ef65-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="5ef65-111">トピック センターでトピックを作成または編集するためのアクセス許可を付与するユーザー</span><span class="sxs-lookup"><span data-stu-id="5ef65-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="5ef65-112">トピック センターに与える名前</span><span class="sxs-lookup"><span data-stu-id="5ef65-112">What name you want to give your topic center</span></span>

<span data-ttu-id="5ef65-113">データのセキュリティとプライバシーが尊重され、トピック エクスペリエンスはユーザーに権限を持たなかったファイルへの追加のアクセス権をユーザーに付与しない。</span><span class="sxs-lookup"><span data-stu-id="5ef65-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="5ef65-114">計画プロセスの一環として [、Microsoft Viva Topics のセキュリティと](topic-experiences-security-privacy.md) プライバシーも確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ef65-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ef65-115">要件</span><span class="sxs-lookup"><span data-stu-id="5ef65-115">Requirements</span></span>

<span data-ttu-id="5ef65-116">Microsoft 365 管理センターにアクセスしてトピックを設定するには、 [ビ](https://www.microsoft.com/microsoft-viva/topics) バ トピックをサブスクライブし、グローバル管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ef65-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="5ef65-117">Topics を使用するユーザーには、トピック エクスペリエンス ライセンス **が必要** です。</span><span class="sxs-lookup"><span data-stu-id="5ef65-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="5ef65-118">ライセンスの割り当てについては [、「Microsoft Viva Topics のセットアップ」を参照してください](set-up-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="5ef65-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="5ef65-119">トピックの検出</span><span class="sxs-lookup"><span data-stu-id="5ef65-119">Topic discovery</span></span>

<span data-ttu-id="5ef65-120">トピック検出設定では、トピックのソースとして使用する SharePoint サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ef65-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="5ef65-121">すべての SharePoint サイト、サイトの特定のリスト、またはサイトを含めないを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="5ef65-122">トピック エクスペリエンスがユーザーに役立つ多数のトピックを検出できるよう、すべてのサイトを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ef65-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="5ef65-123">トピックを設定すると、次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="5ef65-124">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="5ef65-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="5ef65-125">これには、現在および将来のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-125">This includes current and future sites.</span></span>
- <span data-ttu-id="5ef65-126">**[すべて] (選択したサイトを** 除く) : 指定したサイトを除くすべてのサイト。</span><span class="sxs-lookup"><span data-stu-id="5ef65-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="5ef65-127">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="5ef65-128">**選択したサイトのみ**: 指定したサイトのみ。</span><span class="sxs-lookup"><span data-stu-id="5ef65-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="5ef65-129">今後作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="5ef65-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="5ef65-130">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="5ef65-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="5ef65-131">[すべて] **(選択** したサイトを除く) または選択したサイトのみを選択した場合は、サイトの一覧を含む .csv ファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="5ef65-132">これらのオプションは、パイロットを実行し、開始するサイトの数を制限する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5ef65-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="5ef65-133">以下の .csv テンプレートをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="5ef65-134">トピックが自動的に作成または更新されるのを防ぐため、[サイトなし] を選択することをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="5ef65-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="5ef65-135">ただし、トピックを設定し、後でサイトを追加する場合は、このオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="5ef65-136">組織で必要に応じて、ユーザーまたはナレッジ マネージャーが個々のサイトをトピックの検出から削除することを要求するプロセスを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ef65-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="5ef65-137">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5ef65-137">Multi-geo</span></span>

<span data-ttu-id="5ef65-138">組織が [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)を展開している場合、トピック センターは中央の場所にプロビジョニングされ、中央の場所にある SharePoint サイトだけがトピックのソースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="5ef65-139">([すべてのサイト] **を選択した** 場合、Viva Topics は中央の場所のすべてのサイトを使用します)。</span><span class="sxs-lookup"><span data-stu-id="5ef65-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="5ef65-140">コンテンツのすべての処理と保存は、中央の場所で行われます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="5ef65-141">ユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5ef65-141">User permissions</span></span>

<span data-ttu-id="5ef65-142">指定するユーザーのアクセス許可によって、組織内のユーザーがトピックと対話し、そのユーザーが実行できる操作が決まれます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="5ef65-143">現時点では、ビバ トピックはゲスト (外部) ユーザーに対するライセンスまたはユーザーアクセス許可の提供をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="5ef65-143">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="5ef65-144">*トピックを管理する*</span><span class="sxs-lookup"><span data-stu-id="5ef65-144">*Manage topics*</span></span>

<span data-ttu-id="5ef65-145">ナレッジ マネージャーは、組織内の情報の品質、構造化された方法、その他のベスト プラクティスを監督します。</span><span class="sxs-lookup"><span data-stu-id="5ef65-145">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="5ef65-146">トピックを確認および拒否できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-146">They can confirm and reject topics.</span></span>

<span data-ttu-id="5ef65-147">個々のトピック マネージャーを指定することができますが、ナレッジ マネージャーになるユーザーを含むセキュリティ グループ (または既存のグループを使用する) を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ef65-147">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="5ef65-148">このセキュリティ グループは、セットアップ プロセス中に指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-148">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="5ef65-149">*トピックの作成と編集*</span><span class="sxs-lookup"><span data-stu-id="5ef65-149">*Create and edit topics*</span></span>

<span data-ttu-id="5ef65-150">トピックの投稿者は、組織のチャンピオンと件名の専門家です。</span><span class="sxs-lookup"><span data-stu-id="5ef65-150">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="5ef65-151">トピックを作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-151">They can create and edit topics.</span></span> 

<span data-ttu-id="5ef65-152">すべてのユーザーが情報を共有できる場合にトピック エクスペリエンスが最適に機能するために、組織内のすべてのユーザーがトピックを作成および編集することを許可することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ef65-152">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="5ef65-153">トピックの作成と編集を特定のユーザーまたはグループに制限する場合は、そのユーザーのセキュリティ グループを作成し、セットアップ プロセス中に指定します。</span><span class="sxs-lookup"><span data-stu-id="5ef65-153">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="5ef65-154">トピックに投稿するユーザーを許可しない場合は選択できます。ただし、これはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="5ef65-154">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="5ef65-155">このオプションを選択した場合でも、ナレッジ マネージャーはトピックを編集および作成できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-155">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="5ef65-156">*トピック ビューアー*</span><span class="sxs-lookup"><span data-stu-id="5ef65-156">*Topic viewers*</span></span>

<span data-ttu-id="5ef65-157">トピック ビューアーは、トピック ページ、検索結果、および SharePoint ページのようなコンテンツでトピックが強調表示されている場合の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-157">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="5ef65-158">ユーザーは、検出されたトピックが検出されたファイルとページにアクセスできる場合にのみ、検出されたトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-158">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="5ef65-159">トピック ビューアーを設定する場合は、次の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-159">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="5ef65-160">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="5ef65-160">**Everyone in my organization**</span></span>
- <span data-ttu-id="5ef65-161">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="5ef65-161">**Only selected people or security groups**</span></span>
- <span data-ttu-id="5ef65-162">**だれも**</span><span class="sxs-lookup"><span data-stu-id="5ef65-162">**No one**</span></span>

<span data-ttu-id="5ef65-163">組織の **全員をお勧めします** が、パイロットを行う場合は、選択したユーザーまたはセキュリティ グループのみを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ef65-163">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="5ef65-164">また、[トピック] **を設定する** 場合は [いいえ] を選択できますが、まだトピックを表示できません。</span><span class="sxs-lookup"><span data-stu-id="5ef65-164">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="5ef65-165">(ナレッジ マネージャーは、トピックを表示し、トピックを広く利用可能にするための決定に役立つアクセス権を持ちます)。</span><span class="sxs-lookup"><span data-stu-id="5ef65-165">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="5ef65-166">ナレッジ ルール</span><span class="sxs-lookup"><span data-stu-id="5ef65-166">Knowledge rules</span></span>

<span data-ttu-id="5ef65-167">管理者は、トピック エクスペリエンスから特定のトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-167">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="5ef65-168">これは、機密性の高いデータがトピックに表示されない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5ef65-168">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="5ef65-169">ナレッジ マネージャーはトピック センターのトピックを除外することができますが、管理者によって除外されたトピックはナレッジ マネージャーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5ef65-169">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="5ef65-170">(ナレッジ マネージャーは、検出後にトピック センターのトピックを削除できます)。</span><span class="sxs-lookup"><span data-stu-id="5ef65-170">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="5ef65-171">管理者レベルでトピックを除外する場合は、トピックを .csv ファイルに追加し、ファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ef65-171">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="5ef65-172">この操作は、セットアップ中または後で実行できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-172">You can do this during setup or later.</span></span>

<span data-ttu-id="5ef65-173">.csv ファイルには、次のパラメーターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ef65-173">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="5ef65-174">**名前**: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ef65-174">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="5ef65-175">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="5ef65-175">There are two ways to do this:</span></span>
- <span data-ttu-id="5ef65-176">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="5ef65-176">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="5ef65-177">完全一致: 正確な名前または頭字語 (Contoso や ATL *など)\*\*を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="5ef65-177">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="5ef65-178">部分一致: 特定の単語が含まれていますすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-178">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="5ef65-179">たとえば、*円弧は、* アーク円、プラズマアーク溶接、トレーニングアークなど、アークという単語を含むすべてのトピック *を除外します*。テキストが単語の一部として含まれているトピック (Architecture など) は除外されない点に *注意してください*。</span><span class="sxs-lookup"><span data-stu-id="5ef65-179">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="5ef65-180">**略称 (省略可能)**: (拡張とも呼 *ばれる)* 頭字語を除外する場合は、頭字語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ef65-180">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![CSV テンプレートのトピックを除外する](../media/exclude-topics-csv.png) 

<span data-ttu-id="5ef65-182">csv テンプレートは、以下にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-182">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="5ef65-183">管理</span><span class="sxs-lookup"><span data-stu-id="5ef65-183">Administration</span></span>

<span data-ttu-id="5ef65-184">トピックをセットアップすると、セットアップ プロセスの一部として、トピック センターが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-184">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="5ef65-185">トピック センターに名前を付け、URL を何にしたいかを考える。</span><span class="sxs-lookup"><span data-stu-id="5ef65-185">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="5ef65-186">名前と URL の両方をセットアップ プロセスの一部として設定し、後で Microsoft 365 管理センターで名前を変更できます (ただし、URL は変更されません)。</span><span class="sxs-lookup"><span data-stu-id="5ef65-186">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5ef65-187">1 つのトピック センターのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ef65-187">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="5ef65-188">セットアップ チェックリスト</span><span class="sxs-lookup"><span data-stu-id="5ef65-188">Setup checklist</span></span>

<span data-ttu-id="5ef65-189">トピック エクスペリエンスをセットアップする場合は、セットアップ ウィザードを実行するときに次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ef65-189">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5ef65-190">トピック検出用にすべてのサイトを含めない場合に含めるまたは除外するサイトの一覧</span><span class="sxs-lookup"><span data-stu-id="5ef65-190">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="5ef65-191">すべてのユーザーにトピックの表示を許可しない場合のトピック 閲覧者のセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5ef65-191">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="5ef65-192">すべてのユーザーがトピックの作成と編集を許可しない場合のトピック投稿者のセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5ef65-192">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="5ef65-193">すべてのユーザーがトピックを管理できない場合のトピック ナレッジ マネージャーのセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="5ef65-193">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="5ef65-194">トピック検出から除外する機密性の高いトピックの一覧</span><span class="sxs-lookup"><span data-stu-id="5ef65-194">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="5ef65-195">トピック センター サイトの名前</span><span class="sxs-lookup"><span data-stu-id="5ef65-195">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="5ef65-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ef65-196">See also</span></span>

[<span data-ttu-id="5ef65-197">トピック エクスペリエンスを設定する</span><span class="sxs-lookup"><span data-stu-id="5ef65-197">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="5ef65-198">Microsoft 365 でのトピック検出の管理</span><span class="sxs-lookup"><span data-stu-id="5ef65-198">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="5ef65-199">Microsoft 365 でのトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="5ef65-199">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="5ef65-200">Microsoft 365 でのトピックのアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="5ef65-200">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="5ef65-201">Microsoft 365 でトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="5ef65-201">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
