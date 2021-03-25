---
title: Microsoft Viva Topics で新しいトピックを作成する
description: Microsoft Viva Topics で新しいトピックを作成する方法。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: c1f7b67bb49aff8d6656798d80636d9de5858877
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165839"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a><span data-ttu-id="d863b-103">Microsoft Viva Topics で新しいトピックを作成する</span><span class="sxs-lookup"><span data-stu-id="d863b-103">Create a new topic in Microsoft Viva Topics</span></span>

<span data-ttu-id="d863b-104">ビバ トピックでは、インデックス作成によって検出されない場合や、AI テクノロジがトピックとして確立するのに十分な証拠が見つからなかった場合に、新しいトピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-104">In Viva Topics, you can create a new topic if one is not discovered through indexing or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

> [!Note] 
> <span data-ttu-id="d863b-105">AI によって収集されるトピックの情報はセキュリティでトリミング[](topic-experiences-security-trimming.md)されますが、手動で作成したトピックのトピックの説明とユーザー情報は、トピックを表示する権限を持つすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d863b-105">While information in a topic that is gathered by AI is [security trimmed](topic-experiences-security-trimming.md), note that topic description and people information in a manually created topic is visible to all users who have permissions to view the topic.</span></span> 


## <a name="requirements"></a><span data-ttu-id="d863b-106">要件</span><span class="sxs-lookup"><span data-stu-id="d863b-106">Requirements</span></span>

