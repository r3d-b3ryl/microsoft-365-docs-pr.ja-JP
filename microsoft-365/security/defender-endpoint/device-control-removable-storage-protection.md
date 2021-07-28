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
ms.openlocfilehash: 8d36d01c0ccedf11e40f980df8c21997a11ad49f
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2021
ms.locfileid: "53596282"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control リムーバブル Storage保護

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Storage Protection を使用すると、ユーザーまたはコンピューター、または両方が未承認のリムーバブル 記憶域メディアを使用できません。

## <a name="protection-policies"></a>保護ポリシー

### <a name="device-installation"></a>デバイスのインストール

**機能 -** さまざまなデバイスプロパティに基づいて除外の設定または除外なしでインストールを防止します。

**Windows 10サポートの詳細**:

- コンピューター レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます。
- MEM と GPO をサポートします。
- 一覧に示[されている [デバイスのプロパティ](#device-properties)] がサポートされています。
- デバイス の詳細については、「Windows Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法」[を参照してください](control-usb-devices-using-intune.md)。

**サポートされているプラットフォーム**- Windows 10

**macOS サポートの詳細**:

- コンピューター レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます
- macOS 固有の情報については [、「macOS のデバイス コントロール」を参照してください](mac-device-control-overview.md)。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4+ (システム拡張機能が有効な場合)

### <a name="removable-storage-access-control"></a>リムーバブル 記憶域アクセス制御

**Capabilities**

- *監査* さまざまなデバイス プロパティに基づくリムーバブル 記憶域への読み取りまたは書き込みまたは実行アクセス。除外の付きまたは除外なし。
- *[防止]* 読み取りまたは書き込みまたは除外なしのアクセスを実行する - さまざまなデバイスプロパティに基づいて特定のデバイスを許可します。

**Windows 10サポートの詳細**:

- コンピューターまたはユーザー、または両方で適用されます。 特定のコンピューター上の特定のリムーバブル 記憶域への読み取り/書き込み/実行アクセスを実行する特定のユーザーのみを許可します。
- MEM OMA-URI と GPO をサポートします。
- 一覧に示[されている [デバイスのプロパティ](#device-properties)] がサポートされています。
- この機能については、「リムーバブル Windows[アクセス制御」を参照してください](device-control-removable-storage-access-control.md)。

**サポートされているプラットフォーム**- Windows 10

**macOS サポートの詳細**:

- コンピューター レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます。
- macOS 固有の情報については [、「macOS のデバイス コントロール」を参照してください](mac-device-control-overview.md)。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4+ (システム拡張機能が有効な場合)

### <a name="windows-portable-device-access-control"></a>Windowsポータブル デバイス アクセス制御

**機能**- ポータブル デバイスへの読み取りまたは書き [Windows](/windows-hardware/drivers/portable/)アクセスを拒否します 。たとえば、タブレット、iPhone。

**説明**:

- コンピューターまたはユーザー、または両方で適用されます。
- MEM OMA-URI と GPO をサポートします。

**サポートされているプラットフォーム**- Windows 10

### <a name="endpoint-dlp-removable-storage"></a>エンドポイント DLP リムーバブル ストレージ

**機能** - ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーするのを監査または警告または防止します。

**説明**- エンドポイントデータ損失防止のWindows詳細 [については、「Microsoft 365」を参照してください](../../compliance/endpoint-dlp-learn-about.md)。

**サポートされているプラットフォーム**- Windows 10

### <a name="bitlocker"></a>BitLocker

**機能**:

- BitLocker で保護されていないリムーバブル ドライブに書き込まれるデータをブロックします。
- 組織が所有するコンピューターで暗号化されていないリムーバブル ドライブへのアクセスをブロックする

**説明**- 詳細については [、「BitLocker -](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)リムーバブル ドライブ Windows」を参照設定。

**サポートされているプラットフォーム**- Windows 10

## <a name="device-properties"></a>デバイスのプロパティ

Microsoft Defender for Endpoint Device Control リムーバブル Storage保護を使用すると、以下の表に示すプロパティに基づいてリムーバブル 記憶域へのアクセスを制限できます。

<br>

****

|プロパティ名|適用可能なポリシー|オペレーティング システムに適用される|説明|
|---|---|---|---|
|デバイス クラス|[Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|デバイス ID 形式の詳細については、「デバイス セットアップ [クラス」を参照してください](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。 **注**: デバイスインストールは、リムーバブル ストレージだけでなく、任意のデバイスに適用できます。|
|プライマリ ID|リムーバブル 記憶域アクセス制御|Windows|プライマリ ID には、リムーバブル 記憶域と CD/DVD が含まれます。|
|デバイス ID|[Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)。リムーバブル 記憶域アクセス制御|Windows|デバイス ID 形式の詳細については [、「Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers)」を参照してください。たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07|
|ハードウェア ID|[Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)。リムーバブル 記憶域アクセス制御|Windows|システム内のデバイスを識別する文字列 (たとえば、USBSTOR\DiskGeneric_Flash_Disk______8.07)。 **注**: ハードウェア ID は一意ではありません。異なるデバイスが同じ値を共有する場合があります。|
|インスタンス ID|デバイスのインストール。リムーバブル 記憶域アクセス制御|Windows|文字列は、システム内のデバイスを一意に識別します (たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0|
|フレンドリ名|リムーバブル 記憶域アクセス制御|Windows|デバイスに接続されている文字列 (汎用フラッシュ ディスク USB デバイスなど)|
|ベンダー ID / 製品 ID|リムーバブル 記憶域アクセス制御|WindowsMac|ベンダー ID は、USB 委員会がベンダーに割り当てる 4 桁のベンダー コードです。 製品 ID は、ベンダーがデバイスに割り当てる 4 桁の製品コードです。ワイルドカードをサポートします。|
|シリアル番号Id|リムーバブル 記憶域アクセス制御|WindowsMac|たとえば <SerialNumberId>、002324B534BCB431B000058A</SerialNumberId>|
|

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御](device-control-removable-storage-access-control.md)
