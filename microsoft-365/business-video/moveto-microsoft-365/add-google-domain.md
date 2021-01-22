---
title: Google Workspace ドメインを追加する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Google Workspace から Microsoft 365 for business にドメインを移動する方法について説明します。
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925004"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="40876-103">Google Workspace ドメインを Microsoft 365 に追加する</span><span class="sxs-lookup"><span data-stu-id="40876-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="40876-104">Google Workspace ドメインを Microsoft 365 for business に追加して、ビジネス メール アドレスを使用し続けできます。</span><span class="sxs-lookup"><span data-stu-id="40876-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="40876-105">演習</span><span class="sxs-lookup"><span data-stu-id="40876-105">Try it!</span></span>

1. <span data-ttu-id="40876-106">
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。</span><span class="sxs-lookup"><span data-stu-id="40876-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="40876-107">Microsoft 365 管理センターの左側のナビゲーションで、[すべて表示]、[設定]、次に [ドメイン] の順 **に選択します**。 </span><span class="sxs-lookup"><span data-stu-id="40876-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="40876-108">Choose **Add domain,** enter your domain name then select **Use this domain**.</span><span class="sxs-lookup"><span data-stu-id="40876-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="40876-109">Choose, **Add a TXT record to the domains DNS records,** select **Continue,** and copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="40876-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="40876-110">[Google](https://admin.google.com)管理コンソールに戻り、[ドメイン]、[ドメインの管理]、[詳細の表示]、[ドメインの管理 **]、DNS** の順に選択し、下にスクロールしてカスタム リソース レコードを **表示します**。 </span><span class="sxs-lookup"><span data-stu-id="40876-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="40876-111">Open the record type drop-down, choose **TXT,** paste the TXT value you copied then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="40876-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="40876-112">通常、更新には数分かかりますが、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40876-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="40876-113">Microsoft 365 管理センターに戻り、[確認] を **選択し、[** 閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="40876-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="40876-114">ドメインをユーザーのプライマリ メールとして設定するには、左側のナビゲーションで [**ユーザー** アクティブ ユーザー]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="40876-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="40876-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span><span class="sxs-lookup"><span data-stu-id="40876-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="40876-116">ユーザーごとにこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="40876-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="40876-117">完了したら、メール アプリをインストールし、Officeアイテムを Microsoft 365 に移行する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="40876-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 