---
title: 特定のイベントの後に Microsoft Defender ウイルス対策の更新プログラムを適用する
description: Microsoft Defender ウイルス対策が、クラウド配信の検出レポートを起動または受信した後にセキュリティ インテリジェンス更新プログラムを適用する方法を管理します。
keywords: 更新, 保護, 強制更新, イベント, スタートアップ, 最新の確認, 通知
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 315e3e41e78ad29042eadf60ec1a01dba1517583
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387597"
---
# <a name="manage-event-based-forced-updates"></a>イベントベースの強制更新プログラムを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策を使用すると、起動時やクラウド配信保護サービスから特定のレポートを受信した後など、特定のイベントの後に更新を行う必要があるかどうかを判断できます (または行う必要はありません)。

## <a name="check-for-protection-updates-before-running-a-scan"></a>スキャンを実行する前に保護更新プログラムを確認する

Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、WMI を使用して、スケジュールされたスキャンを実行する前に、Microsoft Defender ウイルス対策に対して保護更新プログラムの確認とダウンロードを強制できます。

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Configuration Managerを使用して、スキャンを実行する前に保護更新プログラムを確認する

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで **[資産とコンプライアンス**] をクリックし、ツリーを [**Endpoint Protection** \> **のマルウェア対策ポリシー** の **概要**\>] に展開します)。

2. **[スケジュールされたスキャン**] セクションに移動し、[**スキャンを実行する前に最新のセキュリティ インテリジェンス更新プログラムを確認** する] を **[はい**] に設定します。

3. [**OK**] をクリックします。

4. [更新されたポリシーを通常どおりにデプロイ](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)します。

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>グループ ポリシーを使用して、スキャンを実行する前に保護更新プログラムを確認する

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** を使用して **、コンピューターの構成** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策**\>スキャンに展開 **します**。

5. **スケジュールされたスキャンを実行する前に、[最新のウイルス定義とスパイウェア定義を確認** する] をダブルクリックし、オプションを **[有効]** に設定します。

6. [**OK**] をクリックします。

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>PowerShell コマンドレットを使用して、スキャンを実行する前に保護更新プログラムを確認する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender ウイルス対策 コマンドレット ](/powershell/module/defender/index)」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Windows 管理命令 (WMI) を使用して、スキャンを実行する前に保護更新プログラムを確認する

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
CheckForSignaturesBeforeRunningScan
```

詳細については、「[WINDOWS DEFENDER WMIv2 API」を参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="check-for-protection-updates-on-startup"></a>起動時に保護更新プログラムを確認する

グループ ポリシーを使用して、コンピューターの起動時に Microsoft Defender ウイルス対策に対して保護更新プログラムの確認とダウンロードを強制できます。

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)を開き、構成するグループ ポリシーオブジェクトを右クリックし、[編集] をクリック **します**。

2. **グループ ポリシー管理エディター** を使用して **、コンピューターの構成** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **セキュリティ インテリジェンス 更新** に展開します。

5. **起動時に最新のウイルス定義とスパイウェア定義を確認** するをダブルクリックし、オプションを **[有効]** に設定します。

6. [**OK**] をクリックします。

グループ ポリシー、PowerShell、WMI を使用して、起動時に更新プログラムが実行されていない場合でも、Microsoft Defender ウイルス対策を構成して更新プログラムを確認することもできます。

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Microsoft Defender ウイルス対策が存在しない場合は、グループ ポリシーを使用して更新プログラムをダウンロードする

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** を使用して、[**コンピューターの構成] に移動します**。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **セキュリティ インテリジェンス 更新** に展開します。

5. **[スタートアップ時にセキュリティ インテリジェンスの更新を開始** する] をダブルクリックし、オプションを **[有効]** に設定します。

6. [**OK**] をクリックします。

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Microsoft Defender ウイルス対策が存在しない場合に PowerShell コマンドレットを使用して更新プログラムをダウンロードする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

詳細については、「 [PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策と Defender ウイルス対策コマンドレットを管理する](use-powershell-cmdlets-microsoft-defender-antivirus.md) 」を参照してください。Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「Microsoft Defender ウイルス [対策と Defender ウイルス対策コマンドレット](/powershell/module/defender/index) を管理する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Windows Management Instruction (WMI) を使用して、Microsoft Defender ウイルス対策が存在しない場合に更新プログラムをダウンロードする

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

詳細については、「[WINDOWS DEFENDER WMIv2 API」を参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>クラウド配信の保護に基づいて、保護に対するアドホック変更を許可する

Microsoft Defender ウイルス対策では、クラウド配信の保護に基づいて保護を変更できます。 このような変更は、通常またはスケジュールされた保護更新プログラムの外部で発生する可能性があります。

クラウド配信保護を有効にした場合、Microsoft Defender ウイルス対策は、疑わしいファイルをWindows Defender クラウドに送信します。 クラウド サービスからファイルが悪意のあることが報告され、ファイルが最近の保護更新プログラムで検出された場合は、グループ ポリシーを使用して、その保護更新プログラムを自動的に受信するように Microsoft Defender ウイルス対策を構成できます。 その他の重要な保護更新プログラムも適用できます。

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>グループ ポリシーを使用して、クラウド配信の保護に基づいて最近の更新プログラムを自動的にダウンロードする

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** を使用して **、コンピューターの構成** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> **セキュリティ インテリジェンス 更新** に展開します。

5. **Microsoft MAPS へのレポートに基づいてリアルタイムのセキュリティ インテリジェンス更新プログラムを許可するを** ダブルクリックし、オプションを **[有効]** に設定します。 次に、[ **OK**] をクリックします。

6. **Microsoft MAPS に対する定義ベースのレポートを無効にし** 、オプションを **[有効]** に設定する通知を許可します。 次に、[ **OK**] をクリックします。

> [!NOTE]
> **定義ベースのレポートを無効にする通知を許可すると** 、Microsoft MAPS では、誤検知レポートが発生することがわかっている定義を無効にすることができます。 この関数を機能させるには、Microsoft MAPS に参加するようにコンピューターを構成する必要があります。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策を展開する](deploy-manage-report-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [保護更新プログラムをダウンロードして適用するタイミングを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
