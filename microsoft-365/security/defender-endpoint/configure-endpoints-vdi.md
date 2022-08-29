---
title: 非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスにデプロイして、サービスにオンボードMicrosoft Defender for Endpoint。
keywords: 仮想デスクトップ インフラストラクチャ (VDI) デバイス、VDI、デバイス管理の構成、Microsoft Defender for Endpointの構成、エンドポイント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 04/15/2022
ms.technology: mde
ms.openlocfilehash: 8bf3dda061b582adb7b21029022e61bc890aeec7
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441642"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>Microsoft 365 Defenderで非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスをオンボードする

仮想デスクトップ インフラストラクチャ (VDI) は、エンド ユーザーがほぼすべてのデバイス (パーソナル コンピューター、スマートフォン、タブレットなど) からエンタープライズ仮想デスクトップ インスタンスにアクセスできるようにする IT インフラストラクチャの概念であり、組織がユーザーに物理マシンを提供する必要がなくなります。 VDI デバイスを使用すると、IT 部門が物理エンドポイントの管理、修復、交換を行わなくなったため、コストが削減されます。 承認されたユーザーは、セキュリティで保護されたデスクトップ クライアントまたはブラウザーを使用して、承認された任意のデバイスから同じ会社のサーバー、ファイル、アプリ、サービスにアクセスできます。

