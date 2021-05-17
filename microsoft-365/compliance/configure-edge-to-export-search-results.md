---
title: '[電子情報開示のエクスポート ツール] を使用Microsoft Edge'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: セキュリティとコンプライアンス センター ClickOnceコンテンツ検索と電子情報開示から検索結果をダウンロードするには、Microsoft Edge の最新バージョンを使用するサポートを有効にする必要があります。
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546821"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="516fb-103">[電子情報開示のエクスポート ツール] を使用Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="516fb-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="516fb-104">最新バージョンのバージョンに対する最近の変更の結果Microsoft Edge、ClickOnceサポートは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="516fb-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="516fb-105">引き続き電子情報開示エクスポート ツールを使用してコンテンツ検索または電子情報開示検索結果をダウンロードするには[、Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)を使用するか、最新バージョンの Microsoft Edge で ClickOnce サポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="516fb-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="516fb-106">[ClickOnceでサポートを有効Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="516fb-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="516fb-107">[Microsoft Edge] に移動し、[edge://flags/#edge-click-once]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="516fb-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="516fb-108">ドロップダウン リストで既存の値が [ **既定** ] または [ **無効** ] に設定されている場合は、[有効] に **変更します**。</span><span class="sxs-lookup"><span data-stu-id="516fb-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![ドロップダウン リストから [有効] を選択します。](../media/ClickOnceimage1.png)

3. <span data-ttu-id="516fb-110">ブラウザー ウィンドウの下部まで下にスクロールし、[再起動] を **クリックしてエッジ** を再起動します。</span><span class="sxs-lookup"><span data-stu-id="516fb-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![[再起動] をクリックします。](../media/ClickOnceimage2.png)

<span data-ttu-id="516fb-112">**注:** 組織では、グループ ポリシーを使用して、サポートClickOnce無効にできます。</span><span class="sxs-lookup"><span data-stu-id="516fb-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="516fb-113">サポートに関する組織ポリシーがClickOnce、次の **edge://policy。**</span><span class="sxs-lookup"><span data-stu-id="516fb-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="516fb-114">次のスクリーンショットは、組織ClickOnceで有効になっているデータを示しています。</span><span class="sxs-lookup"><span data-stu-id="516fb-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="516fb-115">このポリシー値が false に **設定されている** 場合は、組織内の管理者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="516fb-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![エッジ組織ポリシーの一覧](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="516fb-117">電子情報開示エクスポート ツールのインストールと実行</span><span class="sxs-lookup"><span data-stu-id="516fb-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="516fb-118">コンテンツ **検索または電子** 情報開示ケースのエクスポートのフライアウト ページで、[結果のダウンロード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="516fb-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![[フライアウト] ページの [結果のダウンロード] をクリックして検索結果をダウンロードする](../media/ClickOnceExport1.png)

2. <span data-ttu-id="516fb-120">ツールを起動する確認メッセージが表示されます。[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="516fb-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![[開く] をクリックして電子情報開示エクスポート ツールを起動する](../media/ClickOnceimage4.png)

   <span data-ttu-id="516fb-122">電子情報開示エクスポート ツールがインストールされていない場合は、セキュリティ警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="516fb-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![[インストール] をクリックして電子情報開示エクスポート ツールをインストールする](../media/ClickOnceimage5.png)

3. <span data-ttu-id="516fb-124">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="516fb-124">Click **Install**.</span></span> <span data-ttu-id="516fb-125">インストール後、エクスポート ツールが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="516fb-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="516fb-126">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="516fb-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="516fb-127">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="516fb-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="516fb-128">テスト フラグを有効にするMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="516fb-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
