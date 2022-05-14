---
title: Microsoft Defender ウイルス対策保護の更新をスケジュールする
description: 保護更新プログラムをダウンロードする必要がある日、時刻、間隔をスケジュールする
keywords: 更新プログラム、セキュリティ ベースライン、更新のスケジュール
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 5ffa9d623b89bc19c7c3ec8817f2df6bc174384b
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419838"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>保護更新プログラムをダウンロードして適用するスケジュールを管理する

> [!IMPORTANT]
> 2022 年 3 月の Microsoft Defender エンジン更新プログラム (**1.1.19100.5**) を適用したお客様は、高いリソース使用率 (CPU またはメモリ) が発生した可能性があります。 Microsoft は、以前のバージョンで導入されたバグを解決する更新プログラム (**1.1.19200.5**) をリリースしました。 お客様は、ウイルス対策エンジン (**1.1.19200.5**) のこの新しいエンジン ビルドに更新することをお勧めします。 パフォーマンスの問題が完全に修正されるようにするには、更新プログラムを適用した後にマシンを再起動することをお勧めします。 詳細については、「 [月次プラットフォームとエンジンのバージョン](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)」を参照してください。

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策では、更新プログラムを検索してダウンロードするタイミングを決定できます。

エンドポイントの更新は、次の方法でスケジュールできます。

- 保護更新プログラムを確認する曜日を指定する
- 保護更新プログラムを確認する間隔を指定する
- 保護更新プログラムを確認する時間を指定する

また、各エンドポイントが保護更新プログラムをチェックしてダウンロードする時間をランダム化することもできます。 詳細については、 [スキャンのスケジュール](scheduled-catch-up-scans-microsoft-defender-antivirus.md) に関するトピックを参照してください。

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Configuration Managerを使用して保護更新プログラムをスケジュールする

1. Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで **[資産とコンプライアンス**] をクリックし、ツリーを [**概要**\>] **Endpoint Protection** \> **[マルウェア対策ポリシー**] に展開します)

2. **[セキュリティ インテリジェンスの更新プログラム] セクションに** 移動します。

3. 特定の時刻に更新プログラムを確認してダウンロードするには:
      1. **特定の間隔でセキュリティ インテリジェンス更新プログラムEndpoint Protectionチェックを** 設定します。.. **を 0** に設定します。
      2. **毎日のセキュリティ インテリジェンス更新プログラムEndpoint Protection** チェックを、更新プログラムを確認する必要がある時刻に設定します。
      3
4. 継続的な間隔で更新プログラムを確認してダウンロードするには、**特定の間隔でセキュリティ インテリジェンス更新プログラムをEndpoint Protectionチェック** を設定します。更新プログラムの間に発生する必要がある時間数に設定します。

5. [更新されたポリシーを通常どおりにデプロイ](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)します。

## <a name="use-group-policy-to-schedule-protection-updates"></a>グループ ポリシーを使用して保護更新プログラムをスケジュールする

> [!IMPORTANT]
> 既定では、"SignatureScheduleDay" は "8" に設定され、"SignatureUpdateInterval" は "0" に設定されているため、Microsoft Defender ウイルス対策は保護更新プログラムをスケジュールしません。
これらの設定を有効にすると、その既定値がオーバーライドされます。

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. ツリーを展開して **、シグネチャ インテリジェンス更新プログラム** Microsoft Defender ウイルス対策 **コンポーネント** \> **をWindows**\>し、次の設定を構成します。

    1. **[セキュリティ インテリジェンス更新プログラムを確認する曜日を指定する**] 設定をダブルクリックし、オプションを **[有効]** に設定します。 更新プログラムを確認する曜日を入力します。 **[OK]** をクリックします。
    2. **[セキュリティ インテリジェンス更新プログラムを確認する間隔を指定する**] 設定をダブルクリックし、オプションを **[有効]** に設定します。 更新までの時間数を入力します。 **[OK]** をクリックします。
    3. **[セキュリティ インテリジェンス更新プログラムを確認する時間を指定する**] 設定をダブルクリックし、オプションを **[有効]** に設定します。 更新プログラムを確認する時間を入力します。 時刻は、エンドポイントのローカル時刻に基づいています。 **[OK]** をクリックします。

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>PowerShell コマンドレットを使用して保護更新プログラムをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

[Microsoft Defender ウイルス対策で PowerShell を使用する](use-powershell-cmdlets-microsoft-defender-antivirus.md)方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Windows管理命令 (WMI) を使用して保護更新プログラムをスケジュールする

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

詳細と許可されるパラメーターについては、次を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

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
- [最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
