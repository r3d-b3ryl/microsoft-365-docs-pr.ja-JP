---
title: Jamf Pro を使用した macOS 用 Microsoft Defender for Endpoint の展開
description: Jamf Pro を使用した macOS 用 Microsoft Defender for Endpoint の展開
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
ms.openlocfilehash: e49a56b138e792f06229345d19a5867c9f6438af
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862261"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="1a6c5-104">Jamf Pro を使用した macOS での Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="1a6c5-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1a6c5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1a6c5-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a6c5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a6c5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1a6c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a6c5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1a6c5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1a6c5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a6c5-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="1a6c5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1a6c5-110">Jamf Pro を使用して macOS に Microsoft Defender for Endpoint を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a6c5-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="1a6c5-111">macOS Catalina (10.15.4) 以降のバージョンの macOS を使用している場合は [、「macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)および macOS の新しいバージョンの新しい構成プロファイル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a6c5-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="1a6c5-112">これは、複数の手順のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1a6c5-112">This is a multi step process.</span></span> <span data-ttu-id="1a6c5-113">次のすべての手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6c5-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="1a6c5-114">Jamf ポータルへのログイン</span><span class="sxs-lookup"><span data-stu-id="1a6c5-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="1a6c5-115">Jamf Pro の macOS デバイス グループで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1a6c5-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="1a6c5-116">Jamf Pro の macOS ポリシーで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1a6c5-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="1a6c5-117">MacOS デバイス上の Microsoft Defender for Endpoint を Jamf Pro に登録する</span><span class="sxs-lookup"><span data-stu-id="1a6c5-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




