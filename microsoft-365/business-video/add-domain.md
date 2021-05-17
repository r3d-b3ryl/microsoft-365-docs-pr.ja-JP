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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: サブスクリプションに別のドメインを追加する方法について学習します。
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903744"
---
# <a name="add-another-domain"></a><span data-ttu-id="90c10-103">別のドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="90c10-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="90c10-104">会社によって、さまざまな目的で複数のドメイン名が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c10-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="90c10-105">たとえば、顧客が既にその会社名を使用していて、顧客とのコミュニケーションに失敗した場合、会社名に別のスペルを追加したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c10-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="90c10-106">お試しください!</span><span class="sxs-lookup"><span data-stu-id="90c10-106">Try it!</span></span>

1. <span data-ttu-id="90c10-107">Microsoft 365 管理センターで、[**セットアップ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="90c10-108">[**カスタム ドメインをセットアップする**] にて、[**表示**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="90c10-109">[**管理**]、[**ドメインの追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="90c10-110">追加する新しいドメイン名を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="90c10-111">ドメイン レジストラー (この場合は GoDaddy) にサインインし、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="90c10-112">メッセージが表示されたら、レジストラーにサインインしてから、[**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="90c10-113">[**DNS レコードを追加してもらう**] を選び、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="90c10-114">新しいドメインのサービスを選び、別のドメインで処理されるサービスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="90c10-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="90c10-115">たとえば、メール用に新しいドメインを使うだけなら、［**Exchange**］ を選び、［**Skype for Business**］ と ［**Mobile Device Management for Office 365**］ のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="90c10-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="90c10-116">[**次へ**］、［**承認**］、［**次へ**］ の順に選択してから、［**完了**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="90c10-117">新しいドメインが追加されました。</span><span class="sxs-lookup"><span data-stu-id="90c10-117">Your new domain has been added.</span></span>

<span data-ttu-id="90c10-118">新しいドメインでメールを受信するには、各ユーザーの新しいメール エイリアスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c10-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="90c10-119">[**ユーザー**］、［**アクティブなユーザー**］ の順に選択してから、新しいエイリアスが割り当てられるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="90c10-120">[**メール エイリアスの管理**]、[**エイリアスを追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="90c10-121">ユーザー名を入力し、ドロップダウン リストから新しいドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c10-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="90c10-122">[**変更を保存する**] を選択し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="90c10-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="90c10-123">新しいドメインでメールを受信する必要がある各ユーザーに、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="90c10-123">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="90c10-124">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="90c10-124">Related content</span></span>

<span data-ttu-id="90c10-125">[Microsoft 365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)する[(記事](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)) DNS レコードを追加してドメインに接続する (記事) ネームサーバーを変更して[、Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)を任意のドメイン レジストラーに設定する (記事) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (記事)</span><span class="sxs-lookup"><span data-stu-id="90c10-125">[Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (article) [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (article) [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) (article) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>