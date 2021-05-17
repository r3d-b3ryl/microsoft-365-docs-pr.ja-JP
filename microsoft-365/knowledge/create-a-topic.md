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
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687533"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a><span data-ttu-id="c6fe1-103">Microsoft Viva Topics で新しいトピックを作成する</span><span class="sxs-lookup"><span data-stu-id="c6fe1-103">Create a new topic in Microsoft Viva Topics</span></span>

<span data-ttu-id="c6fe1-104">ビバ トピックでは、インデックス作成によって検出されない場合や、AI テクノロジがトピックとして確立するのに十分な証拠が見つからなかった場合に、新しいトピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-104">In Viva Topics, you can create a new topic if one is not discovered through indexing or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

> [!Note] 
> <span data-ttu-id="c6fe1-105">AI によって収集されるトピックの情報はセキュリティでトリミング[](topic-experiences-security-trimming.md)されますが、手動で作成したトピックのトピックの説明とユーザー情報は、トピックを表示する権限を持つすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-105">While information in a topic that is gathered by AI is [security trimmed](topic-experiences-security-trimming.md), note that topic description and people information in a manually created topic is visible to all users who have permissions to view the topic.</span></span> 


## <a name="requirements"></a><span data-ttu-id="c6fe1-106">要件</span><span class="sxs-lookup"><span data-stu-id="c6fe1-106">Requirements</span></span>

