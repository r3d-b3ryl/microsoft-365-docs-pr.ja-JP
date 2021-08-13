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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスに展開して、エンドポイント データ損失防止サービスMicrosoft 365オンボーディングします。
ms.openlocfilehash: d86046f474ce0afe3a21354bd36f9ed433b627384aec314f129702bc43480b4d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53807986"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>非永続的な仮想デスクトップ インフラストラクチャ デバイスのオンボード

**適用対象:**
- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)

- 仮想デスクトップ インフラストラクチャ (VDI) デバイス

> [!WARNING]
> Microsoft 365仮想デスクトップのエンドポイント データ損失防止Windowsは、単一のセッション シナリオをサポートします。 仮想デスクトップ上の複数Windowsシナリオは現在サポートされていません。

## <a name="onboard-vdi-devices"></a>オンボード VDI デバイス

Microsoft 365エンドポイント データ損失防止は、永続的でない仮想デスクトップ インフラストラクチャ (VDI) セッションオンボーディングをサポートします。

> [!NOTE]
> 永続的でない VDI セッションをオンボードするには、VDI デバイスが 1809 以上Windows 10必要があります。

VDIs をオンボーディングする際に関連する課題が生じ得る場合があります。 このシナリオの一般的な課題は次のとおりです。

- 短命セッションの早期オンボーディングは、実際のプロビジョニングの前にMicrosoft 365エンドポイント のデータ損失防止にオンボードする必要があります。
- 通常、デバイス名は新しいセッションに再利用されます。

VDI デバイスは、次のいずれかのMicrosoft 365コンプライアンス センターに表示できます。

- デバイスごとに 1 つのエントリ。
この場合、セッションの作成時に、無人応答ファイルを使用する場合など、同じデバイス名を構成する必要があります。
- デバイスごとに複数のエントリ (セッションごとに 1 つ)。

次の手順では、VDI デバイスのオンボードについて説明し、単一エントリと複数エントリの手順を強調表示します。

> [!WARNING]
> リソース構成が低い環境では、VDI ブート手順によってエンドポイント のデータ損失防止オンボーディングMicrosoft 365遅くなる可能性があります。

1. サービス オンボーディング ウィザードから.zipした VDI *構成パッケージ*(DeviceCompliancePackage.zip) を開きます。

2. ナビゲーション ウィンドウで、[デバイスオンボーディングオンボーディング]**設定**  >  **を**  >  **選択します**。

3. [展開方法 **] フィールドで** 、[永続的でないエンドポイントの VDI オンボーディング **スクリプト] を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

5. パスの下のイメージに、.zipから抽出された DeviceCompliancePackage フォルダーからファイル `golden/master` をコピーします `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。

6. デバイスごとに 1 つのエントリを実装していない場合は、DeviceComplianceOnboardingScript.cmd をコピーします。

7. デバイスごとに 1 つのエントリを実装する場合は、デバイスと DeviceComplianceOnboardingScript.cmd の両方Onboard-NonPersistentMachine.ps1コピーします。

    > [!NOTE]
    > フォルダーが表示しない場合 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` は、非表示になる可能性があります。 エクスプローラーから [非表示のファイル **とフォルダーを** 表示する] オプションを選択する必要があります。

8. [ローカル グループ ポリシー エディター] ウィンドウを開き、[コンピューター **の構成**] Windows 設定  >    >  **に**  >  **移動します**。

   > [!NOTE]
   > ドメイン グループ ポリシーは、永続的でない VDI デバイスのオンボーディングにも使用できます。

9. 実装するメソッドに応じて、適切な手順に従います。

   **デバイスごとに 1 つのエントリの場合**

   **[PowerShell スクリプト]** タブを選択し、[追加] **(Windows** オンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます) をクリックします。 PowerShell スクリプトのオンボーディングに移動します `Onboard-NonPersistentMachine.ps1` 。

   **各デバイスの複数のエントリの場合**:

   [スクリプト **] タブを** 選択し、[追加]**をクリック** します (Windows、以前にオンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます)。 オンボーディング bash スクリプトに移動します `DeviceComplianceOnboardingScript.cmd` 。

10. ソリューションをテストします。
    1. 1 つのデバイスでプールを作成します。
    1. デバイスへのログオン。
    1. デバイスからのログオフ。
    1. 別のユーザーと一緒にデバイスにログオンします。
    1. **デバイスごとに 1 つのエントリの場合**: デバイス内の 1 つのエントリMicrosoft Defender セキュリティ センター。
       **デバイスごとに複数のエントリについて**: デバイス内の複数のエントリをMicrosoft Defender セキュリティ センター。

11. [ナビゲーション **] ウィンドウの [** デバイス] リストをクリックします。

12. デバイス名を入力して検索機能を使用し、[検索の種類として **デバイス]** を選択します。

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新

ベスト プラクティスとして、オフライン サービス ツールを使用してゴールデン/マスター イメージにパッチを適用することをお勧めします。

たとえば、次のコマンドを使用して、イメージがオフラインのままで更新プログラムをインストールできます。

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

DISM コマンドとオフライン サービスの詳細については、以下の記事を参照してください。

- [DISM を使用Windowsイメージを変更する](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM イメージ管理Command-Lineオプション](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [オフライン イメージ内のコンポーネント ストアのサイズを小Windowsする](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

非永続的な VDI 環境でオフライン サービスが実行可能なオプションでない場合は、一貫性とセンサーの正常性を確保するために次の手順を実行する必要があります。

1. オンライン サービスまたは修正プログラムのマスター イメージを起動した後、オフボード スクリプトを実行して、エンドポイント データ損失防止センサー Microsoft 365オフにします。 詳細については、「ローカル スクリプトを [使用したオフボード デバイス」を参照してください](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。

2. CMD ウィンドウで以下のコマンドを実行して、センサーが停止した状態を確認します。

   ```console
   sc query sense
   ```

3. 必要に応じてイメージをサービスします。

4. 次のコマンドを PsExec.exe を使用して実行します (起動後にセンサーが蓄積した可能性があるサイバー フォルダーの内容をクリーンアップするためにダウンロード https://download.sysinternals.com/files/PSTools.zip) できます。

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 通常と同じ方法で、ゴールデン/マスター イメージを再シールします。

## <a name="related-topics"></a>関連トピック

- [グループ ポリシー Windows 10デバイスのオンボード](dlp-configure-endpoints-gp.md)
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
