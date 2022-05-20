---
title: モバイル デバイス管理ツールを使用した Windows デバイスのオンボード
description: Mobile デバイス管理 ツールを使用して、デバイスに構成パッケージを展開し、Defender for Endpoint サービスにオンボードします。
keywords: mdm を使用したデバイスのオンボード、デバイス管理、Microsoft Defender for Endpoint デバイスのオンボード、mdm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3e81470cb02742eb94e62118f77f1ae0e8c62f90
ms.sourcegitcommit: b5529afa84f7dde0a89b1e08aeaf6a3a15cd7679
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65599683"
---
# <a name="onboard-windows-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用した Windows デバイスのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

モバイル デバイス管理 (MDM) ソリューションを使用して、Windows 10 デバイスを構成できます。 Defender for Endpoint は、デバイスを管理するポリシーを作成するOMA-URIsを提供することで、MDM をサポートします。


Defender for Endpoint CSP の使用の詳細については、「 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) と [WindowsAdvancedThreatProtection DDF ファイル](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)」を参照してください。

## <a name="before-you-begin"></a>開始する前に

Microsoft Intuneを使用している場合は、デバイス MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。

Microsoft Intuneで MDM を有効にする方法の詳細については、「[デバイスの登録 (Microsoft Intune)](/mem/intune/enrollment/device-enrollment)」を参照してください。

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intuneを使用してデバイスをオンボードする

[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) または[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)を確認して、Defender for Endpoint のデプロイに関するさまざまなパスを確認してください。

[Intune](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune)の指示に従います。


Defender for Endpoint CSP の使用の詳細については、「 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) と [WindowsAdvancedThreatProtection DDF ファイル](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)」を参照してください。

> [!NOTE]
>
> - **オンボードされたデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。
> - 診断データレポートの頻度の構成は、Windows 10 バージョン 1703 のデバイスでのみ使用できます。


[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) またはVisioを確認して、[Microsoft Defender for Endpoint](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)をデプロイする際のさまざまなパスを確認してください。

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボードを検証する
デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)」 を参照してください。


## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理 ツールを使用してデバイスをオフボードおよび監視する

セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

1. ポータルからオフボード パッケージ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>取得します。

   1. ナビゲーション ウィンドウで、[**エンドポイント** \> **デバイス管理** \> **オフボード****設定**\>] を選択します。

   1. オペレーティング システムとしてWindows 10またはWindows 11を選択します。

   1. [**展開方法]** フィールドで、[**モバイル デバイス管理/ Microsoft Intune**] を選択します。

   1. [ **パッケージのダウンロード**] をクリックし、.zip ファイルを保存します。

2. パッケージを展開するネットワーク管理者がアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding* という名前のファイルが必要です。

3. Microsoft Intuneカスタム構成ポリシーを使用して、サポートされている次の OMA-URI 設定をデプロイします。
   - OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
   - 日付型: 文字列
   - 値: [WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding ファイルの内容から値をコピーして貼り付けます]

Microsoft Intune ポリシー設定の詳細については、[Microsoft Intuneのポリシー設定Windows 10](/mem/intune/configuration/custom-settings-windows-10)参照してください。

> [!NOTE]
> **オフボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> オフボーディングにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (発生したアラートへの参照を含む) は、最大 6 か月間保持されます。

## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
