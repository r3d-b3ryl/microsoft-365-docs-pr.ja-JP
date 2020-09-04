---
title: Microsoft Edge で電子情報開示エクスポートツールを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Edge の最新バージョンを使用して、セキュリティ/コンプライアンスセンターでコンテンツ検索と電子情報開示から検索結果をダウンロードするには、ClickOnce サポートを有効にする必要があります。
ms.openlocfilehash: 317e19c81a606565fcb18f3256fd5bac007747e1
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357577"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="13d4c-103">Microsoft Edge で電子情報開示エクスポートツールを使用する</span><span class="sxs-lookup"><span data-stu-id="13d4c-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="13d4c-104">最新バージョンの Microsoft Edge に対する最近の変更の結果として、ClickOnce サポートは既定で有効になりません。</span><span class="sxs-lookup"><span data-stu-id="13d4c-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="13d4c-105">コンテンツ検索や電子情報開示の検索結果をダウンロードするために電子情報開示のエクスポートツールを引き続き使用するには、microsoft [Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) を使用するか、microsoft Edge の最新バージョンで ClickOnce サポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4c-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="13d4c-106">Microsoft Edge で ClickOnce サポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="13d4c-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="13d4c-107">Microsoft Edge で、 **[edge://flags/#edge]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="13d4c-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="13d4c-108">ドロップダウンリストで既存の値が **Default** または **Disabled** に設定されている場合は、[ **有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="13d4c-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![[有効] ドロップダウンリスト](../media/ClickOnceimage1.png)

3. <span data-ttu-id="13d4c-110">ブラウザーウィンドウの一番下までスクロールし、[ **再起動** ] をクリックして、エッジを再起動します。</span><span class="sxs-lookup"><span data-stu-id="13d4c-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![[再起動] をクリックします](../media/ClickOnceimage2.png)

<span data-ttu-id="13d4c-112">**注:** 組織は、グループポリシーを使用して ClickOnce サポートを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="13d4c-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="13d4c-113">ClickOnce サポート用の組織ポリシーがあるかどうかを確認するには、 **edge://policy**に移動します。</span><span class="sxs-lookup"><span data-stu-id="13d4c-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="13d4c-114">次のスクリーンショットは、組織全体で ClickOnce が有効になっていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="13d4c-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="13d4c-115">このポリシー値が **false**に設定されている場合は、組織の管理者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4c-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![エッジ組織ポリシーの一覧](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="13d4c-117">電子情報開示エクスポートツールをインストールして実行する</span><span class="sxs-lookup"><span data-stu-id="13d4c-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="13d4c-118">コンテンツ検索または電子情報開示ケースのエクスポートのポップアップページにある [ **結果のダウンロード** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13d4c-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![検索結果をダウンロードするには、ポップアップページの [結果のダウンロード] をクリックします。](../media/ClickOnceExport1.png)

2. <span data-ttu-id="13d4c-120">ツールを起動するかどうかを確認するメッセージが表示されたら、[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13d4c-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![[開く] をクリックして電子情報開示エクスポートツールを起動します。](../media/ClickOnceimage4.png)

   <span data-ttu-id="13d4c-122">電子情報開示エクスポートツールがインストールされていない場合は、セキュリティの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13d4c-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![[インストール] をクリックして電子情報開示エクスポートツールをインストールします。](../media/ClickOnceimage5.png)

3. <span data-ttu-id="13d4c-124">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13d4c-124">Click **Install**.</span></span> <span data-ttu-id="13d4c-125">インストール後、エクスポートツールが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="13d4c-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="13d4c-126">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13d4c-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="13d4c-127">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="13d4c-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="13d4c-128">Microsoft Edge で実験フラグを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="13d4c-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
