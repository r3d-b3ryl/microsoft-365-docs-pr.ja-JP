---
title: SharePoint Syntex での画像のタグ付け
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: SharePoint Syntex での画像のタグ付けに関する詳細
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296093"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="ab2d8-103">SharePoint Syntex での画像のタグ付け</span><span class="sxs-lookup"><span data-stu-id="ab2d8-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="ab2d8-104">既定では、SharePoint と OneDrive での基本的な画像のタグ付けはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="ab2d8-105">いずれかの場所にアップロードされた画像は自動的にスキャンされ、37 個の基本タグのリストから該当するタグが適用されます (可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="ab2d8-106">ユーザーは、画像タグを検索することで画像を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="ab2d8-107">ユーザーが画像をアップロードすると、タグ付けプロセスが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="ab2d8-108">画像が編集されると、タグ付けプロセスが再度実行され、タグが更新されます。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="ab2d8-109">画像ファイルへのアクセス許可を持つユーザーは、ファイル情報パネルまたは検索結果ページでタグを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="ab2d8-110">ユーザーが画像のタグを編集すると、編集された場合でも、システムはその画像に対して自動タグ付けを実行しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="ab2d8-111">タグ付けをオフにすると、画像に自動的にタグが付けられなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="ab2d8-112">既存のタグは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="ab2d8-113">画像のタグ付けを構成する</span><span class="sxs-lookup"><span data-stu-id="ab2d8-113">Configure image tagging</span></span>

<span data-ttu-id="ab2d8-114">Microsoft365 管理センターで画像のタグ付けを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="ab2d8-115">画像のタグ付けをオンまたはオフにするには</span><span class="sxs-lookup"><span data-stu-id="ab2d8-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="ab2d8-116">Microsoft 365 管理センターで、[**セットアップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="ab2d8-117">**[組織における知識]** の下で、**[コンテンツの理解を自動化する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="ab2d8-118">**[管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-118">Click **Manage**.</span></span>

4. <span data-ttu-id="ab2d8-119">**[画像のタグ付け]** タブで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="ab2d8-120">**[基本的なタグ付け]** を許可するか、タグ付けを **[オフ]** にするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="ab2d8-121">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab2d8-121">Click **Save**.</span></span>

    ![画像のタグ付けコントロールのスクリーンショット](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="ab2d8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab2d8-123">See also</span></span>

[<span data-ttu-id="ab2d8-124">コンテンツの理解をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ab2d8-124">Set up content understanding</span></span>](set-up-content-understanding.md)