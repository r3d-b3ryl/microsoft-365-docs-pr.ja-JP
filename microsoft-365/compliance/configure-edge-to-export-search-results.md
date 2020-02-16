---
title: Microsoft Edge で Office 365 eDiscovery エクスポートツールを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Edge を使用して、セキュリティ/コンプライアンスセンターでコンテンツ検索および電子情報開示から検索結果をエクスポートするには、ClickOnce サポートを有効にする必要があります。
ms.openlocfilehash: db70b4cdbc57f519db3b6b962eb8aa43585ba335
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078584"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="de6fd-103">Microsoft Edge で Office 365 eDiscovery エクスポートツールを使用する</span><span class="sxs-lookup"><span data-stu-id="de6fd-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="de6fd-104">Microsoft Edge に対する最近の変更の結果として、ClickOnce のサポートは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="de6fd-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="de6fd-105">Microsoft Office 365 eDiscovery エクスポートツールを引き続き使用して、コンテンツ検索や電子情報開示の検索結果をダウンロードするには、microsoft [Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)を使用するか、microsoft Edge で ClickOnce サポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6fd-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="de6fd-106">Microsoft Edge で ClickOnce サポートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="de6fd-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="de6fd-107">Microsoft Edge で、 **edge://flags/#edge**に移動します。</span><span class="sxs-lookup"><span data-stu-id="de6fd-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="de6fd-108">ドロップダウンリストで既存の値が**Default**または**Disabled**に設定されている場合は、[**有効**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="de6fd-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="de6fd-109">ブラウザーウィンドウの一番下までスクロールし、[**再起動**] をクリックして、エッジを再起動します。</span><span class="sxs-lookup"><span data-stu-id="de6fd-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="de6fd-110">**注:** 組織は、グループポリシーを使用して ClickOnce サポートを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="de6fd-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="de6fd-111">ClickOnce サポート用の組織ポリシーがあるかどうかを確認するには、 **edge://policy**に移動します。</span><span class="sxs-lookup"><span data-stu-id="de6fd-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="de6fd-112">次のスクリーンショットは、組織全体で ClickOnce が有効になっていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="de6fd-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="de6fd-113">このポリシー値が**false**に設定されている場合は、組織の管理者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6fd-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="de6fd-114">Office 365 eDiscovery エクスポートツールをインストールして実行する</span><span class="sxs-lookup"><span data-stu-id="de6fd-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="de6fd-115">コンテンツ検索または電子情報開示ケースのエクスポートのポップアップページにある [**結果のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de6fd-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![検索結果をダウンロードするには、ポップアップページの [結果のダウンロード] をクリックします。](../media/ClickOnceExport1.png)

2. <span data-ttu-id="de6fd-117">ツールを起動するかどうかを確認するメッセージが表示されたら、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de6fd-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![[開く] をクリックして電子情報開示エクスポートツールを起動します。](../media/ClickOnceimage4.png)

   <span data-ttu-id="de6fd-119">Microsoft Office 365 eDiscovery エクスポートツールがインストールされていない場合は、セキュリティの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de6fd-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![[インストール] をクリックして電子情報開示エクスポートツールをインストールします。](../media/ClickOnceimage5.png)

3. <span data-ttu-id="de6fd-121">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de6fd-121">Click **Install**.</span></span> <span data-ttu-id="de6fd-122">インストール後、エクスポートツールが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="de6fd-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="de6fd-123">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="de6fd-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de6fd-124">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="de6fd-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="de6fd-125">Microsoft Edge で実験フラグを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="de6fd-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
