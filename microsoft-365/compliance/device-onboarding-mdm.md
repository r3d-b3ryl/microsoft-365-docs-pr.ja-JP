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
description: モバイル デバイス管理ツールを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 578a1e06bf5f83f700c5db69ddc32a480d68b729
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62327195"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。 Microsoft 365情報保護は、デバイスを管理するためのポリシーOMA-URIs作成するための情報を提供することで、MDM をサポートします。


## <a name="before-you-begin"></a>はじめに
デバイスを使用している場合Microsoft Intune MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。 

MDM を有効にする方法の詳細については、「Microsoft Intune登録 (Microsoft Intune[)」を参照してください](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>デバイスを使用したオンボード Microsoft Intune

Intune の指示に [従います](/intune/advanced-threat-protection)。

> [!NOTE]
> - オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用したオフボードデバイスと監視デバイス

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. オフボード パッケージをアプリケーション<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">から取得Microsoft 365 コンプライアンス センター</a>。

2. ナビゲーション ウィンドウで、[**Device onboardingOffboarding** > ] **設定** > を **選択します**。

3. [展開 **方法] フィールドで**、[**モバイル デバイスの管理/ 管理] を選択Microsoft Intune**。

4. [ **パッケージのダウンロード]** をクリックし、ファイルを.zipします。

5. パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。 *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding という名前のファイルが必要です*。

6. 次のサポートMicrosoft Intune OMA-URI 設定を展開するには、次のカスタム構成ポリシーを使用します。

    ```text
    OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
    Date type: String
    Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]
    ```
> [!NOTE]
> Microsoft Defender for Endpoint が既に構成されている場合は、デバイスオンボーディングを有効にでき、手順 6 は不要になります。

> [!NOTE]
> オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

## <a name="related-topics"></a>関連項目
- [グループ ポリシー Windows 10デバイスのオンボード](device-onboarding-gp.md)
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](device-onboarding-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
