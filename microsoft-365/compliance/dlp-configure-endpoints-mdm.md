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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: モバイル デバイス管理ツールを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 7d1d51ef048c619f700f5c04d30804ec15f4c15d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204373"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)

モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。 Microsoft 365エンドポイント のデータ損失防止は、デバイスを管理するためのOMA-URIsを作成する機能を提供することで、MDM をサポートします。


## <a name="before-you-begin"></a>はじめに
デバイスを使用している場合Microsoft Intune MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。 

MDM を有効にする方法の詳細については、「デバイスMicrosoft Intune [(Microsoft Intune) 」を参照してください](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>デバイスを使用したオンボード Microsoft Intune

Intune の指示に [従います](/intune/advanced-threat-protection)。

> [!NOTE]
> - オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用したオフボードデバイスと監視デバイス

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. Microsoft コンプライアンス センターからオフボード パッケージ [を取得します](https://compliance.microsoft.com/)。

2. ナビゲーション ウィンドウで、[デバイスオンボーディング **設定**  >  **オフボード]**  >  **を選択します**。

3. [展開 **方法] フィールドで**、[**モバイル デバイスの管理/ 管理] を選択Microsoft Intune。**
    
4. [ **パッケージのダウンロード]** をクリックし、ファイルを.zipします。

5. パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。 *"-MM-DD.offboarding DeviceCompliance_valid_until_YYYYという名前のファイルが必要です*。

6. 次のサポートMicrosoft Intune OMA-URI 設定を展開するには、次のカスタム構成ポリシーを使用します。

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      日付の種類: 文字列      
      値: [ファイルのコンテンツから値をコピーして貼り付DeviceCompliance_valid_until_YYYY-MM-DD.offboarding ファイル]

ポリシー設定の詳細については、「Microsoft Intuneのポリシー設定[Windows 10」を参照Microsoft Intune。](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

## <a name="related-topics"></a>関連トピック
- [グループ ポリシー Windows 10デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)