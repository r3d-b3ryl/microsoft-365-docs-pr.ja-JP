---
title: Microsoft 365 にドメインを接続する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: ドメインをドメインに接続する方法についてMicrosoft 365。
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925112"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="b81e4-103">Connectをビジネス向Microsoft 365に設定する</span><span class="sxs-lookup"><span data-stu-id="b81e4-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="b81e4-104">Google Workspace からメール データMicrosoft 365設定して移動したら、ドメインをユーザーに接続Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b81e4-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="b81e4-105">まず、Google から既存の DNS レコードを削除する必要があります。次に、新しい DNS レコードを新しい DNS レコードから追加Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b81e4-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="b81e4-106">お試しください!</span><span class="sxs-lookup"><span data-stu-id="b81e4-106">Try it!</span></span>

1. <span data-ttu-id="b81e4-107">Google Workspace 管理コンソールにサインインするには[、admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="b81e4-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="b81e4-108">[**ドメイン] 、[\*\*\*\*ドメインの管理]**、[**詳細の** 表示] 、[**ドメインの管理**] の順に選択し、**左側のナビゲーションで DNS** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="b81e4-109">下にスクロールして **代理レコードに移動し\*\*\*\*、Google ワークスペースを開** き、[削除 **]** を選択し、もう一 **度削除** します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="b81e4-110">[カスタム リソース レコード **]** まで下にスクロールし、表示される既存の DNS レコード (以前に作成した DNS レコードを含む) を削除Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b81e4-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="b81e4-111">
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。</span><span class="sxs-lookup"><span data-stu-id="b81e4-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b81e4-112">左側のナビゲーションで、[すべて表示] **、[** ドメイン] 設定 **を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="b81e4-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="b81e4-113">次に、既定のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="b81e4-114">[セットアップ **の続行]** を選択し、ドメインを接続するには、[続行] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b81e4-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="b81e4-115">下にスクロールして、Google にコピーする必要がある DNS レコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="b81e4-116">[MX **レコード] を開** き、[ **ポイント先アドレスまたは値] で** レコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b81e4-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="b81e4-117">Google に戻り、[ユーザー設定のリソース レコード **] セクション** で、レコードの種類ドロップダウンを開き **、[MX]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="b81e4-118">[データ **] フィールド** に、コピーしたレコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b81e4-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="b81e4-119">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-119">Then select **Add**.</span></span>
1. <span data-ttu-id="b81e4-120">CNAME レコードと TXT レコードの処理を繰り返し、Google DNS 管理ページに値を追加します。</span><span class="sxs-lookup"><span data-stu-id="b81e4-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="b81e4-121">管理センターに戻り、[続行Microsoft 365を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="b81e4-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="b81e4-122">ドメインのセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="b81e4-122">Your domain setup is complete.</span></span>