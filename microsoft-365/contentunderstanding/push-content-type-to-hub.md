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
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975717"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="0c9ce-103">コンテンツ タイプをハブにプッシュする</span><span class="sxs-lookup"><span data-stu-id="0c9ce-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="0c9ce-104">重要なコンテンツ タイプを SharePoint ライブラリとリストでより一貫して利用できるようにするために、選択したハブにそれらをプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="0c9ce-105">コンテンツ タイプをプッシュすることで、ハブに関連付けられたサイトで作成された新しいリストとライブラリ、およびハブに追加された新しいサイトにそれらが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="0c9ce-106">この機能を使用するには、プッシュされるコンテンツ タイプがすでに公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-106">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="0c9ce-107">コンテンツ タイプをハブにプッシュするには</span><span class="sxs-lookup"><span data-stu-id="0c9ce-107">To push content types to hubs</span></span>

1. <span data-ttu-id="0c9ce-108">SharePoint 管理センターで、[**コンテンツ サービス**] を展開し、[**コンテンツ タイプ ギャラリー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-108">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="0c9ce-109">ハブにプッシュするコンテンツ タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-109">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="0c9ce-110">コマンド バーの [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-110">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="0c9ce-111">[**ハブ サイトの選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-111">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="0c9ce-112">必要なハブ サイトを選択し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-112">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="0c9ce-113">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-113">Choose **Save**.</span></span>

<span data-ttu-id="0c9ce-114">コンテンツ タイプを既存のハブとその既存の関連サイトに初めてプッシュする場合、ハブまたは関連サイトにアクセスしてからサイトの設定が更新されるまでに最大 1 時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-114">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="0c9ce-115">ハブに新たに関連付けを行う場合、この待機は必要ありません。この設定は数分間で反映されます。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-115">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="0c9ce-116">設定が更新されると、これらの設定のコンテンツ タイプは、数分でハブに新しく関連付けられたサイトで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-116">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="0c9ce-117">その後、作成された新しいリストまたはライブラリには、作成後数分以内にコンテンツ タイプが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-117">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="0c9ce-118">プッシュされたコンテンツ タイプは、ドキュメント コンテンツ タイプから直接または間接的に派生した場合にのみドキュメント ライブラリに追加され、コンテンツ タイプは、ドキュメント コンテンツ タイプから直接または間接的に派生しない場合にのみリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0c9ce-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c9ce-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c9ce-119">See also</span></span>
