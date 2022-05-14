---
title: 古いエンドポイントに Microsoft Defender AV 保護の更新プログラムを適用する
description: しばらく更新されていないエンドポイントに対して更新プログラムを適用するタイミングと方法を定義します。
keywords: 更新、保護、最新ではない、古い、古い、キャッチアップ
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: c6d8eeb23312f7e4775aacfcadc0d040fc3f0394
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415906"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Microsoft Defender ウイルス対策の更新プログラムを管理し、古くなったエンドポイントをスキャンする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策では、エンドポイントが更新を回避できる期間や、更新とスキャン自体が必要になる前に見逃す可能性があるスキャンの数を定義できます。 これは、デバイスが企業または外部ネットワークに頻繁に接続されていない環境や、日常的に使用されていないデバイスで特に便利です。

たとえば、特定の PC を使用する従業員は 3 日間休暇中であり、その間は PC にログオンしません。

ユーザーが職場に戻り、PC にログオンすると、Microsoft Defender ウイルス対策直ちに最新の保護更新プログラムを確認してダウンロードし、スキャンを実行します。

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>しばらく更新されていないエンドポイントのキャッチアップ保護更新プログラムを設定する

指定した期間Microsoft Defender ウイルス対策保護更新プログラムをダウンロードしなかった場合は、次回のログオン時に最新の更新プログラムを自動的に確認してダウンロードするように設定できます。 これは、 [起動時に自動更新のダウンロードをグローバルに無効にしている場合に便利です](manage-event-based-updates-microsoft-defender-antivirus.md)。

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Configuration Managerを使用してキャッチアップ保護更新プログラムを構成する

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで **[資産とコンプライアンス**] をクリックし、ツリーを [**概要**\>] **Endpoint Protection** \> **[マルウェア対策ポリシー**] に展開します)