<span data-ttu-id="d863b-107">新しいトピックを作成するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="d863b-107">To create a new topic, you need to:</span></span>
- <span data-ttu-id="d863b-108">Viva Topics ライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="d863b-108">Have a Viva Topics license.</span></span>
- <span data-ttu-id="d863b-109">トピックを作成または編集 [**できるユーザーに対するアクセス許可を持つ**](./topic-experiences-user-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d863b-109">Have permissions to [**Who can create or edit topics**](./topic-experiences-user-permissions.md).</span></span> <span data-ttu-id="d863b-110">ナレッジ管理者は、ビバ トピックのアクセス許可設定でユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-110">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

> [!Note] 
> <span data-ttu-id="d863b-111">トピック センター (ナレッジ マネージャー) でトピックを管理する権限を持つユーザーには、トピックを作成および編集するためのアクセス許可が既に付与されています。</span><span class="sxs-lookup"><span data-stu-id="d863b-111">Users who have permission to manage topics in the topic center (knowledge managers) already have permissions to create and edit topics.</span></span>

## <a name="to-create-a-topic"></a><span data-ttu-id="d863b-112">トピックを作成するには</span><span class="sxs-lookup"><span data-stu-id="d863b-112">To create a topic</span></span>

<span data-ttu-id="d863b-113">2 つの場所から新しいトピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-113">You can create a new topic from two locations:</span></span>

- <span data-ttu-id="d863b-114">トピック センターのホーム ページ: トピックを作成または編集できるユーザー (投稿者) を持つライセンスユーザーは、[新しい] メニューを選択<b></b>して [トピック] ページを選択して、トピック センターから新しいトピックを<b>作成できます</b>。</span><span class="sxs-lookup"><span data-stu-id="d863b-114">Topic center home page: Any licensed user with the **Who can create or edit topics** permission (contributors) can create a new topic from the topic center by selecting the <b>New</b> menu and select <b>Topic page</b>.</span></span></br> 

    ![トピック センターからの新しいトピック](../media/knowledge-management/new-topic.png) </br> 

- <span data-ttu-id="d863b-116">[トピックの管理] ページ: トピックの管理権限を持つライセンスユーザー (ナレッジ マネージャー) は、[トピック センター] の [トピックの管理] ページで [新しいトピック] ページを選択して、新しいトピックを<b>作成できます</b>。</span><span class="sxs-lookup"><span data-stu-id="d863b-116">Manage topics page:  Any licensed user who has **Who can manage topics** permission (knowledge managers) can create a new topic from the Manage topics page in the Topic Center by selecting <b>New topic page</b>.</span></span></br> 

    ![トピックの管理に関する新しいトピック](../media/knowledge-management/new-topic-topic-center.png) </br> 

### <a name="to-create-a-new-topic"></a><span data-ttu-id="d863b-118">新しいトピックを作成するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="d863b-118">To create a new topic:</span></span>

1. <span data-ttu-id="d863b-119">[トピックの管理] ページのリボンから新しいトピック ページを作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d863b-119">Select the option to create a new Topic Page from the ribbon on the Manage Topics page.</span></span>

2.   <span data-ttu-id="d863b-120">[この **トピックに名前を付け** ] セクションに、新しいトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d863b-120">In the **Name this topic** section, type the name of the new topic.</span></span>

    ![このトピックに名前を付け](../media/knowledge-management/k-new-topic-page.png) </br> 


3. <span data-ttu-id="d863b-122">[代替 <b>名] セクション</b> で、トピックが参照される可能性があるその他の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d863b-122">In the <b>Alternate Names</b> section, type any other names that the topic might be referred to.</span></span> 

    ![代替名](../media/knowledge-management/alt-names.png) </br> 
4. <span data-ttu-id="d863b-124">[説明 <b>] セクション</b> で、トピックについて説明する文を 2 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="d863b-124">In the <b>Description</b> section, type a couple of sentences that describe the topic.</span></span> 

    ![トピックの説明](../media/knowledge-management/description.png)</br>

4. <span data-ttu-id="d863b-126">[ピン <b>留めされた</b> ユーザー] セクションでは、ユーザーを "ピン留め" して、トピックへの接続 (たとえば、接続されたリソースの所有者) として表示できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-126">In the <b>Pinned people</b> section, you can "pin" a person to show them as having a connection to the topic (for example, an owner of a connected resource).</span></span> <span data-ttu-id="d863b-127">まず、[新しいユーザーの追加] ボックス<b></b>に名前またはメール アドレスを入力し、検索結果から追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d863b-127">Begin by typing their name or email address in the <b>add a new user</b> box, and then select the user you want to add from the search results.</span></span> <span data-ttu-id="d863b-128">ユーザー カードの [リストから削除] アイコン<b></b>を選択して、ピン留めを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d863b-128">You can also "unpin" them by selecting the <b>Remove from list</b> icon on the user card.</span></span> <span data-ttu-id="d863b-129">ユーザーをドラッグして、ユーザーのリストが表示される順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-129">You can also drag the person to change the order that the list of people appear.</span></span>
 
    ![ピン留めされたユーザー](../media/knowledge-management/pinned-people.png)</br>


5. <span data-ttu-id="d863b-131">[ピン留 <b>めされたファイルとページ</b> ] セクションでは、トピックに関連付けられているファイルまたは SharePoint サイト ページを追加または "ピン留め" できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-131">In the <b>Pinned files and pages</b> section, you can add or "pin" a file or SharePoint site page that is associated to the topic.</span></span>

   ![ピン留めされたファイルとページ](../media/knowledge-management/pinned-files-and-pages.png)</br>
 
    <span data-ttu-id="d863b-133">新しいファイルを追加するには、[<b></b>追加] を選択し、頻繁またはフォローしているサイトから SharePoint サイトを選択し、サイトのドキュメント ライブラリからファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d863b-133">To add a new file, select <b>Add</b>, select the SharePoint site from your Frequent or Followed sites, and then select the file from the site's document library.</span></span>

    <span data-ttu-id="d863b-134">[リンクから] オプション <b>を使用して</b> 、URL を指定してファイルまたはページを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d863b-134">You can also use the <b>From a link</b> option to add a file or page by providing the URL.</span></span> 

    > [!Note] 
    > <span data-ttu-id="d863b-135">追加するファイルとページは、同じ Microsoft 365 テナント内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d863b-135">Files and pages that you add must be located within the same Microsoft 365 tenant.</span></span> <span data-ttu-id="d863b-136">トピックの外部リソースへのリンクを追加する場合は、手順 8 のキャンバス アイコンを使用して追加できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-136">If you want to add a link to an external resource in the topic, you can add it through the canvas icon in step 8.</span></span>


6.  <span data-ttu-id="d863b-137">[ <b>関連サイト]</b> セクションには、トピックに関する情報を持つサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d863b-137">The <b>Related sites</b> section shows sites that have information about the topic.</span></span> 

    ![[関連サイト] セクション](../media/knowledge-management/related-sites.png)</br>

    <span data-ttu-id="d863b-139">[追加] を選択してからサイトを<b></b>検索するか、[頻繁なサイト] または [最近使用したサイト] の一覧からサイトを選択して、関連サイトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-139">You can add a related site by selecting <b>Add</b> and then either searching for the site, or selecting it from your list of Frequent or Recent sites.</span></span></br>
    
    ![サイトの選択](../media/knowledge-management/sites.png)</br>

7. <span data-ttu-id="d863b-141">[ <b>関連トピック] セクション</b> には、トピック間に存在する接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d863b-141">The <b>Related topics</b> section shows connections that exist between topics.</span></span> <span data-ttu-id="d863b-142">別のトピックに接続を追加するには、[関連するトピックに<b></b>接続する] ボタンを選択し、関連するトピックの名前を入力し、検索結果から接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="d863b-142">You can add a connection to a different topic by selecting the <b>Connect to a related topic</b> button, and then typing the name of the related topic, and selecting it from the search results.</span></span> 

   ![関連項目](../media/knowledge-management/related-topic.png)</br>  

    <span data-ttu-id="d863b-144">次に、トピックの関連付け方法について説明し、[更新] を選択 <b>します</b>。</span><span class="sxs-lookup"><span data-stu-id="d863b-144">You can then give a description of how the topics are related, and select <b>Update</b>.</span></span></br>

   ![関連トピックの説明](../media/knowledge-management/related-topics-update.png)</br> 

   <span data-ttu-id="d863b-146">追加した関連トピックは、接続されているトピックとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d863b-146">The related topic you added will display as a connected topic.</span></span>

   ![関連トピックが接続されている](../media/knowledge-management/related-topics-final.png)</br> 

   <span data-ttu-id="d863b-148">関連するトピックを削除するには、削除するトピックを選択し、[トピックの削除] <b>アイコンを選択</b> します。</span><span class="sxs-lookup"><span data-stu-id="d863b-148">To remove a related topic, select the topic you want to remove, then select the <b>Remove topic</b> icon.</span></span></br>
 
   ![関連トピックの削除](../media/knowledge-management/remove-related.png)</br>  

   <span data-ttu-id="d863b-150">次に、[削除] <b>を選択します</b>。</span><span class="sxs-lookup"><span data-stu-id="d863b-150">Then select <b>Remove</b>.</span></span></br>

   ![削除の確認](../media/knowledge-management/remove-related-confirm.png)</br> 
     
 


8. <span data-ttu-id="d863b-152">また、短い説明の下にあるキャンバス アイコンを選択して、静的なアイテム (テキスト、画像、リンクなど) をページに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d863b-152">You can also add static items to the page (such as text, images, or links) by selecting the canvas icon, which you can find below the short description.</span></span> <span data-ttu-id="d863b-153">選択すると SharePoint ツールボックスが開き、そこからページに追加するアイテムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d863b-153">Selecting it will open the SharePoint toolbox from which you can choose the item you want to add to the page.</span></span>

   ![キャンバス アイコン](../media/knowledge-management/webpart-library.png)</br> 


9. <span data-ttu-id="d863b-155">[発行 **] を** 選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d863b-155">Select **Publish** to save your changes.</span></span> 

<span data-ttu-id="d863b-156">ページを発行すると、トピック名、代替名、説明、ピン留めされたユーザーが、トピックを表示するライセンスを持つすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d863b-156">After you publish the page, the topic name, alternate name, description, and pinned people will display to all licensed users who view the topic.</span></span> <span data-ttu-id="d863b-157">特定のファイル、ページ、およびサイトは、ビューアーがアイテムに対して 365 のアクセス許可を持Office場合にのみトピック ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d863b-157">Specific files, pages, and sites will only appear on the topic page if the viewer has Office 365 permissions to the item.</span></span> 



## <a name="see-also"></a><span data-ttu-id="d863b-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="d863b-158">See also</span></span>



