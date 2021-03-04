---
title: ドメインの追加
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: サブスクリプションに別のドメインを追加する方法について学習します。
ms.openlocfilehash: fef3dc06f270b79cc7f9e729b39727c9116b923d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423085"
---
# <a name="add-another-domain"></a><span data-ttu-id="23fda-103">別のドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="23fda-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="23fda-104">会社が異なる目的で複数のドメイン名を必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="23fda-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="23fda-105">たとえば、顧客が既に会社名を使用し、通信が届かないので、会社名の別のスペルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="23fda-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="23fda-106">演習</span><span class="sxs-lookup"><span data-stu-id="23fda-106">Try it!</span></span>

1. <span data-ttu-id="23fda-107">Microsoft 365 管理センターで、[セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="23fda-108">[カスタム **ドメインの設定を取得する] で、[** 表示] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="23fda-109">[管理 **] を** 選択し、[ドメインの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="23fda-110">追加する新しいドメイン名を入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="23fda-111">ドメイン レジストラー (この場合は GoDaddy) にサインインし、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="23fda-112">メッセージが表示されたら、レジストラーにサインインし、[承認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="23fda-113">[自分 **の DNS レコードを追加する] を選択し**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="23fda-114">新しいドメインのサービスを選択し、別のドメインで処理されるサービスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="23fda-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="23fda-115">たとえば、新しいドメインを電子メールに使用する場合は **、[Exchange]** を選択し **、[Skype for Business]** および [モバイル デバイス管理 for Office **365] のチェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="23fda-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="23fda-116">[次 **へ]**、[**承認] 、[\*\*\*\*次へ] の** 順に選択し、[完了]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="23fda-117">新しいドメインが追加されました。</span><span class="sxs-lookup"><span data-stu-id="23fda-117">Your new domain has been added.</span></span>

<span data-ttu-id="23fda-118">新しいドメインでメールを受信するには、ユーザーごとに新しいメール エイリアスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23fda-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="23fda-119">[ **ユーザー]**、[ **アクティブユーザー]** の順に選択し、新しいエイリアスを割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="23fda-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="23fda-120">[ **メール エイリアスの管理] を選択** し、[エイリアス **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="23fda-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="23fda-121">ユーザー名を入力し、ドロップダウン リストから新しいドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="23fda-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="23fda-122">[変更 **の保存] を** 選択し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="23fda-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="23fda-123">新しいドメインで電子メールを受信する必要があるユーザーごとに、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="23fda-123">Repeat these steps for each user who should receive email at the new domain.</span></span>