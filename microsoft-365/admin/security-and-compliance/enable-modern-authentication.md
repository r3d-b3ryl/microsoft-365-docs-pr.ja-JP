---
title: Windows デバイスの Office 2013 の先進認証を有効にする
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Microsoft Office 2013 がインストールされているデバイスの最新の認証を有効にするレジストリ キーの設定方法を説明します。
ms.openlocfilehash: 8bfe515fefed9d58f140a67e53ce0d078457aa72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393657"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="e4a8a-103">Windows デバイスの Office 2013 の先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="e4a8a-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="e4a8a-104">Office 2013 がインストールされている Windows デバイスで先進認証を有効にするには、特定のレジストリ キーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a8a-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="e4a8a-105">Office 2013 クライアントの先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="e4a8a-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="e4a8a-106">先進認証は Office 2016 クライアントで既に有効になっているため、Office 2016 のレジストリ キーを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4a8a-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="e4a8a-p101">Microsoft Office 2013 がインストールされている Windows を実行しているデバイス (たとえばノート PC やタブレット) で先進認証を有効にするには、次のレジストリ キーを設定する必要があります。先進認証を有効にするデバイスごとに、次のキーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a8a-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="e4a8a-109">**レジストリ キー**</span><span class="sxs-lookup"><span data-stu-id="e4a8a-109">**Registry key**</span></span>|<span data-ttu-id="e4a8a-110">**型**</span><span class="sxs-lookup"><span data-stu-id="e4a8a-110">**Type**</span></span>|<span data-ttu-id="e4a8a-111">**値**</span><span class="sxs-lookup"><span data-stu-id="e4a8a-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="e4a8a-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="e4a8a-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="e4a8a-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e4a8a-113">REG_DWORD</span></span>  |<span data-ttu-id="e4a8a-114">1</span><span class="sxs-lookup"><span data-stu-id="e4a8a-114">1</span></span>  |
|<span data-ttu-id="e4a8a-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="e4a8a-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="e4a8a-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e4a8a-116">REG_DWORD</span></span> |<span data-ttu-id="e4a8a-117">1</span><span class="sxs-lookup"><span data-stu-id="e4a8a-117">1</span></span> |
   
<span data-ttu-id="e4a8a-118">レジストリ キーを設定したら、2013 デバイス アプリで複数要素認証[(MFA)](set-up-multi-factor-authentication.md)を使用Office 2013 デバイス アプリをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e4a8a-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="e4a8a-p102">現在、クライアント アプリのいずれかを使ってサインインしている場合、変更を有効にするには、サインアウトしてサインインし直す必要があります。それ以外の場合は、ADAL ID が確立されるまで、MRU とローミングの設定が無効になります。</span><span class="sxs-lookup"><span data-stu-id="e4a8a-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="e4a8a-121">デバイスで先進認証を無効にする</span><span class="sxs-lookup"><span data-stu-id="e4a8a-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="e4a8a-122">デバイスで先進認証を無効にするには、デバイスで次のレジストリ キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4a8a-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="e4a8a-123">**レジストリ キー**</span><span class="sxs-lookup"><span data-stu-id="e4a8a-123">**Registry key**</span></span>|<span data-ttu-id="e4a8a-124">**型**</span><span class="sxs-lookup"><span data-stu-id="e4a8a-124">**Type**</span></span>|<span data-ttu-id="e4a8a-125">**値**</span><span class="sxs-lookup"><span data-stu-id="e4a8a-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="e4a8a-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="e4a8a-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="e4a8a-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="e4a8a-127">REG_DWORD</span></span>|<span data-ttu-id="e4a8a-128">0</span><span class="sxs-lookup"><span data-stu-id="e4a8a-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="e4a8a-129">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e4a8a-129">Related content</span></span>

<span data-ttu-id="e4a8a-130">[2 番目の検証Office 2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)にサインインする (記事)</span><span class="sxs-lookup"><span data-stu-id="e4a8a-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>\
<span data-ttu-id="e4a8a-131">[Outlookを求めるメッセージ](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)が表示され、モダン認証を使用してパスワードに接続Office 365しない (記事)</span><span class="sxs-lookup"><span data-stu-id="e4a8a-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

