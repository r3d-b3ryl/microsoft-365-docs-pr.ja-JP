---
title: モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Mobile デバイス管理ツールを使用して、デバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 9b329ccf86a2364c13ac72bd4348711d72c17ff5
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634495"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。 Microsoft 365情報保護は、デバイスを管理するためのポリシーOMA-URIs作成するための情報を提供することで、MDM をサポートします。


## <a name="before-you-begin"></a>開始する前に
デバイスを使用している場合Microsoft Intune MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。 

MDM を有効にする方法の詳細については、「Microsoft Intune登録 (Microsoft Intune[)」を参照してください](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>デバイスを使用したオンボード Microsoft Intune

次の手順に[従Intune。](/mem/intune/protect/advanced-threat-protection-configure)
 
> [!NOTE]
> - オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理 ツールを使用してデバイスをオフボードおよび監視する

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. アプリケーションからオフボード パッケージを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">取得</a>Microsoft 365 コンプライアンス センター。

2. ナビゲーション ウィンドウで、[**Device onboardingOffboarding** > ] **設定** > を **選択します**。

3. [展開方法 **] フィールドで**、[**Mobile デバイス管理/ Microsoft Intune] を選択します**。

4. [ **パッケージのダウンロード]** をクリックし、ファイルを.zipします。

5. パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。 "- *MM-DD.offboarding DeviceCompliance_valid_until_YYYYという名前のファイルが必要です*。

6. 次のサポートMicrosoft Intune OMA-URI 設定を展開するには、カスタム構成ポリシーを使用します。

    ```text
    OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
    Date type: String
    Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]
    ```
> [!NOTE]
> このMicrosoft Defender for Endpoint構成済みの場合は、デバイスオンボーディングを有効にでき、手順 6 は不要になります。

> [!NOTE]
> オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

## <a name="related-topics"></a>関連項目
- [デバイスをWindows 10デバイスをオンボードグループ ポリシー](device-onboarding-gp.md)
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](device-onboarding-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
