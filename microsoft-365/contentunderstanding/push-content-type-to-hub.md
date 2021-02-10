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
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144973"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="7b768-103">コンテンツ タイプをハブにプッシュする</span><span class="sxs-lookup"><span data-stu-id="7b768-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="7b768-104">重要なコンテンツ タイプを SharePoint ライブラリとリストでより一貫して利用できるようにするために、選択したハブにそれらをプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="7b768-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="7b768-105">コンテンツ タイプをプッシュすることで、ハブに関連付けられたサイトで作成された新しいリストとライブラリ、およびハブに追加された新しいサイトにそれらが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7b768-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span> <span data-ttu-id="7b768-106">この機能には、[SharePoint Syntex](index.md) ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b768-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="7b768-107">この機能を使用するには、プッシュされるコンテンツ タイプがすでに公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b768-107">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="7b768-108">コンテンツ タイプをハブにプッシュするには</span><span class="sxs-lookup"><span data-stu-id="7b768-108">To push content types to hubs</span></span>

1. <span data-ttu-id="7b768-109">SharePoint 管理センターで、[**コンテンツ サービス**] を展開し、[**コンテンツ タイプ ギャラリー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b768-109">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="7b768-110">ハブにプッシュするコンテンツ タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b768-110">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="7b768-111">コマンド バーの [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b768-111">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="7b768-112">[**ハブ サイトの選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b768-112">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="7b768-113">必要なハブ サイトを選択し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b768-113">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="7b768-114">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b768-114">Choose **Save**.</span></span>

<span data-ttu-id="7b768-115">コンテンツ タイプを既存のハブとその既存の関連サイトに初めてプッシュする場合、ハブまたは関連サイトにアクセスしてからサイトの設定が更新されるまでに最大 1 時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b768-115">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="7b768-116">ハブに新たに関連付けを行う場合、この待機は必要ありません。この設定は数分間で反映されます。</span><span class="sxs-lookup"><span data-stu-id="7b768-116">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="7b768-117">設定が更新されると、これらの設定のコンテンツ タイプは、数分でハブに新しく関連付けられたサイトで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7b768-117">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="7b768-118">その後、作成された新しいリストまたはライブラリには、作成後数分以内にコンテンツ タイプが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7b768-118">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="7b768-119">プッシュされたコンテンツ タイプは、ドキュメント コンテンツ タイプから直接または間接的に派生した場合にのみドキュメント ライブラリに追加され、コンテンツ タイプは、ドキュメント コンテンツ タイプから直接または間接的に派生しない場合にのみリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7b768-119">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b768-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b768-120">See also</span></span>
