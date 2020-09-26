---
title: データ調査で関心のあるユーザーを管理する (プレビュー)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 目的のユーザーを管理する方法について説明します。検索の範囲を指定したり、連絡先、場所、アクティビティログなどの情報を表示したりできます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 58c590b2d72d7eb265dd4f90679effb7cdf68f79
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285583"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="d6f48-103">データ調査で関心のあるユーザーを管理する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d6f48-103">Manage people of interest in Data Investigations (preview)</span></span>

<span data-ttu-id="d6f48-104">データ調査は、多くの場合、関心を持っています。</span><span class="sxs-lookup"><span data-stu-id="d6f48-104">Data investigations often involve people of interest.</span></span> <span data-ttu-id="d6f48-105">通常、これは、調査中または修正しようとしている、置き忘れ、機密、または悪意のあるデータを所有するユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d6f48-105">Usually they are people who own the misplaced, sensitive, or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="d6f48-106">**データ調査 (プレビュー)** で、それらを追加して、検索の範囲を指定したり、連絡先、場所、アクティビティログなどの追加情報を表示したりするために、データソースを見つけ出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-106">In **Data Investigations (preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location, and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="d6f48-107">関心のある人を追加する</span><span class="sxs-lookup"><span data-stu-id="d6f48-107">Add people of interest</span></span>

<span data-ttu-id="d6f48-108">[ **関心のあるユーザー** ] タブでは、関心のある人を追加して、検索範囲を特定するために使用できる Exchange メールボックスや OneDrive for business サイトなどのデータソースを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-108">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="d6f48-109">対象ユーザーによって下位に範囲指定されている場合は、画像やサポートされていないファイルの種類などのインデックスが設定されていないデータが再処理されるため、検索のパフォーマンスと正確性が向上します</span><span class="sxs-lookup"><span data-stu-id="d6f48-109">When scoped down by people of interest, searches are more performant and accurate because the tool reprocesses any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="d6f48-110">また、コミュニケーションを開始したり、アクティビティをさらに調べたりするために使用できる、連絡先情報、場所情報、およびアクティビティログを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-110">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="d6f48-111">調査対象のユーザーを追加するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-111">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="d6f48-112">[ **データ調査 (プレビュー)** ] ページで、調査に移動します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-112">From the **Data Investigations (preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="d6f48-113">調査を選択したら、[関心のある **ユーザー** ] タブに移動し、[ **関心のある人を追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-113">After you have selected an investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="d6f48-114">調査に追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-114">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="d6f48-115">開始するには、組織の Azure Active Directory からユーザーを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-115">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="d6f48-116">関心のある人物のリストを完成させると、[ **次へ** ] をクリックしてデータソースをマップします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-116">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="d6f48-117">オプション各ユーザーについて、[ **exchange** ] を選択して、ユーザーのプライマリ Exchange メールボックスを追加し、 **onedrive** を使用してユーザーのプライマリ onedrive for business サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-117">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="d6f48-118">オプション[ **次へ** ] をクリックして、関心のあるユーザーに関連する追加のデータソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-118">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="d6f48-119">オプションメールボックス、サイト、Teams などのコンテンツの場所をユーザーに割り当てるには、[ **更新** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-119">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="d6f48-120">オプションフライアウトの場合:</span><span class="sxs-lookup"><span data-stu-id="d6f48-120">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="d6f48-121">**Exchange メールボックス** -[ **ユーザー、グループ、またはチームを選択** する] をクリックし、[ **ユーザー、グループ、または teams を再度選択** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-121">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="d6f48-122">メールボックスをさらに追加するには、検索ボックスを使用してユーザーのメールボックスと配布グループを検索します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-122">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="d6f48-123">Microsoft 365 グループまたは Microsoft チーム情報を格納するために使用されるメールボックスを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-123">You can also add mailboxes used to store a Microsoft 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="d6f48-124">[ユーザー、グループ、チーム] チェックボックスをオンにし、[ **選択**] をクリックし、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-124">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d6f48-125">[ユーザー、グループ、またはチームの選択] をクリックしてメールボックスを指定すると、表示されているメールボックスピッカーが空になります。</span><span class="sxs-lookup"><span data-stu-id="d6f48-125">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="d6f48-126">これは、パフォーマンスを向上させるための仕様です。</span><span class="sxs-lookup"><span data-stu-id="d6f48-126">This is by design to enhance performance.</span></span> <span data-ttu-id="d6f48-127">このリストにユーザーを追加するには、検索ボックスに名前 (少なくと3文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-127">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="d6f48-128">**Sharepoint サイト** -[ **サイトの選択** ] をクリックし、[ **サイトの選択** ] をもう一度クリックして、ユーザーに追加する SharePoint および OneDrive for business サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-128">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you want to add to a person.</span></span> <span data-ttu-id="d6f48-129">また、Microsoft 365 グループまたは Microsoft チームの SharePoint サイトの URL を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-129">You can also add the URL for the SharePoint site for a Microsoft 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="d6f48-130">割り当てる各サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-130">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="d6f48-131">[ **選択**] をクリックし、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-131">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="d6f48-132">**Microsoft Teams** – [ **チームの選択** ] をクリックし、[ **teams の選択** ] をもう一度クリックして、その人物が現在参加している microsoft チームグループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-132">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="d6f48-133">ユーザーに追加するチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-133">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="d6f48-134">このチェックボックスをオンにすると、関連付けられた SharePoint サイトと、その Microsoft teams に関連付けられているグループメールボックスを選択 & が自動的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-134">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="d6f48-135">[ **選択**] をクリックし、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-135">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="d6f48-136">Microsoft Teams を追加するには、上記のように、メールボックスと SharePoint サイトを個別に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f48-136">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="d6f48-137">関心のあるユーザーにデータソースのマッピングを完了すると、追加したメールボックス、サイト、およびチームの合計の概要を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-137">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="d6f48-138">関心のあるユーザーに対して追加のデータソースをマップし、関心のある人による検索の範囲を決定した場合、関心のある人物へのドキュメントのマッピングは、調査全体を通じて保持されるため、関心のある人物による証拠の整理またはレポートの生成が容易になります。</span><span class="sxs-lookup"><span data-stu-id="d6f48-138">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="d6f48-139">その他の関心のある人の情報を表示する</span><span class="sxs-lookup"><span data-stu-id="d6f48-139">View additional people of interest information</span></span>

<span data-ttu-id="d6f48-140">[ **関心のあるユーザー** ] タブで、追加したユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f48-140">In **People of interest** tab, click on a person that you added.</span></span> <span data-ttu-id="d6f48-141">フライアウトの場合は、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-141">In a flyout, you'll see:</span></span>

- <span data-ttu-id="d6f48-142">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="d6f48-142">Contact information</span></span>

  - <span data-ttu-id="d6f48-143">[**表示名**: アドレス帳に表示される個人の名前。</span><span class="sxs-lookup"><span data-stu-id="d6f48-143">**Display Name**: The person's name displayed in the address book.</span></span> <span data-ttu-id="d6f48-144">これは通常、名、ミドルネーム、姓の組み合わせになります。</span><span class="sxs-lookup"><span data-stu-id="d6f48-144">This is usually the combination of first name, middle initial, and last name.</span></span>
  - <span data-ttu-id="d6f48-145">[**メール/SMTP**]: ユーザーの SMTP アドレスです。たとえば、jeff@contoso.onmicrosoft.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6f48-145">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="d6f48-146">**タイトル**: 役職</span><span class="sxs-lookup"><span data-stu-id="d6f48-146">**Title**: Job title.</span></span>
  - <span data-ttu-id="d6f48-147">**Department**: ユーザーが働く部署の名前。</span><span class="sxs-lookup"><span data-stu-id="d6f48-147">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="d6f48-148">**上司**: ユーザーの上司。</span><span class="sxs-lookup"><span data-stu-id="d6f48-148">**Manager**: The person's manager.</span></span> <span data-ttu-id="d6f48-149">上司がこの人物のすべてのエスカレーション情報を受信します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-149">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="d6f48-150">場所情報</span><span class="sxs-lookup"><span data-stu-id="d6f48-150">Location information</span></span>

  - <span data-ttu-id="d6f48-151">**City**: 人物が配置されている市区町村。</span><span class="sxs-lookup"><span data-stu-id="d6f48-151">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="d6f48-152">[**状態**: 人物が配置されている都道府県を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-152">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="d6f48-153">[**国/地域**]: 人物が配置されている国/地域。たとえば、"US" や "UK" などです。</span><span class="sxs-lookup"><span data-stu-id="d6f48-153">**Country/Region**: The country/region in which the person is located; for example, "US" or "UK".</span></span>
  - <span data-ttu-id="d6f48-154">**Office**: ユーザーの勤務先所在地。</span><span class="sxs-lookup"><span data-stu-id="d6f48-154">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="d6f48-155">処理状態</span><span class="sxs-lookup"><span data-stu-id="d6f48-155">Processing status</span></span>

  - <span data-ttu-id="d6f48-156">**インデックスの状態**: データソースの詳細なインデックス作成の状態</span><span class="sxs-lookup"><span data-stu-id="d6f48-156">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="d6f48-157">**インデックス作成の最終更新日時**: ディープインデックス作成ジョブが最後にトリガーされた時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="d6f48-157">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="d6f48-158">**データソース**: ユーザーにマップされたメールボックス、サイト、およびチームの数を示します。</span><span class="sxs-lookup"><span data-stu-id="d6f48-158">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="d6f48-159">インデックスの更新</span><span class="sxs-lookup"><span data-stu-id="d6f48-159">Update index</span></span>
    - <span data-ttu-id="d6f48-160">このユーザーのデータソースのインデックスを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-160">You can reindex this person's data sources.</span></span> 

- <span data-ttu-id="d6f48-161">アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="d6f48-161">View activity</span></span> 

    - <span data-ttu-id="d6f48-162">ユーザーのアクティビティログを表示し、検索することができます。</span><span class="sxs-lookup"><span data-stu-id="d6f48-162">You can view and search user's activity logs.</span></span> <span data-ttu-id="d6f48-163">詳細については、「[ユーザーの重要なアクティビティを表示](view-people-of-interest-activity.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6f48-163">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
