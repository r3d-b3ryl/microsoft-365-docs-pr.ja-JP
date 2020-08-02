---
title: コンテンツセンターを作成する (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: コンテンツセンターを作成する方法について説明します。
ms.openlocfilehash: ced47f8029079910479dd9aa5c43b39870a56aea
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537569"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="149a1-103">コンテンツセンターを作成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="149a1-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="149a1-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="149a1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="149a1-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="149a1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="149a1-106">ドキュメントを作成および管理するには、まずコンテンツセンターが必要です。</span><span class="sxs-lookup"><span data-stu-id="149a1-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="149a1-107">コンテンツセンターはモデル作成インターフェイスで、どのドキュメントライブラリ発行モデルが適用されたかに関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="149a1-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![ドキュメントライブラリを選択する](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="149a1-109">初期コンテンツセンターは[セットアップ](set-up-content-understanding.md)中に作成されますが、SharePoint 管理者は必要に応じて追加のコンテンツセンターを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="149a1-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="149a1-110">すべてのモデルアクティビティのロールアップを表示する必要がある環境では、単一のコンテンツセンターが適している場合がありますが、組織内に複数の部署があり、そのモデルのニーズや要件が異なる場合は、それを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="149a1-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="149a1-111">SharePoint 管理者は、サイトテンプレートを使用して[他の sharepoint サイトを作成するの](https://docs.microsoft.com/sharepoint/create-site-collection)と同じように、コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="149a1-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="149a1-112">新しいコンテンツセンターを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="149a1-112">To create a new content center:</span></span>

1. <span data-ttu-id="149a1-113">Microsoft 365 管理センターで、SharePoint 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="149a1-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="149a1-114">SharePoint 管理センターの [**サイト**] で、[**アクティブなサイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="149a1-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="149a1-115">[**アクティブなサイト**] ページで、[**作成**] をクリックし、[**その他のオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="149a1-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="149a1-116">[**テンプレートの選択**] メニューで、[**コンテンツセンター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="149a1-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="149a1-117">新しいサイトの場合は、**サイト名**、**プライマリ管理者**、および**言語**を指定します。</span><span class="sxs-lookup"><span data-stu-id="149a1-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="149a1-118">コンテンツセンターサイトを選択して、使用可能な任意の言語で表示することができますが、現在のモデルは英語ファイルに対してのみ作成できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="149a1-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="149a1-119">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="149a1-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="149a1-120">他のユーザーへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="149a1-120">Give access to additional users</span></span>
 
<span data-ttu-id="149a1-121">サイトを作成した後は、SharePoint サイトの標準の[アクセス許可モデル](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)を使用して、そのサイトへのアクセス権をユーザーに付与できます。</span><span class="sxs-lookup"><span data-stu-id="149a1-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="149a1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="149a1-122">See Also</span></span>
[<span data-ttu-id="149a1-123">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="149a1-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="149a1-124">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="149a1-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="149a1-125">[コンテンツセンター](create-a-content-center.md) 
 を作成する[ドキュメント理解の概要](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="149a1-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="149a1-126">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="149a1-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="149a1-127">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="149a1-127">Apply a model</span></span>](apply-a-model.md)    




