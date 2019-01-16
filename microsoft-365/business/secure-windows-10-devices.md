---
title: Windows 10 デバイスをセキュリティで保護する
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'デフォルトおよび 10 の Windows デバイスをセキュリティで保護するその他の設定について説明します。 '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869557"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="cccb0-103">Windows 10 デバイスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="cccb0-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="cccb0-p101">ここで構成する設定は、Windows 10 の既定のデバイス ポリシーの一部です。職場アカウントでサインインして、モバイル デバイスや PC などの Windows 10 デバイスに接続するすべてのユーザーは、これらの設定を自動的に受け取ります。セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cccb0-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="cccb0-107">Windows 10 デバイスをセキュリティで保護する設定</span><span class="sxs-lookup"><span data-stu-id="cccb0-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="cccb0-p102">既定では、すべての設定が **オン**になっています。次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cccb0-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cccb0-110">設定</span><span class="sxs-lookup"><span data-stu-id="cccb0-110">Setting</span></span>  <br/> |<span data-ttu-id="cccb0-111">説明</span><span class="sxs-lookup"><span data-stu-id="cccb0-111">Description</span></span>  <br/> |
|<span data-ttu-id="cccb0-112">Windows Defender ウイルス対策を使用してウイルスなどの脅威から PC を保護する</span><span class="sxs-lookup"><span data-stu-id="cccb0-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="cccb0-113">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cccb0-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="cccb0-114">Microsoft Edge で Web ベースの脅威から PC を保護する</span><span class="sxs-lookup"><span data-stu-id="cccb0-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="cccb0-115">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="cccb0-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="cccb0-116">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="cccb0-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="cccb0-p103">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーが、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりすると、デバイスを無作為な視線に向けて無防備な状態にしてしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="cccb0-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="cccb0-120">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="cccb0-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="cccb0-p104">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="cccb0-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="cccb0-123">ユーザーが Cortana にアクセスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="cccb0-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="cccb0-p105">Cortana は非常に役に立つ場合があります。Cortana によって設定をオンまたはオフにしたり、手順を示したり、ユーザーが予定に間に合うようにしたりすることができるため、既定では、Microsoft はこの設定を **オン**にしています。  </span><span class="sxs-lookup"><span data-stu-id="cccb0-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="cccb0-126">ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する</span><span class="sxs-lookup"><span data-stu-id="cccb0-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="cccb0-127">Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cccb0-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="cccb0-128">Windows 10 デバイスを自動的に最新の状態に維持する</span><span class="sxs-lookup"><span data-stu-id="cccb0-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="cccb0-129">Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="cccb0-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

