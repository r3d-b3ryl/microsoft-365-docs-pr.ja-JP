---
title: モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード
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
description: モバイルデバイス管理ツールを使用して、サービスに利用されるように構成パッケージをデバイスに展開します。
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769482"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

モバイルデバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。 Microsoft 365 エンドポイントのデータ損失防止は、デバイスを管理するためのポリシーを作成するための OMA-URIs を提供することにより、MDMs をサポートします。


## <a name="before-you-begin"></a>開始する前に
Microsoft Intune を使用している場合は、デバイス MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。 

Microsoft Intune で MDM を有効にする方法の詳細については、「 [Device enrollment (Microsoft intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)」を参照してください。

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intune を使用しているオンボードデバイス

[Intune](https://docs.microsoft.com/intune/advanced-threat-protection)からの指示に従います。

> [!NOTE]
> - **利用 devices policy の** 状態は読み取り専用プロパティを使用しており、修復することはできません。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイルデバイス管理ツールを使用した offboard およびモニターデバイス

セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。 有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。 オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。

> [!NOTE]
> オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。

1. [Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)からオフボードパッケージを取得します。

2. ナビゲーションウィンドウで、[ **設定** ] [デバイスのオンボードオフボード] を選択し  >  **Device onboarding**  >  **Offboarding** ます。

3. [ **展開方法** ] フィールドで、[ **モバイルデバイス管理]/[Microsoft Intune** ] を選択します。
    
4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. .Zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。 *DeviceCompliance_valid_until_YYYY-MM-DD* という名前のファイルが必要です。

6. Microsoft Intune カスタム構成ポリシーを使用して、次のサポートされている OMA URI 設定を展開します。

      OMA URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      日付型: String      
      値: [次の値をコピーして貼り付け DeviceCompliance_valid_until_YYYY-MM-DD ファイルの内容をコピーして貼り付ける]

Microsoft Intune ポリシー設定の詳細については、「 [Microsoft intune の Windows 10 ポリシー設定](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)」を参照してください。

> [!NOTE]
> **Offboarded devices policy の** 状態は読み取り専用プロパティを使用しており、修復することはできません。

> [!IMPORTANT]
> オフボードを使用すると、デバイスはポータルへのセンサーデータの送信を停止しますが、デバイスからのデータは、必要なアラートへの参照も含めて最大6か月保持されます。

## <a name="related-topics"></a>関連項目
- [グループポリシーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-sccm.md)
- [ローカルスクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス](dlp-configure-endpoints-vdi.md)
- [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
