---
title: Microsoft Defender for Endpoint Device Control Printer Protection
description: Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを介してユーザーが印刷をブロックします。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809262"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="bee6f-103">Device Control Printer Protection</span><span class="sxs-lookup"><span data-stu-id="bee6f-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="bee6f-104">Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを介してユーザーが印刷をブロックします。</span><span class="sxs-lookup"><span data-stu-id="bee6f-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="bee6f-105">ライセンス</span><span class="sxs-lookup"><span data-stu-id="bee6f-105">Licensing</span></span> 

<span data-ttu-id="bee6f-106">Printer Protection の使用を開始する前に、サブスクリプションを[確認Microsoft 365必要があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="bee6f-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="bee6f-107">Printer Protection にアクセスして使用するには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="bee6f-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="bee6f-108">Microsoft 365 E3/ポリシーの展開の詳細</span><span class="sxs-lookup"><span data-stu-id="bee6f-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="bee6f-109">Microsoft 365 E5レポートの詳細</span><span class="sxs-lookup"><span data-stu-id="bee6f-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="bee6f-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="bee6f-110">Permission</span></span> 

<span data-ttu-id="bee6f-111">Intune でのポリシー展開では、OMA-URI を使用してポリシーを展開するには、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="bee6f-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="bee6f-112">カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bee6f-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="bee6f-113">ポリシーとプロファイル マネージャーの役割。</span><span class="sxs-lookup"><span data-stu-id="bee6f-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="bee6f-114">または、デバイス構成プロファイルでレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール</span><span class="sxs-lookup"><span data-stu-id="bee6f-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="bee6f-115">またはグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="bee6f-115">Or Global admin</span></span>

<span data-ttu-id="bee6f-116">デバイス構成レポートを表示するには、アカウントにレポートの表示権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="bee6f-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="bee6f-117">カスタム ロールを作成するか、次のアクセス許可を持つ組み込みの役割を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bee6f-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="bee6f-118">グローバル セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="bee6f-118">Global security admin</span></span>
- <span data-ttu-id="bee6f-119">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="bee6f-119">Security admin</span></span>
- <span data-ttu-id="bee6f-120">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="bee6f-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="bee6f-121">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="bee6f-121">Prepare your endpoints</span></span>

<span data-ttu-id="bee6f-122">これらの要件を満Windows 10プリンター保護を展開する予定のデバイスがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee6f-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="bee6f-123">Insider プログラムに参加します。</span><span class="sxs-lookup"><span data-stu-id="bee6f-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="bee6f-124">次の Windows Update がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bee6f-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="bee6f-125">1809 Windows: 更新プログラム[KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) Windowsインストールする</span><span class="sxs-lookup"><span data-stu-id="bee6f-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="bee6f-126">1909 Windows: 更新プログラム[KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) Windowsインストールする</span><span class="sxs-lookup"><span data-stu-id="bee6f-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="bee6f-127">2004 Windows以降の場合</span><span class="sxs-lookup"><span data-stu-id="bee6f-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="bee6f-128">グループ ポリシーを使用してポリシーを展開する予定の場合は、デバイスが参加しているMDATPがあります。MEM 経由でポリシーを展開する場合は、デバイスが Intune に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee6f-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="bee6f-129">デバイスコントロールプリンター保護ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="bee6f-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="bee6f-130">グループ ポリシーまたは Intune を使用してポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="bee6f-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="bee6f-131">タイトル</span><span class="sxs-lookup"><span data-stu-id="bee6f-131">Title</span></span> | <span data-ttu-id="bee6f-132">説明</span><span class="sxs-lookup"><span data-stu-id="bee6f-132">Description</span></span> | <span data-ttu-id="bee6f-133">CSP サポート</span><span class="sxs-lookup"><span data-stu-id="bee6f-133">CSP Support</span></span> | <span data-ttu-id="bee6f-134">GPO サポート</span><span class="sxs-lookup"><span data-stu-id="bee6f-134">GPO Support</span></span> | <span data-ttu-id="bee6f-135">ユーザー ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="bee6f-135">User-based Support</span></span> | <span data-ttu-id="bee6f-136">コンピューター ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="bee6f-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="bee6f-137">**デバイスコントロールの印刷制限を有効にする**</span><span class="sxs-lookup"><span data-stu-id="bee6f-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="bee6f-138">企業以外のプリンターを使用してユーザーの印刷をブロックする</span><span class="sxs-lookup"><span data-stu-id="bee6f-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="bee6f-139">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-139">Yes</span></span>|<span data-ttu-id="bee6f-140">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-140">Yes</span></span>|<span data-ttu-id="bee6f-141">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-141">Yes</span></span>|<span data-ttu-id="bee6f-142">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-142">Yes</span></span>|
|<span data-ttu-id="bee6f-143">**承認済みの USB 接続印刷デバイスの一覧**\*</span><span class="sxs-lookup"><span data-stu-id="bee6f-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="bee6f-144">特定の USB プリンターを許可する</span><span class="sxs-lookup"><span data-stu-id="bee6f-144">Allow specific USB printer</span></span>|<span data-ttu-id="bee6f-145">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-145">Yes</span></span>|<span data-ttu-id="bee6f-146">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-146">Yes</span></span>|<span data-ttu-id="bee6f-147">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-147">Yes</span></span>|<span data-ttu-id="bee6f-148">はい</span><span class="sxs-lookup"><span data-stu-id="bee6f-148">Yes</span></span>|
|||||||

<span data-ttu-id="bee6f-149">\* このポリシーは、[デバイスコントロール印刷の制限を **有効にする] と一緒に使用する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="bee6f-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="bee6f-150">Intune 経由でポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="bee6f-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="bee6f-151">Intune では、現在デバイスコントロール プリンター保護は OMA-URI のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bee6f-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="bee6f-152">**シナリオ 1: 企業以外のプリンターを使用してユーザーの印刷をブロックする**</span><span class="sxs-lookup"><span data-stu-id="bee6f-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="bee6f-153">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="bee6f-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="bee6f-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="bee6f-155">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="bee6f-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="bee6f-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="bee6f-157">CSP は、次の文字列をサポートします `` <enabled/>`` 。</span><span class="sxs-lookup"><span data-stu-id="bee6f-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="カスタム編集行":::

<span data-ttu-id="bee6f-159">**シナリオ 2: 特定の承認済み USB プリンターを許可する**</span><span class="sxs-lookup"><span data-stu-id="bee6f-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="bee6f-160">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="bee6f-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="bee6f-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="bee6f-162">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="bee6f-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="bee6f-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="bee6f-164">CSP は、'ApprovedUsbPrintDevices' プロパティを使用して承認された USB プリンターを使用して文字列をサポートします。次の例を示します `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` 。</span><span class="sxs-lookup"><span data-stu-id="bee6f-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="行の編集":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="bee6f-166">グループ ポリシーを使用してポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="bee6f-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="bee6f-167">デバイスが Intune に参加しない場合は、グループ ポリシーを使用してポリシーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="bee6f-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="bee6f-168">**シナリオ 1: 企業以外のプリンターを使用してユーザーの印刷をブロックする**</span><span class="sxs-lookup"><span data-stu-id="bee6f-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="bee6f-169">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="bee6f-170">[コンピューターの構成>管理用テンプレート>プリンター: デバイスコントロールの印刷制限を有効にする</span><span class="sxs-lookup"><span data-stu-id="bee6f-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="bee6f-171">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="bee6f-172">[ユーザー構成>管理用テンプレート>コントロール >プリンター: デバイスコントロールの印刷制限を有効にする</span><span class="sxs-lookup"><span data-stu-id="bee6f-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="デバイスの印刷制限を有効にする":::
 

<span data-ttu-id="bee6f-174">**シナリオ 2: 特定の承認済み USB プリンターを許可する**</span><span class="sxs-lookup"><span data-stu-id="bee6f-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="bee6f-175">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="bee6f-176">[コンピューター構成>管理用テンプレート>プリンター: 承認済み USB 接続印刷デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="bee6f-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="bee6f-177">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="bee6f-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="bee6f-178">[ユーザー構成>管理用テンプレート>コントロール >プリンター: 承認済み USB 接続印刷デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="bee6f-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="承認済みの USB 接続印刷デバイスの一覧":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="bee6f-180">Microsoft Defender for Endpoint ポータルでデバイスコントロールプリンター保護データを表示する</span><span class="sxs-lookup"><span data-stu-id="bee6f-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="bee6f-181">この[Microsoft 365は、](https://security.microsoft.com)上記の Device Control Printer Protection ポリシーによってブロックされた印刷を示しています。</span><span class="sxs-lookup"><span data-stu-id="bee6f-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高度な狩猟":::
