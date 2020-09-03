---
title: 基本的なモビリティとセキュリティのトラブルシューティング
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
description: 基本的なモビリティとセキュリティの問題を追跡するには、次の手順を実行してください。
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336974"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="25638-103">基本的なモビリティとセキュリティのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="25638-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="25638-104">基本的なモビリティとセキュリティでデバイスを登録しようとしたときに問題が発生している場合は、次の手順を実行して問題を追跡します。</span><span class="sxs-lookup"><span data-stu-id="25638-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="25638-105">一般的な手順で問題が解決しない場合は、デバイスの種類に固有の手順が記載された後のセクションのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25638-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="25638-106">最初に試す手順</span><span class="sxs-lookup"><span data-stu-id="25638-106">Steps to try first</span></span>

<span data-ttu-id="25638-107">開始するには、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-107">To start, check the following:</span></span>

- <span data-ttu-id="25638-108">デバイスが他のモバイルデバイス管理プロバイダー (Intune など) に登録されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="25638-109">デバイスが正しい日付と時刻に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25638-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="25638-110">デバイス上の別の WIFI または携帯ネットワークに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="25638-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="25638-111">Android または iOS デバイスの場合は、デバイス上の Intune ポータルサイトアプリをアンインストールしてから再インストールします。</span><span class="sxs-lookup"><span data-stu-id="25638-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="25638-112">iOS 電話またはタブレット</span><span class="sxs-lookup"><span data-stu-id="25638-112">iOS phone or tablet</span></span>

- <span data-ttu-id="25638-113">APNs 証明書を設定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="25638-114">詳細については、「 [iOS のデバイス用の APNs 証明書を作成する](create-an-apns-certificate-for-ios-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25638-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="25638-115">[ **Settings**   >  **General**   >  **profile (または Device Management)**] で、管理プロファイルがまだインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="25638-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="25638-116">その場合は、削除します。</span><span class="sxs-lookup"><span data-stu-id="25638-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="25638-117">"デバイスの登録に失敗しました" というエラーメッセージが表示される場合は、Microsoft 365 にサインインして、デバイスにサインインしているユーザーに Exchange Online を含むライセンスが割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="25638-118">"プロファイルをインストールできませんでした" というエラーメッセージが表示される場合は、次のいずれかを試してください。</span><span class="sxs-lookup"><span data-stu-id="25638-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="25638-119">Safari がデバイスの既定のブラウザーであること、および cookie が無効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="25638-120">デバイスを再起動して、portal.manage.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="25638-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="25638-121">Microsoft 365 のユーザー ID とパスワードを使用してサインインし、プロファイルを手動でインストールしてみます。</span><span class="sxs-lookup"><span data-stu-id="25638-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="25638-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="25638-122">Windows RT</span></span>

- <span data-ttu-id="25638-123">基本的なモビリティとセキュリティを使用するために、ドメインが Microsoft 365 で設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25638-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="25638-124">詳細については、「 [基本モビリティとセキュリティを設定](set-up-basic-mobility-and-security.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25638-124">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="25638-125">[参加] を選択せずに、ユーザーが **[オン**] を選択していることを確認し   ます。 **Join**</span><span class="sxs-lookup"><span data-stu-id="25638-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="25638-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="25638-126">Windows 10 PC</span></span>

- <span data-ttu-id="25638-127">基本的なモビリティとセキュリティを使用するために、ドメインが Microsoft 365 で設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25638-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="25638-128">詳細については、「 [基本モビリティとセキュリティを設定](set-up-basic-mobility-and-security.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25638-128">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="25638-129">Azure Active Directory Premium を使用していない場合は、[接続] を選択するのではなく、ユーザーが [ **デバイス管理にのみ登録**] を選択していることを確認してください   。 **Connect**</span><span class="sxs-lookup"><span data-stu-id="25638-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="25638-130">Android フォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="25638-130">Android phone or tablet</span></span>

- <span data-ttu-id="25638-131">デバイスが Android 4.4 以降を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="25638-132">Chrome が最新のものであり、既定のブラウザーとして設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25638-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="25638-133">"このデバイスを登録できませんでした" というエラーメッセージが表示された場合は、Microsoft 365 にサインインして、Exchange Online を含むライセンスが、デバイスにサインインしているユーザーに割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25638-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="25638-134">デバイスの通知領域を調べて、必要なエンドユーザー操作が保留中であるかどうかを確認し、完了している場合は、操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="25638-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>