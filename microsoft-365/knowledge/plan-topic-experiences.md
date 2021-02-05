---
title: Microsoft のトピックを計画する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft の計画に関するトピックを計画する方法について説明します。
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107956"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="7762f-103">Microsoft のトピックを計画する</span><span class="sxs-lookup"><span data-stu-id="7762f-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="7762f-104">組織でのトピックのエクスペリエンスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="7762f-105">トピックの計画に関する決定により、質の高いトピックがユーザーに表示され、知識を利用して投稿するための適切なアクセス許可をユーザーに与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7762f-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="7762f-106">この記事では、計画に関する次の決定について取り上します。</span><span class="sxs-lookup"><span data-stu-id="7762f-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="7762f-107">トピックに対してクロールする SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="7762f-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="7762f-108">トピックエクスペリエンスから除外するトピック (存在する場合)</span><span class="sxs-lookup"><span data-stu-id="7762f-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="7762f-109">トピックを表示するユーザー</span><span class="sxs-lookup"><span data-stu-id="7762f-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="7762f-110">トピック センターでトピックを管理するためのアクセス許可を付与するユーザー</span><span class="sxs-lookup"><span data-stu-id="7762f-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="7762f-111">トピック センターでトピックを作成または編集するためのアクセス許可を付与するユーザー</span><span class="sxs-lookup"><span data-stu-id="7762f-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="7762f-112">トピック センターに付けしたい名前</span><span class="sxs-lookup"><span data-stu-id="7762f-112">What name you want to give your topic center</span></span>

<span data-ttu-id="7762f-113">お客様のデータのセキュリティとプライバシーは尊重され、トピックエクスペリエンスでは、権限を持たなかったファイルへの追加アクセスはユーザーに付与されません。</span><span class="sxs-lookup"><span data-stu-id="7762f-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="7762f-114">計画プロセスの一環として [、Microsoft 多くのトピックの](topic-experiences-security-privacy.md) セキュリティとプライバシーも確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7762f-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="7762f-115">要件</span><span class="sxs-lookup"><span data-stu-id="7762f-115">Requirements</span></span>

<span data-ttu-id="7762f-116">Microsoft 365 管理センターにアクセスしてトピックを設定するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7762f-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="7762f-117">トピックを使用するユーザーには、トピック エクスペリエンス ライセンス **が必要** です。</span><span class="sxs-lookup"><span data-stu-id="7762f-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="7762f-118">ライセンスの割り当てについては [、「Microsoft のセットアップに関するトピック」を参照してください](set-up-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="7762f-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="7762f-119">トピックの検出</span><span class="sxs-lookup"><span data-stu-id="7762f-119">Topic discovery</span></span>

<span data-ttu-id="7762f-120">トピック検出設定では、トピックのソースとして使用する SharePoint サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7762f-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="7762f-121">すべての SharePoint サイト、サイトの特定のリスト、またはサイトを含めない選択を行います。</span><span class="sxs-lookup"><span data-stu-id="7762f-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="7762f-122">トピック エクスペリエンスでユーザーに最適な多数のトピックを見つけできるよう、すべてのサイトを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7762f-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="7762f-123">トピックをセットアップするときに、次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="7762f-124">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="7762f-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="7762f-125">これには、現在および将来のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7762f-125">This includes current and future sites.</span></span>
- <span data-ttu-id="7762f-126">**選択したサイトを除くすべての** サイト: 指定したサイトを除くすべてのサイト。</span><span class="sxs-lookup"><span data-stu-id="7762f-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="7762f-127">将来作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="7762f-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="7762f-128">**選択したサイト** のみ: 指定したサイトのみ。</span><span class="sxs-lookup"><span data-stu-id="7762f-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="7762f-129">将来作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="7762f-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="7762f-130">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="7762f-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="7762f-131">[すべて] **(選択** したサイトを除く) または選択したサイトのみを選択した場合は、サイトの一覧を含む .csv ファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="7762f-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="7762f-132">これらのオプションは、パイロットを行い、開始するサイトの数を制限する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="7762f-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="7762f-133">.csv テンプレートは、次の場所にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="7762f-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="7762f-134">トピックが自動的に **作成または更新** されるのを防ぐため、[サイトなし] を選択はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7762f-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="7762f-135">ただし、トピックを設定してから後でサイトを追加する場合は、このオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="7762f-136">組織で必要に応じて、トピックの検出から個々のサイトを削除することをユーザーまたはナレッジ マネージャーに要求するプロセスを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7762f-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="7762f-137">ユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7762f-137">User permissions</span></span>

