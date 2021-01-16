---
title: Basic Mobility and Security のトラブルシューティング
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Basic Mobility and Security の問題を追跡するには、次の手順を実行します。
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876854"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="ab226-103">Basic Mobility and Security のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ab226-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="ab226-104">デバイスを Basic Mobility and Security に登録しようとするときに問題が発生している場合は、次の手順を実行して問題を追跡してください。</span><span class="sxs-lookup"><span data-stu-id="ab226-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="ab226-105">一般的な手順で問題が解決しない場合は、デバイスの種類に固有の手順を示す、後のセクションのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab226-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="ab226-106">最初に試す手順</span><span class="sxs-lookup"><span data-stu-id="ab226-106">Steps to try first</span></span>

<span data-ttu-id="ab226-107">開始するには、以下を確認します。</span><span class="sxs-lookup"><span data-stu-id="ab226-107">To start, check the following:</span></span>

- <span data-ttu-id="ab226-108">デバイスが Intune などの別のモバイル デバイス管理プロバイダーに登録されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ab226-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="ab226-109">デバイスが正しい日付と時刻に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab226-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="ab226-110">デバイス上の別の WIFI または携帯ネットワークに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="ab226-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="ab226-111">Android または iOS デバイスの場合は、Intune ポータル サイト アプリをアンインストールし、デバイスに再インストールします。</span><span class="sxs-lookup"><span data-stu-id="ab226-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="ab226-112">iOS スマートフォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="ab226-112">iOS phone or tablet</span></span>

- <span data-ttu-id="ab226-113">必ず APNs 証明書を設定してください。</span><span class="sxs-lookup"><span data-stu-id="ab226-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="ab226-114">詳しくは [、「iOS デバイス用の APNs 証明書の作成」をご覧ください](create-an-apns-certificate-for-ios-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="ab226-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="ab226-115">[ **設定]** の [全般プロファイル] (または [デバイス管理]) で、管理プロファイルがインストール   >  \*\*\*\*   >  \*\*\*\* されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ab226-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="ab226-116">削除されている場合は、削除します。</span><span class="sxs-lookup"><span data-stu-id="ab226-116">If it is, remove it.</span></span>

- <span data-ttu-id="ab226-117">"デバイスの登録に失敗しました" というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、デバイスにサインインしているユーザーに Exchange Online を含むライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab226-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="ab226-118">"Profile failed to install" というエラー メッセージが表示された場合は、次のいずれかを試してください。</span><span class="sxs-lookup"><span data-stu-id="ab226-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="ab226-119">Safari がデバイスの既定のブラウザーであり、Cookie が無効になされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ab226-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="ab226-120">デバイスを再起動し、デバイスに移動portal.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ab226-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="ab226-121">Microsoft 365 ユーザー ID とパスワードでサインインし、プロファイルを手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab226-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="ab226-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="ab226-122">Windows RT</span></span>

- <span data-ttu-id="ab226-123">ドメインが Microsoft 365 に設定され、Basic Mobility and Security と一緒に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab226-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="ab226-124">詳細については [、「Basic Mobility and Security のセットアップ」を参照してください](set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="ab226-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="ab226-125">[参加] を選択するのではなく、ユーザーが [ **オン]** を   選択している必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="ab226-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="ab226-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="ab226-126">Windows 10 PC</span></span>

- <span data-ttu-id="ab226-127">ドメインが Microsoft 365 に設定され、Basic Mobility and Security と一緒に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab226-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="ab226-128">詳細については [、「Basic Mobility and Security のセットアップ」を参照してください](set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="ab226-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="ab226-129">Azure Active Directory Premium がない場合は、[接続] を選択 \*\*\*\* するのではなく、ユーザーが [デバイス管理への登録] のみを選択   するように **します**。</span><span class="sxs-lookup"><span data-stu-id="ab226-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="ab226-130">Android スマートフォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="ab226-130">Android phone or tablet</span></span>

- <span data-ttu-id="ab226-131">デバイスが Android 4.4 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab226-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="ab226-132">Chrome が最新であり、既定のブラウザーとして設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab226-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="ab226-133">"このデバイスを登録できなかった" というエラー メッセージが表示された場合は、Microsoft 365 にサインインし、デバイスにサインインしているユーザーに Exchange Online を含むライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab226-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="ab226-134">デバイスの通知領域を確認して、必要なエンド ユーザーの操作が保留中の場合は、操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="ab226-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>