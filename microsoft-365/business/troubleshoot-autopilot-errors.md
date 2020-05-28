---
title: AutoPilot デバイス エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Microsoft 365 Business Premium で自動操縦デバイスファイルを操作するときに表示される可能性のあるエラーのトラブルシューティング方法について説明します。
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403412"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="f9365-103">AutoPilot デバイス エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f9365-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="f9365-104">デバイスファイルのエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="f9365-104">Device file error messages</span></span>

<span data-ttu-id="f9365-105">ここでは、Microsoft 365 Business Premium で自動操縦デバイスファイルを処理するときに表示される可能性のあるエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f9365-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="f9365-106">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="f9365-106">**Error code**</span></span>|<span data-ttu-id="f9365-107">**解決策を実行する**</span><span class="sxs-lookup"><span data-stu-id="f9365-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9365-108">無効な要求本文</span><span class="sxs-lookup"><span data-stu-id="f9365-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="f9365-109">このエラーが発生することはまれです。このエラーが表示された場合は、操作を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="f9365-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="f9365-110">デバイスのハードウェアハッシュ値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f9365-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="f9365-111">このエラーが表示される場合は、1つのデバイスのハードウェアハッシュで CSV ファイルに指定した値が正しくないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9365-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="f9365-112">最初に、値が正しく入力されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9365-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="f9365-113">値が正しいと考えられるが、このエラーがまだ発生している場合は、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f9365-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f9365-114">別のテナントに割り当てられたデバイス</span><span class="sxs-lookup"><span data-stu-id="f9365-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="f9365-115">このエラーが表示される場合は、1つまたは複数のデバイスのシリアル番号またはプロダクトキーで CSV ファイルに指定した値が正しくないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9365-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="f9365-116">最初に、値が正しく入力されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9365-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="f9365-117">値が正しいと考えられるが、このエラーがまだ発生している場合は、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f9365-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f9365-118">CSV ファイルに無効なシリアル番号またはプロダクトキーが含まれています</span><span class="sxs-lookup"><span data-stu-id="f9365-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="f9365-119">このエラーが表示される場合は、登録しようとしているデバイスが別の組織によって既に登録されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9365-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="f9365-120">このエラーを解決するには、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f9365-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f9365-121">このデバイスは自動操縦を使用したセットアップではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="f9365-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="f9365-122">このエラーは、デバイスが自動操縦展開の要件を満たしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9365-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="f9365-123">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9365-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="f9365-124">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="f9365-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="f9365-125">Windows の標準外の機能を使用していない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="f9365-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="f9365-126">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="f9365-126">Device not found</span></span>  <br/> |<span data-ttu-id="f9365-127">このエラーは、CSV ファイル内の1つ以上のデバイスが組織に登録されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9365-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="f9365-128">この問題を解決するには、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f9365-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
