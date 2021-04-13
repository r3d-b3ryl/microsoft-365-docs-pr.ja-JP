---
title: Jamf Pro でデバイス グループを設定する
description: MacOS 用 Microsoft Defender ATP の Jamf Pro でデバイス グループを設定する方法について説明します。
keywords: device, group, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6c1d6ae5d4635186bf0a1cbb55c7f906e8584f01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689691"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="19625-104">Jamf Pro の macOS デバイス グループで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="19625-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19625-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="19625-105">**Applies to:**</span></span>
- [<span data-ttu-id="19625-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="19625-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19625-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19625-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19625-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="19625-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="19625-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="19625-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="19625-110">グループ ポリシー組織単位 (OUs)、Microsoft Endpoint Configuration Manager のデバイス コレクション、Intune のデバイス グループに似たデバイス グループを設定します。</span><span class="sxs-lookup"><span data-stu-id="19625-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="19625-111">[静的コンピューター **グループ] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="19625-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="19625-112">[**新規**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="19625-112">Select **New**.</span></span> 

    ![Jamf Pro1 のイメージ](images/jamf-pro-static-group.png)

3. <span data-ttu-id="19625-114">表示名を指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="19625-114">Provide a display name and select **Save**.</span></span>

    ![Jamf Pro2 の画像](images/jamfpro-machine-group.png)

4. <span data-ttu-id="19625-116">これで、[静的コンピューター グループ] の **下に Contoso のコンピューター** **グループが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="19625-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Jamf Pro3 の画像](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="19625-118">次の手順</span><span class="sxs-lookup"><span data-stu-id="19625-118">Next step</span></span>
- [<span data-ttu-id="19625-119">Jamf Pro の macOS ポリシーで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="19625-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
