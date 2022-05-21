---
title: Microsoft Defender ウイルス対策保護更新プログラムを古いエンドポイントに適用する
description: しばらく更新していないエンドポイントに更新プログラムを適用するタイミングと方法を定義します。
keywords: 更新, 保護, 古い, 古い, キャッチアップ
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: fcf13258b8012bfd2a5875b52b8d844040aee73e
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623485"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Microsoft Defender ウイルス対策の更新プログラムを管理し、古くなったエンドポイントをスキャンする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**

- Windows

Microsoft Defender ウイルス対策を使用すると、セキュリティ チームは、エンドポイントが更新を回避できる期間や、更新プログラムを受信してスキャンを実行する前に見逃す可能性があるスキャンの数を定義できます。 この機能は、デバイスが企業や外部ネットワークに頻繁に接続されていない環境や、日常的に使用されていないデバイスの場合に特に便利です。

たとえば、特定のコンピューターを使用する従業員は、3 日間仕事を休み、その間はコンピューターにサインオンしません。 従業員が職場に戻り、コンピューターにサインインすると、Microsoft Defender ウイルス対策直ちに最新の保護更新プログラムを確認してダウンロードし、スキャンを実行します。

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>しばらく更新されていないエンドポイントのキャッチアップ保護更新プログラムを設定する

Microsoft Defender ウイルス対策が指定した期間保護更新プログラムをダウンロードしなかった場合は、ユーザーが次回エンドポイントにサインインするときに、最新の更新プログラムを自動的に確認してダウンロードするように設定できます。 この構成は、 [起動時に自動更新のダウンロードをグローバルに無効にしている場合に便利です](manage-event-based-updates-microsoft-defender-antivirus.md)。

次のいずれかの方法を使用して、キャッチアップ保護の更新プログラムを設定できます。

