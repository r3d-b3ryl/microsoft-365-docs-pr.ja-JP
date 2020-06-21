---
title: Windows デバイスの Office 2013 の先進認証を有効にする
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Microsoft Office 2013 がインストールされているデバイスの最新の認証を有効にするレジストリ キーの設定方法を説明します。
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779967"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="67376-103">Windows デバイスの Office 2013 の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="67376-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="67376-104">Office 2013 がインストールされている Windows デバイスで先進認証を有効にするには、特定のレジストリ キーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67376-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="67376-105">Office 2013 クライアントの先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="67376-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="67376-106">先進認証は Office 2016 クライアントで既に有効になっているため、Office 2016 のレジストリ キーを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="67376-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="67376-107">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys.</span><span class="sxs-lookup"><span data-stu-id="67376-107">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys.</span></span> <span data-ttu-id="67376-108">The keys have to be set on each device that you want to enable for modern authentication:</span><span class="sxs-lookup"><span data-stu-id="67376-108">The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="67376-109">**レジストリ キー**</span><span class="sxs-lookup"><span data-stu-id="67376-109">**Registry key**</span></span>|<span data-ttu-id="67376-110">**型**</span><span class="sxs-lookup"><span data-stu-id="67376-110">**Type**</span></span>|<span data-ttu-id="67376-111">**値**</span><span class="sxs-lookup"><span data-stu-id="67376-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="67376-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="67376-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="67376-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="67376-113">REG_DWORD</span></span>  |<span data-ttu-id="67376-114">1</span><span class="sxs-lookup"><span data-stu-id="67376-114">1</span></span>  |
|<span data-ttu-id="67376-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="67376-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="67376-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="67376-116">REG_DWORD</span></span> |<span data-ttu-id="67376-117">1</span><span class="sxs-lookup"><span data-stu-id="67376-117">1</span></span> |
   
<span data-ttu-id="67376-118">レジストリキーを設定したら、Microsoft 365 で[多要素認証 (MFA)](set-up-multi-factor-authentication.md)を使用するように Office 2013 デバイスアプリを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="67376-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="67376-119">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect.</span><span class="sxs-lookup"><span data-stu-id="67376-119">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect.</span></span> <span data-ttu-id="67376-120">Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span><span class="sxs-lookup"><span data-stu-id="67376-120">Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="67376-121">デバイスで先進認証を無効にする</span><span class="sxs-lookup"><span data-stu-id="67376-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="67376-122">デバイスで先進認証を無効にするには、デバイスで次のレジストリ キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="67376-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="67376-123">**レジストリ キー**</span><span class="sxs-lookup"><span data-stu-id="67376-123">**Registry key**</span></span>|<span data-ttu-id="67376-124">**型**</span><span class="sxs-lookup"><span data-stu-id="67376-124">**Type**</span></span>|<span data-ttu-id="67376-125">**値**</span><span class="sxs-lookup"><span data-stu-id="67376-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="67376-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="67376-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="67376-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="67376-127">REG_DWORD</span></span>|<span data-ttu-id="67376-128">0</span><span class="sxs-lookup"><span data-stu-id="67376-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="67376-129">関連記事</span><span class="sxs-lookup"><span data-stu-id="67376-129">Related articles</span></span>
[<span data-ttu-id="67376-130">第 2 検証方法を使用して Office 2013 にサインインする</span><span class="sxs-lookup"><span data-stu-id="67376-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

