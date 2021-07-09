---
title: デバイスのオンボーディング方法Windows 10ツール
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
description: センサー Windows 10コンプライアンス ソリューションにセンサー データを送信できるよう、Microsoft 365デバイスをオンボードする
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341702"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="a3a2c-103">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="a3a2c-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="a3a2c-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a3a2c-104">**Applies to:**</span></span>
- [<span data-ttu-id="a3a2c-105">Microsoft 365エンドポイント データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a3a2c-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="a3a2c-106">組織のデバイスは、エンドポイントデータ損失防止サービスMicrosoft 365センサー データを取得するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="a3a2c-107">組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="a3a2c-108">次の展開ツールとメソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="a3a2c-109">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="a3a2c-109">group policy</span></span>
- <span data-ttu-id="a3a2c-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a3a2c-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="a3a2c-111">モバイル デバイスの管理 (Microsoft Intune を含む)</span><span class="sxs-lookup"><span data-stu-id="a3a2c-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="a3a2c-112">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="a3a2c-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a3a2c-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a3a2c-113">In this section</span></span>
<span data-ttu-id="a3a2c-114">トピック</span><span class="sxs-lookup"><span data-stu-id="a3a2c-114">Topic</span></span> | <span data-ttu-id="a3a2c-115">説明</span><span class="sxs-lookup"><span data-stu-id="a3a2c-115">Description</span></span>
:---|:---
[<span data-ttu-id="a3a2c-116">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a3a2c-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="a3a2c-117">グループ ポリシーを使用して、構成パッケージをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="a3a2c-118">デバイスWindowsデバイスのオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a3a2c-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="a3a2c-119">Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1606 または Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1602 以前を使用して、デバイスに構成パッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="a3a2c-120">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a3a2c-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="a3a2c-121">デバイスに構成パッケージを展開するには、Microsoft Intune管理ツールまたはモバイル デバイス管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="a3a2c-122">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a3a2c-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="a3a2c-123">ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="a3a2c-124">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a3a2c-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="a3a2c-125">構成パッケージを使用して VDI デバイスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3a2c-125">Learn how to use the configuration package to configure VDI devices.</span></span>