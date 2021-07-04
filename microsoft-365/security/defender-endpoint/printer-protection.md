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
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289693"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="768c2-103">デバイス制御のプリンター保護</span><span class="sxs-lookup"><span data-stu-id="768c2-103">Device Control Printer Protection</span></span>

<span data-ttu-id="768c2-104">Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを介してユーザーが印刷をブロックします。</span><span class="sxs-lookup"><span data-stu-id="768c2-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="768c2-105">ライセンス</span><span class="sxs-lookup"><span data-stu-id="768c2-105">Licensing</span></span>

<span data-ttu-id="768c2-106">Printer Protection の使用を開始する前に、サブスクリプションを[確認Microsoft 365必要があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="768c2-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="768c2-107">Printer Protection にアクセスして使用するには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="768c2-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="768c2-108">Microsoft 365 E3/ポリシーの展開の詳細</span><span class="sxs-lookup"><span data-stu-id="768c2-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="768c2-109">Microsoft 365 E5レポートの詳細</span><span class="sxs-lookup"><span data-stu-id="768c2-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="768c2-110">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="768c2-110">Permission</span></span>

<span data-ttu-id="768c2-111">Intune でのポリシー展開では、OMA-URI を使用してポリシーを展開するには、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="768c2-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="768c2-112">カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="768c2-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="768c2-113">ポリシーとプロファイル マネージャーの役割。</span><span class="sxs-lookup"><span data-stu-id="768c2-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="768c2-114">または、デバイス構成プロファイルでレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール</span><span class="sxs-lookup"><span data-stu-id="768c2-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="768c2-115">またはグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="768c2-115">Or Global admin</span></span>

<span data-ttu-id="768c2-116">デバイス構成レポートを表示するには、アカウントにレポートの表示権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="768c2-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="768c2-117">カスタム ロールを作成するか、次のアクセス許可を持つ組み込みの役割を使用できます。</span><span class="sxs-lookup"><span data-stu-id="768c2-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="768c2-118">グローバル セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="768c2-118">Global security admin</span></span>
- <span data-ttu-id="768c2-119">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="768c2-119">Security admin</span></span>
- <span data-ttu-id="768c2-120">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="768c2-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="768c2-121">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="768c2-121">Prepare your endpoints</span></span>

<span data-ttu-id="768c2-122">これらの要件を満Windows 10プリンター保護を展開する予定のデバイスがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="768c2-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="768c2-123">Insider プログラムに参加します。</span><span class="sxs-lookup"><span data-stu-id="768c2-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="768c2-124">次の Windows Update がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="768c2-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="768c2-125">1809 Windows: 更新プログラム[KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) Windowsインストールする</span><span class="sxs-lookup"><span data-stu-id="768c2-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="768c2-126">1909 Windows: 更新プログラム[KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) Windowsインストールする</span><span class="sxs-lookup"><span data-stu-id="768c2-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="768c2-127">2004 Windows以降の場合</span><span class="sxs-lookup"><span data-stu-id="768c2-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="768c2-128">グループ ポリシーを使用してポリシーを展開する予定の場合、デバイスは MDATP に参加している必要があります。MEM 経由でポリシーを展開する場合は、デバイスが Intune に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="768c2-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="768c2-129">デバイスコントロールプリンター保護ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="768c2-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="768c2-130">グループ ポリシーまたは Intune を使用してポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="768c2-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="768c2-131">タイトル</span><span class="sxs-lookup"><span data-stu-id="768c2-131">Title</span></span>|<span data-ttu-id="768c2-132">説明</span><span class="sxs-lookup"><span data-stu-id="768c2-132">Description</span></span>|<span data-ttu-id="768c2-133">CSP サポート</span><span class="sxs-lookup"><span data-stu-id="768c2-133">CSP Support</span></span> | <span data-ttu-id="768c2-134">GPO サポート</span><span class="sxs-lookup"><span data-stu-id="768c2-134">GPO Support</span></span> | <span data-ttu-id="768c2-135">ユーザー ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="768c2-135">User-based Support</span></span> | <span data-ttu-id="768c2-136">コンピューター ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="768c2-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="768c2-137">**デバイスコントロールの印刷制限を有効にする**</span><span class="sxs-lookup"><span data-stu-id="768c2-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="768c2-138">企業以外のプリンターを使用してユーザーの印刷をブロックする</span><span class="sxs-lookup"><span data-stu-id="768c2-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="768c2-139">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-139">Yes</span></span>|<span data-ttu-id="768c2-140">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-140">Yes</span></span>|<span data-ttu-id="768c2-141">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-141">Yes</span></span>|<span data-ttu-id="768c2-142">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-142">Yes</span></span>|
|<span data-ttu-id="768c2-143">**承認済みの USB 接続印刷デバイスの一覧**\*</span><span class="sxs-lookup"><span data-stu-id="768c2-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="768c2-144">特定の USB プリンターを許可する</span><span class="sxs-lookup"><span data-stu-id="768c2-144">Allow specific USB printer</span></span>|<span data-ttu-id="768c2-145">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-145">Yes</span></span>|<span data-ttu-id="768c2-146">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-146">Yes</span></span>|<span data-ttu-id="768c2-147">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-147">Yes</span></span>|<span data-ttu-id="768c2-148">はい</span><span class="sxs-lookup"><span data-stu-id="768c2-148">Yes</span></span>|
|

<span data-ttu-id="768c2-149">\* このポリシーは、[デバイスコントロールの印刷制限を **有効にする] と一緒に使用する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="768c2-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="768c2-150">Intune 経由でポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="768c2-150">Deploy policy via Intune</span></span>

<span data-ttu-id="768c2-151">Intune では、現在デバイスコントロール プリンター保護は OMA-URI のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="768c2-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="768c2-152">シナリオ 1: Intune を使用して企業以外のプリンターを使用してユーザーの印刷をブロックする</span><span class="sxs-lookup"><span data-stu-id="768c2-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="768c2-153">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="768c2-154">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="768c2-155">CSP は、次の文字列をサポートします `<enabled/>` 。</span><span class="sxs-lookup"><span data-stu-id="768c2-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="カスタム編集行":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="768c2-157">シナリオ 2: Intune を使用して特定の承認済み USB プリンターを許可する</span><span class="sxs-lookup"><span data-stu-id="768c2-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="768c2-158">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="768c2-159">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="768c2-160">CSP は、'ApprovedUsbPrintDevices' プロパティを使用して承認された USB プリンターを使用して文字列をサポートします。次の例を示します `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` 。</span><span class="sxs-lookup"><span data-stu-id="768c2-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="行の編集":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="768c2-162">グループ ポリシーを使用してポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="768c2-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="768c2-163">デバイスが Intune に参加しない場合は、グループ ポリシーを使用してポリシーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="768c2-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="768c2-164">シナリオ 1: グループ ポリシーを使用して、企業以外のプリンター経由でユーザーの印刷をブロックする</span><span class="sxs-lookup"><span data-stu-id="768c2-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="768c2-165">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-165">Apply policy over machine:</span></span>

  <span data-ttu-id="768c2-166">コンピューター構成 \> 管理用テンプレート \> プリンター: デバイスコントロールの印刷制限を有効にする</span><span class="sxs-lookup"><span data-stu-id="768c2-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="768c2-167">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-167">Apply policy over user:</span></span>

  <span data-ttu-id="768c2-168">ユーザー構成 \> 管理用テンプレート \> コントロール パネル \> プリンター: デバイス コントロールの印刷制限を有効にする</span><span class="sxs-lookup"><span data-stu-id="768c2-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="デバイスの印刷制限を有効にする":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="768c2-170">シナリオ 2: グループ ポリシーを使用して特定の承認済み USB プリンターを許可する</span><span class="sxs-lookup"><span data-stu-id="768c2-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="768c2-171">コンピューターにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-171">Apply policy over machine:</span></span>

  <span data-ttu-id="768c2-172">コンピューター構成 \> 管理用テンプレート \> プリンター: 承認済み USB 接続印刷デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="768c2-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="768c2-173">ユーザーにポリシーを適用する:</span><span class="sxs-lookup"><span data-stu-id="768c2-173">Apply policy over user:</span></span>

  <span data-ttu-id="768c2-174">ユーザー構成 \> 管理用テンプレート \> コントロール パネル プリンター: 承認済み USB 接続印刷 \> デバイスの一覧</span><span class="sxs-lookup"><span data-stu-id="768c2-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="承認済みの USB 接続印刷デバイスの一覧":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="768c2-176">Microsoft Defender for Endpoint ポータルでデバイスコントロールプリンター保護データを表示する</span><span class="sxs-lookup"><span data-stu-id="768c2-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="768c2-177">この[Microsoft 365は、](https://security.microsoft.com)上記の Device Control Printer Protection ポリシーによってブロックされた印刷を示しています。</span><span class="sxs-lookup"><span data-stu-id="768c2-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

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
