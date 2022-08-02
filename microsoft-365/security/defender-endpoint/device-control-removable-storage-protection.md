---
title: Microsoft Defender for Endpoint デバイス コントロールリムーバブル ストレージ保護
description: ユーザーまたはマシンまたはその両方が承認されていないリムーバブル ストレージ メディアを使用するのを防ぐのに役立つ '機能' を理解する
keywords: リムーバブル ストレージ メディア
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
ms.date: 08/01/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a0225c12521812dc3888aac6c0179019dfa0ea72
ms.sourcegitcommit: adc4e5707aa074fc4aa0cb9e8c2986fc8b88813c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67112529"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint デバイス コントロールリムーバブル ストレージ保護


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

外部ストレージを管理するには、 [デバイスのインストール](#device-installation)ではなく、リムーバブル ストレージアクセス制御を使用します。

**Windows 10とWindows 11のサポートの詳細**:

- デバイス レベル、ユーザー レベルのいずれかで適用されます。 または両方。 特定のコンピューター上の特定のリムーバブル ストレージへの読み取り/書き込み/実行アクセスを実行する特定のユーザーのみを許可します。
- MEM OMA-URI と GPO をサポートします。
- Windows デバイスの場合は、「[リムーバブル ストレージ Access Control](device-control-removable-storage-access-control.md)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

**macOS サポートの詳細**:

- デバイス レベルで適用されます。ログオンしているすべてのユーザーに同じポリシーが適用されます。
- macOS 固有の情報については、 [macOS のデバイスコントロールに関するページを](mac-device-control-overview.md)参照してください。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4 以降 (システム拡張機能が有効になっている場合)


### <a name="device-installation"></a>デバイスのインストール

**機能** - さまざまなデバイスのプロパティに基づいて、除外の有無にかかわらずインストールを禁止します。

**Windows 10とWindows 11のサポートの詳細**:

- デバイス レベルで適用されます。ログオンしているすべてのユーザーに同じポリシーが適用されます。
- Microsoft エンドポイント マネージャー オブジェクトとグループ ポリシー オブジェクトをサポートします。
- Windows の詳細については、「[Microsoft Defender for Endpointを使用して USB デバイスやその他のリムーバブル メディアを制御する方法](control-usb-devices-using-intune.md)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

**macOS サポートの詳細**:

- デバイス レベルで適用: ログオンしているすべてのユーザーに同じポリシーが適用されます
- macOS 固有の情報については、 [macOS のデバイスコントロールに関するページを](mac-device-control-overview.md)参照してください。

**サポートされているプラットフォーム** - macOS Catalina 10.15.4 以降 (システム拡張機能が有効) 以降

### <a name="endpoint-dlp-removable-storage"></a>エンドポイント DLP リムーバブル ストレージ

**機能** - ユーザーがアイテムや情報をリムーバブル メディアまたは USB デバイスにコピーすることを監査、警告、または禁止します。

**説明** - Windows の詳細については、「 [エンドポイントデータ損失防止の詳細](../../compliance/endpoint-dlp-learn-about.md)」を参照してください。

**サポートされているプラットフォーム** - Windows 10、Windows 11

### <a name="bitlocker"></a>BitLocker

**機能**:

- BitLocker で保護されていないリムーバブル ドライブに書き込まれるデータをブロックします。
- 組織が所有するコンピューターでリムーバブル ドライブが暗号化されていない限り、リムーバブル ドライブへのアクセスをブロックする

**説明** - Windows の詳細については、「 [BitLocker - リムーバブル ドライブの設定」を参照してください](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)。

**サポートされているプラットフォーム** - Windows 10、Windows 11
