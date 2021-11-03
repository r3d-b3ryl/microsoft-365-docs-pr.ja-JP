---
title: Microsoft Defender for Endpoint Device Control Printer Protection
description: Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを介してユーザーが印刷をブロックします。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: dansimp
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: da6a875a7d9fc5a3445a18312245ffebdf6503c0
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667116"
---
# <a name="device-control-printer-protection"></a>デバイス制御のプリンター保護

Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを介してユーザーが印刷をブロックします。

## <a name="licensing"></a>ライセンス

Printer Protection の使用を開始する前に、サブスクリプションを[確認Microsoft 365必要があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 Printer Protection にアクセスして使用するには、次の情報が必要です。

- Microsoft 365 E3/ポリシーの展開の詳細
- Microsoft 365 E5レポートの詳細

## <a name="permission"></a>アクセス許可

Intune でのポリシー展開では、OMA-URI を使用してポリシーを展開するには、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。 カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールを使用できます。

- ポリシーとプロファイル マネージャーの役割。
- または、デバイス構成プロファイルでレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール
- またはグローバル管理者

デバイス構成レポートを表示するには、アカウントにレポートの表示権限が必要です。 カスタム ロールを作成するか、次のアクセス許可を持つ組み込みの役割を使用できます。

- グローバル セキュリティ管理者
- セキュリティ管理者
- セキュリティ閲覧者

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

これらの要件を満Windows 10プリンター保護を展開する予定のデバイスがインストールされている必要があります。

1. 次の Windows Update がインストールされています。
    - 1809 Windows: 更新プログラム[KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) Windowsインストールする
    - 1909 Windows: 更新プログラム[KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) Windowsインストールする
    - 2004 Windows以降の場合

2. グループ ポリシーを使用してポリシーを展開する予定の場合、デバイスは Microsoft Defender for Endpoint に参加している必要があります。ポリシーを展開する予定の場合は、Microsoft エンドポイント マネージャーを使用してデバイスを参加Microsoft Intune。

## <a name="deploy-device-control-printer-protection-policy"></a>デバイスコントロールプリンター保護ポリシーの展開

グループ ポリシーまたは Intune を使用してポリシーを展開できます。

<br>

****

|Title|説明|CSP サポート | GPO サポート | ユーザー ベースのサポート | コンピューター ベースのサポート |
|---|---|:---:|:---:|:---:|:---:|
|**デバイスコントロールの印刷制限を有効にする**|企業以外のプリンターを使用してユーザーの印刷をブロックする|はい|はい|はい|はい|
|**承認済みの USB 接続印刷デバイスの一覧**\*|特定の USB プリンターを許可する|はい|はい|はい|はい|
|

\* このポリシーは、[デバイスコントロールの印刷制限を **有効にする] と一緒に使用する必要があります**。

## <a name="deploy-policy-via-intune"></a>Intune 経由でポリシーを展開する

Intune では、現在デバイスコントロール プリンター保護は OMA-URI のみをサポートしています。

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>シナリオ 1: Intune を使用して企業以外のプリンターを使用してユーザーの印刷をブロックする

- コンピューターにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- ユーザーにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

CSP は、次の文字列をサポートします `<enabled/>` 。

:::image type="content" source="../../media/customeditrow.png" alt-text="カスタム編集行。":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>シナリオ 2: Intune を使用して特定の承認済み USB プリンターを許可する

- コンピューターにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- ユーザーにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

CSP は、'ApprovedUsbPrintDevices' プロパティを使用して承認された USB プリンターを使用して文字列をサポートします。次の例を示します `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` 。

:::image type="content" source="../../media/editrow.png" alt-text="行の編集。":::

## <a name="deploy-policy-via-group-policy"></a>グループ ポリシーを使用してポリシーを展開する

デバイスが Intune に参加しない場合は、グループ ポリシーを使用してポリシーを展開することもできます。

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>シナリオ 1: グループ ポリシーを使用して、企業以外のプリンター経由でユーザーの印刷をブロックする

- コンピューターにポリシーを適用する:

  コンピューター構成 \> 管理用テンプレート \> プリンター: デバイスコントロールの印刷制限を有効にする

- ユーザーにポリシーを適用する:

  ユーザー構成 \> 管理用テンプレート \> コントロール パネル \> プリンター: デバイス コントロールの印刷制限を有効にする

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="デバイスの印刷制限を有効にします。":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>シナリオ 2: グループ ポリシーを使用して特定の承認済み USB プリンターを許可する

- コンピューターにポリシーを適用する:

  コンピューター構成 \> 管理用テンプレート \> プリンター: 承認済み USB 接続印刷デバイスの一覧

- ユーザーにポリシーを適用する:

  ユーザー構成 \> 管理用テンプレート \> コントロール パネル プリンター: 承認済み USB 接続印刷 \> デバイスの一覧

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="承認された USB 接続印刷デバイスの一覧。":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Microsoft Defender for Endpoint ポータルでデバイスコントロールプリンター保護データを表示する

この[Microsoft 365は、](https://security.microsoft.com)上記の Device Control Printer Protection ポリシーによってブロックされた印刷を示しています。

```kusto
DeviceEvents
| where ActionType == 'PrintJobBlocked'
| extend parsed=parse_json(AdditionalFields)
| extend PrintedFile=tostring(parsed.JobOrDocumentName)
| extend PrintPortName=tostring(parsed.PortName)
| extend PrinterName=tostring(parsed.PrinterName)
| extend Policy=tostring(parsed.RestrictionReason) 
| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName, Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields
| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高度な狩猟。":::
 
 PnP イベントを使用して、組織で使用されている USB プリンターを検索できます。
 
```kusto
//find the USB Printer VID/PID
DeviceEvents
| where ActionType == "PnpDeviceConnected"
| extend parsed=parse_json(AdditionalFields)
| extend DeviceDescription = tostring(parsed.DeviceDescription) 
| extend PrinterDeviceId = tostring(parsed.DeviceId) 
| extend VID_PID_Array = split(split(PrinterDeviceId, "\\")[1], "&")
| extend VID_PID = replace_string(strcat(VID_PID_Array[0], '/', VID_PID_Array[1]), 'VID_', '')
| extend VID_PID = replace_string(VID_PID, 'PID_', '')
| extend ClassId = tostring(parsed.ClassId) 
| extend VendorIds = tostring(parsed.VendorIds) 
| where DeviceDescription == 'USB Printing Support'
| project Timestamp , DeviceId, DeviceName, ActionType, DeviceDescription, VID_PID, ClassId, PrinterDeviceId, VendorIds, parsed
| order by Timestamp desc
```

 :::image type="content" source="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png" alt-text="高度な狩猟":::








 
 
 
 
