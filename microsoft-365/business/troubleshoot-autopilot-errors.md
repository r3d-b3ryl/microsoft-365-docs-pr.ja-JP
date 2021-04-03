---
title: AutoPilot デバイス エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Microsoft 365 Business Premium の AutoPilot デバイス ファイルの操作中に表示される可能性のあるエラーのトラブルシューティング方法について説明します。
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578089"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="1be95-103">AutoPilot デバイス エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1be95-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="1be95-104">デバイス ファイルのエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="1be95-104">Device file error messages</span></span>

<span data-ttu-id="1be95-105">Microsoft 365 Business Premium で AutoPilot デバイス ファイルを操作している間に表示されるエラーの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="1be95-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="1be95-106">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="1be95-106">**Error code**</span></span>|<span data-ttu-id="1be95-107">**試してみる修正**</span><span class="sxs-lookup"><span data-stu-id="1be95-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1be95-108">要求本文が無効です</span><span class="sxs-lookup"><span data-stu-id="1be95-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="1be95-109">このエラーはまれに発生します。このエラーが表示された場合は、もう一度操作を試してください。</span><span class="sxs-lookup"><span data-stu-id="1be95-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="1be95-110">デバイスのハードウェア ハッシュ値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="1be95-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="1be95-111">このエラーが表示された場合は、1 つのデバイスのハードウェア ハッシュに対して CSV ファイルに指定した値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="1be95-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="1be95-112">最初に、値が正しく入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1be95-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="1be95-113">値が正しいと思うが、このエラーがまだ発生している場合は、ハードウェア ベンダーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1be95-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1be95-114">別のテナントに割り当てられたデバイス</span><span class="sxs-lookup"><span data-stu-id="1be95-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="1be95-115">このエラーが表示された場合は、1 つ以上のデバイスのシリアル番号またはプロダクト キーに対して CSV ファイルに指定した値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="1be95-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="1be95-116">最初に、値が正しく入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1be95-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="1be95-117">値が正しいと思うが、このエラーがまだ発生している場合は、ハードウェア ベンダーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1be95-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1be95-118">CSV ファイルに無効なシリアル番号またはプロダクト キーが含まれている</span><span class="sxs-lookup"><span data-stu-id="1be95-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="1be95-119">このエラーが表示された場合は、登録しようとしているデバイスが別の組織によって既に登録されているという意味です。</span><span class="sxs-lookup"><span data-stu-id="1be95-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="1be95-120">このエラーを修正するには、ハードウェア ベンダーにヘルプを求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1be95-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1be95-121">このデバイスは、AutoPilot を使用したセットアップではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="1be95-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="1be95-122">このエラーは、デバイスが AutoPilot の展開要件を満たしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1be95-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="1be95-123">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1be95-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="1be95-124">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="1be95-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="1be95-125">Windows のアウトオブボックス エクスペリエンスを使用していない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="1be95-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="1be95-126">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="1be95-126">Device not found</span></span>  <br/> |<span data-ttu-id="1be95-127">このエラーは、CSV ファイル内の 1 つ以上のデバイスが組織に登録されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1be95-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="1be95-128">これを修正するには、ハードウェア ベンダーにヘルプを求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1be95-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
