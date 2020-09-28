---
title: コンテンツタイプをハブにプッシュする
description: コンテンツタイプをハブにプッシュする方法について説明します。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296102"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="56098-103">コンテンツタイプをハブにプッシュする</span><span class="sxs-lookup"><span data-stu-id="56098-103">Push content types to a hub</span></span>

<span data-ttu-id="56098-104">SharePoint ライブラリとリストで重要なコンテンツタイプをより一貫して利用できるようにするには、選択したハブにそれらをプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="56098-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="56098-105">これにより、ハブに関連付けられたサイトで作成されたすべての新しいリストとライブラリ、およびハブに追加された新しいサイトに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="56098-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="56098-106">この機能を使用するには、プッシュされるコンテンツタイプが既に公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="56098-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="56098-107">コンテンツタイプをハブにプッシュするには</span><span class="sxs-lookup"><span data-stu-id="56098-107">To push content types to hubs</span></span>

1. <span data-ttu-id="56098-108">SharePoint 管理センターで、[ **コンテンツサービス**] を展開し、[ **コンテンツタイプギャラリー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56098-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="56098-109">ハブにプッシュするコンテンツタイプをクリックします。</span><span class="sxs-lookup"><span data-stu-id="56098-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="56098-110">コマンドバーの [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56098-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="56098-111">[ **ハブサイトの選択] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="56098-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="56098-112">目的のハブサイトを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56098-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="56098-113">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56098-113">Click **Save**.</span></span>

<span data-ttu-id="56098-114">既存のハブにコンテンツタイプを最初に関連付け &、そのサイトの設定を更新するために、ハブまたは関連付けられたサイトがアクセスされるまでに最大1時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="56098-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="56098-115">ハブに新たに関連付けを行う場合、この待機は必要ありません。設定は数分で反映されます。</span><span class="sxs-lookup"><span data-stu-id="56098-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="56098-116">これを構成すると、これらの設定を持つコンテンツタイプが、ハブを使用して数分で新たに関連付けられた任意のサイトで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="56098-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="56098-117">利用可能になると、作成された新しいリストまたはライブラリのコンテンツタイプが、作成から数分以内に自動的に追加されるようになります。</span><span class="sxs-lookup"><span data-stu-id="56098-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="56098-118">プッシュされたコンテンツタイプは、ドキュメントコンテンツタイプから直接または間接的に派生している場合にのみ、ドキュメントライブラリに追加されます。コンテンツタイプは、ドキュメントコンテンツタイプから直接または間接的に派生していない場合にのみ、リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="56098-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="56098-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="56098-119">See also</span></span>



  






