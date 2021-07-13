---
title: ドメインを追加する
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
- AdminTemplateSet
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 組織では、複数のドメインが必要になる場合があります。 サブスクリプションに別のドメインを追加する方法について学習します。
ms.openlocfilehash: 766d0f6c1e3c68a262bc01ba432e042f0d274ce8
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394847"
---
# <a name="add-another-domain"></a><span data-ttu-id="e66a6-104">別のドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="e66a6-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="e66a6-105">会社によって、さまざまな目的で複数のドメイン名が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e66a6-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="e66a6-106">たとえば、顧客が既にその会社名を使用していて、顧客とのコミュニケーションに失敗した場合、会社名に別のスペルを追加したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e66a6-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="e66a6-107">お試しください!</span><span class="sxs-lookup"><span data-stu-id="e66a6-107">Try it!</span></span>

1. <span data-ttu-id="e66a6-108">Microsoft 365 管理センターで、[**セットアップ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="e66a6-109">[**カスタム ドメインをセットアップする**] にて、[**表示**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="e66a6-110">[**管理**]、[**ドメインの追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="e66a6-111">追加する新しいドメイン名を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="e66a6-112">ドメイン レジストラー (この場合は GoDaddy) にサインインし、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="e66a6-113">メッセージが表示されたら、レジストラーにサインインしてから、[**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="e66a6-114">[**DNS レコードを追加してもらう**] を選び、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="e66a6-115">新しいドメインのサービスを選び、別のドメインで処理されるサービスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e66a6-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="e66a6-116">たとえば、メール用に新しいドメインを使うだけなら、［**Exchange**］ を選び、［**Skype for Business**］ と ［**Mobile Device Management for Office 365**］ のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e66a6-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="e66a6-117">[**次へ**］、［**承認**］、［**次へ**］ の順に選択してから、［**完了**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="e66a6-118">新しいドメインが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e66a6-118">Your new domain has been added.</span></span>

<span data-ttu-id="e66a6-119">新しいドメインでメールを受信するには、各ユーザーの新しいメール エイリアスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66a6-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="e66a6-120">[**ユーザー**］、［**アクティブなユーザー**］ の順に選択してから、新しいエイリアスが割り当てられるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="e66a6-121">[**メール エイリアスの管理**]、[**エイリアスを追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="e66a6-122">ユーザー名を入力し、ドロップダウン リストから新しいドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="e66a6-123">[**変更を保存する**] を選択し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e66a6-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="e66a6-124">新しいドメインでメールを受信する必要がある各ユーザーに、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e66a6-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="e66a6-125">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e66a6-125">Related content</span></span>

<span data-ttu-id="e66a6-126">[ドメインをドメインに追加Microsoft 365](../admin/setup/add-domain.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="e66a6-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="e66a6-127">[DNS レコードを追加してドメインに接続](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="e66a6-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="e66a6-128">[任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="e66a6-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="e66a6-129">[ドメインの FAQ](../admin/setup/domains-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="e66a6-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>