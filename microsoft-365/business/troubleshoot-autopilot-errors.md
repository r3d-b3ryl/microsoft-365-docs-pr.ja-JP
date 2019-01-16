---
title: 自動操縦デバイス エラーをトラブルシューティングする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 自動操縦装置のデバイス ファイルのエラーをトラブルシューティングする方法について説明します。
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869179"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="ea2b8-103">自動操縦デバイス エラーをトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="ea2b8-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="ea2b8-104">デバイス ファイルのエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="ea2b8-104">Device file error messages</span></span>

<span data-ttu-id="ea2b8-105">エラーのいくつかのここでの情報表示されるマイクロソフト 365 ビジネス内のデバイス ファイルの自動操縦装置の操作中にあります。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="ea2b8-106">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ea2b8-106">**Error code**</span></span>|<span data-ttu-id="ea2b8-107">**しようとする修正プログラム**</span><span class="sxs-lookup"><span data-stu-id="ea2b8-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea2b8-108">無効な要求の本体</span><span class="sxs-lookup"><span data-stu-id="ea2b8-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="ea2b8-109">まれには、このエラーが発生このエラーが発生した場合、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="ea2b8-110">デバイスのハードウェア ハッシュの値が正しくないです。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="ea2b8-p101">このエラーが表示された場合は、1 つのデバイスのハードウェア ハッシュの CSV ファイルで指定した値が正しくないことを意味します。最初に、値が正しく入力されているを確認します。値は正しいですが、このエラーが引き続き発生している場合は、ヘルプについては、ハードウェアの製造元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ea2b8-114">他のテナントに割り当てられたデバイス</span><span class="sxs-lookup"><span data-stu-id="ea2b8-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="ea2b8-p102">このエラーが表示された場合は、シリアル番号または 1 つまたは複数のデバイスのプロダクト キーのいずれかの CSV ファイルで指定された値が正しくないことを意味します。最初に、値が正しく入力されているを確認します。値は正しいですが、このエラーが引き続き発生している場合は、ヘルプについては、ハードウェアの製造元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ea2b8-118">CSV ファイルには、無効なシリアル番号、またはプロダクト キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="ea2b8-p103">このエラーが発生する場合は、他の組織で登録しようとしたときのデバイスが既に登録されていることを意味します。これを修正するには、ヘルプについては、ハードウェアの製造元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ea2b8-121">このデバイスが自動操縦を使用して、セットアップでサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ea2b8-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="ea2b8-p104">このエラーは、デバイスが自動操縦装置の配置の要件を満たしていないを意味します。デバイスは、これらの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="ea2b8-124">Windows 10 バージョン 1703 以降。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="ea2b8-125">Windows out-of-box experience を行っていない新しいデバイス。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="ea2b8-126">装置が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-126">Device not found</span></span>  <br/> |<span data-ttu-id="ea2b8-p105">このエラーは、CSV ファイル内の 1 つまたは複数のデバイスが組織に登録されていないことを意味します。これを修正するには、ヘルプについては、ハードウェアの製造元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ea2b8-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
