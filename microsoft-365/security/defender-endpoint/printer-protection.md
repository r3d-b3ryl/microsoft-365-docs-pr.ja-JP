---
title: Microsoft Defender for Endpoint デバイス コントロール プリンター保護
description: Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを使用して印刷できないようにします。
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
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 9a700cd57b7843625f40289b43acd0e7a7eda45a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466677"
---
# <a name="device-control-printer-protection"></a>デバイス制御のプリンター保護

**適用対象**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint Device Control Printer Protection は、企業以外のプリンターまたは承認されていない USB プリンターを使用して印刷できないようにします。

## <a name="licensing"></a>ライセンス

Printer Protection の使用を開始する前に、[Microsoft 365 サブスクリプションを確認する](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)必要があります。 Printer Protection にアクセスして使用するには、次のものが必要です。

- 機能/ポリシーの展開のMicrosoft 365 E3
- レポートのMicrosoft 365 E5

## <a name="permission"></a>アクセス許可

Intuneでのポリシーの展開では、OMA-URI を使用してポリシーを展開するには、アカウントにデバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可が必要です。 カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールのいずれかを使用できます。

- ポリシーとプロファイル マネージャーのロール。
- または、デバイス構成プロファイルの作成/編集/更新/読み取り/削除/レポートの表示アクセス許可が有効になっているカスタム ロール
- またはグローバル管理者

デバイス構成レポートを表示するには、アカウントにレポートの表示アクセス許可が必要です。 カスタム ロールを作成するか、次のアクセス許可を持つ組み込みロールを使用できます。

- グローバル セキュリティ管理者
- セキュリティ管理者
- セキュリティ閲覧者

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

これらの要件を満たすために、Printer Protection の展開を計画しているデバイスをWindows 10またはWindows 11していることを確認します。

1. 次の Windows Update がインストールされています。
    - Windows 1809 の場合: [WINDOWS UPDATE KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) をインストールする
    - Windows 1909 の場合: [WINDOWS UPDATE KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) をインストールする
    - Windows 2004 以降の場合

2. グループ ポリシー経由でポリシーを展開する予定の場合は、デバイスを参加Microsoft Defender for Endpointオンボードする必要があります。Microsoft エンドポイント マネージャー経由でポリシーを展開する場合は、Microsoft Intuneを使用してデバイスを参加させる必要があります。

## <a name="deploy-device-control-printer-protection-policy"></a>デバイス制御プリンター保護ポリシーを展開する

グループ ポリシーまたはIntuneを使用してポリシーをデプロイできます。

<br>

****

|Title|説明|CSP サポート | GPO のサポート | ユーザー ベースのサポート | マシンベースのサポート |
|---|---|:---:|:---:|:---:|:---:|
|**デバイスコントロールの印刷制限を有効にする**|企業以外のプリンターを使用してユーザーの印刷をブロックする|はい|はい|はい|はい|
|**承認済みの USB 接続印刷デバイスの一覧**\*|特定の USB プリンターを許可する|はい|はい|はい|はい|
|

\* このポリシーは、 **デバイスコントロールの印刷制限を有効にする** と共に使用する必要があります。

## <a name="deploy-policy-via-intune"></a>Intuneを使用してポリシーをデプロイする

Intuneの場合、現在、Device Control Printer Protection では OMA-URI のみがサポートされています。

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>シナリオ 1: Intuneを使用して、企業以外のプリンターを使用して印刷できないようにする

- コンピューターにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- ユーザーにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

CSP では、次の文字列が `<enabled/>`サポートされます。

:::image type="content" source="../../media/customeditrow.png" alt-text="[カスタム] ページ" lightbox="../../media/customeditrow.png":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>シナリオ 2: Intuneを使用して特定の承認済み USB プリンターを許可する

- コンピューターにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- ユーザーにポリシーを適用する:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

CSP では、"ApprovedUsbPrintDevices" プロパティを使用して承認された USB プリンターを含む文字列がサポートされます。例:`<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`

:::image type="content" source="../../media/editrow.png" alt-text="[行の編集] ウィンドウ" lightbox="../../media/editrow.png":::

## <a name="deploy-policy-via-group-policy"></a>グループ ポリシーを使用してポリシーをデプロイする

デバイスが参加していないIntune場合は、グループ ポリシー経由でポリシーを展開することもできます。

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>シナリオ 1: グループ ポリシーを使用して、企業以外のプリンターを使用して印刷できないようにする

- コンピューターにポリシーを適用する:

  コンピューター構成 \> 管理用テンプレート \> プリンター: デバイス制御印刷の制限を有効にする

- ユーザーにポリシーを適用する:

  プリンターコントロール パネル\>ユーザー構成\>管理テンプレート\>: デバイス制御印刷の制限を有効にする

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="[デバイスコントロール印刷の制限を有効にする] ウィンドウ" lightbox="../../media/enable-device-ctrl-printing-restrictions.png":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>シナリオ 2: グループ ポリシーを使用して特定の承認済み USB プリンターを許可する

- コンピューターにポリシーを適用する:

  コンピューター構成 \> 管理用テンプレート \> プリンター: 承認済みの USB 接続印刷デバイスの一覧

- ユーザーにポリシーを適用する:

  プリンターコントロール パネル\>ユーザー構成\>管理用テンプレート\>: 承認済みの USB 接続印刷デバイスの一覧

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="承認済みの USB 接続印刷デバイスの一覧" lightbox="../../media/list-of-approved-connected-print-devices.png":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>ポータルで Device Control Printer Protection データMicrosoft Defender for Endpoint表示する

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>には、上記の Device Control Printer Protection ポリシーによってブロックされた印刷が表示されます。

```kusto
DeviceEvents
| where ActionType == 'PrintJobBlocked'
| extend parsed=parse_json(AdditionalFields)
| extend PrintedFile=tostring(parsed.JobOrDocumentName)
| extend PrintPortName=tostring(parsed.PortName)
| extend PrinterName=tostring(parsed.PrinterName)
| extend Policy=tostring(parsed.RestrictionReason) 
| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName, Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields
| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高度なハンティング" lightbox="../../media/device-control-advanced-hunting.png":::

 PnP イベントを使用して、組織内で使用されている USB プリンターを見つけることができます。

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

 :::image type="content" source="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png" alt-text="[高度なハンティング] ページ" lightbox="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png":::
