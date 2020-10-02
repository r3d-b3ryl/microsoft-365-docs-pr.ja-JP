---
title: Microsoft SharePoint Syntexでコンテンツセンターを作成する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: コンテンツセンターを作成する方法を説明します。
ms.openlocfilehash: f65b542dfe9cbb945f347323053cee582deef25b
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321835"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="163fa-103">Microsoft SharePoint Syntexでコンテンツセンターを作成する</span><span class="sxs-lookup"><span data-stu-id="163fa-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="163fa-104">ドキュメント理解モデルを作成および管理するには、まずコンテンツ センターが必要です。</span><span class="sxs-lookup"><span data-stu-id="163fa-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="163fa-105">コンテンツ センターはモデル作成インターフェイスであり、公開されたモデルが適用されたドキュメント ライブラリに関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="163fa-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![ドキュメントライブラリを選択する](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="163fa-107">[セットアップ](set-up-content-understanding.md)中に既定のコンテンツ センターを作成します。</span><span class="sxs-lookup"><span data-stu-id="163fa-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="163fa-108">ただし、SharePoint 管理者は、必要に応じて追加のセンターを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="163fa-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="163fa-109">すべてのモデル アクティビティをロールアップする環境では単一のコンテンツ センターで十分な場合もありますが、組織内の複数の部門に追加のセンターを用意することもできます。これらの部門では、モデルのニーズと権限要件が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="163fa-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="163fa-110">SharePoint 管理者は、管理センター サイトプ ロビジョニング パネルを介して[他のSharePoint サイトを作成する](https://docs.microsoft.com/sharepoint/create-site-collection)のと同じように、コンテンツ センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="163fa-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="163fa-111">新しいコンテンツ センターを作成するには</span><span class="sxs-lookup"><span data-stu-id="163fa-111">To create a new content center:</span></span>

1. <span data-ttu-id="163fa-112">Microsoft 365 管理センターで、SharePoint 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="163fa-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="163fa-113">SharePoint 管理センターの [**サイト**] で、[**アクティブなサイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="163fa-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="163fa-114">[**アクティブなサイト**] ページで、[**作成**] をクリックし、[**その他のオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="163fa-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="163fa-115">[**テンプレートの選択**] メニューで、[**コンテンツセンター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="163fa-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="163fa-116">新しいサイトの場合は、**サイト名**、**プライマリ管理者**、および**言語**を指定します。</span><span class="sxs-lookup"><span data-stu-id="163fa-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="163fa-117">コンテンツ センター サイトを選択して、使用可能な任意の言語で表示できますが、現在、モデルは英語のファイルに対してのみ作成できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="163fa-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="163fa-118">また、他のサイト テンプレートと同様に、サイトの作成後に既定のサイトの言語を編集できないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="163fa-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="163fa-119">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="163fa-119">Select **Finished**.</span></span>
 
<span data-ttu-id="163fa-120">コンテンツセンターサイトを作成すると、SharePoint 管理センターの [**アクティブなサイト**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="163fa-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="163fa-121">追加のユーザーにアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="163fa-121">Give access to additional users</span></span>
 
<span data-ttu-id="163fa-122">サイトを作成した後、標準の [SharePoint サイト アクセス許可モデル](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)を使用して、追加のユーザーにサイトへのアクセスを許可できます。</span><span class="sxs-lookup"><span data-stu-id="163fa-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="163fa-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="163fa-123">See Also</span></span>
[<span data-ttu-id="163fa-124">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="163fa-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="163fa-125">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="163fa-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="163fa-126">コンテンツ センターを作成する</span><span class="sxs-lookup"><span data-stu-id="163fa-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="163fa-127">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="163fa-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="163fa-128">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="163fa-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="163fa-129">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="163fa-129">Apply a model</span></span>](apply-a-model.md)    
