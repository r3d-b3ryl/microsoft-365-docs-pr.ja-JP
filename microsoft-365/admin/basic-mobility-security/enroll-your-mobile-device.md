---
title: 基本モビリティとセキュリティを使用してモバイル デバイスを登録する
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: デバイスで Microsoft 365 サービスを使用する前に、最初にデバイスの Basic Mobility and Security に登録する必要Microsoft 365。
ms.openlocfilehash: 9da3424409a950670e3be45354a5c399fec52372
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228185"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="9f7ef-103">基本モビリティとセキュリティを使用してモバイル デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="9f7ef-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="9f7ef-104">仕事のために携帯電話、タブレット、その他のモバイル デバイスを使用すると、オフィスから離れてビジネス プロジェクトに関する情報を得て作業を行うのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="9f7ef-105">デバイスで Microsoft 365 サービスを使用する前に、デバイスを使用するために、最初に Basic Mobility and Security に登録するMicrosoft 365必要Microsoft Intune ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="9f7ef-106">組織では、従業員がモバイル デバイスを使用して仕事用メール、予定表、およびドキュメントに安全にアクセスできる一方で、ビジネスが重要なデータをセキュリティで保護し、コンプライアンス要件を満たしていることを確認するために、Basic Mobility and Security を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="9f7ef-107">詳細については、「基本モビリティとセキュリティ[の概要」を参照Microsoft 365。](overview.md)</span><span class="sxs-lookup"><span data-stu-id="9f7ef-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="9f7ef-108">詳細については、「デバイスを登録するときに組織に表示できる [情報」を参照してください](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f7ef-109">Microsoft 365 の Basic Mobility and Security にデバイスを登録する場合、作業組織がデバイスをワイプするオプションを許可すると共に、パスワードの設定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="9f7ef-110">たとえば、パスワードが何度も誤って入力された場合、または使用条件が壊れている場合に、デバイスからすべてのデータを削除するために、Microsoft 365 管理センター からデバイスワイプを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="9f7ef-111">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="9f7ef-111">Supported devices</span></span>

<span data-ttu-id="9f7ef-112">Intune サービスによってホストMicrosoft 365基本的なモビリティとセキュリティは、ほとんどのモバイル デバイスで動作しますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="9f7ef-113">Basic Mobility and Security では、以下がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="9f7ef-114">iOS 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="9f7ef-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="9f7ef-115">Android 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="9f7ef-115">Android 4.4 or later</span></span>

- <span data-ttu-id="9f7ef-116">Windows 8.1とWindows 10 (電話 PC)</span><span class="sxs-lookup"><span data-stu-id="9f7ef-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="9f7ef-117">デバイスが上記に記載されていない場合に、Basic Mobility and Security でデバイスを使用する必要がある場合は、仕事または学校の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

> [!TIP]
> <span data-ttu-id="9f7ef-118">デバイスの登録に問題がある場合は、「Troubleshoot Basic Mobility and Security 」 [を参照してください](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="9f7ef-119">Intune と Basic Mobility and Security を使用してモバイル デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9f7ef-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="9f7ef-120">このIntune ポータル サイトを使用すると、デバイスをデバイスと Basic Mobility and Security Microsoft 365で管理できます。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="9f7ef-121">iPhoneまたはiPad</span><span class="sxs-lookup"><span data-stu-id="9f7ef-121">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="9f7ef-122">この手順を完了するまで、電子メールの送受信は行えなかね。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="9f7ef-123">Apple App Store に移動し、アプリをダウンロードしてインストールIntune ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="9f7ef-124">ポータル サイトで iOS スマートフォンまたはタブレットを接続して構成するには、「Office 365リソースへの iOS デバイス アクセスをセットアップする」[を参照してください](/mem/intune/user-help/enroll-your-device-in-intune-ios)。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="9f7ef-125">Android スマートフォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="9f7ef-125">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="9f7ef-126">この手順を完了するまで、電子メールの送受信は行えなかね。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="9f7ef-127">Google Play ストアに移動し、アプリをダウンロードしてインストールIntune ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="9f7ef-128">ポータル サイトを使用して Android スマートフォンまたはタブレットを接続して構成するには、「Microsoft 365にデバイスを登録する」[をポータル サイト。](/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="9f7ef-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="9f7ef-129">Windows 8.1とWindows 10</span><span class="sxs-lookup"><span data-stu-id="9f7ef-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="9f7ef-130">[サーバー] に移動Microsoft Store、ダウンロードしてインストールIntune ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="9f7ef-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="9f7ef-131">ポータル サイトを使用してWindows電話または PC に接続して構成するには、「Microsoft 365でのWindowsデバイスの登録」を[参照Intune ポータル サイト。](/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="9f7ef-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f7ef-132">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9f7ef-132">Next steps</span></span>

<span data-ttu-id="9f7ef-133">デバイスが Basic Mobility and Security に登録された後、デバイス上の Office アプリの使用を開始して、電子メール、予定表、連絡先、ドキュメントを操作できます。</span><span class="sxs-lookup"><span data-stu-id="9f7ef-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>