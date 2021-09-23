---
title: 特定のMicrosoft Defender ウイルス対策後に更新プログラムを適用する
description: スタートアップ後Microsoft Defender ウイルス対策クラウド配信の検出レポートの受信後にセキュリティ インテリジェンス更新プログラムを適用する方法を管理します。
keywords: 更新、保護、強制的な更新、イベント、スタートアップ、最新のチェック、通知
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 3edca602d9e49d8ddc67da0e740c862364b0d6b4
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491351"
---
# <a name="manage-event-based-forced-updates"></a>イベントベースの強制更新プログラムを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策を使用すると、起動時やクラウド配信の保護サービスから特定のレポートを受信した後など、特定のイベントの後に更新プログラムが発生する必要があるかどうかを判断できます。

## <a name="check-for-protection-updates-before-running-a-scan"></a>スキャンを実行する前に保護更新プログラムを確認する

スケジュールされたスキャンをMicrosoft Endpoint Configuration Manager前に、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、WMI を使用して、Microsoft Defender ウイルス対策 に強制的に保護更新プログラムをチェックしてダウンロードすることができます。

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Configuration Manager を使用して、スキャンを実行する前に保護更新プログラムを確認する

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーションウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを[概要] Endpoint Protection マルウェア対策ポリシー \>  \> ) に展開します。

2. [スケジュールされたスキャン **] セクションに移動** し、スキャンを実行する前に最新のセキュリティ インテリジェンス更新プログラムのチェックを [は **い** ] に **設定します**。

3. [**OK**] をクリックします。

4. [更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>グループ ポリシーを使用して、スキャンを実行する前に保護更新プログラムを確認する

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

4. ツリーを展開して、[**スキャン] WindowsコンポーネントMicrosoft Defender ウイルス対策** \>  \> **展開します**。

5. [スケジュールされたスキャン **を実行する** 前に最新のウイルスとスパイウェアの定義を確認する] をダブルクリックし、オプションを [有効] に **設定します**。

6. [**OK**] をクリックします。

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>PowerShell コマンドレットを使用して、スキャンを実行する前に保護更新プログラムを確認する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/index)」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>スキャンWindows前に保護更新プログラムを確認するには、WMI (管理命令) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
CheckForSignaturesBeforeRunningScan
```

詳細については[、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="check-for-protection-updates-on-startup"></a>起動時に保護更新プログラムを確認する

グループ ポリシーを使用して、コンピューターのMicrosoft Defender ウイルス対策保護更新プログラムを強制的に確認してダウンロードできます。

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

4. ツリーを展開して、**セキュリティ Windows更新** \> **Microsoft Defender ウイルス対策** \> **コンポーネントを展開します**。

5. [起動時に **最新のウイルス** とスパイウェアの定義を確認する] をダブルクリックし、オプションを [有効] に **設定します**。

6. [**OK**] をクリックします。

また、グループ ポリシー、PowerShell、または WMI を使用して、実行中Microsoft Defender ウイルス対策起動時に更新プログラムを確認するサーバーを構成できます。

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>グループ ポリシーを使用して、ユーザーが存在Microsoft Defender ウイルス対策更新プログラムをダウンロードする

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターを使用して、[** コンピューターの構成] **に移動します**。

3. [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

4. ツリーを展開して、**セキュリティ Windows更新** \> **Microsoft Defender ウイルス対策** \> **コンポーネントを展開します**。

5. [起動時にセキュリティ **インテリジェンス更新プログラムを開始** する] をダブルクリックし、オプションを [有効] に **設定します**。

6. [**OK**] をクリックします。

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>PowerShell コマンドレットを使用して、ユーザーが存在しないMicrosoft Defender ウイルス対策更新プログラムをダウンロードする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して powerShell コマンドレットを使用して、Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/index)コマンドレットを管理する」を Microsoft Defender ウイルス対策参照してください。

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>[Windows管理命令 (WMI) を使用して、インストールされていないMicrosoft Defender ウイルス対策更新プログラムをダウンロードする

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

詳細については[、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>クラウドによる保護に基づく保護に対するアドホックな変更を許可する

Microsoft Defender AV は、クラウドによる保護に基づいて保護を変更できます。 このような変更は、通常またはスケジュールされた保護更新プログラムの外部で行われる可能性があります。

クラウド配信保護を有効にしている場合、Microsoft Defender AV は疑わしいファイルをクラウドに送信Windows Defenderします。 クラウド サービスがファイルが悪意のあると報告し、最近の保護更新プログラムでファイルが検出された場合は、グループ ポリシーを使用して Microsoft Defender AV を構成して、その保護更新プログラムを自動的に受信できます。 その他の重要な保護更新プログラムも適用できます。

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>グループ ポリシーを使用して、クラウド配信の保護に基づいて最新の更新プログラムを自動的にダウンロードする

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

4. ツリーを展開して、**セキュリティ Windows更新** \> **Microsoft Defender ウイルス対策** \> **コンポーネントを展開します**。

5. [Microsoft **MAPS へのレポートに基づいて** リアルタイムのセキュリティ インテリジェンス更新を許可する] をダブルクリックし、オプションを [有効] に **設定します**。 次に、[ **OK**] をクリックします。

6. **Microsoft MAPS への定義ベースのレポートを** 無効にし、オプションを [有効] に設定する通知を **許可します**。 次に、[ **OK**] をクリックします。

> [!NOTE]
> **定義ベースのレポートを無効にする通知を許可すると** 、Microsoft MAPS は誤検知レポートを引き起こすと知られている定義を無効にできます。 この関数を動作するには、Microsoft MAPS に参加するコンピューターを構成する必要があります。

## <a name="see-also"></a>関連項目

- [展開Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)
- [更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)