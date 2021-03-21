---
title: Windows 10 デバイスのオンボード ツールと各種方法
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
description: センサー データを Microsoft 365 コンプライアンス ソリューションに送信できるよう、Windows 10 デバイスをオンボードする
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917853"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="ef62b-103">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="ef62b-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="ef62b-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ef62b-104">**Applies to:**</span></span>
- [<span data-ttu-id="ef62b-105">Microsoft 365 Endpoint データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="ef62b-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="ef62b-106">Microsoft 365 Endpoint データ損失防止サービスがセンサー データを取得できるよう、組織内のデバイスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef62b-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="ef62b-107">組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="ef62b-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="ef62b-108">次の展開ツールとメソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ef62b-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="ef62b-109">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="ef62b-109">group policy</span></span>
- <span data-ttu-id="ef62b-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ef62b-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="ef62b-111">モバイル デバイスの管理 (Microsoft Intune を含む)</span><span class="sxs-lookup"><span data-stu-id="ef62b-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="ef62b-112">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="ef62b-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ef62b-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ef62b-113">In this section</span></span>
<span data-ttu-id="ef62b-114">トピック</span><span class="sxs-lookup"><span data-stu-id="ef62b-114">Topic</span></span> | <span data-ttu-id="ef62b-115">説明</span><span class="sxs-lookup"><span data-stu-id="ef62b-115">Description</span></span>
:---|:---
[<span data-ttu-id="ef62b-116">グループ ポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ef62b-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="ef62b-117">グループ ポリシーを使用して、構成パッケージをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="ef62b-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="ef62b-118">Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ef62b-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="ef62b-119">Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1606 または Microsoft Endpoint Configuration Manager (現在のブランチ) バージョン 1602 以前を使用して、デバイスに構成パッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="ef62b-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="ef62b-120">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ef62b-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="ef62b-121">デバイスに構成パッケージを展開するには、モバイル デバイス管理ツールまたは Microsoft Intune を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef62b-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="ef62b-122">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ef62b-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="ef62b-123">ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef62b-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="ef62b-124">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ef62b-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="ef62b-125">構成パッケージを使用して VDI デバイスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef62b-125">Learn how to use the configuration package to configure VDI devices.</span></span>