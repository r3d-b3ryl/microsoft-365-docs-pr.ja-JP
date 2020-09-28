---
title: Microsoft SharePoint の同期 Tex でコンテンツセンターを作成する
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: コンテンツセンターを作成する方法について説明します。
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295434"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="aab92-103">Microsoft SharePoint の同期 Tex でコンテンツセンターを作成する</span><span class="sxs-lookup"><span data-stu-id="aab92-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="aab92-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="aab92-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="aab92-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aab92-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="aab92-106">ドキュメントを作成および管理するには、まずコンテンツセンターが必要です。</span><span class="sxs-lookup"><span data-stu-id="aab92-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="aab92-107">コンテンツセンターはモデル作成インターフェイスで、ドキュメントライブラリに発行されたどのモデルが適用されているかに関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="aab92-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![ドキュメントライブラリを選択する](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="aab92-109">[セットアップ](set-up-content-understanding.md)時に最初のコンテンツセンターを作成します。</span><span class="sxs-lookup"><span data-stu-id="aab92-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="aab92-110">ただし、SharePoint 管理者は必要に応じて追加のセンターを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="aab92-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="aab92-111">すべてのモデルのアクティビティをロールアップする必要がある環境では、1つのコンテンツセンターが適している場合がありますが、組織内の複数の部門に対して追加のセンターが必要になる場合があります。これには、それぞれのモデルのニーズや要件が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aab92-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="aab92-112">SharePoint 管理者は、サイトテンプレートを使用して [他の sharepoint サイトを作成するの](https://docs.microsoft.com/sharepoint/create-site-collection) と同じように、コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aab92-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="aab92-113">新しいコンテンツセンターを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="aab92-113">To create a new content center:</span></span>

1. <span data-ttu-id="aab92-114">Microsoft 365 管理センターから、SharePoint 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="aab92-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="aab92-115">SharePoint 管理センターの [ **サイト**] で、[ **アクティブなサイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aab92-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="aab92-116">[ **アクティブなサイト** ] ページで、[ **作成**] をクリックし、[ **その他のオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aab92-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="aab92-117">[ **テンプレートの選択** ] メニューで、[ **コンテンツセンター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aab92-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="aab92-118">新しいサイトの場合は、 **サイト名**、 **プライマリ管理者**、および **言語**を指定します。</span><span class="sxs-lookup"><span data-stu-id="aab92-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="aab92-119">必要に応じて、コンテンツセンターサイトを選択して、使用可能な任意の言語で表示することができます。</span><span class="sxs-lookup"><span data-stu-id="aab92-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="aab92-120">英語のファイルには、現在のモデルのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aab92-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="aab92-121">[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aab92-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="aab92-122">他のユーザーへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="aab92-122">Give access to additional users</span></span>
 
<span data-ttu-id="aab92-123">サイトを作成した後、追加のユーザーに、標準の [SharePoint サイトアクセス許可モデル](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)を使用してサイトへのアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="aab92-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="aab92-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="aab92-124">See Also</span></span>
[<span data-ttu-id="aab92-125">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="aab92-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="aab92-126">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="aab92-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="aab92-127">[コンテンツセンター](create-a-content-center.md) 
 を作成する[ドキュメント理解の概要](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="aab92-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="aab92-128">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="aab92-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="aab92-129">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="aab92-129">Apply a model</span></span>](apply-a-model.md)    
