---
title: アドレス デバイス名の依存関係
description: デバイス名への依存関係を削除するか、例外を要求する
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
ms.openlocfilehash: 8c82acb5306e3add7c41fd4e6f7e313782d47574
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893902"
---
# <a name="address-device-name-dependency"></a><span data-ttu-id="c132d-103">アドレス デバイス名の依存関係</span><span class="sxs-lookup"><span data-stu-id="c132d-103">Address device name dependency</span></span>

<span data-ttu-id="c132d-104">Microsoft マネージド デスクトップ登録時に標準化された名前形式が適用され、後で名前が変更された場合はデバイスの名前が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c132d-104">Microsoft Managed Desktop applies a standardized name format when devices are enrolled and will automatically rename devices if the name is changed later.</span></span> <span data-ttu-id="c132d-105">詳細については、「デバイス名 [」を参照してください](../service-description/device-names.md)。</span><span class="sxs-lookup"><span data-stu-id="c132d-105">For more info, see [Device names](../service-description/device-names.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c132d-106">環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft マネージド デスクトップ に登録する前に、その依存関係を削除するオプションを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c132d-106">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c132d-107">名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c132d-107">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>