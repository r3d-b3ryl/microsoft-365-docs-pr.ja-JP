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
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788985"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="3ea3d-103">Microsoft から別のホストにドメインを移行する</span><span class="sxs-lookup"><span data-stu-id="3ea3d-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="3ea3d-104">Microsoft からドメインを購入した後、Microsoft 365 ドメインを別60のレジストラーに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="3ea3d-105">_Whois_   クエリは、Microsoft が購入したドメインレジストラーを「ワイルド (_ West Domains) ドメイン」として示しています。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="3ea3d-106">ただし、microsoft 365 の購入済みドメインについては、Microsoft のみに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="3ea3d-107">Microsoft 365 でコードを取得するには、次の手順に従います。その後、他のドメインレジストラー web サイトに移動して、ドメイン名を新しいレジストラーに転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="3ea3d-108">ドメインを転送する</span><span class="sxs-lookup"><span data-stu-id="3ea3d-108">Transfer a domain</span></span>

1. <span data-ttu-id="3ea3d-109">管理センターで、[  **設定**] [ドメイン] に移動し   >  **Domains**ます。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="3ea3d-110"><[ **ドメイン** ] ページで、別のドメインレジストラーに移行する Microsoft 365 ドメインを選択して、[ **状態の確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-110"><On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="3ea3d-111">ページの上部で、[ドメインの **移行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="3ea3d-112">[ **ドメインを移行する場所を選択** してください] ページで、別の **レジストラー**を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="3ea3d-113">[**ドメイン転送のロック解除**] ページで、[ **_ドメイン_ > <の転送のロック解除**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="3ea3d-114">ドメイン転送の連絡先情報を確認し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="3ea3d-115">次の手順に進む前に、承認コードをコピーして、[**登録**] タブで**転送のロックが解除**されたことを示す30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="3ea3d-116">ドメイン名を今後も管理するドメインレジストラーの web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="3ea3d-117">ドメインを転送する手順に従います (web サイトでヘルプを検索)。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-117">Follow directions for transferring a domain (search for help on their website).</span></span>

<span data-ttu-id="3ea3d-118">[認証コードの **登録** ] タブは、Microsoft 365 の [  **ドメイン** ] ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-118">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>

9. <span data-ttu-id="3ea3d-119">移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-119">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="3ea3d-120">プロセスを終了するには、管理センターの [ **ドメイン** ] ページに戻り、[  **完全なドメイン転送**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-120">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ea3d-121">Microsoft 365 で購入したドメインは、ネームサーバーの変更、または Microsoft 365 組織間でのドメインの転送には適していません。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-121">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="3ea3d-122">これらのどちらかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea3d-122">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
