---
title: モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: モバイル デバイス管理ツールを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917993"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365 Endpoint データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)

モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。 Microsoft 365 Endpoint データ損失防止は、デバイスを管理するためのポリシーをOMA-URIsする機能を提供することで、MDM をサポートします。


## <a name="before-you-begin"></a>はじめに
Microsoft Intune を使用している場合は、デバイス MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。 

Microsoft Intune で MDM を有効にする方法の詳細については、「デバイス登録 [(Microsoft Intune)」を参照してください](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intune を使用したオンボード デバイス

Intune の指示に [従います](/intune/advanced-threat-protection)。

> [!NOTE]
> - オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用したオフボードデバイスと監視デバイス

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. Microsoft コンプライアンス センターからオフボード パッケージ [を取得します](https://compliance.microsoft.com/)。

2. ナビゲーション ウィンドウで、[設定デバイスオン **ボーディング** オフボード]  >    >  **を選択します**。

3. [展開 **方法] フィールドで** 、[ **モバイル デバイス管理] / [Microsoft Intune] を選択します**。
    
4. [パッケージ **のダウンロード]** をクリックし、.zip ファイルを保存します。

5. .zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。 *"-MM-DD.offboarding DeviceCompliance_valid_until_YYYYという名前のファイルが必要です*。

6. Microsoft Intune カスタム構成ポリシーを使用して、次のサポートされる OMA-URI 設定を展開します。

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      日付の種類: 文字列      
      値: [ファイルのコンテンツから値をコピーして貼り付DeviceCompliance_valid_until_YYYY-MM-DD.offboarding ファイル]

Microsoft Intune ポリシー設定の詳細については [、「Microsoft Intune の Windows 10 ポリシー設定」を参照してください](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。

> [!NOTE]
> オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager を使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-sccm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)