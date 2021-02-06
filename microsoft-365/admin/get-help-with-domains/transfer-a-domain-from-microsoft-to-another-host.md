---
title: Microsoft から別のホストにドメインを転送する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'ドメインを Microsoft から別のレジストラーに転送するには、以下の手順を実行します。 '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126349"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="17520-103">Microsoft から別のホストにドメインを転送する</span><span class="sxs-lookup"><span data-stu-id="17520-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="17520-104">Microsoft からドメインを購入した後、60 日間、Microsoft 365 ドメインを別のレジストラーに転送できない。</span><span class="sxs-lookup"><span data-stu-id="17520-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="17520-105">_Whois クエリは_   、Microsoft が購入したドメイン レジストラーを Wild West Domains LLC として表示します。</span><span class="sxs-lookup"><span data-stu-id="17520-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="17520-106">ただし、Microsoft 365 購入ドメインに関して Microsoft にのみ連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17520-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="17520-107">次の手順に従って Microsoft 365 でコードを取得し、他のドメイン レジストラー Web サイトに移動して、ドメイン名を新しいレジストラーに転送する設定を行います。</span><span class="sxs-lookup"><span data-stu-id="17520-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="17520-108">ドメインを転送する</span><span class="sxs-lookup"><span data-stu-id="17520-108">Transfer a domain</span></span>

1. <span data-ttu-id="17520-109">管理センターで、[設定ドメイン]  **に**   >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="17520-109">In the admin center, go to   **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="17520-110">[ **ドメイン] ページ** で、別のドメイン レジストラーに転送する Microsoft 365 ドメインを選択し、[正常性の確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="17520-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="17520-111">ページの上部で、[ドメインの転送] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17520-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="17520-112">On the **Choose where to transfer your domain** page, select A different **registrar,** and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="17520-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="17520-113">On the **Unlock domain transfer** page, select Unlock transfer for <your **_domain,_ >** and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="17520-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="17520-114">ドメイン転送の連絡先情報を確認し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="17520-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="17520-115">次の手順に進む前に、認証コードをコピーして、ドメインの転送状態が [登録]タブの [ロック解除済み] に変わるまで約 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="17520-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="17520-116">今後ドメイン名を管理するドメイン レジストラーの Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="17520-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="17520-117">ドメインを転送するための指示に従います (Web サイトでヘルプを検索してください)。</span><span class="sxs-lookup"><span data-stu-id="17520-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="17520-118">これは通常、転送料金を支払い、新しいレジストラーに認証コードを提供して、転送を開始できるという意味です。</span><span class="sxs-lookup"><span data-stu-id="17520-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="17520-119">Microsoft から転送要求を受け取ったことを確認するメールが送信され、ドメインは 5 日以内に転送されます。</span><span class="sxs-lookup"><span data-stu-id="17520-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="17520-120">認証コードの登録タブは、Microsoft 365 の [ドメイン] ページにあります。  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="17520-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="17520-121">.uk ドメインには別の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="17520-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="17520-122">Microsoft サポートに連絡して、今後ドメインを管理するレジストラーと一致するように **IPS Tag タグを変更** を依頼します。</span><span class="sxs-lookup"><span data-stu-id="17520-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="17520-123">タグを変更すると、ドメインは直ちに新しいレジストラーに移動します。</span><span class="sxs-lookup"><span data-stu-id="17520-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="17520-124">転送を完了するには、新しいレジストラーでするべきことがあります。移転手数料を支払って、新しいレジストラーで転送されたドメインをアカウントに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17520-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="17520-125">移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="17520-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="17520-126">プロセスを完了するには、管理センターの [ **ドメイン** ] ページに戻り、[ドメインの転送の完了]  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17520-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="17520-127">これにより、ドメインが Microsoft 365 から購入されなくなったとマークされ、ドメイン サブスクリプションが無効にされます。</span><span class="sxs-lookup"><span data-stu-id="17520-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="17520-128">テナントからドメインは削除されません。また、ドメイン上の既存のユーザーとメールボックスには影響を与えされません。</span><span class="sxs-lookup"><span data-stu-id="17520-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="17520-129">Microsoft 365 購入ドメインは、ネームサーバーの変更または Microsoft 365 組織間でのドメインの転送の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="17520-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="17520-130">これらのどちらかが必要な場合は、ドメイン登録を別のレジストラーに転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17520-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
