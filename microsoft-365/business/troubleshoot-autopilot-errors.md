---
title: AutoPilot デバイス エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Microsoft 365 Business で自動操縦デバイスファイルを操作するときに表示される可能性のあるエラーのトラブルシューティング方法について説明します。
ms.openlocfilehash: 7569f18097a1f5959b3dd491958c78886e1e05d6
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547473"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="08697-103">AutoPilot デバイス エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="08697-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="08697-104">デバイスファイルのエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="08697-104">Device file error messages</span></span>

<span data-ttu-id="08697-105">Microsoft 365 Business で自動操縦デバイスファイルを処理するときに表示される可能性のあるいくつかのエラーについては、以下の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08697-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="08697-106">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="08697-106">**Error code**</span></span>|<span data-ttu-id="08697-107">**解決策を実行する**</span><span class="sxs-lookup"><span data-stu-id="08697-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08697-108">無効な要求本文</span><span class="sxs-lookup"><span data-stu-id="08697-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="08697-109">このエラーが発生することはまれです。このエラーが表示された場合は、操作を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="08697-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="08697-110">デバイスのハードウェアハッシュ値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="08697-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="08697-111">このエラーが表示される場合は、1つのデバイスのハードウェアハッシュで CSV ファイルに指定した値が正しくないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="08697-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="08697-112">最初に、値が正しく入力されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="08697-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="08697-113">値が正しいと考えられるが、このエラーがまだ発生している場合は、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="08697-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="08697-114">別のテナントに割り当てられたデバイス</span><span class="sxs-lookup"><span data-stu-id="08697-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="08697-115">このエラーが表示される場合は、1つまたは複数のデバイスのシリアル番号またはプロダクトキーで CSV ファイルに指定した値が正しくないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="08697-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="08697-116">最初に、値が正しく入力されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="08697-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="08697-117">値が正しいと考えられるが、このエラーがまだ発生している場合は、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="08697-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="08697-118">CSV ファイルに無効なシリアル番号またはプロダクトキーが含まれています</span><span class="sxs-lookup"><span data-stu-id="08697-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="08697-119">このエラーが表示される場合は、登録しようとしているデバイスが別の組織によって既に登録されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="08697-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="08697-120">このエラーを解決するには、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="08697-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="08697-121">このデバイスは自動操縦を使用したセットアップではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="08697-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="08697-122">このエラーは、デバイスが自動操縦展開の要件を満たしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="08697-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="08697-123">デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08697-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="08697-124">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="08697-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="08697-125">Windows の標準外の機能を使用していない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="08697-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="08697-126">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="08697-126">Device not found</span></span>  <br/> |<span data-ttu-id="08697-127">このエラーは、CSV ファイル内の1つ以上のデバイスが組織に登録されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="08697-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="08697-128">この問題を解決するには、ハードウェアベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="08697-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
