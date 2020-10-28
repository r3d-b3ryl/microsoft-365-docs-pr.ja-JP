---
title: Windows 10 デバイスのオンボードツールおよび方法 (プレビュー)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft 365 コンプライアンスソリューションにセンサーデータを送信できるように、Windows 10 デバイスをオンボードにします。
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769644"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="eb246-103">Windows 10 デバイスのオンボードツールおよび方法 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="eb246-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="eb246-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="eb246-104">**Applies to:**</span></span>
- [<span data-ttu-id="eb246-105">Microsoft 365 エンドポイントのデータ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="eb246-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="eb246-106">組織内のデバイスは、Microsoft 365 エンドポイントデータ損失防止サービスがそれらからセンサーデータを取得できるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb246-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="eb246-107">組織内のデバイスの構成に使用できるさまざまな方法と展開ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="eb246-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="eb246-108">次の展開ツールと方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eb246-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="eb246-109">グループポリシー</span><span class="sxs-lookup"><span data-stu-id="eb246-109">group policy</span></span>
- <span data-ttu-id="eb246-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eb246-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="eb246-111">モバイルデバイス管理 (Microsoft Intune を含む)</span><span class="sxs-lookup"><span data-stu-id="eb246-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="eb246-112">ローカルスクリプト</span><span class="sxs-lookup"><span data-stu-id="eb246-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb246-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eb246-113">In this section</span></span>
<span data-ttu-id="eb246-114">トピック</span><span class="sxs-lookup"><span data-stu-id="eb246-114">Topic</span></span> | <span data-ttu-id="eb246-115">説明</span><span class="sxs-lookup"><span data-stu-id="eb246-115">Description</span></span>
:---|:---
[<span data-ttu-id="eb246-116">グループポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="eb246-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="eb246-117">グループポリシーを使用して、構成パッケージをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb246-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="eb246-118">Microsoft エンドポイント構成マネージャーを使用した Windows デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="eb246-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="eb246-119">構成パッケージをデバイスに展開するには、Microsoft エンドポイント構成マネージャー (current branch) バージョン1606または Microsoft エンドポイント構成マネージャー (current branch) version 1602 またはそれ以前のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb246-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="eb246-120">モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="eb246-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="eb246-121">モバイルデバイス管理ツールまたは Microsoft Intune を使用して、構成パッケージをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="eb246-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="eb246-122">ローカルスクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="eb246-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="eb246-123">ローカルスクリプトを使用して構成パッケージをエンドポイントに展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb246-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="eb246-124">オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="eb246-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="eb246-125">構成パッケージを使用して VDI デバイスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb246-125">Learn how to use the configuration package to configure VDI devices.</span></span>
