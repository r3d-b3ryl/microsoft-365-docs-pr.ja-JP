---
title: SharePoint Syntex での画像のタグ付け
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: SharePoint Syntex での画像のタグ付けに関する詳細
ms.openlocfilehash: c6d7513db2fd6aadabe5d813f3b49073a8f8c933
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413736"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="9fd24-103">SharePoint Syntex での画像のタグ付け</span><span class="sxs-lookup"><span data-stu-id="9fd24-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="9fd24-104">(近日公開予定)</span><span class="sxs-lookup"><span data-stu-id="9fd24-104">(Coming soon)</span></span>

<span data-ttu-id="9fd24-105">SharePoint Syntex での画像のタグ付けを使って、ユーザーは、画像タグを検索することで画像を見つけることができ、画像タグを使ってワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9fd24-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="9fd24-106">既定では、SharePoint と OneDrive での基本的な画像のタグ付けはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9fd24-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="9fd24-107">いずれかの場所にアップロードされた画像は自動的にスキャンされ、37 個の基本タグのリストから該当するタグが適用されます (可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="9fd24-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="9fd24-108">ユーザーは、画像タグを検索することで画像を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="9fd24-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="9fd24-109">ユーザーが画像をアップロードすると、タグ付けプロセスが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="9fd24-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="9fd24-110">画像が編集されると、タグ付けプロセスが再度実行され、タグが更新されます。</span><span class="sxs-lookup"><span data-stu-id="9fd24-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="9fd24-111">画像ファイルへのアクセス許可を持つユーザーは、ファイル情報パネルまたは検索結果ページでタグを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="9fd24-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="9fd24-112">ユーザーが画像のタグを編集すると、編集されている場合でも、システムはその画像に自動タグ付けを実行しなくなります。</span><span class="sxs-lookup"><span data-stu-id="9fd24-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="9fd24-113">タグ付けをオフにすると、画像に自動的にタグ付けされなくなります。</span><span class="sxs-lookup"><span data-stu-id="9fd24-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="9fd24-114">既存のタグは削除されません。</span><span class="sxs-lookup"><span data-stu-id="9fd24-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="9fd24-115">システム生成のタグは、画像またはタグ技術の更新プログラムで変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fd24-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="9fd24-116">画像のタグ付けを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd24-116">Configure image tagging</span></span>

<span data-ttu-id="9fd24-117">[SharePoint Syntex の設定](set-up-content-understanding.md)をすると、Microsoft 365 管理センターで画像のタグ付けを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9fd24-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="9fd24-118">画像のタグ付けをオンまたはオフにするには</span><span class="sxs-lookup"><span data-stu-id="9fd24-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="9fd24-119">Microsoft 365 管理センターで、[**セットアップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fd24-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="9fd24-120">**[組織における知識]** の下で、**[コンテンツの理解を自動化する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fd24-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="9fd24-121">**[管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fd24-121">Click **Manage**.</span></span>

4. <span data-ttu-id="9fd24-122">**[画像のタグ付け]** タブで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fd24-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="9fd24-123">**[基本的なタグ付け]** を許可するか、タグ付けを **[オフ]** にするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9fd24-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="9fd24-124">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fd24-124">Click **Save**.</span></span>

    ![画像のタグ付けコントロールのスクリーンショット](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
