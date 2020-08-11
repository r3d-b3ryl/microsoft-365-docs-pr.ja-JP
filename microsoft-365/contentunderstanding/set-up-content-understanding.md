---
title: 'コンテンツの理解を設定する (プレビュー) '
description: プロジェクト Cortex をセットアップする方法について説明します。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612704"
---
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="61c79-103">コンテンツの理解を設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="61c79-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="61c79-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="61c79-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="61c79-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c79-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="61c79-106">管理者は、Microsoft 365 管理センターを使用して、コンテンツの理解を設定し、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="61c79-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="61c79-107">セットアップの前に、環境内のコンテンツの理解を設定して構成するための最善の方法を計画してください。</span><span class="sxs-lookup"><span data-stu-id="61c79-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="61c79-108">たとえば、次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c79-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="61c79-109">どの SharePoint サイトでフォーム処理を有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="61c79-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="61c79-110">すべてのサイト、一部、またはサイトの選択</span><span class="sxs-lookup"><span data-stu-id="61c79-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="61c79-111">コンテンツセンターの名前、およびプライマリサイト管理者は誰ですか。</span><span class="sxs-lookup"><span data-stu-id="61c79-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="61c79-112">管理者は、コンテンツのセットアップ後に、選択した設定を変更して、Microsoft 365 管理センターの管理設定を理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="61c79-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="61c79-113">Requirements</span><span class="sxs-lookup"><span data-stu-id="61c79-113">Requirements</span></span> 
<span data-ttu-id="61c79-114">Microsoft 365 管理センターにアクセスし、コンテンツの理解を設定するには、グローバル管理者または SharePoint 管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c79-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="61c79-115">コンテンツの理解を設定するには</span><span class="sxs-lookup"><span data-stu-id="61c79-115">To set up content understanding</span></span>

1. <span data-ttu-id="61c79-116">Microsoft 365 管理センターで、[**セットアップ**] を選択し、[**組織ナレッジ**] セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="61c79-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="61c79-117">[**組織ナレッジ**] セクションで、[**コンテンツの理解を自動化**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61c79-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![組織ナレッジの設定ページ](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="61c79-119">[**コンテンツを自動的に理解**する] ページで、[**開始**] をクリックして、セットアッププロセスを案内します。</span><span class="sxs-lookup"><span data-stu-id="61c79-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![セットアップの開始](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="61c79-121">[**フォーム処理の構成**] ページで、ユーザーが AI ビルダーを使用して、特定の SharePoint ドキュメントライブラリのフォーム処理モデルを作成できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="61c79-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="61c79-122">[ドキュメントライブラリ] リボンでメニューオプションを使用して、フォーム処理モデルが有効になっている SharePoint ドキュメントライブラリに**フォーム処理モデルを作成**できます。</span><span class="sxs-lookup"><span data-stu-id="61c79-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="61c79-123">**フォーム処理モデルを作成するためのオプションをどの SharePoint ライブラリに表示するかを指定**するには、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="61c79-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="61c79-124">テナント内のすべての SharePoint ライブラリで利用できるようにするための**すべての sharepoint ライブラリ**。</span><span class="sxs-lookup"><span data-stu-id="61c79-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="61c79-125">[**選択したサイトのライブラリのみ**] を選択し、使用できるようにするサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="61c79-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="61c79-126">現在、どのサイトでも使用できるようにしない場合は、 **SharePoint ライブラリはありません**(セットアップ後に変更できます)。</span><span class="sxs-lookup"><span data-stu-id="61c79-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="61c79-127">![フォーム処理を構成する](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="61c79-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="61c79-128">SharePoint ドキュメントライブラリでこの設定を有効にしても、ライブラリに適用されている既存のモデル、またはドキュメントを認識するモデルをライブラリに適用する機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="61c79-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="61c79-129">[**コンテンツセンターの作成**] ページで、ユーザーがドキュメントを作成および管理できる SharePoint コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61c79-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="61c79-130">a.</span><span class="sxs-lookup"><span data-stu-id="61c79-130">a.</span></span> <span data-ttu-id="61c79-131">[**サイト名**] に、コンテンツセンターサイトに付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="61c79-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="61c79-132">b.</span><span class="sxs-lookup"><span data-stu-id="61c79-132">b.</span></span> <span data-ttu-id="61c79-133">サイト**アドレス**には、サイト名に対して選択した内容に基づいてサイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61c79-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="61c79-134">サポートされている言語を選択することはできますが、モデルを理解しているのは英語版のコンテンツのみを作成できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61c79-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![コンテンツセンターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="61c79-136">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61c79-136">Select **Next**.</span></span>
6. <span data-ttu-id="61c79-137">[**完了と確認**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="61c79-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="61c79-138">選択内容に問題がなければ、[**アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61c79-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="61c79-139">コンテンツを理解すると、**アクティブ化**されたページが表示され、システムがフォーム処理の設定を追加し、コンテンツセンターサイトを作成したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="61c79-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="61c79-140">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61c79-140">Select **Done**.</span></span>

8. <span data-ttu-id="61c79-141">**コンテンツの自動理解**ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="61c79-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="61c79-142">このページでは、[**管理**] を選択して構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="61c79-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="61c79-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="61c79-143">See also</span></span>



  






