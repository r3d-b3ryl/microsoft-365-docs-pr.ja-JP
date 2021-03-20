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
description: 仕事または学校のアカウントにサインインすると、Windows 10 デバイスが受け取る既定のデバイス ポリシーの設定を構成する方法について説明します。
ms.openlocfilehash: 85383b1e1d2f2af3fd49d4a0c56c5d99586d607d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912612"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="bbe94-103">Windows 10 デバイスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="bbe94-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="bbe94-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bbe94-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="bbe94-105">ここで構成する設定は、Windows 10 の既定のデバイス ポリシーの一部です。</span><span class="sxs-lookup"><span data-stu-id="bbe94-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="bbe94-106">モバイル デバイスや PC を含む Windows 10 デバイスを自分の仕事用アカウントでサインインして接続するユーザーはすべて、これらの設定を自動的に受信します。</span><span class="sxs-lookup"><span data-stu-id="bbe94-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="bbe94-107">セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bbe94-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="bbe94-108">Windows 10 デバイスをセキュリティで保護する設定</span><span class="sxs-lookup"><span data-stu-id="bbe94-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="bbe94-p102">既定では、すべての設定が **オン** になっています。次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bbe94-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bbe94-111">Setting</span><span class="sxs-lookup"><span data-stu-id="bbe94-111">Setting</span></span>  <br/> |<span data-ttu-id="bbe94-112">説明</span><span class="sxs-lookup"><span data-stu-id="bbe94-112">Description</span></span>  <br/> |
|<span data-ttu-id="bbe94-113">Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="bbe94-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="bbe94-114">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe94-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="bbe94-115">Microsoft Edge で PC を Web ベースの脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="bbe94-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="bbe94-116">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="bbe94-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="bbe94-117">不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する</span><span class="sxs-lookup"><span data-stu-id="bbe94-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="bbe94-118">BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="bbe94-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="bbe94-119">詳細については [、「Bitlocker FAQ」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)。</span><span class="sxs-lookup"><span data-stu-id="bbe94-119">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="bbe94-120">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="bbe94-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="bbe94-p104">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bbe94-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|