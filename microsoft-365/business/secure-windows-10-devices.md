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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Windows 10 デバイスが職場または学校のアカウントにサインインしたときに受信する既定のデバイスポリシーの設定を構成する方法について説明します。
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898070"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="0d2a3-103">Windows 10 デバイスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="0d2a3-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="0d2a3-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="0d2a3-105">ここで構成する設定は、Windows 10 の既定のデバイス ポリシーの一部です。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="0d2a3-106">Windows 10 デバイス (モバイルデバイスや Pc を含む) に接続するすべてのユーザーは、職場アカウントを使用してサインインすることで、これらの設定を自動的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="0d2a3-107">セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="0d2a3-108">Windows 10 デバイスをセキュリティで保護する設定</span><span class="sxs-lookup"><span data-stu-id="0d2a3-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="0d2a3-p102">既定では、すべての設定が **オン**になっています。次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d2a3-111">Setting</span><span class="sxs-lookup"><span data-stu-id="0d2a3-111">Setting</span></span>  <br/> |<span data-ttu-id="0d2a3-112">説明</span><span class="sxs-lookup"><span data-stu-id="0d2a3-112">Description</span></span>  <br/> |
|<span data-ttu-id="0d2a3-113">Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="0d2a3-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="0d2a3-114">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="0d2a3-115">Microsoft Edge で PC を Web ベースの脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="0d2a3-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="0d2a3-116">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="0d2a3-117">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="0d2a3-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="0d2a3-p103">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0d2a3-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="0d2a3-121">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="0d2a3-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="0d2a3-p104">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="0d2a3-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|