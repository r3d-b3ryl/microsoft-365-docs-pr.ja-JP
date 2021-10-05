---
title: モバイル Windowsツールを使用してデバイスをオンボードする
description: モバイル デバイス管理ツールを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
keywords: mdm を使用したオンボード デバイス、デバイス管理、オンボード Microsoft Defender for Endpoint デバイス、mdm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6cb99f300c7d87497f31729507695a9a633b345a
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124699"
---
# <a name="onboard-the-windows-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールWindowsデバイスをオンボードする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

モバイル デバイス管理 (MDM) ソリューションを使用してデバイスを構成できます。 Defender for Endpoint は、デバイスを管理OMA-URIsポリシーを作成するためのユーザー情報を提供することで、MDM をサポートします。

Defender for Endpoint CSP の使用の詳細については [、「WindowsAdvancedThreatProtection CSP」](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) および [「WindowsAdvancedThreatProtection DDF ファイル」を参照してください](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。

## <a name="before-you-begin"></a>はじめに

デバイスを使用している場合Microsoft Intune MDM が登録されている必要があります。 それ以外の場合、設定は正常に適用されません。

MDM を有効にする方法の詳細については、「デバイスMicrosoft Intune [(Microsoft Intune) 」を参照してください](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>デバイスを使用したオンボード Microsoft Intune

[[](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)エンドポイント用 Defender [Visio展開](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)] のさまざまなパスを確認するには、PDF またはドキュメントを参照してください。

Intune の指示に [従います](/intune/advanced-threat-protection)。

Defender for Endpoint CSP の使用の詳細については [、「WindowsAdvancedThreatProtection CSP」](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) および [「WindowsAdvancedThreatProtection DDF ファイル」を参照してください](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。

> [!NOTE]
>
> - オンボード **デバイスの正常性状態ポリシーでは** 、読み取り専用プロパティが使用され、修復できません。
> - 診断データレポートの頻度の構成は、バージョン 1703 の Windows 10デバイスでのみ使用できます。


[MICROSOFT](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) Defender for Endpoint[の展開](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)Visioパスを確認するには、PDF またはドキュメントを参照してください。

## <a name="run-a-detection-test-to-verify-onboarding"></a>検出テストを実行してオンボーディングを確認する
デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](run-detection-test.md)。


## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>モバイル デバイス管理ツールを使用したオフボードデバイスと監視デバイス

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. ポータルからオフボード パッケージ[Microsoft 365 Defenderします](https://security.microsoft.com/)。

   1. ナビゲーション ウィンドウで、[エンドポイント **デバイス** 設定 \> **オフ** \> **ボード]** \> **を選択します**。

   1. オペレーティング Windows 10としてWindows 11 を選択します。

   1. [展開 **方法] フィールドで**、[**モバイル デバイスの管理/ 管理] を選択Microsoft Intune。**

   1. [ **パッケージのダウンロード]** をクリックし、ファイルを.zipします。

2. パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。 *"-MM-DD.offboarding WindowsDefenderATP_valid_until_YYYYという名前のファイルが必要です*。

3. 次のサポートMicrosoft Intune OMA-URI 設定を展開するには、次のカスタム構成ポリシーを使用します。
   - OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
   - 日付の種類: 文字列
   - 値: [ファイルのコンテンツから値をコピーして貼りWindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding ファイル]

ポリシー設定の詳細については、「Microsoft Intuneのポリシー設定[Windows 10」を参照Microsoft Intune。](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> オフ **ボードデバイスの正常性状態** ポリシーでは、読み取り専用プロパティが使用され、修復できません。

> [!IMPORTANT]
> Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。

## <a name="related-topics"></a>関連トピック

- [グループ ポリシー Windowsデバイスのオンボード](configure-endpoints-gp.md)
- [デバイスWindowsデバイスのオンボードMicrosoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [ローカル Windowsを使用してデバイスをオンボードする](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)
- [Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング](troubleshoot-onboarding.md)
