---
title: Windows 10 デバイスをセキュリティで保護する
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Windows 10 デバイスが職場または学校のアカウントにサインインしたときに受信する既定のデバイスポリシーの設定を構成する方法について説明します。
ms.openlocfilehash: dfa6aca1f12ab37b8b0926dea4a6a79c934b1250
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561282"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="d7566-103">Windows 10 デバイスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="d7566-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="d7566-104">ここで構成する設定は、Windows 10 の既定のデバイス ポリシーの一部です。</span><span class="sxs-lookup"><span data-stu-id="d7566-104">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="d7566-105">Windows 10 デバイス (モバイルデバイスや Pc を含む) に接続するすべてのユーザーは、職場アカウントを使用してサインインすることで、これらの設定を自動的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7566-105">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="d7566-106">セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7566-106">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="d7566-107">Windows 10 デバイスをセキュリティで保護する設定</span><span class="sxs-lookup"><span data-stu-id="d7566-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="d7566-p102">既定では、すべての設定が **オン**になっています。次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7566-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d7566-110">設定</span><span class="sxs-lookup"><span data-stu-id="d7566-110">Setting</span></span>  <br/> |<span data-ttu-id="d7566-111">説明</span><span class="sxs-lookup"><span data-stu-id="d7566-111">Description</span></span>  <br/> |
|<span data-ttu-id="d7566-112">Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="d7566-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="d7566-113">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7566-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="d7566-114">Microsoft Edge で PC を Web ベースの脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="d7566-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="d7566-115">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="d7566-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="d7566-116">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="d7566-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="d7566-p103">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d7566-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="d7566-120">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="d7566-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="d7566-p104">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="d7566-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="d7566-123">ユーザーが Cortana にアクセスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="d7566-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="d7566-124">Cortana は非常に役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7566-124">Cortana can be very helpful!</span></span> <span data-ttu-id="d7566-125">Cortana では、設定を有効または無効にしたり、案内を表示したり、予定に時間があるかどうかを確認したりすることができます。**この設定は既定でオンに**しておきます。</span><span class="sxs-lookup"><span data-stu-id="d7566-125">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="d7566-126">ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する</span><span class="sxs-lookup"><span data-stu-id="d7566-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="d7566-127">Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d7566-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="d7566-128">Windows 10 デバイスを自動的に最新の状態に維持する</span><span class="sxs-lookup"><span data-stu-id="d7566-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="d7566-129">Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="d7566-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

