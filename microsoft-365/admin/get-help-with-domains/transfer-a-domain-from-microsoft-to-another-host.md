---
title: Microsoft から別のホストにドメインを移行する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'この記事では、Microsoft から別のレジストラーにドメインを移行するための手順について説明します。 '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370326"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="c2d9a-103">Microsoft から別のホストにドメインを移行する</span><span class="sxs-lookup"><span data-stu-id="c2d9a-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="c2d9a-104">Microsoft からドメインを購入した後、Microsoft 365 ドメインを別60のレジストラーに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="c2d9a-105">_Whois_   クエリは、Microsoft が購入したドメインレジストラーを「ワイルド (_ West Domains) ドメイン」として示しています。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="c2d9a-106">ただし、microsoft 365 の購入済みドメインについては、Microsoft のみに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="c2d9a-107">Microsoft 365 でコードを取得するには、次の手順に従います。その後、他のドメインレジストラー web サイトに移動して、ドメイン名を新しいレジストラーに転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="c2d9a-108">ドメインを転送する</span><span class="sxs-lookup"><span data-stu-id="c2d9a-108">Transfer a domain</span></span>

1. <span data-ttu-id="c2d9a-109">管理センターで、[  **設定**] [ドメイン] に移動し   >  **Domains**ます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="c2d9a-110">[ **ドメイン** ] ページで、別のドメインレジストラーに移行する Microsoft 365 ドメインを選択し、[状態の **確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="c2d9a-111">ページの上部で、[ドメインの **移行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="c2d9a-112">[ **ドメインを移行する場所を選択** してください] ページで、別の **レジストラー**を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="c2d9a-113">[**ドメイン転送のロック解除**] ページで、[ **_ドメイン_ > <の転送のロック解除**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="c2d9a-114">ドメイン転送の連絡先情報を確認し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="c2d9a-115">次の手順に進む前に、承認コードをコピーして、[**登録**] タブで**転送のロックが解除**されたことを示す30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="c2d9a-116">ドメイン名を今後も管理するドメインレジストラーの web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="c2d9a-117">ドメインを転送する手順に従います (web サイトでヘルプを検索)。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="c2d9a-118">これは通常、転送料金を支払い、新しいレジストラーに Authcode を提供して、ユーザーが転送を開始できるようにすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="c2d9a-119">転送要求を受信し、ドメインは5日以内に転送されることを確認するため、Microsoft からメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="c2d9a-120">[認証コードの **登録** ] タブは、Microsoft 365 の [  **ドメイン** ] ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c2d9a-121">uk ドメインには、別の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="c2d9a-122">Microsoft サポートに連絡して、ドメインの管理を行うレジストラーに一致するように **IPS タグの変更** を要求します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="c2d9a-123">タグが変更されると、ドメインはすぐに新しいレジストラーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="c2d9a-124">その後、新しいレジストラーを使用して転送を完了し、新しいレジストラーを使用して転送料金を支払ったり、アカウントに転送されたドメインを追加したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="c2d9a-125">移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="c2d9a-126">プロセスを終了するには、管理センターの [ **ドメイン** ] ページに戻り、[  **完全なドメイン転送**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="c2d9a-127">これにより、Microsoft 365 から購入されなくなったことをドメインにマークし、ドメインサブスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="c2d9a-128">テナントからドメインを削除することはできません。ドメインの既存のユーザーおよびメールボックスには影響しません。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="c2d9a-129">Microsoft 365 で購入したドメインは、ネームサーバーの変更、または Microsoft 365 組織間でのドメインの転送には適していません。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="c2d9a-130">これらのどちらかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d9a-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
