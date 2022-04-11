---
title: 非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード
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
search.appverid:
- MET150
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスに展開して、Microsoft 365 エンドポイント データ損失防止サービスにオンボードします。
ms.openlocfilehash: 6bfb0f69198afbcc9d2949d583e151631cc7953b
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760627"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>非永続的仮想デスクトップ インフラストラクチャ デバイスをオンボードする

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

- 仮想デスクトップ インフラストラクチャ (VDI) デバイス

> [!WARNING]
> Microsoft 365 Windows Virtual Desktop のエンドポイント データ損失防止サポートでは、単一セッション シナリオがサポートされます。 Windows Virtual Desktop でのマルチセッション シナリオは現在サポートされていません。

## <a name="onboard-vdi-devices"></a>VDI デバイスをオンボードする

Microsoft 365では、非永続的仮想デスクトップ インフラストラクチャ (VDI) セッションのオンボードがサポートされます。

> [!NOTE]
> 非永続的 VDI セッションをオンボードするには、VDI デバイスが 1809 以上Windows 10されている必要があります。

VDI のオンボード時に、関連する課題が発生する可能性があります。 このシナリオの一般的な課題は次のとおりです。

- 短期間のセッションの即時早期オンボード。これは、実際のプロビジョニングの前にMicrosoft 365にオンボードする必要があります。
- 通常、デバイス名は新しいセッションに再利用されます。

VDI デバイスは、Microsoft 365 コンプライアンス センターに次のように表示できます。

- デバイスごとに 1 つのエントリ。
この場合、無人応答ファイルを使用するなど、セッションの作成時に *同じ* デバイス名を構成する必要があることに注意してください。
- デバイスごとに複数のエントリ (セッションごとに 1 つ)。

次の手順では、VDI デバイスのオンボードについて説明し、1 つまたは複数のエントリの手順を強調表示します。

> [!WARNING]
> リソース構成が低い環境では、VDI ブート手順によってデバイスのオンボード プロセスが遅くなる可能性があります。

1. [Microsoft コンプライアンス センター](https://compliance.microsoft.com)から VDI 構成パッケージ .zip ファイル (*DeviceCompliancePackage.zip*) を取得します。

2. ナビゲーション ウィンドウで、**設定** > **Device onboardingOnboarding を** > 選択します。

3. **[展開方法]** フィールドで、**非永続的エンドポイントの VDI オンボード スクリプトを選択します**。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. .zip ファイルから抽出された DeviceCompliancePackage フォルダーから、パス`C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`の下の`golden`イメージにファイルをコピーします。

6. デバイスごとに 1 つのエントリを実装していない場合は、DeviceComplianceOnboardingScript.cmd をコピーします。

7. デバイスごとに 1 つのエントリを実装する場合は、Onboard-NonPersistentMachine.ps1と DeviceComplianceOnboardingScript.cmd の両方をコピーします。

    > [!NOTE]
    > フォルダーが表示 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` されない場合は、非表示になっている可能性があります。 [**非表示のファイルとフォルダーを表示** する] オプションをエクスプローラーから選択する必要があります。

8. [ローカル グループ ポリシー エディター] ウィンドウを開き、**コンピューターの構成** > **Windows 設定** > **ScriptsStartup** >  に移動します。

   > [!NOTE]
   > ドメイン グループ ポリシーは、非永続的 VDI デバイスのオンボードにも使用できます。

9. 実装するメソッドに応じて、適切な手順に従います。

   **デバイスごとに 1 つのエントリの場合**

   **[PowerShell スクリプト**] タブを選択し、[**追加**] をクリックします (Windows エクスプローラーは、オンボード スクリプトを先にコピーしたパスで直接開きます)。 PowerShell スクリプトのオンボードに移動します `Onboard-NonPersistentMachine.ps1`。

   **デバイスごとに複数のエントリの場合**:

   [**スクリプト**] タブを選択し、[**追加**] をクリックします (Windows エクスプローラーは、オンボード スクリプトを先にコピーしたパスで直接開きます)。 オンボード bash スクリプトに移動します `DeviceComplianceOnboardingScript.cmd`。

10. ソリューションをテストします。
    1. 1 つのデバイスでプールを作成します。
    1. デバイスにログオンします。
    1. デバイスからログオフします。
    1. 別のユーザーと一緒にデバイスにログオンします。
    1. **デバイスごとに 1 つのエントリの場合**: Microsoft Defender セキュリティ センターで 1 つのエントリのみを確認します。
       **デバイスごとに複数のエントリの場合**: Microsoft Defender セキュリティ センターで複数のエントリを確認します。

11. ナビゲーション ウィンドウで [ **デバイス] の一覧** をクリックします。

12. デバイス名を入力して検索機能を使用し、検索の種類として **[デバイス** ] を選択します。

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新

ベスト プラクティスとして、オフライン サービス ツールを使用してゴールデン イメージにパッチを適用することをお勧めします。

たとえば、次のコマンドを使用して、イメージがオフラインのままの間に更新プログラムをインストールできます。

```DOS
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

DISM コマンドとオフライン サービスの詳細については、以下の記事を参照してください。

- [DISM を使用してWindowsイメージを変更する](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM イメージ管理Command-Lineオプション](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [オフライン Windows イメージ内のコンポーネント ストアのサイズを小さくする](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

オフライン サービスが非永続的 VDI 環境で実行可能なオプションでない場合は、一貫性とセンサーの正常性を確保するために次の手順を実行する必要があります。

1. オンライン サービスまたはパッチ適用用のゴールデン イメージを起動した後、オフボード スクリプトを実行して、Microsoft 365デバイス監視センサーをオフにします。 詳細については、「 [ローカル スクリプトを使用したオフボード デバイス](device-onboarding-script.md#offboard-devices-using-a-local-script)」を参照してください。

2. CMD ウィンドウで次のコマンドを実行して、センサーが停止していることを確認します。

   ```DOS
   sc query sense
   ```

3. 必要に応じてイメージをサービスします。

4. PsExec.exeを使用して次のコマンドを実行します (このコマンドは、起動後にセンサーが蓄積した可能性のあるサイバー フォルダーの内容をクリーンアップするためにダウンロード https://download.sysinternals.com/files/PSTools.zip) できます。

    ```DOS
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 通常と同じように、ゴールデン イメージを再シールします。

## <a name="related-topics"></a>関連項目

- [グループ ポリシーを使用してWindows 10デバイスとWindows 11 デバイスをオンボードする](device-onboarding-gp.md)
- [Microsoft Endpoint Configuration Managerを使用してWindows 10デバイスとWindows 11 デバイスをオンボードする](device-onboarding-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-mdm.md)
- [ローカル スクリプトを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-script.md)
- [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
