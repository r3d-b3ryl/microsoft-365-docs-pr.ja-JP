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
ROBOTS: NOINDEX, NOFOLLOW
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
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702790"
---
# <a name="add-another-domain"></a><span data-ttu-id="d86d6-103">別のドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="d86d6-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="d86d6-104">会社で異なる目的のために複数のドメイン名が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86d6-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="d86d6-105">たとえば、顧客が既に会社名を使用し、連絡に失敗した場合に、別のスペルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d86d6-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="d86d6-106">演習</span><span class="sxs-lookup"><span data-stu-id="d86d6-106">Try it!</span></span>

1. <span data-ttu-id="d86d6-107">Microsoft 365 管理センターで、[セットアップ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d86d6-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="d86d6-108">[ **カスタム ドメインのセットアップを取得する] で、[表示**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d86d6-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="d86d6-109">Choose **Manage,** and then **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="d86d6-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="d86d6-110">追加する新しいドメイン名を入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d86d6-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="d86d6-111">ドメイン レジストラー (この場合は GoDaddy) にサインインし、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d86d6-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="d86d6-112">ダイアログが表示されたら、レジストラーにサインインし、[承認] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="d86d6-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="d86d6-113">Choose **Add the DNS records for me,** and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="d86d6-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="d86d6-114">新しいドメインのサービスを選択し、別のドメインによって処理されるサービスのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d86d6-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="d86d6-115">たとえば、電子メールに新しいドメインを使用するだけの場合は **、[Exchange]** を選択し **、Skype for Business** およびモバイル デバイス管理 (Office **365** 用) のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d86d6-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="d86d6-116">[**次へ] を** 選択し **、[承認]、[\*\*\*\*次へ**]、および [完了] の順に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d86d6-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="d86d6-117">新しいドメインが追加されました。</span><span class="sxs-lookup"><span data-stu-id="d86d6-117">Your new domain has been added.</span></span>

<span data-ttu-id="d86d6-118">新しいドメインでメールを受信するには、ユーザーごとに新しいメール エイリアスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86d6-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="d86d6-119">[ **ユーザー]**、[ **アクティブなユーザー**] の順に選択し、新しいエイリアスを割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d86d6-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="d86d6-120">Choose **Manage email aliases,** and then **Add an alias**.</span><span class="sxs-lookup"><span data-stu-id="d86d6-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="d86d6-121">ユーザー名を入力し、ドロップダウン リストから新しいドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="d86d6-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="d86d6-122">[変更 **の保存] を** 選択し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d86d6-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="d86d6-123">新しいドメインでメールを受信する必要があるユーザーごとに、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d86d6-123">Repeat these steps for each user who should receive email at the new domain.</span></span>