---
title: Microsoft Defender for Endpoint デバイス コントロールのリムーバブル Storage保護
description: ユーザーまたはマシンまたはその両方が承認されていないリムーバブル ストレージ メディアを使用するのを防ぐのに役立つ '機能' を理解する
keywords: リムーバブル ストレージ メディア
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5210530bb9102436e66667a0482aa09d941e26f9
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939413"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint デバイス コントロールのリムーバブル Storage保護


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpointのデバイス制御リムーバブル ストレージ保護により、ユーザー、エンドポイント、またはその両方で承認されていないリムーバブル ストレージ メディアを使用できなくなります。

## <a name="protection-policies"></a>保護ポリシー

### <a name="removable-storage-access-control"></a>リムーバブル ストレージ のアクセス制御

**Capabilities**

- *監査* 除外の有無にかかわらず、さまざまなデバイスプロパティに基づいてリムーバブル ストレージへのアクセスを読み取りまたは書き込みまたは実行します。
- *防ぐ* 除外の有無にかかわらずアクセスを読み取りまたは書き込みまたは実行する - さまざまなデバイスプロパティに基づいて特定のデバイスを許可します。

**Windows 10とWindows 11のサポートの詳細**:

- デバイス レベル、ユーザー レベルのいずれかで適用されます。 または両方。 特定のコンピューター上の特定のリムーバブル ストレージへの読み取り/書き込み/実行アクセスを実行する特定のユーザーのみを許可します。
- MEM OMA-URI と GPO をサポートします。
- 一覧でサポートされている "[デバイスのプロパティ](#device-properties)" です。
- Windowsの機能については、「[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

**macOS サポートの詳細**:

- デバイス レベルで適用されます。ログオンしているすべてのユーザーに同じポリシーが適用されます。
- macOS 固有の情報については、 [macOS のデバイスコントロールに関するページを](mac-device-control-overview.md)参照してください。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4 以降 (システム拡張機能が有効になっている場合)


### <a name="device-installation"></a>デバイスのインストール

**機能** - さまざまなデバイスのプロパティに基づいて、除外の有無にかかわらずインストールを禁止します。

**Windows 10とWindows 11のサポートの詳細**:

- デバイス レベルで適用されます。ログオンしているすべてのユーザーに同じポリシーが適用されます。
- Microsoft エンドポイント マネージャーオブジェクトとグループ ポリシー オブジェクトをサポートします。
- 一覧でサポートされている "[デバイスのプロパティ](#device-properties)" です。
- Windowsの詳細については、「[Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

**macOS サポートの詳細**:

- デバイス レベルで適用: ログオンしているすべてのユーザーに同じポリシーが適用されます
- macOS 固有の情報については、 [macOS のデバイスコントロールに関するページを](mac-device-control-overview.md)参照してください。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4 以降 (システム拡張機能が有効) 以降

### <a name="endpoint-dlp-removable-storage"></a>エンドポイント DLP リムーバブル ストレージ

**機能** - ユーザーがアイテムや情報をリムーバブル メディアまたは USB デバイスにコピーすることを監査、警告、または禁止します。

**説明** - Windowsの詳細については、「[エンドポイントデータ損失防止の詳細](../../compliance/endpoint-dlp-learn-about.md)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

### <a name="bitlocker"></a>BitLocker

**機能**:

- BitLocker で保護されていないリムーバブル ドライブに書き込まれるデータをブロックします。
- 組織が所有するコンピューターでリムーバブル ドライブが暗号化されていない限り、リムーバブル ドライブへのアクセスをブロックする

**説明** - Windowsの詳細については、「[BitLocker - リムーバブル ドライブ 設定](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

## <a name="device-properties"></a>デバイス プロパティ

Microsoft Defender for Endpoint Device Control リムーバブル Storage Protection を使用すると、次の表に示すプロパティに基づいてリムーバブル ストレージ へのアクセスを制限できます。

<br/><br/>

|プロパティ名|適用されるポリシー|オペレーティング システムに適用されます|説明|
|---|---|---|---|
|デバイス クラス|[Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|デバイス ID 形式の詳細については、 [デバイス セットアップ クラス](/windows-hardware/drivers/install/overview-of-device-setup-classes)に関するページを参照してください。 次の 2 つのリンクは、デバイス セットアップ クラスの完全な一覧を提供します。 'System Use' クラスは、主にファクトリからコンピューター/マシンに付属するデバイスを指しますが、"Vendor" クラスは、主に既存のコンピューター/マシンに接続できるデバイスを指します。[ベンダーが使用できるシステム定義デバイス セットアップ クラス - Windows ドライバー](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)と[システム定義デバイスセットアップ クラスは、システム使用用に予約されているシステム定義デバイス セットアップ クラス - Windows ドライバー](/windows-hardware/drivers/install/system-defined-device-setup-classes-reserved-for-system-use)です。 **注**: デバイスのインストールは、リムーバブル ストレージだけでなく、任意のデバイスに適用できます。|
|プライマリ ID|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md)|Windows|プライマリ ID には、リムーバブル ストレージ、CD/DVD、Windowsポータブル デバイス/WPD が含まれます。|
|デバイス ID|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md); <p> [Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|デバイス ID 形式の詳細については、「 [標準 USB 識別子](/windows-hardware/drivers/install/standard-usb-identifiers) (USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07 など)」を参照してください。|
|ハードウェア ID|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md) <p> [Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|USBSTOR\DiskGeneric_Flash_Disk___8.07 など、システム内のデバイスを識別した文字列。 **注**: ハードウェア ID は一意ではありません。異なるデバイスが同じ値を共有している可能性があります。|
|インスタンス ID|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md) <p> デバイスのインストール|Windows|文字列は、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0 など、システム内のデバイスを一意に識別します。|
|フレンドリ名|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md)|Windows|デバイスにアタッチされている文字列 (たとえば、汎用フラッシュ ディスク USB デバイス)|
|ベンダー ID/製品 ID|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md)|Windows <p> macOS|ベンダー ID は、USB 委員会がベンダーに割り当てる 4 桁のベンダー コードです。 製品 ID は、ベンダーがデバイスに割り当てる 4 桁の製品コードです。ワイルドカードをサポートします。|
|シリアル NumberId|[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md)|Windows <p> macOS |たとえば、`<SerialNumberId>002324B534BCB431B000058A</SerialNumberId>` のように指定します。|