2. **[セキュリティ インテリジェンス更新プログラム**] セクションに移動し、次の設定を構成します。

    1. **2 つ以上の連続したスケジュールされた更新プログラムに対してクライアント コンピューターがオフラインの場合は、[セキュリティ インテリジェンス更新プログラムを強制** する] を **[はい**] に設定します。
    2. [**セキュリティ インテリジェンス更新プログラムのソースとしてConfiguration Managerが使用されている場合**. で、Configuration Managerによって配信される保護更新プログラムを最新でないと見なす時間を指定します。 これにより、定義された [フォールバック ソースの順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)に基づいて、次の更新場所が使用されます。

3. **[OK]** をクリックします。

4. [更新されたポリシーを通常どおりにデプロイ](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)します。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>グループ ポリシーを使用してキャッチアップ更新機能を有効にして構成する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを右クリックし、[編集] をクリック **します**。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを展開して **、シグネチャ更新プログラム> Microsoft Defender ウイルス対策 >コンポーネントをWindowsします**。

5. キャッチ **アップ セキュリティ インテリジェンスの更新が必要な日数を定義する設定を** ダブルクリックし、オプションを **[有効]** に設定します。 Microsoft Defender AV で最新の保護更新プログラムを確認してダウンロードする日数を入力します。

6. **[OK]** をクリックします。

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>PowerShell コマンドレットを使用してキャッチアップ保護更新プログラムを構成する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

[Microsoft Defender ウイルス対策で PowerShell を使用する](use-powershell-cmdlets-microsoft-defender-antivirus.md)方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Windows管理命令 (WMI) を使用してキャッチアップ保護更新プログラムを構成する

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
SignatureUpdateCatchupInterval
```

詳細と許可されるパラメーターについては、次を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>保護が最新でないと報告されるまでの日数を設定する

Microsoft Defender ウイルス対策保護が古いか古いものと見なされるまでの日数を指定することもできます。 指定した日数が経過すると、クライアントは自身を最新の状態として報告し、PC のユーザーにエラーを表示します。 また、WSUS または Microsoft Update を最初のソースとして設定した後に MMPC をセカンダリ ソースとして使用する場合など、(定義済みの[フォールバック ソース順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)に基づいて) 他のソースから更新プログラムをダウンロードしようとするMicrosoft Defender ウイルス対策が発生する可能性もあります。

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>グループ ポリシーを使用して、保護が最新でないと見なされるまでの日数を指定する

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを展開して **、シグネチャ更新プログラム> Microsoft Defender ウイルス対策 >コンポーネントをWindows** し、次の設定を構成します。

    1. **スパイウェア定義が古いと見なされるまでの日数** をダブルクリックし、オプションを **[有効]** に設定します。 Microsoft Defender AV でスパイウェアセキュリティ インテリジェンスを最新の状態と見なす日数を入力します。

    2. **[OK]** をクリックします。

    3. [ **ウイルス定義が古いと見なされるまでの日数を定義** する] をダブルクリックし、オプションを **[有効]** に設定します。 Microsoft Defender AV がウイルス セキュリティ インテリジェンスを最新の状態と見なす日数を入力します。

    4. **[OK]** をクリックします。

## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>しばらくスキャンされていないエンドポイントのキャッチアップ スキャンを設定する

Microsoft Defender ウイルス対策がスキャンを強制的に実行する前に見逃すことができる連続したスケジュールされたスキャンの数を設定できます。

この機能を有効にするプロセスは次のとおりです。

1. 1 つ以上のスケジュールされたスキャンを設定します (スキャンの [スケジュール](scheduled-catch-up-scans-microsoft-defender-antivirus.md) に関するトピックを参照)。
2. キャッチアップ スキャン機能を有効にします。
3. キャッチアップ スキャンが発生する前にスキップできるスキャンの数を定義します。

この機能は、完全スキャンとクイック スキャンの両方に対して有効にすることができます。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>グループ ポリシーを使用して、キャッチアップ スキャン機能を有効にして構成する

1. スケジュールされたスキャンが少なくとも 1 つ設定されていることを確認します。

2. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

3. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

4. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

5. ツリーを展開して **、スキャン> Microsoft Defender ウイルス対策 >コンポーネントをWindows** し、次の設定を構成します。

    1. スケジュールされたクイック スキャンを設定している場合は、[ **キャッチアップクイック スキャンを有効にする** ] 設定をダブルクリックし、オプションを **[有効]** に設定します。
    2. スケジュールされたフル スキャンを設定している場合は、[ **キャッチアップフル スキャンを有効にする** ] 設定をダブルクリックし、オプションを **[有効]** に設定します。 **[OK]** をクリックします。
    3. **[キャッチアップ スキャンが強制された日数を定義** する] 設定をダブルクリックし、オプションを **[有効]** に設定します。
    4. ユーザーが次に PC にログオンしたときにスキャンが自動的に実行される前に見逃すことができるスキャンの数を入力します。 実行されるスキャンの種類は、**スケジュールされたスキャンに使用するスキャンの種類を指定する (「**[スキャンのスケジュール](scheduled-catch-up-scans-microsoft-defender-antivirus.md)」トピックを参照) によって決まります。 **[OK]** をクリックします。

> [!NOTE]
> グループ ポリシー設定タイトルは、日数を参照します。 ただし、この設定は、キャッチアップ スキャンが実行されるまでのスキャン数 (日数ではなく) に適用されます。

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>PowerShell コマンドレットを使用してキャッチアップ スキャンを構成する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

[Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策](use-powershell-cmdlets-microsoft-defender-antivirus.md)および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を管理する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Windows管理命令 (WMI) を使用してキャッチアップ スキャンを構成する

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

詳細と許可されるパラメーターについては、次を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Configuration Managerを使用してキャッチアップ スキャンを構成する

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで **[資産とコンプライアンス**] をクリックし、ツリーを [**概要**\>] **Endpoint Protection** \> **[マルウェア対策ポリシー**] に展開します)

2. **[スケジュールされたスキャン**] セクションに移動し **、クライアント コンピューターがオフラインの場合は、選択したスキャンの種類のスキャンを強制** します。[**はい**] に移動します。

3. **[OK]** をクリックします。

4. [更新されたポリシーを通常どおりにデプロイ](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策を展開する](deploy-manage-report-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [保護更新プログラムをダウンロードして適用するタイミングを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
