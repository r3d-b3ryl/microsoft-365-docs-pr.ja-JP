---
title: Microsoft Defender for Endpoint Device Control リムーバブル Storage保護
description: ユーザーまたはコンピューター、または両方が未承認のリムーバブル 記憶域メディアを使用できない '機能を理解する
keywords: リムーバブル 記憶域メディア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538389"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="63dab-104">Microsoft Defender for Endpoint Device Control リムーバブル Storage保護</span><span class="sxs-lookup"><span data-stu-id="63dab-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="63dab-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection を使用すると、ユーザーまたはコンピューター、または両方が未承認のリムーバブル 記憶域メディアを使用できません。</span><span class="sxs-lookup"><span data-stu-id="63dab-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="63dab-106">保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="63dab-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="63dab-107">デバイスのインストール</span><span class="sxs-lookup"><span data-stu-id="63dab-107">Device installation</span></span>

<span data-ttu-id="63dab-108">**機能 -** さまざまなデバイスプロパティに基づいて除外の設定または除外なしでインストールを防止します。</span><span class="sxs-lookup"><span data-stu-id="63dab-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="63dab-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="63dab-109">**Description**</span></span>
- <span data-ttu-id="63dab-110">コンピューター レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="63dab-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="63dab-111">MEM と GPO をサポートします。</span><span class="sxs-lookup"><span data-stu-id="63dab-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="63dab-112">一覧に示[されている [デバイスのプロパティ](#device-properties)] がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63dab-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="63dab-113">デバイス の詳細については、「Windows Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法」[を参照してください](control-usb-devices-using-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="63dab-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="63dab-114">**サポートされているプラットフォーム**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="63dab-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="63dab-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="63dab-115">**Description**</span></span>
- <span data-ttu-id="63dab-116">コンピューター レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます</span><span class="sxs-lookup"><span data-stu-id="63dab-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="63dab-117">macOS 固有の情報については [、「macOS のデバイス コントロール」を参照してください](mac-device-control-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="63dab-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="63dab-118">**サポートされているプラットフォーム** - macOS Catalina 10.15.4+ (システム拡張機能が有効な場合)</span><span class="sxs-lookup"><span data-stu-id="63dab-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="63dab-119">リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-119">Removable storage Access Control</span></span>

<span data-ttu-id="63dab-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="63dab-120">**Capabilities**</span></span>
- <span data-ttu-id="63dab-121">*監査* さまざまなデバイス プロパティに基づくリムーバブル 記憶域への読み取りまたは書き込みまたは実行アクセス。除外の付きまたは除外なし。</span><span class="sxs-lookup"><span data-stu-id="63dab-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="63dab-122">*[防止]* 読み取りまたは書き込みまたは除外なしのアクセスを実行する - さまざまなデバイスプロパティに基づいて特定のデバイスを許可します。</span><span class="sxs-lookup"><span data-stu-id="63dab-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="63dab-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="63dab-123">**Description**</span></span>
- <span data-ttu-id="63dab-124">コンピューターまたはユーザーのどちらかまたは両方で適用されます。特定のユーザーが特定のコンピューター上の特定のリムーバブル 記憶域への読み取り/書き込み/実行アクセスを実行できる唯一の許可。</span><span class="sxs-lookup"><span data-stu-id="63dab-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="63dab-125">MEM OMA-URI と GPO をサポートします。</span><span class="sxs-lookup"><span data-stu-id="63dab-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="63dab-126">一覧に示[されている [デバイスのプロパティ](#device-properties)] がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63dab-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="63dab-127">この機能については、「リムーバブル Windows[アクセス制御」を参照してください](device-control-removable-storage-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="63dab-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="63dab-128">**サポートされているプラットフォーム**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="63dab-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="63dab-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="63dab-129">**Description**</span></span>
- <span data-ttu-id="63dab-130">コンピューター レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="63dab-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="63dab-131">macOS 固有の情報については [、「macOS のデバイス コントロール」を参照してください](mac-device-control-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="63dab-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="63dab-132">**サポートされているプラットフォーム** - macOS Catalina 10.15.4+ (システム拡張機能が有効な場合)</span><span class="sxs-lookup"><span data-stu-id="63dab-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="63dab-133">Windowsポータブル デバイス アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="63dab-134">**機能**- ポータブル デバイスへの読み取りまたは書き [Windows](/windows-hardware/drivers/portable/)アクセスを拒否します 。たとえば、タブレット、iPhone。</span><span class="sxs-lookup"><span data-stu-id="63dab-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="63dab-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="63dab-135">**Description**</span></span>
- <span data-ttu-id="63dab-136">コンピューターまたはユーザー、または両方で適用されます。</span><span class="sxs-lookup"><span data-stu-id="63dab-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="63dab-137">MEM OMA-URI と GPO をサポートします。</span><span class="sxs-lookup"><span data-stu-id="63dab-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="63dab-138">**サポートされているプラットフォーム**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="63dab-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="63dab-139">エンドポイント DLP リムーバブル ストレージ</span><span class="sxs-lookup"><span data-stu-id="63dab-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="63dab-140">**機能** - ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーするのを監査または警告または防止します。</span><span class="sxs-lookup"><span data-stu-id="63dab-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="63dab-141">**説明**- エンドポイントデータ損失防止のWindows詳細 [については、「Microsoft 365」を参照してください](../../compliance/endpoint-dlp-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="63dab-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="63dab-142">**サポートされているプラットフォーム**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="63dab-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="63dab-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="63dab-143">BitLocker</span></span> 

<span data-ttu-id="63dab-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="63dab-144">**Capabilities**</span></span>
- <span data-ttu-id="63dab-145">保護されていないリムーバブル ドライブに書き込まれるデータをBitLockerします。</span><span class="sxs-lookup"><span data-stu-id="63dab-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="63dab-146">組織が所有するコンピューターで暗号化されていないリムーバブル ドライブへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="63dab-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="63dab-147">**説明**- 詳細については、「Windows – リムーバブル ドライブ [BitLocker」を参照設定。](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)</span><span class="sxs-lookup"><span data-stu-id="63dab-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="63dab-148">**サポートされているプラットフォーム**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="63dab-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="63dab-149">デバイスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="63dab-149">Device properties</span></span>

<span data-ttu-id="63dab-150">Microsoft Defender for Endpoint Device Control リムーバブル Storage保護を使用すると、以下の表に示すプロパティに基づいてリムーバブル 記憶域へのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="63dab-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="63dab-151">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="63dab-151">Property Name</span></span>  |<span data-ttu-id="63dab-152">適用可能なポリシー</span><span class="sxs-lookup"><span data-stu-id="63dab-152">Applicable Policies</span></span>  |<span data-ttu-id="63dab-153">オペレーティング システムに適用される</span><span class="sxs-lookup"><span data-stu-id="63dab-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="63dab-154">説明</span><span class="sxs-lookup"><span data-stu-id="63dab-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="63dab-155">デバイス クラス</span><span class="sxs-lookup"><span data-stu-id="63dab-155">Device Class</span></span>    |     [<span data-ttu-id="63dab-156">Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法</span><span class="sxs-lookup"><span data-stu-id="63dab-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="63dab-157">Windows</span><span class="sxs-lookup"><span data-stu-id="63dab-157">Windows</span></span>      |  <span data-ttu-id="63dab-158">デバイス ID 形式の詳細については、「デバイス セットアップ [クラス」を参照してください](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。</span><span class="sxs-lookup"><span data-stu-id="63dab-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="63dab-159">**注**: デバイスインストールは、リムーバブル ストレージだけでなく、任意のデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="63dab-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="63dab-160">プライマリ ID</span><span class="sxs-lookup"><span data-stu-id="63dab-160">Primary ID</span></span>   |     <span data-ttu-id="63dab-161">リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="63dab-162">Windows</span><span class="sxs-lookup"><span data-stu-id="63dab-162">Windows</span></span>      |      <span data-ttu-id="63dab-163">プライマリ ID には、リムーバブル 記憶域と CD/DVD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63dab-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="63dab-164">デバイス ID</span><span class="sxs-lookup"><span data-stu-id="63dab-164">Device ID</span></span>     |  <span data-ttu-id="63dab-165">[Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)。リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="63dab-166">Windows</span><span class="sxs-lookup"><span data-stu-id="63dab-166">Windows</span></span>   |    <span data-ttu-id="63dab-167">デバイス ID 形式の詳細については [、「Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers)」を参照してください。たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="63dab-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="63dab-168">ハードウェア ID</span><span class="sxs-lookup"><span data-stu-id="63dab-168">Hardware ID</span></span>     |     <span data-ttu-id="63dab-169">[Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)。リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="63dab-170">Windows</span><span class="sxs-lookup"><span data-stu-id="63dab-170">Windows</span></span>    |    <span data-ttu-id="63dab-171">システム内のデバイスを識別する文字列 (たとえば、USBSTOR\DiskGeneric_Flash_Disk______8.07)。 **注**: ハードウェア ID は一意ではありません。異なるデバイスが同じ値を共有する場合があります。</span><span class="sxs-lookup"><span data-stu-id="63dab-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="63dab-172">インスタンス ID</span><span class="sxs-lookup"><span data-stu-id="63dab-172">Instance ID</span></span>    | <span data-ttu-id="63dab-173">デバイスのインストール。リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="63dab-174">Windows</span><span class="sxs-lookup"><span data-stu-id="63dab-174">Windows</span></span>    |   <span data-ttu-id="63dab-175">文字列は、システム内のデバイスを一意に識別します (たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="63dab-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="63dab-176">フレンドリ名</span><span class="sxs-lookup"><span data-stu-id="63dab-176">Friendly Name</span></span>     |     <span data-ttu-id="63dab-177">リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="63dab-178">Windows</span><span class="sxs-lookup"><span data-stu-id="63dab-178">Windows</span></span>      |    <span data-ttu-id="63dab-179">デバイスに接続されている文字列 (汎用フラッシュ ディスク USB デバイスなど)</span><span class="sxs-lookup"><span data-stu-id="63dab-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="63dab-180">ベンダー ID / 製品 ID</span><span class="sxs-lookup"><span data-stu-id="63dab-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="63dab-181">リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="63dab-182">WindowsMac</span><span class="sxs-lookup"><span data-stu-id="63dab-182">Windows Mac</span></span>      |     <span data-ttu-id="63dab-183">ベンダー ID は、USB 委員会がベンダーに割り当てる 4 桁のベンダー コードです。</span><span class="sxs-lookup"><span data-stu-id="63dab-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="63dab-184">製品 ID は、ベンダーがデバイスに割り当てる 4 桁の製品コードです。ワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="63dab-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="63dab-185">シリアル番号Id</span><span class="sxs-lookup"><span data-stu-id="63dab-185">Serial NumberId</span></span>     |     <span data-ttu-id="63dab-186">リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="63dab-187">WindowsMac</span><span class="sxs-lookup"><span data-stu-id="63dab-187">Windows Mac</span></span>   |     <span data-ttu-id="63dab-188">たとえば <SerialNumberId>、002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="63dab-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="63dab-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="63dab-189">Related topic</span></span>

- [<span data-ttu-id="63dab-190">Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御</span><span class="sxs-lookup"><span data-stu-id="63dab-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

