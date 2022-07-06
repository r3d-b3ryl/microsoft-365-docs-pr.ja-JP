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
description: モバイル デバイス管理 ツールを使用して、構成パッケージをデバイスに展開して、サービスにオンボードします。
ms.openlocfilehash: d5c03c80c9a38d34ab27f888084604372874a64a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624203"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)

モバイル デバイス管理 (MDM) ソリューションを使用して、デバイスを構成できます。 Microsoft 365 情報保護は、デバイスを管理するポリシーを作成するOMA-URIsを提供することで、MMM をサポートします。


## <a name="before-you-begin"></a>はじめに
Microsoft Intuneを使用している場合は、デバイス MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。 

Microsoft Intuneで MDM を有効にする方法の詳細については、「[デバイスの登録 (Microsoft Intune)](/mem/intune/enrollment/device-enrollment)」を参照してください。

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intuneを使用してデバイスをオンボードする

[Intune](/mem/intune/protect/advanced-threat-protection-configure)の指示に従います。
 
> [!NOTE]
> - **オンボードされたデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理 ツールを使用してデバイスをオフボードおよび監視する

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>からオフボード パッケージを取得します。

2. ナビゲーション ウィンドウで、[デバイスオン **ボーディング** > **オフボーディング****の設定]** >  を選択します。

3. [**展開方法]** フィールドで、[**モバイル デバイス管理/ Microsoft Intune**] を選択します。

4. [ **パッケージのダウンロード**] をクリックし、.zip ファイルを保存します。

5. パッケージを展開するネットワーク管理者がアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* という名前のファイルが必要です。

6. Microsoft Intuneカスタム構成ポリシーを使用して、サポートされている次の OMA-URI 設定をデプロイします。

    ```text
    OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
    Date type: String
    Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]
    ```
> [!NOTE]
> Microsoft Defender for Endpointが既に構成されている場合は、**デバイスのオンボードを有効に** できます。手順 6 は不要になりました。

> [!NOTE]
> **オフボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="related-topics"></a>関連トピック
- [グループ ポリシーを使用してWindows 10 デバイスをオンボードする](device-onboarding-gp.md)
- [Microsoft Endpoint Configuration Managerを使用してWindows 10 デバイスをオンボードする](device-onboarding-sccm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](device-onboarding-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
