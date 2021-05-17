---
title: Google ワークスペース ドメインを追加する
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: ドメインを Google ワークスペースからビジネス向けMicrosoft 365する方法について説明します。
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578773"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="782da-103">Google Workspace ドメインをユーザーに追加Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="782da-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="782da-104">ビジネス用に Google Workspace Microsoft 365を追加して、ビジネス 用のメール アドレスを使用し続けできます。</span><span class="sxs-lookup"><span data-stu-id="782da-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="782da-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="782da-105">Try it!</span></span>

1. <span data-ttu-id="782da-106">
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。</span><span class="sxs-lookup"><span data-stu-id="782da-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="782da-107">管理センター Microsoft 365左側のナビゲーションで、[すべて表示] を選択し、[ドメイン] 設定 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="782da-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="782da-108">[ **ドメインの追加] を** 選択し、ドメイン名を入力し、[このドメインを **使用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="782da-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="782da-109">[ドメイン **DNS レコードに TXT レコード** を追加する] を選択し、[続行] を選択 **し**、TXT 値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="782da-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="782da-110">[Google](https://admin.google.com)管理コンソールに戻り、[ドメイン] 、[ドメインの管理] 、[詳細の表示] 、[ドメインの管理] **、[DNS]** の順に選択し、[カスタム リソース レコード]**まで下にスクロールします**。 </span><span class="sxs-lookup"><span data-stu-id="782da-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="782da-111">[レコードの種類] ドロップダウンを開き **、[TXT]** を選択し、コピーした TXT 値を貼り付け、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="782da-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="782da-112">更新プログラムは通常、数分以内に事実を取るが、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="782da-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="782da-113">[管理センター] にMicrosoft 365し、[確認] を **選択し**、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="782da-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="782da-114">ユーザーのプライマリ メールとしてドメインを設定するには、左側のナビゲーションで [ユーザーのアクティブな **ユーザー**]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="782da-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="782da-115">ユーザーを選択し、[ユーザー名とメールの **管理**] 、[**編集**] を選択し、ドロップダウンからドメインを選択し、[完了] と [変更の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="782da-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="782da-116">ユーザーごとにこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="782da-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="782da-117">完了したら、アプリをインストールし、電子メールOffice予定表アイテムを別のアプリに移行するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="782da-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 