- [Configuration Manager](#use-configuration-manager-to-configure-catch-up-protection-updates)
- [グループ ポリシー](#use-group-policy-to-enable-and-configure-the-catch-up-update-feature)
- [PowerShell コマンドレット](#use-powershell-cmdlets-to-configure-catch-up-protection-updates)
- [Windows管理命令 (WMI)](#use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Configuration Managerを使用してキャッチアップ保護更新プログラムを構成する

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで **[資産とコンプライアンス**] を選択し、ツリーを [**概要**\>] **Endpoint Protection** \> **[マルウェア対策ポリシー**] に展開します)

2. **[セキュリティ インテリジェンス更新プログラム**] セクションに移動し、次の設定を構成します。

    - **2 つ以上の連続したスケジュールされた更新プログラムに対してクライアント コンピューターがオフラインの場合は、[セキュリティ インテリジェンス更新プログラムを強制** する] を **[はい**] に設定します。
    - [**セキュリティ インテリジェンス更新プログラムのソースとしてConfiguration Managerが使用されている場合**. で、Configuration Managerによって配信される保護更新プログラムが古いと見なされる時間を指定します。 この設定により、定義された [フォールバック ソースの順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)に基づいて、次の更新場所が使用されます。

3. **[OK]** をクリックします。

4. [更新されたポリシーを通常どおりにデプロイ](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)します。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>グループ ポリシーを使用してキャッチアップ更新機能を有効にして構成する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを右クリックし、[**編集]** を選択します。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. [ **ポリシー** ]、[ **管理用テンプレート]** の順に選択します。

4. ツリーを展開して **、シグネチャ更新プログラム> Microsoft Defender ウイルス対策 >コンポーネントをWindowsします**。

5. キャッチ **アップ セキュリティ インテリジェンスの更新が必要な日数を定義する設定を** ダブルクリックし、オプションを **[有効]** に設定します。 Microsoft Defender ウイルス対策最新の保護更新プログラムを確認してダウンロードする日数を入力します。

6. **[OK]** をクリックします。

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>PowerShell コマンドレットを使用してキャッチアップ保護更新プログラムを構成する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、次の記事を参照してください。

- [PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成する](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender ウイルス対策コマンドレット](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Windows管理命令 (WMI) を使用してキャッチアップ保護更新プログラムを構成する

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
SignatureUpdateCatchupInterval
```

詳細と許可されるパラメーターについては、次の記事を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>保護が最新でないと報告されるまでの日数を設定する

Microsoft Defender ウイルス対策保護が古いか古いものと見なされるまでの日数を指定することもできます。 指定した日数が経過すると、クライアント自体が "古い" と報告され、エンドポイント ユーザーにエラーが表示されます。 エンドポイントが古いと見なされると、Microsoft Defender ウイルス対策が (定義済みの[フォールバック ソースの順序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)に基づいて) 他のソースから更新プログラムをダウンロードしようとする可能性があります。

グループ ポリシーを使用して、エンドポイント保護が古いと見なされる日数を指定できます。

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>グループ ポリシーを使用して、保護が古いと見なされるまでの日数を指定する

1. グループ ポリシー管理マシンで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. [ **ポリシー** ]、[ **管理用テンプレート]** の順に選択します。

4. ツリーを展開して **、シグネチャ更新プログラム> Microsoft Defender ウイルス対策 >コンポーネントをWindows** し、次の設定を構成します。

    1. **スパイウェア定義が古いと見なされるまでの日数** をダブルクリックし、オプションを **[有効]** に設定します。 スパイウェア セキュリティ インテリジェンスを最新の状態と見なすMicrosoft Defender ウイルス対策日数を入力します。

    2. **[OK]** をクリックします。

    3. [ **ウイルス定義が古いと見なされるまでの日数を定義** する] をダブルクリックし、オプションを **[有効]** に設定します。 ウイルス セキュリティ インテリジェンスを最新の状態と見なすMicrosoft Defender ウイルス対策後の日数を入力します。

    4. **[OK]** をクリックします。

## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>しばらくスキャンされていないエンドポイントのキャッチアップ スキャンを設定する

Microsoft Defender ウイルス対策がスキャンを強制的に実行する前に見逃すことができる連続したスケジュールされたスキャンの数を設定できます。

この機能を有効にするプロセスは次のとおりです。

1. 少なくとも 1 つのスケジュールされたスキャンを設定します ( [スケジュールされたスキャン](scheduled-catch-up-scans-microsoft-defender-antivirus.md) に関する記事を参照)。

2. キャッチアップ スキャン機能を有効にします。

3. キャッチアップ スキャンが発生する前にスキップできるスキャンの数を定義します。

この機能は、完全スキャンとクイック スキャンの両方に対して有効にすることができます。 

> [!TIP]
> ほとんどの場合、クイック スキャンを使用することをお勧めします。 詳細については、「 [クイック スキャン、フル スキャン、カスタム スキャン](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)」を参照してください。 

次のいずれかの方法を使用して、キャッチアップ スキャンを設定できます。

- [グループ ポリシー](#use-group-policy-to-enable-and-configure-the-catch-up-scan-feature)
- [PowerShell コマンドレットを使用してキャッチアップ スキャンを構成する](#use-powershell-cmdlets-to-configure-catch-up-scans)
- [Windows管理命令 (WMI)](#use-windows-management-instruction-wmi-to-configure-catch-up-scans)
- [Configuration Manager](#use-configuration-manager-to-configure-catch-up-scans)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>グループ ポリシーを使用して、キャッチアップ スキャン機能を有効にして構成する

1. スケジュールされたスキャンが少なくとも 1 つ設定されていることを確認します。

2. グループ ポリシー管理マシンで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

3. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

4. [ **ポリシー** ]、[ **管理用テンプレート]** の順に選択します。

5. ツリーを展開して **、スキャン> Microsoft Defender ウイルス対策 >コンポーネントをWindows** し、次の設定を構成します。

    - スケジュールされたクイック スキャンを設定している場合は、[ **キャッチアップクイック スキャンを有効にする** ] 設定をダブルクリックし、オプションを **[有効]** に設定します。
    - スケジュールされたフル スキャンを設定している場合は、[ **キャッチアップフル スキャンを有効にする** ] 設定をダブルクリックし、オプションを **[有効]** に設定します。 **[OK]** をクリックします。
    - **[キャッチアップ スキャンが強制された日数を定義** する] 設定をダブルクリックし、オプションを **[有効]** に設定します。
    - ユーザーが次にエンドポイントにサインインしたときに、スキャンが自動的に実行される前に見逃すことができるスキャンの数を入力します。 実行されるスキャンの種類は、 **スケジュールされたスキャンに使用するスキャンの種類を指定する (スキャン** の [スケジュール](scheduled-catch-up-scans-microsoft-defender-antivirus.md) に関する記事を参照) によって決まります。 **[OK]** をクリックします。

> [!NOTE]
> グループ ポリシー設定タイトルは、日数を参照します。 ただし、この設定は、キャッチアップ スキャンが実行されるまでのスキャン数 (日数ではなく) に適用されます。

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>PowerShell コマンドレットを使用してキャッチアップ スキャンを構成する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、次の記事を参照してください。

- [PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md) 
- [Defender ウイルス対策コマンドレット](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Windows管理命令 (WMI) を使用してキャッチアップ スキャンを構成する

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

詳細と許可されるパラメーターについては、次の記事を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Configuration Managerを使用してキャッチアップ スキャンを構成する

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで **[資産とコンプライアンス**] を選択し、ツリーを [**概要**\>] **Endpoint Protection** \> **[マルウェア対策ポリシー**] に展開します)

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
