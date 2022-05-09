---
title: Microsoft Defender ウイルス対策検出の修復を構成する
description: 脅威を検出したときに実行するMicrosoft Defender ウイルス対策と、検疫されたファイルを検疫フォルダーに保持する期間を構成する
keywords: 修復、修正、削除、脅威、検疫、スキャン、復元
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 257a3bfc4fc9dcb6353bb158bc3cd4296891ae76
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790154"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Microsoft Defender ウイルス対策検出の修復を構成する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策はスキャンを実行すると、検出された脅威の修復または削除を試みます。 特定の脅威に対処Microsoft Defender ウイルス対策方法、修復前に復元ポイントを作成する必要があるかどうか、脅威を削除するタイミングを構成できます。

この記事では、グループ ポリシーを使用してこれらの設定を構成する方法について説明しますが、[Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)と[Microsoft Intune](/intune/device-restrictions-configure)を使用することもできます。

PowerShell コマンドレットまたは [`MSFT_MpPreference` WMI クラス](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)を[`Set-MpPreference`](/powershell/module/defender/set-mppreference)使用して、これらの設定を構成することもできます。

## <a name="configure-remediation-options"></a>修復オプションを構成する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを右クリックし、[編集] をクリック **します**。

2. **グループ ポリシー管理エディター** で **[コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

3. ツリーを展開して **、Microsoft Defender ウイルス対策コンポーネント** \> **をWindows** します。

4. 次の表を使用して場所を選択し、必要に応じてポリシーを編集します。

5. **[OK]** を選択します。

<br/><br/>

|Location|Setting|説明|既定の設定 (構成されていない場合)|
|---|---|---|---|
|スキャン|システム復元ポイントを作成する|システム復元ポイントは、クリーニングまたはスキャンが試行される前に毎日作成されます|無効|
|スキャン|スキャン履歴フォルダーからのアイテムの削除を有効にする|スキャン履歴にアイテムを保持する日数を指定する|30 日間|
|ルート|定期的な修復を無効にする|脅威を自動的に修復Microsoft Defender ウイルス対策かどうか、またはエンドポイント ユーザーに何をすべきかを尋ねる必要があるかどうかを指定できます。|無効 (脅威は自動的に修復されます)|
|検疫する|検疫フォルダーからのアイテムの削除を構成する|アイテムを削除する前に検疫に保持する日数を指定する|90 日間|
|Threats|検出されたときに既定のアクションを実行しない脅威アラート レベルを指定する|Microsoft Defender ウイルス対策によって検出されるすべての脅威には、脅威レベル (低、中、高、または重大) が割り当てられます。 この設定を使用して、各脅威レベルのすべての脅威を修復する方法 (検疫、削除、または無視) を定義できます。|該当なし|
|Threats|検出されたときに既定のアクションを実行しない脅威を指定する|(脅威 ID を使用して) 特定の脅威を修復する方法を指定します。 特定の脅威を検疫、削除、または無視するかどうかを指定できます。|該当なし|

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、さまざまな要因に基づいてファイルを検出して修復します。 修復を完了するには再起動が必要な場合があります。 検出が後で誤検知と判断された場合でも、再起動を完了して、追加のすべての修復手順が完了していることを確認する必要があります。
>
> 誤検知に基づいてファイルを検疫Microsoft Defender ウイルス対策特定の場合は、デバイスの再起動後に検疫からファイルを復元できます。 [Microsoft Defender ウイルス対策での検疫済みファイルの復元に関するページを参照](restore-quarantined-files-microsoft-defender-antivirus.md)してください。
>
> 今後、この問題を回避するために、スキャンからファイルを除外できます。 「[Microsoft Defender ウイルス対策のスキャンの除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)」を参照してください。

さらに修復関連の設定については、「[修復に必要なスケジュールされた完全Microsoft Defender ウイルス対策 スキャンの構成](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)」も参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策スキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [スケジュールされたMicrosoft Defender ウイルス対策 スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
- [エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
- [エンド ユーザーのMicrosoft Defender ウイルス対策操作を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