<span data-ttu-id="7762f-138">指定するユーザーのアクセス許可によって、組織内のユーザーがトピックとやり取りできる内容が決まれます。</span><span class="sxs-lookup"><span data-stu-id="7762f-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="7762f-139">*トピックを管理する*</span><span class="sxs-lookup"><span data-stu-id="7762f-139">*Manage topics*</span></span>

<span data-ttu-id="7762f-140">ナレッジ マネージャーは、組織内の情報の品質、情報の構造化方法、その他のベスト プラクティスを監督します。</span><span class="sxs-lookup"><span data-stu-id="7762f-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="7762f-141">トピックの確認と拒否を行います。</span><span class="sxs-lookup"><span data-stu-id="7762f-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="7762f-142">個々のトピック マネージャーを指定することができますが、ナレッジ マネージャーになるユーザーを含むセキュリティ グループを作成 (または既存のグループを使用) することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7762f-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="7762f-143">このセキュリティ グループは、セットアップ プロセス中に指定できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="7762f-144">*トピックの作成と編集*</span><span class="sxs-lookup"><span data-stu-id="7762f-144">*Create and edit topics*</span></span>

<span data-ttu-id="7762f-145">トピックの投稿者は、組織内のチャンピオンおよび対象分野の専門家です。</span><span class="sxs-lookup"><span data-stu-id="7762f-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="7762f-146">トピックを作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-146">They can create and edit topics.</span></span> 

<span data-ttu-id="7762f-147">すべてのユーザーが情報を共有できる場合にトピックエクスペリエンスが最適に機能するために、組織内のすべてのユーザーにトピックの作成と編集を許可することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7762f-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="7762f-148">トピックの作成と編集を特定のユーザーまたはグループに限定する場合は、そのユーザーのセキュリティ グループを作成し、セットアップ プロセス中に指定します。</span><span class="sxs-lookup"><span data-stu-id="7762f-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="7762f-149">トピックへの投稿を誰にも許可しない選択はできます。ただし、これはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7762f-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="7762f-150">このオプションを選択した場合でも、ナレッジ マネージャーはトピックを編集および作成できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="7762f-151">*トピック ビューアー*</span><span class="sxs-lookup"><span data-stu-id="7762f-151">*Topic viewers*</span></span>

<span data-ttu-id="7762f-152">トピック閲覧者は、トピック ページ、検索結果、および SharePoint ページのようなコンテンツでトピックが強調表示されている場合の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="7762f-153">検出されたトピックは、検出されたトピックのファイルとページにアクセスできる場合にのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="7762f-154">トピック ビューアーを設定する場合は、次の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="7762f-155">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="7762f-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="7762f-156">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="7762f-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="7762f-157">**だれも**</span><span class="sxs-lookup"><span data-stu-id="7762f-157">**No one**</span></span>

<span data-ttu-id="7762f-158">組織内の **全員をお勧** めしますが、パイロットを行う場合は、選択したユーザーまたはセキュリティ グループのみを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7762f-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="7762f-159">また、トピックを **設定する場合** は [No one] を選択できますが、まだトピックを表示できません。</span><span class="sxs-lookup"><span data-stu-id="7762f-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="7762f-160">(ナレッジ マネージャーは、トピックを表示し、トピックを広く利用するための決定に役立つアクセス権を引き続き持ちます)。</span><span class="sxs-lookup"><span data-stu-id="7762f-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="7762f-161">ナレッジ ルール</span><span class="sxs-lookup"><span data-stu-id="7762f-161">Knowledge rules</span></span>

