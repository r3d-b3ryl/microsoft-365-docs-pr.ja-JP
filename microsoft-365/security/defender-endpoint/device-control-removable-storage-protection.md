---
title: Microsoft Defender for Endpoint Device Control リムーバブル 記憶域保護
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
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300206"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control リムーバブル 記憶域保護

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Removable Storage Protection を使用すると、ユーザーまたはコンピューター、あるいはその両方が未承認のリムーバブル 記憶域メディアを使用できません。

**Microsoft Defender for Endpoint リムーバブル 記憶域保護**


|ポリシー  |機能 |説明  |
|---------|---------|---------|
|デバイスのインストール    |  除外の付きまたは除外なしのインストールを防止する - さまざまなプロパティに基づいて特定のデバイスを許可します。詳細については、以下の「 [デバイスのプロパティ」セクションを](#device-properties) 参照してください。        |    コンピューター上で動作します。 同じコンピューターにログインするユーザーは、同じポリシーによって制限されます。 詳細については、「Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法 [」を参照してください](control-usb-devices-using-intune.md)。     |
|リムーバブル 記憶域アクセス制御      | (1) 監査 読み取りまたは書き込みまたはさまざまなデバイスのプロパティに基づいてリムーバブル 記憶域へのアクセスを実行します。例外の場合と例外なし。 詳細については、以下の「 [デバイスのプロパティ」セクションを](#device-properties) 参照してください。 (2) 読み取りまたは書き込み、または除外なしのアクセスの実行を防止する - さまざまなデバイスプロパティに基づいて特定のデバイスを許可する。デバイスのプロパティの詳細については、以下の「 [デバイスのプロパティ」セクションを](#device-properties) 参照してください。     |     コンピューターまたはユーザーのどちらかまたは両方で動作します。特定のコンピューター上の特定のリムーバブル 記憶域への読み取り/書き込み/実行アクセスを実行する特定のユーザーのみを許可します。Windows の機能については、「リムーバブル 記憶域 [アクセス制御」を参照してください](device-control-removable-storage-access-control.md)。Mac の機能については、「macOS の [デバイス コントロール」を参照してください](mac-device-control-overview.md)。     |
|エンドポイント DLP リムーバブル ストレージ      |    ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーする監査または警告を表示または防止します。     |  詳細については [、「Microsoft Endpoint DLP」を参照してください](/compliance/endpoint-dlp-learn-about.md)。       |
|BitLocker    |     BitLocker で保護されていないリムーバブル ドライブに書き込まれるデータをブロックする: 組織が所有するコンピューターで暗号化されていない限り、リムーバブル ドライブへのアクセスをブロックします。    |   詳細については、「BitLocker - リムーバブル [ドライブの設定」を参照してください](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md)。      |

## <a name="device-properties"></a>デバイスのプロパティ

Microsoft Defender for Endpoint Device Control Removable Storage Protection を使用すると、以下の表に示すプロパティに基づいてリムーバブル 記憶域アクセスを制限できます。


|プロパティ名  |適用可能なポリシー  |オペレーティング システムに適用される  |説明  |
|---------|---------|---------|---------|
|デバイス クラス    |     [Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)     |   Windows      |  デバイス ID 形式の詳細については、「デバイス セットアップ [クラス」を参照してください](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。 **注**: デバイスインストールは、リムーバブル ストレージだけでなく、任意のデバイスに適用できます。       |
|プライマリ ID   |     リムーバブル 記憶域アクセス制御    |   Windows      |      プライマリ ID には、リムーバブル 記憶域と CD/DVD が含まれます。   |
|デバイス ID     |  [Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)。リムーバブル 記憶域アクセス制御       |      Windows   |    デバイス ID 形式の詳細については [、「Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers)」を参照してください。たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|ハードウェア ID     |     [Microsoft Defender for Endpoint を使用して USB デバイスや他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)。リムーバブル 記憶域アクセス制御    |     Windows    |    システム内のデバイスを識別する文字列 (たとえば、USBSTOR\DiskGeneric_Flash_Disk______8.07)。 **注**: ハードウェア ID は一意ではありません。異なるデバイスが同じ値を共有する場合があります。|
|インスタンス ID    | デバイスのインストール。リムーバブル 記憶域アクセス制御     |     Windows    |   文字列は、システム内のデバイスを一意に識別します (たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|フレンドリ名     |     リムーバブル 記憶域アクセス制御    |   Windows      |    デバイスに接続されている文字列 (汎用フラッシュ ディスク USB デバイスなど)     |
|ベンダー ID / 製品 ID     |  リムーバブル 記憶域アクセス制御       |   Windows Mac      |     ベンダー ID は、USB 委員会がベンダーに割り当てる 4 桁のベンダー コードです。 製品 ID は、ベンダーがデバイスに割り当てる 4 桁の製品コードです。ワイルドカードをサポートします。    |
|シリアル番号Id     |     リムーバブル 記憶域アクセス制御    |      Windows Mac   |     たとえば <SerialNumberId>、002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpoint Device Control リムーバブル 記憶域アクセス制御](device-control-removable-storage-access-control.md)
