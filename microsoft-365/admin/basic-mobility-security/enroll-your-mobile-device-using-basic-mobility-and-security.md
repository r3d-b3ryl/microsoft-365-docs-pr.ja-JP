---
title: 基本的なモビリティとセキュリティを使用してモバイルデバイスを登録する
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
description: Microsoft 365 サービスをデバイスで使用するには、まず、Microsoft 365 の基本的なモビリティとセキュリティに登録する必要があります。
ms.openlocfilehash: 83eb80809db1d05843a0014a5178deff4f4756c2
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336986"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="83b8f-103">基本的なモビリティとセキュリティを使用してモバイルデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="83b8f-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="83b8f-104">電話、タブレット、その他のモバイルデバイスを職場で使用することは、外出中にビジネスプロジェクトの情報を入手して作業するための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="83b8f-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="83b8f-105">Microsoft 365 services をデバイスで使用できるようにするには、microsoft Intune ポータルサイトを使用して、microsoft 365 の基本的なモビリティとセキュリティに最初に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b8f-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="83b8f-106">組織は基本的なモビリティとセキュリティを選択するので、従業員はモバイルデバイスを使用して、職場の電子メール、予定表、およびドキュメントに安全にアクセスでき、ビジネスは重要なデータをセキュリティで保護し、コンプライアンスの要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="83b8f-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="83b8f-107">詳細については、「 [Microsoft 365 の基本的なモビリティとセキュリティの概要](overview-of-basic-mobility-and-security-for-microsoft-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview-of-basic-mobility-and-security-for-microsoft-365.md).</span></span> <span data-ttu-id="83b8f-108">詳細については、「 [デバイスの登録時に組織が表示できる情報](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="83b8f-109">Microsoft 365 の基本的なモビリティおよびセキュリティにデバイスを登録する場合、パスワードの設定と共に、職場の組織がデバイスをワイプできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b8f-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="83b8f-110">パスワードの誤入力回数が多すぎる場合、または使用条件が破損している場合は、Microsoft 365 管理センターからデバイスのワイプを実行できます (たとえば、デバイスからすべてのデータを削除する場合)。</span><span class="sxs-lookup"><span data-stu-id="83b8f-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="83b8f-111">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="83b8f-111">Supported devices</span></span>

<span data-ttu-id="83b8f-112">Intune サービスによってホストされている Microsoft 365 の基本的なモビリティとセキュリティは、ほとんどのモバイルデバイスでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="83b8f-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="83b8f-113">基本的なモビリティとセキュリティでは、次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="83b8f-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="83b8f-114">iOS 10.0 以降</span><span class="sxs-lookup"><span data-stu-id="83b8f-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="83b8f-115">Android 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="83b8f-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="83b8f-116">Windows 8.1 と Windows 10 (電話と PC)</span><span class="sxs-lookup"><span data-stu-id="83b8f-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="83b8f-117">デバイスが上にリストされておらず、基本的なモビリティとセキュリティで使用する必要がある場合は、職場または学校の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="83b8f-118">デバイスの登録で問題が発生している場合は、「 [基本的なモビリティとセキュリティのトラブルシューティング](troubleshoot-basic-mobility-and-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot-basic-mobility-and-security.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="83b8f-119">Intune および基本的なモビリティとセキュリティを使用してモバイルデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="83b8f-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="83b8f-120">Intune ポータルサイトを使用すると、Microsoft 365 および基本的なモビリティとセキュリティでデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="83b8f-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="83b8f-121">iPhone または iPad</span><span class="sxs-lookup"><span data-stu-id="83b8f-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="83b8f-122">この手順が完了するまで、電子メールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="83b8f-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="83b8f-123">Apple App Store に移動し、Intune ポータルサイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="83b8f-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="83b8f-124">会社のポータルで iOS 電話またはタブレットを Office 365 に接続して構成するには、「 [会社のリソースへの ios デバイスアクセスの設定](https://go.microsoft.com/fwlink/?linkid=875316)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="83b8f-125">Android フォンまたはタブレット</span><span class="sxs-lookup"><span data-stu-id="83b8f-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="83b8f-126">この手順が完了するまで、電子メールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="83b8f-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="83b8f-127">Google Play ストアに移動し、Intune ポータルサイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="83b8f-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="83b8f-128">ポータルサイトを使用して Android 携帯電話またはタブレットを Microsoft 365 に接続して構成するには、「 [会社のポータルでデバイスを登録](https://go.microsoft.com/fwlink/?linkid=875317)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="83b8f-129">Windows 8.1 と Windows 10</span><span class="sxs-lookup"><span data-stu-id="83b8f-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="83b8f-130">Microsoft ストアに移動し、Intune ポータルサイトをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="83b8f-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="83b8f-131">会社のポータルを使用して Windows phone または PC を Microsoft 365 に接続して構成するには、「 [Intune Company portal での windows デバイスの登録](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83b8f-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="83b8f-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="83b8f-132">What's next?</span></span>

<span data-ttu-id="83b8f-133">基本的なモビリティとセキュリティにデバイスを登録した後、デバイスで Office アプリを使用して、電子メール、予定表、連絡先、およびドキュメントを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="83b8f-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>