<span data-ttu-id="7762f-162">管理者は、トピックエクスペリエンスから特定のトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="7762f-163">これは、機密性の高いデータがトピックに表示されない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="7762f-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="7762f-164">ナレッジ マネージャーはトピック センターのトピックを除外することができますが、管理者によって除外されたトピックはナレッジ マネージャーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="7762f-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="7762f-165">(ナレッジ マネージャーは、検出後にトピック センターのトピックを削除できます)。</span><span class="sxs-lookup"><span data-stu-id="7762f-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="7762f-166">管理者レベルでトピックを除外する場合は、.csv ファイルに追加してファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7762f-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="7762f-167">これは、セットアップ中以降に実行できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-167">You can do this during setup or later.</span></span>

<span data-ttu-id="7762f-168">.csv ファイルには、次のパラメーターを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7762f-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="7762f-169">**[名前**]: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7762f-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="7762f-170">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="7762f-170">There are two ways to do this:</span></span>
- <span data-ttu-id="7762f-171">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="7762f-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="7762f-172">完全一致: 正確な名前または頭字語 *(Contoso* や ATL など) *を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="7762f-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="7762f-173">部分一致: 特定の単語を含むすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="7762f-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="7762f-174">たとえば、円弧 *には*、円弧、円弧の円弧、トレーニング用の円弧など、その中に円弧を含むすべてのトピック *が除外されます*。 Architecture など、単語の一部としてテキストが含まれるトピックは除外されない点に注意 *してください*。</span><span class="sxs-lookup"><span data-stu-id="7762f-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="7762f-175">**略語 (省略可能)**: (拡張とも呼 *ばれる)* 頭字語を除外する場合は、頭字語が表す単語を入力します。</span><span class="sxs-lookup"><span data-stu-id="7762f-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![CSV テンプレートでトピックを除外する](../media/exclude-topics-csv.png) 

<span data-ttu-id="7762f-177">csv テンプレートは、次の場所にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="7762f-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="7762f-178">管理</span><span class="sxs-lookup"><span data-stu-id="7762f-178">Administration</span></span>

<span data-ttu-id="7762f-179">セットアップ プロセスの一環としてトピックをセットアップすると、トピック センターが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="7762f-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="7762f-180">トピック センターに名前を付け、URL を何にしたいかを考えてみる。</span><span class="sxs-lookup"><span data-stu-id="7762f-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="7762f-181">セットアップ プロセスの一部として名前と URL の両方を設定し、後で Microsoft 365 管理センターで名前を変更できます (URL は変更されません)。</span><span class="sxs-lookup"><span data-stu-id="7762f-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7762f-182">トピック センターは 1 つしか持てない。</span><span class="sxs-lookup"><span data-stu-id="7762f-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="7762f-183">セットアップ チェックリスト</span><span class="sxs-lookup"><span data-stu-id="7762f-183">Setup checklist</span></span>

<span data-ttu-id="7762f-184">トピックエクスペリエンスをセットアップする場合は、セットアップ ウィザードを実行するときに次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="7762f-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="7762f-185">トピック検出用のすべてのサイトを含めない場合に含めるまたは除外するサイトのリスト</span><span class="sxs-lookup"><span data-stu-id="7762f-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="7762f-186">すべてのユーザーにトピックの表示を許可していない場合のトピック閲覧者のセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="7762f-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="7762f-187">すべてのユーザーにトピックの作成と編集を許可しない場合のトピック投稿者のセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="7762f-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="7762f-188">すべてのユーザーにトピックの管理を許可していない場合のトピックナレッジ マネージャーのセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="7762f-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="7762f-189">トピック検出から除外する機密性の高いトピックのリスト</span><span class="sxs-lookup"><span data-stu-id="7762f-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="7762f-190">トピック センター サイトの名前</span><span class="sxs-lookup"><span data-stu-id="7762f-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="7762f-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="7762f-191">See also</span></span>

[<span data-ttu-id="7762f-192">トピック エクスペリエンスを設定する</span><span class="sxs-lookup"><span data-stu-id="7762f-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="7762f-193">Microsoft 365 でトピックの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="7762f-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="7762f-194">Microsoft 365 でトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="7762f-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="7762f-195">Microsoft 365 でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="7762f-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="7762f-196">Microsoft 365 のトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="7762f-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
