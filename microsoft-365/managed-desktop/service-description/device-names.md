---
title: デバイス名
description: デバイスMicrosoft マネージド デスクトップ管理する方法
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893892"
---
# <a name="device-names"></a><span data-ttu-id="3e21e-103">デバイス名</span><span class="sxs-lookup"><span data-stu-id="3e21e-103">Device names</span></span>

<span data-ttu-id="3e21e-104">Microsoft マネージド デスクトップオートパイロットWindows、Azure Active Directory、およびMicrosoft Intune。</span><span class="sxs-lookup"><span data-stu-id="3e21e-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="3e21e-105">これらのサービスがシームレスに連携するには、デバイスに一貫性のある標準化された名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e21e-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="3e21e-106">Microsoft マネージド デスクトップ登録時に、標準化された名前形式 *(MMD-%RAND11* という形式) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e21e-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="3e21e-107">WindowsAutopilot は、これらの名前を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="3e21e-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="3e21e-108">自動パイロットの詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="3e21e-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="3e21e-109">名前の自動変更</span><span class="sxs-lookup"><span data-stu-id="3e21e-109">Automated name changes</span></span>

<span data-ttu-id="3e21e-110">デバイスの名前が後で変更された場合Microsoft マネージド デスクトップ、デバイスの名前は標準化された形式で新しい名前に自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="3e21e-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="3e21e-111">このプロセスは 4 時間ごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="3e21e-111">This process occurs every four hours.</span></span> <span data-ttu-id="3e21e-112">名前の変更は、ユーザーが次回デバイスを再起動する際に行います。</span><span class="sxs-lookup"><span data-stu-id="3e21e-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e21e-113">環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft マネージド デスクトップ に登録する前に、その依存関係を削除するオプションを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e21e-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="3e21e-114">名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e21e-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>