<span data-ttu-id="c6fe1-107">新しいトピックを作成するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-107">To create a new topic, you need to:</span></span>
- <span data-ttu-id="c6fe1-108">Viva トピック ライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-108">Have a Viva Topics license.</span></span>
- <span data-ttu-id="c6fe1-109">トピックを作成または編集 [**Whoアクセス許可を持っている**](./topic-experiences-user-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-109">Have permissions to [**Who can create or edit topics**](./topic-experiences-user-permissions.md).</span></span> <span data-ttu-id="c6fe1-110">ナレッジ管理者は、Viva トピックでのトピックに関するアクセス許可の設定でユーザーにこのアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-110">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

> [!Note] 
> <span data-ttu-id="c6fe1-111">トピック センター (ナレッジ マネージャー) でトピックを管理する権限を持つユーザーには、トピックを作成および編集するためのアクセス許可が既に付与されています。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-111">Users who have permission to manage topics in the topic center (knowledge managers) already have permissions to create and edit topics.</span></span>

## <a name="to-create-a-topic"></a><span data-ttu-id="c6fe1-112">トピックを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6fe1-112">To create a topic</span></span>

<span data-ttu-id="c6fe1-113">次の 2 つの場所から新しいトピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-113">You can create a new topic from two locations:</span></span>

- <span data-ttu-id="c6fe1-114">トピック センターのホーム ページ: **Who** を持つライセンスを持つユーザーは、[新しい] メニューを選択して [トピック] ページを選択することで、トピック センターから新しいトピックを作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-114">Topic center home page: Any licensed user with the **Who can create or edit topics** permission (contributors) can create a new topic from the topic center by selecting the **New** menu and select **Topic page**.</span></span> 

    ![トピック センターからの新しいトピック](../media/knowledge-management/new-topic.png)  

- <span data-ttu-id="c6fe1-116">[トピックの管理] ページ: **Who** を持つライセンスユーザーは、トピックのアクセス許可 (ナレッジ マネージャー) を管理できます。新しいトピック ページを選択すると、トピック センターの [トピックの管理] ページから新しいトピック **を作成できます**。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-116">Manage topics page:  Any licensed user who has **Who can manage topics** permission (knowledge managers) can create a new topic from the Manage topics page in the Topic Center by selecting **New topic page**.</span></span> 

    ![トピックの管理に関する新しいトピック](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a><span data-ttu-id="c6fe1-118">新しいトピックを作成する方法:</span><span class="sxs-lookup"><span data-stu-id="c6fe1-118">To create a new topic:</span></span>

1. <span data-ttu-id="c6fe1-119">[トピックの管理] ページでリボンから新しいトピック ページを作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-119">Select the option to create a new Topic Page from the ribbon on the Manage Topics page.</span></span>

2.  <span data-ttu-id="c6fe1-120">**[このトピックに名前を付ける]** セクションで、新しいトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-120">In the **Name this topic** section, type the name of the new topic.</span></span>

    ![このトピックに名前を付け](../media/knowledge-management/k-new-topic-page.png)  

3. <span data-ttu-id="c6fe1-122">[代替 **名] セクション** で、トピックが参照される可能性があるその他の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-122">In the **Alternate Names** section, type any other names that the topic might be referred to.</span></span> 

    ![代替名](../media/knowledge-management/alt-names.png)  

4. <span data-ttu-id="c6fe1-124">[説明 **] セクション** で、トピックについて説明する文を 2 つ入力します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-124">In the **Description** section, type a couple of sentences that describe the topic.</span></span> 

    ![トピックの説明](../media/knowledge-management/description.png)

4. <span data-ttu-id="c6fe1-126">[ピン **留めされた** ユーザー] セクションでは、ユーザーを "ピン留め" して、トピックへの接続 (たとえば、接続されたリソースの所有者) として表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-126">In the **Pinned people** section, you can "pin" a person to show them as having a connection to the topic (for example, an owner of a connected resource).</span></span> <span data-ttu-id="c6fe1-127">まず、[新しいユーザーの追加] ボックスに名前またはメール アドレスを入力し、検索結果から追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-127">Begin by typing their name or email address in the **add a new user** box, and then select the user you want to add from the search results.</span></span> <span data-ttu-id="c6fe1-128">ユーザー カードの [リストから削除] アイコンを選択して、ピン留めを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-128">You can also "unpin" them by selecting the **Remove from list** icon on the user card.</span></span> <span data-ttu-id="c6fe1-129">ユーザーをリスト内の別の場所にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-129">You can also drag the person to another place in the list.</span></span>
 
    ![ピン留めされたユーザー](../media/knowledge-management/pinned-people.png)

5. <span data-ttu-id="c6fe1-131">[ピン留 **めされたファイルとページ**] セクションでは、トピックに関連付けられているファイルまたはサイト SharePointを追加または "ピン留め" できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-131">In the **Pinned files and pages** section, you can add or "pin" a file or SharePoint site page that is associated to the topic.</span></span>

   ![ピン留めされたファイルとページ](../media/knowledge-management/pinned-files-and-pages.png)
 
    <span data-ttu-id="c6fe1-133">新しいファイルを追加するには、[追加] を選択し、フリークエント サイトまたはフォローサイトから SharePoint サイトを選択し、サイトのドキュメント ライブラリからファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-133">To add a new file, select **Add**, select the SharePoint site from your Frequent or Followed sites, and then select the file from the site's document library.</span></span>

    <span data-ttu-id="c6fe1-134">[リンクから] オプション **を使用して** 、URL を指定してファイルまたはページを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-134">You can also use the **From a link** option to add a file or page by providing the URL.</span></span> 

    > [!Note] 
    > <span data-ttu-id="c6fe1-135">追加するファイルとページは、同じテナント内Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-135">Files and pages that you add must be located within the same Microsoft 365 tenant.</span></span> <span data-ttu-id="c6fe1-136">トピックの外部リソースへのリンクを追加する場合は、手順 8 のキャンバス アイコンを使用して追加できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-136">If you want to add a link to an external resource in the topic, you can add it through the canvas icon in step 8.</span></span>


6.  <span data-ttu-id="c6fe1-137">[ **関連サイト]** セクションには、トピックに関する情報を持つサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-137">The **Related sites** section shows sites that have information about the topic.</span></span> 

    ![[関連サイト] セクション](../media/knowledge-management/related-sites.png)

    <span data-ttu-id="c6fe1-139">[追加] を選択してからサイトを検索するか、[頻繁なサイト] または [最近使用したサイト] の一覧からサイトを選択して、関連サイトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-139">You can add a related site by selecting **Add** and then either searching for the site, or selecting it from your list of Frequent or Recent sites.</span></span>
    
    ![サイトの選択](../media/knowledge-management/sites.png)

7. <span data-ttu-id="c6fe1-141">[ **関連トピック] セクション** には、トピック間に存在する接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-141">The **Related topics** section shows connections that exist between topics.</span></span> <span data-ttu-id="c6fe1-142">関連するトピック ボタンに **Connect** を選択し、関連するトピックの名前を入力し、検索結果から選択することで、別のトピックに接続を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-142">You can add a connection to a different topic by selecting the **Connect to a related topic** button, and then typing the name of the related topic, and selecting it from the search results.</span></span> 

   ![関連項目](../media/knowledge-management/related-topic.png)  

    <span data-ttu-id="c6fe1-144">次に、トピックの関連付け方法について説明し、[更新] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-144">You can then give a description of how the topics are related, and select **Update**.</span></span>

   ![関連トピックの説明](../media/knowledge-management/related-topics-update.png) 

   <span data-ttu-id="c6fe1-146">追加した関連トピックは、接続されているトピックとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-146">The related topic you added will display as a connected topic.</span></span>

   ![関連トピックが接続されている](../media/knowledge-management/related-topics-final.png) 

   <span data-ttu-id="c6fe1-148">関連するトピックを削除するには、削除するトピックを選択し、[トピックの削除] **アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-148">To remove a related topic, select the topic you want to remove, then select the **Remove topic** icon.</span></span>
 
   ![関連トピックの削除](../media/knowledge-management/remove-related.png)  

   <span data-ttu-id="c6fe1-150">次に、[削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-150">Then select **Remove**.</span></span>

   ![削除の確認](../media/knowledge-management/remove-related-confirm.png) 

8. <span data-ttu-id="c6fe1-152">また、短い説明の下にあるキャンバス アイコンを選択して、静的なアイテム (テキスト、画像、リンクなど) をページに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-152">You can also add static items to the page (such as text, images, or links) by selecting the canvas icon, which you can find below the short description.</span></span> <span data-ttu-id="c6fe1-153">選択すると、ページにSharePointするアイテムを選択できる新しいツールボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-153">Selecting it will open the SharePoint toolbox from which you can choose the item you want to add to the page.</span></span>

   ![キャンバス アイコン](../media/knowledge-management/webpart-library.png) 

9. <span data-ttu-id="c6fe1-155">**[公開]** を選択して、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-155">Select **Publish** to save your changes.</span></span> 

<span data-ttu-id="c6fe1-156">ページを公開すると、トピック名、代替名、説明、ピン留めされたユーザーが、トピックを表示するライセンスを取得したユーザーすべてに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-156">After you publish the page, the topic name, alternate name, description, and pinned people will display to all licensed users who view the topic.</span></span> <span data-ttu-id="c6fe1-157">特定のファイル、ページ、サイトは、閲覧者がそのアイテムに対する Office 365 のアクセス許可を持つ場合にのみ、トピック ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fe1-157">Specific files, pages, and sites will only appear on the topic page if the viewer has Office 365 permissions to the item.</span></span> 



## <a name="see-also"></a><span data-ttu-id="c6fe1-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6fe1-158">See also</span></span>



