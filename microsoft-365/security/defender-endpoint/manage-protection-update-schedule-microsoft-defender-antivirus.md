---
title: 保護Microsoft Defender ウイルス対策のスケジュールを設定する
description: 保護更新プログラムをダウンロードする日、時刻、間隔をスケジュールする
keywords: 更新プログラム、セキュリティ基準、更新プログラムのスケジュール
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bdc3ddea542a888dbcd7fcf095835f327fb19e0a
ms.sourcegitcommit: c41e3f48451e2d7b45901faee21b1e1d19a16688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2021
ms.locfileid: "58823927"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>保護更新プログラムをダウンロードして適用するスケジュールを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策では、更新プログラムを探してダウンロードする必要がある場合に判断できます。

エンドポイントの更新プログラムは、次の方法でスケジュールできます。

- 保護更新プログラムを確認する週の日を指定する
- 保護更新プログラムを確認する間隔を指定する
- 保護更新プログラムを確認する時間を指定する

また、各エンドポイントが保護更新プログラムをチェックしてダウンロードする時間をランダム化できます。 詳細については、「 [スキャンのスケジュール」](scheduled-catch-up-scans-microsoft-defender-antivirus.md) のトピックを参照してください。

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Configuration Manager を使用して保護更新プログラムをスケジュールする

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーションウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを[概要] Endpoint Protection マルウェア対策ポリシー \>  \> ) に展開します。

2. [セキュリティ インテリジェンスの **更新プログラム] セクションに移動** します。

3. 特定の時間に更新プログラムを確認してダウンロードするには、次の方法を実行します。
      1. セキュリティ **インテリジェンス更新プログラムEndpoint Protectionを特定の間隔で確認する...** を **0 に設定します**。
      2. セキュリティ **インテリジェンスの更新Endpoint Protectionを毎日チェックします。更新** プログラムをチェックする必要がある時刻に設定します。
      3
4. 継続的な間隔で更新プログラムを確認してダウンロードするには、特定の間隔で Endpoint Protection セキュリティ インテリジェンス更新プログラムのチェックを設定 **します**。更新プログラムの間に発生する必要がある時間数を指定します。

5. [更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="use-group-policy-to-schedule-protection-updates"></a>グループ ポリシーを使用して保護更新プログラムをスケジュールする

> [!IMPORTANT]
> 既定では、Microsoft Defender ウイルス対策スキャンの時刻の 15 分前に更新プログラムがチェックされます。 これらの設定を有効にすると、既定の設定は上書きされます。

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

4. ツリーを展開して **、[署名インテリジェンスWindows更新** Microsoft Defender ウイルス対策 \>  \> **コンポーネントを追加し**、次の設定を構成します。

    1. [セキュリティ インテリジェンスの更新 **プログラム** を確認する週の日を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 更新プログラムを確認する週の日を入力します。 [**OK**] をクリックします。
    2. [セキュリティ インテリジェンスの更新 **プログラム** を確認する間隔を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 更新間の時間数を入力します。 [**OK**] をクリックします。
    3. [セキュリティ インテリジェンスの更新 **プログラム** を確認する時間を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 更新プログラムをチェックする時刻を入力します。 時刻は、エンドポイントのローカル時刻に基づいて行います。 [**OK**] をクリックします。

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>PowerShell コマンドレットを使用して保護更新プログラムをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>保護Windowsスケジュールを設定するには、WMI 管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

詳細と許可されるパラメーターについては、以下を参照してください。

- [Windows DefenderWMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>関連記事

- [展開Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)
- [更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
