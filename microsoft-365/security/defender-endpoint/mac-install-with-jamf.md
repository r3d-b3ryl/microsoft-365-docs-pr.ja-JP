---
title: Jamf Pro を使用した macOS 用 Microsoft Defender ATP の展開
description: Jamf Pro を使用した macOS 用 Microsoft Defender ATP の展開
keywords: microsoft、 defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0d4d0e46bf563c392d1c00f00491ec5511ef0f92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062284"
---
# <a name="deploying-microsoft-defender-for-endpoint-for-macos-with-jamf-pro"></a><span data-ttu-id="27921-104">Jamf Pro を使用した macOS 用 Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="27921-104">Deploying Microsoft Defender for Endpoint for macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="27921-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="27921-105">**Applies to:**</span></span>
- [<span data-ttu-id="27921-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="27921-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="27921-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27921-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="27921-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="27921-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="27921-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="27921-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="27921-110">Jamf Pro を使用して MacOS 用 Microsoft Defender for Endpoint を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27921-110">Learn how to deploy Microsoft Defender for Endpoint for macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="27921-111">macOS Catalina (10.15.4) 以降のバージョンの macOS を使用している場合は [、「macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)および macOS の新しいバージョンの新しい構成プロファイル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27921-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="27921-112">これは、複数の手順のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="27921-112">This is a multi step process.</span></span> <span data-ttu-id="27921-113">次のすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27921-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="27921-114">Jamf ポータルへのログイン</span><span class="sxs-lookup"><span data-stu-id="27921-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="27921-115">Jamf Pro で MacOS デバイス グループの Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="27921-115">Setup the Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="27921-116">Jamf Pro で MacOS ポリシーの Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="27921-116">Setup the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="27921-117">MacOS デバイスの Microsoft Defender for Endpoint を Jamf Pro に登録する</span><span class="sxs-lookup"><span data-stu-id="27921-117">Enroll the Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




