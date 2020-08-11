---
title: 'ナレッジ管理ネットワークを管理する (プレビュー) '
description: ナレッジ管理をセットアップする方法について説明します。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: af53f4d563d286ad29138f935fbb69aa10b902ca
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612622"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="6222d-103">ナレッジ管理ネットワークを管理する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="6222d-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="6222d-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="6222d-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="6222d-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6222d-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="6222d-106">[ナレッジ管理を設定](set-up-knowledge-network.md)した後、管理者が Microsoft 365 管理センターを使用して構成設定を調整できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6222d-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="6222d-107">たとえば、次のいずれかの設定を調整しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6222d-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="6222d-108">新しい SharePoint ソースを採鉱所のトピックに追加します。</span><span class="sxs-lookup"><span data-stu-id="6222d-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="6222d-109">トピックにアクセスできるユーザーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6222d-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="6222d-110">トピックセンターでタスクを実行するためのアクセス許可を持つユーザーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6222d-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="6222d-111">トピックセンターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="6222d-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="6222d-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="6222d-112">Requirements</span></span> 
<span data-ttu-id="6222d-113">グローバル管理者または SharePoint 管理者のアクセス許可を持っている必要があります。これを行うには、Microsoft 365 管理センターにアクセスして、組織のナレッジタスクを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6222d-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="6222d-114">ナレッジ管理設定にアクセスするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6222d-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="6222d-115">Microsoft 365 管理センターで、[**セットアップ**] を選択し、[**組織ナレッジ**] セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="6222d-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="6222d-116">[**組織ナレッジ**] セクションで、[**ユーザーをナレッジに接続する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6222d-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![ユーザーを知識に結び付ける](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="6222d-118">[**ユーザーをナレッジに接続**] ページで、[**管理**] を選択して [**ナレッジネットワーク設定**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6222d-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![ナレッジ-ネットワーク設定](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="6222d-120">ナレッジネットワークがトピックを見つける方法を変更する</span><span class="sxs-lookup"><span data-stu-id="6222d-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="6222d-121">SharePoint トピックソースの選択肢を更新する場合は、[**トピックの検索**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="6222d-122">この設定を使用すると、トピックでクロールおよびマイニングされるテナント内の SharePoint サイトを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="6222d-123">[**トピック探索**] タブの [ **SharePoint トピックソースの選択**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="6222d-124">[ **Sharepoint トピックソースの選択**] ページで、検出時にトピックのソースとしてクロールする sharepoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="6222d-125">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6222d-125">This includes:</span></span></br>
    <span data-ttu-id="6222d-126">a.</span><span class="sxs-lookup"><span data-stu-id="6222d-126">a.</span></span> <span data-ttu-id="6222d-127">**すべてのサイト**: テナント内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="6222d-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="6222d-128">これにより、現在および今後のサイトがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="6222d-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="6222d-129">b.</span><span class="sxs-lookup"><span data-stu-id="6222d-129">b.</span></span> <span data-ttu-id="6222d-130">**[すべて]: 選択したサイトを除き、** 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6222d-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="6222d-131">また、探索対象から除外するサイトの一覧をアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6222d-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="6222d-132">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="6222d-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="6222d-133">c. </span><span class="sxs-lookup"><span data-stu-id="6222d-133">c.</span></span> <span data-ttu-id="6222d-134">[**選択したサイトのみ**: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6222d-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="6222d-135">サイトのリストをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6222d-135">You can also upload a list of sites.</span></span> <span data-ttu-id="6222d-136">今後作成されるサイトは、トピック検出のソースとしては含まれません。</span><span class="sxs-lookup"><span data-stu-id="6222d-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![トピックの検索方法を選択する](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="6222d-138">除外するサイトが複数ある場合 (選択した**サイトを除くすべて**を選択した場合)、または (選択した**サイトのみ**を選択した場合)、CSV ファイルをサイト名と url でアップロードすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="6222d-139">CSV テンプレートファイルを使用する場合は、[**サイトテンプレート .csv のダウンロード**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="6222d-140">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="6222d-141">組織内のトピックを表示できるユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="6222d-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="6222d-142">組織内の誰が検索結果の検出されたトピックを表示できるかを更新する場合、または SharePoint ページなどのコンテンツでトピックを強調表示している場合は、[ **Topic discovery** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="6222d-143">[ **Topic discovery** ] タブで、[**ナレッジネットワーク内のトピックを参照できるユーザー**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="6222d-144">[**ナレッジネットワーク内のトピックを参照できるユーザー** ] で、強調表示されたトピック、トピックカード、トピックの回答、トピックページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="6222d-145">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-145">You can select:</span></span></br>
    <span data-ttu-id="6222d-146">a.</span><span class="sxs-lookup"><span data-stu-id="6222d-146">a.</span></span> <span data-ttu-id="6222d-147">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="6222d-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="6222d-148">b.</span><span class="sxs-lookup"><span data-stu-id="6222d-148">b.</span></span> <span data-ttu-id="6222d-149">**選択したユーザーまたはセキュリティグループのみ**</span><span class="sxs-lookup"><span data-stu-id="6222d-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="6222d-150">c. </span><span class="sxs-lookup"><span data-stu-id="6222d-150">c.</span></span> <span data-ttu-id="6222d-151">**だれも**</span><span class="sxs-lookup"><span data-stu-id="6222d-151">**No one**</span></span></br>

    ![トピックを参照できるユーザー](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="6222d-153">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="6222d-154">この設定では、組織内のユーザーを選択できますが、ナレッジ管理ライセンスが割り当てられているユーザーのみがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="6222d-155">トピックセンターでタスクを実行する権限を持つユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="6222d-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="6222d-156">[トピックセンター] ページで次の操作を実行する権限を持つユーザーを更新する場合は、[**トピックの権限**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="6222d-157">トピックを作成および編集できるユーザー: 検出時に見つからなかった新しいトピックを作成する、または既存のトピックページの詳細を編集する。</span><span class="sxs-lookup"><span data-stu-id="6222d-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="6222d-158">どのユーザーがトピックを管理できるか: 検出されたトピックを確認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="6222d-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="6222d-159">トピックを作成および編集する権限を持つユーザーを更新するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6222d-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="6222d-160">[**トピックの権限**] タブの [**トピックの作成と編集が可能なユーザー**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="6222d-161">[**トピックの作成と編集が可能なユーザー** ] ページで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="6222d-162">a.</span><span class="sxs-lookup"><span data-stu-id="6222d-162">a.</span></span> <span data-ttu-id="6222d-163">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="6222d-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="6222d-164">b.</span><span class="sxs-lookup"><span data-stu-id="6222d-164">b.</span></span> <span data-ttu-id="6222d-165">**選択したユーザーまたはセキュリティグループのみ**</span><span class="sxs-lookup"><span data-stu-id="6222d-165">**Only selected people or security groups**</span></span></br>

    ![トピックを作成および編集する](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="6222d-167">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-167">Select **Save**.</span></span></br>

<span data-ttu-id="6222d-168">トピックを管理する権限を持つユーザーを更新するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6222d-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="6222d-169">[**トピックの権限**] タブの [**トピックを管理できるユーザー**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="6222d-170">[**トピックの管理が可能なユーザー** ] ページで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6222d-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="6222d-171">a.</span><span class="sxs-lookup"><span data-stu-id="6222d-171">a.</span></span> <span data-ttu-id="6222d-172">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="6222d-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="6222d-173">b.</span><span class="sxs-lookup"><span data-stu-id="6222d-173">b.</span></span> <span data-ttu-id="6222d-174">**選択されたユーザーまたはセキュリティグループ**</span><span class="sxs-lookup"><span data-stu-id="6222d-174">**Selected people or security groups**</span></span></br>

    ![トピックを管理する](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="6222d-176">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="6222d-177">トピックセンター名を更新する</span><span class="sxs-lookup"><span data-stu-id="6222d-177">Update your topic center name</span></span>

<span data-ttu-id="6222d-178">トピックセンターの名前を更新する場合は、[**トピックセンター** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="6222d-179">[**トピックセンター** ] タブの [**トピックセンター名**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6222d-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="6222d-180">[**トピックセンター名の編集**] ページの [**トピックセンター名**] ボックスに、トピックセンターの新しい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6222d-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="6222d-181">**[保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="6222d-181">Select **Save**</span></span>

    ![トピックセンターの名前を編集する](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="6222d-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="6222d-183">See also</span></span>



  






