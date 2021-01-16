---
title: Basic Mobility and Security を使用してモバイル デバイスを登録する
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
ms.openlocfilehash: dc5a43b12fce50c9146200a4559fe9b7e6824b18
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877058"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="91e1b-103">Basic Mobility and Security を使用してモバイル デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="91e1b-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="91e1b-104">電話、タブレット、その他のモバイル デバイスを業務に使用すると、オフィスから離れた場所でビジネス プロジェクトに関する情報を得て作業を行うのに便利です。</span><span class="sxs-lookup"><span data-stu-id="91e1b-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="91e1b-105">デバイスで Microsoft 365 サービスを使用する前に、Microsoft Intune ポータル サイトを使用して Microsoft 365 の Basic Mobility and Security に登録する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="91e1b-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="91e1b-106">組織は、従業員がモバイル デバイスを使用して仕事用の電子メール、予定表、ドキュメントに安全にアクセスできる一方で、ビジネスが重要なデータをセキュリティで保護し、コンプライアンス要件を満たできるよう、Basic Mobility and Security を選択します。</span><span class="sxs-lookup"><span data-stu-id="91e1b-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="91e1b-107">詳細については [、「Microsoft 365 の Basic Mobility and Security の概要」を参照](overview.md)してください。</span><span class="sxs-lookup"><span data-stu-id="91e1b-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="91e1b-108">詳しくは、「デバイスの登録時に組織に表示される情報 [」をご覧ください](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="91e1b-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="91e1b-109">デバイスを Microsoft 365 の Basic Mobility and Security に登録するときに、パスワードの設定と、作業組織がデバイスをワイプするオプションを許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="91e1b-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="91e1b-110">デバイス ワイプは、Microsoft 365 管理センターから実行できます。たとえば、パスワードが誤って何度も入力された場合や、使用条件が壊れている場合に、デバイスからすべてのデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="91e1b-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="91e1b-111">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="91e1b-111">Supported devices</span></span>

<span data-ttu-id="91e1b-112">Intune サービスによってホストされる Microsoft 365 の基本的なモビリティとセキュリティは、ほとんどのモバイル デバイスで動作しますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="91e1b-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="91e1b-113">Basic Mobility and Security では、次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="91e1b-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="91e1b-114">iOS 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="91e1b-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="91e1b-115">Android 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="91e1b-115">Android 4.4 or later</span></span>

- <span data-ttu-id="91e1b-116">Windows 8.1 と Windows 10 (電話と PC)</span><span class="sxs-lookup"><span data-stu-id="91e1b-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="91e1b-117">デバイスが上記の一覧に記載されていない場合、Basic Mobility and Security でデバイスを使用する必要がある場合は、仕事または学校の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="91e1b-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="91e1b-118">デバイスの登録で問題が発生した場合は、「Basic Mobility and Security のトラブルシューティング [」を参照してください](/basic-mobility-security/troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="91e1b-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](/basic-mobility-security/troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="91e1b-119">Intune と Basic Mobility and Security を使用してモバイル デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="91e1b-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="91e1b-120">Intune ポータル サイトを使用すると、デバイスを Microsoft 365 と Basic Mobility and Security で管理できます。</span><span class="sxs-lookup"><span data-stu-id="91e1b-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="91e1b-121">iPhone または iPad</span><span class="sxs-lookup"><span data-stu-id="91e1b-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="91e1b-122">この手順を完了するまで、電子メールを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="91e1b-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="91e1b-123">Apple App Store に移動し、Intune ポータル サイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="91e1b-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="91e1b-124">Office 365 にポータル サイトを使用して iOS 電話またはタブレットに接続して構成するには、「会社のリソースへの iOS デバイス アクセスをセットアップする」を [参照してください](https://go.microsoft.com/fwlink/?linkid=875316)。</span><span class="sxs-lookup"><span data-stu-id="91e1b-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="91e1b-125">Android スマートフォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="91e1b-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="91e1b-126">この手順を完了するまで、電子メールを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="91e1b-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="91e1b-127">Google Play ストアに移動し、Intune ポータル サイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="91e1b-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="91e1b-128">ポータル サイトを使用して Android スマートフォンまたはタブレットを Microsoft 365 に接続して構成するには、「ポータル サイトにデバイスを登録する」 [を参照してください](https://go.microsoft.com/fwlink/?linkid=875317)。</span><span class="sxs-lookup"><span data-stu-id="91e1b-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="91e1b-129">Windows 8.1 と Windows 10</span><span class="sxs-lookup"><span data-stu-id="91e1b-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="91e1b-130">Microsoft Store に移動し、Intune ポータル サイトをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="91e1b-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="91e1b-131">ポータル サイトを使用して Windows Phone または PC を Microsoft 365 に接続して構成するには、Intune ポータル サイトでの Windows デバイスの登録に関する [ページを参照してください](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="91e1b-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="91e1b-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="91e1b-132">What's next?</span></span>

<span data-ttu-id="91e1b-133">デバイスが Basic Mobility and Security に登録された後、デバイスで Office アプリを使用して、メール、予定表、連絡先、ドキュメントを操作できます。</span><span class="sxs-lookup"><span data-stu-id="91e1b-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
