---
title: Microsoft Defender for Endpoint Device Control リムーバブル Storage保護
description: ユーザーまたはコンピューター、または両方が未承認のリムーバブル 記憶域メディアを使用できない '機能を理解する
keywords: リムーバブル 記憶域メディア
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
ms.openlocfilehash: cf57eb6e08278625ac8887985a39d355266f47d5
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962929"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control リムーバブル Storage保護

Microsoft Defender for Endpoint のデバイス制御リムーバブル 記憶域保護により、ユーザー、エンドポイント、または両方が未承認のリムーバブル 記憶域メディアを使用できません。

## <a name="protection-policies"></a>保護ポリシー

### <a name="removable-storage-access-control"></a>リムーバブル 記憶域アクセス制御

**Capabilities**

- *監査* さまざまなデバイス プロパティに基づくリムーバブル 記憶域への読み取りまたは書き込みまたは実行アクセス。除外の付きまたは除外なし。
- *[防止]* 読み取りまたは書き込みまたは除外なしのアクセスを実行する - さまざまなデバイスプロパティに基づいて特定のデバイスを許可します。

**Windows 10およびWindows 11 のサポートの詳細**:

- デバイス レベル、ユーザー レベルのどちらかで適用されます。 または両方を指定します。 特定のコンピューター上の特定のリムーバブル 記憶域への読み取り/書き込み/実行アクセスを実行する特定のユーザーのみを許可します。
- MEM OMA-URI と GPO をサポートします。
- 一覧に示[されている [デバイスのプロパティ](#device-properties)] がサポートされています。
- この機能については、「リムーバブル Windows[アクセス制御」を参照してください](device-control-removable-storage-access-control.md)。

**サポートされているプラットフォーム**- Windows 10、Windows 11

**macOS サポートの詳細**:

- デバイス レベルで適用されます。ログオンしているユーザーに対して同じポリシーが適用されます。
- macOS 固有の情報については [、「macOS のデバイス コントロール」を参照してください](mac-device-control-overview.md)。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4+ (システム拡張機能が有効な場合)


### <a name="device-installation"></a>デバイスのインストール

**機能 -** さまざまなデバイスプロパティに基づいて除外の設定または除外なしでインストールを防止します。

**Windows 10およびWindows 11 のサポートの詳細**:

- デバイス レベルで適用されます。ログオンしているユーザーに対して同じポリシーが適用されます。
- グループ ポリシー Microsoft エンドポイント マネージャーオブジェクトをサポートします。
- 一覧に示[されている [デバイスのプロパティ](#device-properties)] がサポートされています。
- デバイス の詳細については、「Windows Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法」[を参照してください](control-usb-devices-using-intune.md)。

**サポートされているプラットフォーム**- Windows 10、Windows 11

**macOS サポートの詳細**:

- デバイス レベルで適用: ログオンしているユーザーに対して同じポリシーが適用されます。
- macOS 固有の情報については [、「macOS のデバイス コントロール」を参照してください](mac-device-control-overview.md)。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4+ (システム拡張機能が有効な場合) 以降

### <a name="endpoint-dlp-removable-storage"></a>エンドポイント DLP リムーバブル ストレージ

**機能** - ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーする監査、警告、または防止します。

**説明**- エンドポイントデータ損失防止のWindows詳細 [については、「Microsoft 365」を参照してください](../../compliance/endpoint-dlp-learn-about.md)。

**サポートされているプラットフォーム**- Windows 10、Windows 11

### <a name="bitlocker"></a>BitLocker

**機能**:

- BitLocker で保護されていないリムーバブル ドライブに書き込まれるデータをブロックします。
- 組織が所有するコンピューターで暗号化されていないリムーバブル ドライブへのアクセスをブロックする

**説明**- 詳細については [、「BitLocker -](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)リムーバブル ドライブ Windows」を参照設定。

**サポートされているプラットフォーム**- Windows 10、Windows 11

## <a name="device-properties"></a>デバイス プロパティ

Microsoft Defender for Endpoint Device Control リムーバブル Storage保護を使用すると、以下の表に示すプロパティに基づいてリムーバブル 記憶域へのアクセスを制限できます。

<br/><br/>

|プロパティ名|適用可能なポリシー|オペレーティング システムに適用される|説明|
|---|---|---|---|
|デバイス クラス|[Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|デバイス ID 形式の詳細については、「デバイス セットアップ [クラス」を参照してください](/windows-hardware/drivers/install/overview-of-device-setup-classes)。 次の 2 つのリンクは、デバイス セットアップ クラスの完全な一覧を提供します。 'System Use' クラスは、主に、工場出荷時のコンピューター/コンピューターに含むデバイスを参照しますが、「ベンダー」クラスは、主に、既存のコンピューター/コンピューターに接続できるデバイスを参照します。ベンダーが利用できるシステム定義デバイス セットアップ クラス[- Windows](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)ドライバーとシステム使用用に予約されたシステム定義デバイス セットアップ クラス[- Windows](/windows-hardware/drivers/install/system-defined-device-setup-classes-reserved-for-system-use)ドライバーです。 **注**: デバイスインストールは、リムーバブル ストレージだけでなく、任意のデバイスに適用できます。|
|プライマリ ID|[リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md)|Windows|プライマリ ID には、リムーバブル ストレージと CD/DVD、ポータブル デバイス/WPD Windowsが含まれます。|
|デバイス ID|[リムーバブル 記憶域のアクセス制御](device-control-removable-storage-access-control.md)。 <p> [Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|デバイス ID 形式の詳細については [、「Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers)」を参照してください。たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07|
|ハードウェア ID|[リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md) <p> [Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)|Windows|USBSTOR\DiskGeneric_Flash_Disk___8.07 など、システム内のデバイスを識別した文字列。 **注**: ハードウェア ID は一意ではありません。異なるデバイスが同じ値を共有する場合があります。|
|インスタンス ID|[リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md) <p> デバイスのインストール|Windows|文字列は、システム内のデバイスを一意に識別します (たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0|
|フレンドリ名|[リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md)|Windows|デバイスに接続されている文字列 (汎用フラッシュ ディスク USB デバイスなど)|
|ベンダー ID / 製品 ID|[リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md)|Windows <p> macOS|ベンダー ID は、USB 委員会がベンダーに割り当てる 4 桁のベンダー コードです。 製品 ID は、ベンダーがデバイスに割り当てる 4 桁の製品コードです。ワイルドカードをサポートします。|
|シリアル番号Id|[リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md)|Windows <p> macOS |たとえば <SerialNumberId>、002324B534BCB431B000058A</SerialNumberId>|
