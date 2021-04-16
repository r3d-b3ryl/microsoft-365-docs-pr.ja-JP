---
title: Jamf Pro でデバイス グループを設定する
description: MacOS 用エンドポイント向け Microsoft Defender 用 Jamf Pro でデバイス グループをセットアップする方法について説明します。
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
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861613"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="a5111-104">Jamf Pro の macOS デバイス グループで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a5111-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a5111-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a5111-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5111-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5111-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5111-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5111-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5111-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a5111-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a5111-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a5111-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a5111-110">グループ ポリシー組織単位 (OUs)、Microsoft Endpoint Configuration Manager のデバイス コレクション、Intune のデバイス グループに似たデバイス グループを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5111-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="a5111-111">[静的コンピューター **グループ] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a5111-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="a5111-112">[**新規**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5111-112">Select **New**.</span></span> 

    ![Jamf Pro1 のイメージ](images/jamf-pro-static-group.png)

3. <span data-ttu-id="a5111-114">表示名を指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5111-114">Provide a display name and select **Save**.</span></span>

    ![Jamf Pro2 の画像](images/jamfpro-machine-group.png)

4. <span data-ttu-id="a5111-116">これで、[静的コンピューター グループ] の **下に Contoso のコンピューター** **グループが表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a5111-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Jamf Pro3 の画像](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="a5111-118">次の手順</span><span class="sxs-lookup"><span data-stu-id="a5111-118">Next step</span></span>
- [<span data-ttu-id="a5111-119">Jamf Pro の macOS ポリシーで Microsoft Defender for Endpoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a5111-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
