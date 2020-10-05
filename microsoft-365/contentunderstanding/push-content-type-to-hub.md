---
title: コンテンツ タイプをハブにプッシュする
description: コンテンツ タイプをハブにプッシュする方法を説明します
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 6adaef77f6989d541f8028252c5bb1ec7db7a6fc
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337195"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="76f06-103">コンテンツ タイプをハブにプッシュする</span><span class="sxs-lookup"><span data-stu-id="76f06-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="76f06-104">重要なコンテンツ タイプを SharePoint ライブラリとリストでより一貫して利用できるようにするために、選択したハブにそれらをプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="76f06-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="76f06-105">これにより、ハブに関連付けられたサイトで作成された新しいリストとライブラリ、およびハブに追加された新しいサイトにそれらが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="76f06-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="76f06-106">この機能を使用するには、プッシュされるコンテンツ タイプがすでに公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76f06-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="76f06-107">コンテンツ タイプをハブにプッシュするには</span><span class="sxs-lookup"><span data-stu-id="76f06-107">To push content types to hubs</span></span>

1. <span data-ttu-id="76f06-108">SharePoint 管理センターで、[**コンテンツ サービス**] を展開し、[**コンテンツ タイプ ギャラリー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f06-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="76f06-109">ハブにプッシュするコンテンツ タイプをクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f06-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="76f06-110">コマンド バーの [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f06-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="76f06-111">[**ハブ サイトの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f06-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="76f06-112">目的のハブ サイトを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f06-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="76f06-113">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f06-113">Click **Save**.</span></span>

<span data-ttu-id="76f06-114">コンテンツ タイプを既存のハブとその既存の関連サイトに初めてプッシュする場合、ハブまたは関連サイトにアクセスしてからサイトの設定が更新されるまでに最大 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="76f06-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="76f06-115">ハブに新たに関連付けを行う場合、この待機は必要ありません。この設定は数分間で反映されます。</span><span class="sxs-lookup"><span data-stu-id="76f06-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="76f06-116">構成が完了すると、これらの設定のコンテンツ タイプは、ハブに新しく関連付けられたサイトで数分で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="76f06-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="76f06-117">利用可能になると、作成された新しいリストまたはライブラリには、作成後数分以内にコンテンツ タイプが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="76f06-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="76f06-118">プッシュされたコンテンツ タイプは、ドキュメント コンテンツ タイプから直接または間接的に派生した場合にのみドキュメント ライブラリに追加され、コンテンツ タイプは、ドキュメント コンテンツ タイプから直接または間接的に派生しない場合にのみリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="76f06-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="76f06-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="76f06-119">See also</span></span>



  






