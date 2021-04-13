---
title: Microsoft Defender ウイルス対策の更新プログラムをスケジュールする
description: 保護更新プログラムをダウンロードする日、時刻、間隔をスケジュールする
keywords: 更新プログラム、セキュリティ基準、更新プログラムのスケジュール
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691031"
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

1.  Microsoft Endpoint Manager コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを [Overview  >  **Endpoint Protection**  >  **Antimalware Policies]** に展開します)。

2.  [セキュリティ インテリジェンスの **更新プログラム] セクションに移動** します。

3. 特定の時間に更新プログラムを確認してダウンロードするには、次の方法を実行します。
      1. [ **エンドポイント保護のセキュリティ インテリジェンス更新プログラムの確認]** を特定の間隔で設定します。. **に 0 を設定します**。
      2. [ **エンドポイント保護のセキュリティ インテリジェンス更新プログラム** を毎日チェックする] を設定します。更新プログラムをチェックする必要がある時刻に設定します。
      3
4. 継続的な間隔で更新プログラムを確認してダウンロードするには、特定の間隔でエンドポイント保護セキュリティ インテリジェンス更新プログラムのチェックを設定 **します** 。更新プログラムの間に発生する時間数を指定します。

5.  [更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="use-group-policy-to-schedule-protection-updates"></a>グループ ポリシーを使用して保護更新プログラムをスケジュールする

> [!IMPORTANT]
> 既定では、Microsoft Defender ウイルス対策は、スケジュールされたスキャンの 15 分前に更新プログラムをチェックします。 これらの設定を有効にすると、既定の設定は上書きされます。

1.  グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4.  [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

5.  ツリーを Windows コンポーネント **の Microsoft** Defender  >  **ウイルス対策シグネチャ** インテリジェンス更新プログラムに展開  >  **し、** 次の設定を構成します。

    1. [セキュリティ インテリジェンスの更新 **プログラム** を確認する週の日を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 更新プログラムを確認する週の日を入力します。 **[OK]** をクリックします。
    2. [セキュリティ インテリジェンスの更新 **プログラム** を確認する間隔を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 更新間の時間数を入力します。 **[OK]** をクリックします。
    3. [セキュリティ インテリジェンスの更新 **プログラム** を確認する時間を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 更新プログラムをチェックする時刻を入力します。 時刻は、エンドポイントのローカル時刻に基づいて行います。 **[OK]** をクリックします。


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>PowerShell コマンドレットを使用して保護更新プログラムをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Windows 管理命令 (WMI) を使用して保護更新プログラムをスケジュールする

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策の展開](deploy-manage-report-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [イベントベースの強制的な更新の管理](manage-event-based-updates-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)