IT 環境内の他のシステムと同様に、高度な脅威や攻撃から保護するためのエンドポイント検出と応答 (EDR) とウイルス対策ソリューションも用意されている必要があります。


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 仮想デスクトップ インフラストラクチャ (VDI) デバイス
- Windows 10、Windows 11、Windows Server 2019、Windows Server 2022、Windows Server 2008R2/2012R2/2016


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)

 > [!NOTE]
  > **永続的 VDI** - 永続的な VDI マシンをMicrosoft Defender for Endpointにオンボードする方法は、デスクトップやノート PC などの物理マシンをオンボードする場合と同じように処理されます。 グループ ポリシー、Microsoft エンドポイント マネージャー、およびその他の方法を使用して、永続的なマシンをオンボードできます。 Microsoft 365 Defender ポータルで (https://security.microsoft.com)オンボーディングの下で、優先するオンボード方法を選択し、その種類の指示に従います。 詳細については、「 [Windows クライアントのオンボード」](onboard-windows-client.md)を参照してください。

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード

Defender for Endpoint では、非永続的な VDI セッションオンボードがサポートされます。

VDI インスタンスのオンボード時に、関連する課題が発生する可能性があります。 このシナリオの一般的な課題は次のとおりです。

- 短時間のセッションの即時早期オンボード。これは、実際のプロビジョニングの前に Defender for Endpoint にオンボードする必要があります。
- 通常、デバイス名は新しいセッションに再利用されます。

VDI 環境では、VDI インスタンスの有効期間が短い場合があります。 VDI デバイスは、次のいずれかの方法で Defender for Endpoint ポータルに表示できます。


- VDI インスタンスごとに 1 つのポータル エントリ。 VDI インスタンスが既にMicrosoft Defender for Endpointにオンボードされていて、ある時点で削除された後、同じホスト名で再作成された場合、この VDI インスタンスを表す新しいオブジェクトはポータルに作成されません。 

  > [!NOTE]
  > この場合、無人応答ファイルを使用するなど、セッションの作成時に *同じ* デバイス名を構成する必要があります。

- デバイスごとに複数のエントリ (VDI インスタンスごとに 1 つ)。

次の手順では、VDI デバイスのオンボードについて説明し、1 つまたは複数のエントリの手順を強調表示します。

> [!WARNING]
> リソース構成が低い環境では、VDI ブート手順によって Defender for Endpoint センサーのオンボードが遅くなる可能性があります。

### <a name="onboarding-steps"></a>オンボード手順

> [!NOTE]
> この機能を機能させるには、「[Windows サーバーのオンボード](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2012-r2-and-windows-server-2016)」の手順を使用して、インストール パッケージを最初に適用して、Windows Server 2016と Windows Server 2012 R2 を準備する必要があります。

1.  サービス オンボード ウィザードからダウンロードした VDI 構成パッケージ .zip ファイル (*WindowsDefenderATPOnboardingPackage.zip*) を開きます。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>からパッケージを取得することもできます。

    1. ナビゲーション ウィンドウで、[設定 **エンドポイント** > **デバイス管理** > **オンボード****]** >  を選択します。

    1. オペレーティング システムを選択します。

    1.  **[展開方法]** フィールドで、**非永続的エンドポイントの VDI オンボード スクリプトを選択します**。

    1. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. .zip ファイルから抽出された WindowsDefenderATPOnboardingPackage フォルダーから、パス `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`の下のゴールデン/マスター イメージにファイルをコピーします。
    1. デバイスごとに複数のエントリ (セッションごとに 1 つずつ) を実装する場合は、WindowsDefenderATPOnboardingScript.cmd をコピーします。
    2. デバイスごとに 1 つのエントリを実装する場合は、Onboard-NonPersistentMachine.ps1と WindowsDefenderATPOnboardingScript.cmd の両方をコピーします。

    > [!NOTE]
    > フォルダーが表示 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` されない場合は、非表示になっている可能性があります。 [**非表示のファイルとフォルダーを表示** する] オプションをエクスプローラーから選択する必要があります。

3. [ローカル グループ ポリシー エディター] ウィンドウを開き、[**コンピューター構成** **Windows 設定****スクリプト** \> **のスタートアップ**] \> \> に移動します。

   > [!NOTE]
   > ドメイン グループ ポリシーは、非永続的 VDI デバイスのオンボードにも使用できます。

4. 実装するメソッドに応じて、適切な手順に従います。
    - デバイスごとに 1 つのエントリの場合:

         **[PowerShell スクリプト**] タブを選択し、[**追加**] をクリックします (Windows エクスプローラーは、前にオンボード スクリプトをコピーしたパスで直接開きます)。 PowerShell スクリプトのオンボードに移動します `Onboard-NonPersistentMachine.ps1`。 自動的にトリガーされるため、他のファイルを指定する必要はありません。

    - デバイスごとに複数のエントリの場合:

         [ **スクリプト** ] タブを選択し、[ **追加** ] をクリックします (Windows エクスプローラーは、前にオンボード スクリプトをコピーしたパスで直接開きます)。 オンボード bash スクリプトに移動します `WindowsDefenderATPOnboardingScript.cmd`。

5. ソリューションをテストします。
   1. 1 つのデバイスでプールを作成します。
   2. デバイスにログオンします。
   3. デバイスからログオフします。
   4. 別のユーザーと一緒にデバイスにログオンします。
   5. 実装するメソッドに応じて、適切な手順に従います。
      - デバイスごとに 1 つのエントリの場合: ポータルで 1 つのエントリのみを確認Microsoft 365 Defender。
      - デバイスごとに複数のエントリの場合: ポータルで複数のエントリMicrosoft 365 Defender確認します。

6. ナビゲーション ウィンドウで [ **デバイス] の一覧** をクリックします。

7. デバイス名を入力して検索機能を使用し、検索の種類として **[デバイス** ] を選択します。

## <a name="for-downlevel-skus-windows-server-2008-r2"></a>ダウンレベル SKU の場合 (Windows Server 2008 R2)

> [!NOTE]
> 他の Windows サーバー バージョンのこれらの手順は、MMA を必要とする Windows Server 2016 および Windows Server 2012 R2 に対して前のMicrosoft Defender for Endpointを実行している場合にも適用されます。 新しい統合ソリューションに移行する手順は、「[Microsoft Defender for Endpoint のサーバー移行シナリオ](/microsoft-365/security/defender-endpoint/server-migration)」 にあります。

> [!NOTE]
> 次のレジストリは、目的が "デバイスごとに 1 つのエントリ" を達成する場合にのみ関連します。

1. レジストリ値を次に設定します。

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    またはコマンド ラインを使用する:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. サーバーの [オンボード プロセスに](configure-server-endpoints.md)従います。 

## <a name="updating-virtual-desktop-infrastructure-vdi-images-persistent-or-non-persistent"></a>仮想デスクトップ インフラストラクチャ (VDI) イメージの更新 (永続的または非永続的)

VDI で実行されている VM に更新プログラムを簡単にデプロイする機能を使用して、このガイドを短縮し、コンピューターで迅速かつ簡単に更新プログラムを入手する方法に焦点を当てています。 更新プログラムがホスト サーバー上のコンポーネント ビットに展開され、オンになると VM に直接ダウンロードされるため、ゴールデン イメージを定期的に作成してシールする必要はなくなりました。

詳細については、「 [Virtual Desktop インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド」のガイダンスに](/microsoft-365/security/defender-endpoint/deployment-vdi-microsoft-defender-antivirus)従ってください。

   > [!NOTE]
   > VDI 環境のマスター イメージをオンボードした (SENSE サービスが実行されている) 場合は、イメージを運用環境に戻す前に、一部のデータをオフにしてクリアする必要があります。
   > 1. CMD ウィンドウで次のコマンドを実行して、センサーが停止していることを確認します。
   >  ```console
   >  sc query sense
   >  ```
   > 2. PsExec.exeを使用して次のコマンドを実行します (次のコマンドからダウンロードできます)。 https://download.sysinternals.com/files/PSTools.zip)
   >
   >  ```console
   >  PsExec.exe -s cmd.exe
   >  cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
   >  del *.* /f /s /q
   >  REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
   >  exit
   >  ```

## <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

デバイスをサービスにオンボードした後は、次の推奨構成設定で有効にすることで、付属の脅威保護機能を利用することが重要です。

### <a name="next-generation-protection-configuration"></a>次世代の保護構成

次の構成設定をお勧めします。

#### <a name="cloud-protection-service"></a>Cloud Protection Service

- クラウドによる保護を有効にする: はい
- クラウドによる保護レベル: 未構成
- Defender Cloud 延長タイムアウト (秒単位): 20

#### <a name="exclusions"></a>除外
- ローカル管理者マージを無効にする: 未構成
- 除外する Defender プロセス:
  - `%Programfiles%\FSLogix\Apps\frxccd.exe`
  - `%Programfiles%\FSLogix\Apps\frxccds.exe`
  - `%Programfiles%\FSLogix\Apps\frxsvc.exe`

- スキャンとリアルタイム保護から除外するファイル拡張子:
  -  `%Programfiles%\FSLogix\Apps\frxccd.sys`
  - `%Programfiles%\FSLogix\Apps\frxdrv.sys`
  - `%Programfiles%\FSLogix\Apps\frxdrvvt.sys`
  - `%TEMP%*.VHD`
  - `%TEMP%*.VHDX`
  - `%Windir%\TEMP*.VHD`
  - `%Windir%\TEMP*.VHDX`
  - `\\stroageaccount.file.core.windows.net\share**.VHD`
  -  `\\stroageaccount.file.core.windows.net\share**.VHDX`

#### <a name="real-time-protection"></a>リアルタイム保護

- すべての設定をオンにし、すべてのファイルを監視するように設定する

#### <a name="remediation"></a>修復
- 検疫されたマルウェアを保持する日数: 30
- サンプルの同意を送信する: すべてのサンプルを自動的に送信する
- 望ましくない可能性のあるアプリに対して実行するアクション: 有効
- 検出された脅威に対するアクション:
  - 低脅威: クリーン
  - 中程度の脅威、高い脅威、重大な脅威: 検疫

#### <a name="scan"></a>スキャン

- アーカイブされたファイルをスキャンする: はい
- スケジュールされたスキャンに低い CPU 優先度を使用する: 未構成
- キャッチアップフル スキャンを無効にする: 未構成
- キャッチアップ クイック スキャンを無効にする: 未構成
- スキャンあたりの CPU 使用率の制限: 50
- フル スキャン中にマップされた netoword ドライブをスキャンする: 未構成
- 毎日のクイック スキャンを午後 12 時に実行する
- スキャンの種類: 未構成
- スケジュールされたスキャンを実行する曜日: 未構成
- スケジュールされたスキャンを実行する時刻: 未構成
- スキャンを実行する前に署名の更新を確認する: はい

#### <a name="updates"></a>更新プログラム
- セキュリティ インテリジェンス更新プログラムを確認する頻度を入力します: 8
- 他の設定は既定の状態のままにする

#### <a name="user-experience"></a>ユーザー エクスペリエンス
- Microsoft Defender アプリへのユーザー アクセスを許可する: 未構成

#### <a name="enable-tamper-protection"></a>改ざん防止を有効にする
- 改ざん防止を有効にして Microsoft Defender が無効にならないようにする: 有効にする

#### <a name="attack-surface-reduction"></a>攻撃面の縮小

- ネットワーク保護を有効にする: 監査モード
- Microsoft Edge の SmartScreen を必要とする: はい
- 悪意のあるサイト へのアクセスをブロックする: はい
- 未検証ファイルのダウンロードをブロックする: はい

#### <a name="attack-surface-reduction-rules"></a>攻撃面の減少ルール
- 監査に使用できるすべてのルールを構成します。

> [!NOTE]
> これらのアクティビティをブロックすると、正当なビジネス プロセスが中断される可能性があります。 最善の方法は、すべてを監査に設定し、有効にしても安全なものを特定し、誤検知検出がないエンドポイントでこれらの設定を有効にすることです。

## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
