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
description: デバイスで Microsoft 365 サービスを使用する前に、最初に Microsoft 365 の Basic Mobility and Security に登録する必要があります。
ms.openlocfilehash: 119039f86f1c7f81ffb535b4a159c935823f2f07
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904230"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="bb3e8-103">基本モビリティとセキュリティを使用してモバイル デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="bb3e8-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="bb3e8-104">仕事のために携帯電話、タブレット、その他のモバイル デバイスを使用すると、オフィスから離れてビジネス プロジェクトに関する情報を得て作業を行うのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="bb3e8-105">デバイスで Microsoft 365 サービスを使用する前に、Microsoft Intune ポータル サイトを使用して Microsoft 365 の基本モビリティとセキュリティに最初に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="bb3e8-106">組織では、従業員がモバイル デバイスを使用して仕事用メール、予定表、およびドキュメントに安全にアクセスできる一方で、ビジネスが重要なデータをセキュリティで保護し、コンプライアンス要件を満たしていることを確認するために、Basic Mobility and Security を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="bb3e8-107">詳細については [、「Basic Mobility and Security for Microsoft 365](overview.md)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="bb3e8-108">詳細については、「デバイスを登録するときに組織に表示できる [情報」を参照してください](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="bb3e8-109">デバイスを Microsoft 365 の Basic Mobility and Security に登録する場合は、作業組織がデバイスをワイプするオプションを許可すると共に、パスワードの設定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="bb3e8-110">Microsoft 365 管理センターからデバイスワイプを実行すると、パスワードが何度も誤って入力された場合や使用条件が壊れている場合に、デバイスからすべてのデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="bb3e8-111">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="bb3e8-111">Supported devices</span></span>

<span data-ttu-id="bb3e8-112">Intune サービスによってホストされる Microsoft 365 の基本的なモビリティとセキュリティは、ほとんどのモバイル デバイスと動作しますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="bb3e8-113">Basic Mobility and Security では、以下がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="bb3e8-114">iOS 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="bb3e8-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="bb3e8-115">Android 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="bb3e8-115">Android 4.4 or later</span></span>

- <span data-ttu-id="bb3e8-116">Windows 8.1 と Windows 10 (電話と PC)</span><span class="sxs-lookup"><span data-stu-id="bb3e8-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="bb3e8-117">デバイスが上記に記載されていない場合に、Basic Mobility and Security でデバイスを使用する必要がある場合は、仕事または学校の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="bb3e8-118">デバイスの登録に問題がある場合は、「Troubleshoot Basic Mobility and Security 」 [を参照してください](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="bb3e8-119">Intune と Basic Mobility and Security を使用してモバイル デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bb3e8-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="bb3e8-120">Intune ポータル サイトを使用すると、デバイスを Microsoft 365 と Basic Mobility and Security で管理できます。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="bb3e8-121">iPhone または iPad</span><span class="sxs-lookup"><span data-stu-id="bb3e8-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="bb3e8-122">この手順を完了するまで、電子メールの送受信は行えなかね。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="bb3e8-123">Apple App Store に移動し、Intune ポータル サイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="bb3e8-124">会社ポータルで iOS スマートフォンまたはタブレットを Office 365 に接続して構成するには、「会社のリソースへの iOS デバイス アクセスをセットアップする」を [参照してください](/mem/intune/user-help/enroll-your-device-in-intune-ios)。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="bb3e8-125">Android スマートフォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="bb3e8-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="bb3e8-126">この手順を完了するまで、電子メールの送受信は行えなかね。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="bb3e8-127">Google Play ストアに移動し、Intune ポータル サイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="bb3e8-128">Microsoft 365 へのポータル サイトを使用して Android スマートフォンまたはタブレットに接続して構成するには、「デバイスをポータル サイトに登録する」 [を参照してください](/mem/intune/user-help/enroll-device-android-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="bb3e8-129">Windows 8.1 と Windows 10</span><span class="sxs-lookup"><span data-stu-id="bb3e8-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="bb3e8-130">Microsoft Store に移動し、Intune ポータル サイトをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="bb3e8-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="bb3e8-131">Microsoft 365 へのポータル サイトを使用して Windows 電話または PC に接続して構成するには、「Intune ポータル サイトでの Windows デバイスの登録」 [を参照してください](/intune-user-help/windows-enrollment-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="bb3e8-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="bb3e8-132">What's next?</span></span>

<span data-ttu-id="bb3e8-133">デバイスが Basic Mobility and Security に登録された後、デバイス上の Office アプリの使用を開始して、電子メール、予定表、連絡先、ドキュメントを操作できます。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>