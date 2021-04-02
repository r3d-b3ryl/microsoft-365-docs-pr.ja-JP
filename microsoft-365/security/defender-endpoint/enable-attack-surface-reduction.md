---
title: 攻撃面の減少ルールを有効にする
description: 攻撃表面の縮小 (ASR) ルールを有効にして、マクロ、スクリプト、一般的なインジェクション手法を使用する攻撃からデバイスを保護します。
keywords: 攻撃表面の縮小、腰、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、有効化、有効にする
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf4fa88b3fbbf5d977d54a78c480129665049b23
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499403"
---
# <a name="enable-attack-surface-reduction-rules"></a>攻撃面の減少ルールを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[攻撃表面の縮小ルール](attack-surface-reduction.md) (ASR ルール) は、マルウェアが頻繁にデバイスやネットワークを侵害するアクションを防ぐのに役立ちます。 次のエディションとバージョンの Windows を実行しているデバイスに対して ASR ルールを設定できます。
- Windows 10 Pro [バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows 10 Enterprise バージョン [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降
- Windows Server バージョン [1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 以降
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

各 ASR ルールには、次の 3 つの設定のいずれかを含む。

- 構成されていません: ASR ルールを無効にする
- ブロック: ASR ルールを有効にする
- 監査: ASR ルールが有効な場合に組織に与える影響を評価する

Microsoft Defender for Endpoint (Defender [for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection) で使用できる高度な監視およびレポート機能を利用するには、Windows E5 ライセンス (または類似のライセンス SKU) で ASR ルールを使用することを強くお勧めします。 ただし、高度な監視およびレポート機能にアクセスできない Windows Professional や E3 などの他のライセンスの場合は、ASR ルールがトリガーされる際に各エンドポイントで生成されるイベント (イベント転送など) の上に独自の監視およびレポート ツールを開発できます。

> [!TIP]
> Windows ライセンスの詳細については [、「Windows 10 Licensing」](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) を参照し [、Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)のボリューム ライセンス ガイドを参照してください。

攻撃表面の縮小ルールは、次の方法で有効にできます。

- [Microsoft Intune](#intune)
- [モバイル デバイス管理 (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [グループ ポリシー](#group-policy)
- [PowerShell](#powershell)

Intune や Microsoft Endpoint Manager などのエンタープライズ レベルの管理をお勧めします。 エンタープライズ レベルの管理では、起動時に競合するグループ ポリシーまたは PowerShell 設定が上書きされます。

## <a name="exclude-files-and-folders-from-asr-rules"></a>ASR ルールからファイルとフォルダーを除外する

ほとんどの攻撃表面の縮小ルールによってファイルとフォルダーが評価されるのを除外できます。 つまり、ASR ルールがファイルまたはフォルダーに悪意のある動作が含まれていると判断した場合でも、ファイルの実行をブロックしません。 これにより、安全でないファイルを実行してデバイスに感染する可能性があります。

指定された Defender for Endpoint ファイルと証明書インジケーターを許可することで、証明書とファイル ハッシュに基づいて ASR ルールをトリガーから除外することもできます。 (「指標 [の管理」を参照](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)してください。

> [!IMPORTANT]
> ファイルまたはフォルダーを除外すると、ASR ルールによって提供される保護が大幅に低下する可能性があります。 除外されたファイルの実行が許可され、レポートやイベントは記録されません。
> ASR ルールで検出すべきではないと思うファイルを検出する場合は、まず監査モードを使用して [ルールをテストする必要があります](evaluate-attack-surface-reduction.md)。


個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、除外が適用されるルールを指定することはできません。 除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。 たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。

ASR ルールは、環境変数とワイルドカードをサポートします。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。

ASR ルールを有効にする次の手順には、ファイルとフォルダーを除外する方法の手順が含まれます。

## <a name="intune"></a>Intune

1. [デバイス **構成プロファイル**  >  **] を選択します**。 既存のエンドポイント保護プロファイルを選択するか、新しいエンドポイント保護プロファイルを作成します。 新しいプロファイルを作成するには、[プロファイルの作成] **を選択し** 、このプロファイルの情報を入力します。 [プロファイル **の種類] で**、[ **エンドポイント保護] を選択します**。 既存のプロファイルを選択した場合は、[プロパティ] を選択 **し、[設定** ] を **選択します**。

2. [エンドポイント保護 **] ウィンドウで** 、[Exploit **Guard] をWindows Defenderし**、[攻撃表面の縮小 **] を選択します**。 各 ASR ルールの目的の設定を選択します。

3. [ **攻撃表面の縮小の例外] で**、個々のファイルとフォルダーを入力します。 [インポート] を **選択して** 、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。 CSV ファイルの各行は、次のように書式設定する必要があります。

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 3 つの構成ウィンドウで **[OK]** を選択します。 次に、**新しい** エンドポイント保護ファイルを作成する場合は[作成] を選択し、既存のエンドポイント保護ファイルを編集する場合は [保存] を選択します。

## <a name="mdm"></a>MDM

各ルールのモードを個別に有効にして設定するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 構成サービス プロバイダー (CSP) を使用します。

ASR ルールに GUID 値を使用して参照 [するサンプルを次に示します](attack-surface-reduction.md#attack-surface-reduction-rules)。

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

監査モードで有効、無効、または有効にする値は次のとおりです。

- Disable = 0
- ブロック (ASR ルールを有効にする) = 1
- 監査 = 2

除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。

例:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> スペースを使用せずに OMA-URI 値を入力してください。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Microsoft Endpoint Configuration Manager で、[アセットとコンプライアンス エンドポイント保護] に移動 **し**、[Exploit  >    >  **Guard Windows Defenderに移動します**。

2. [ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。

3. 名前と説明を入力し、[攻撃表面の縮小] を **選択** し、[次へ] を **選択します**。

4. アクションをブロックまたは監査するルールを選択し、[次へ] を **選択します**。

5. 設定を確認し、[次へ] **を選択** してポリシーを作成します。

6. ポリシーが作成された後、閉 **じます**。

## <a name="group-policy"></a>グループ ポリシー

> [!WARNING]
> Intune、Configuration Manager、または他のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理する場合、管理ソフトウェアは起動時に競合するグループ ポリシー設定を上書きします。

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを Windows コンポーネント **に展開**  >  **する Microsoft Defender ウイルス** 対策  >  **Microsoft Defender Exploit Guard**  >  **攻撃表面の縮小**。

4. [攻撃 **表面縮小ルールの構成] を選択し、[** 有効] を **選択します**。 その後、[オプション] セクションで各ルールの個別の状態を設定できます。

   **[Show....]** を選択し、[値名] 列にルール ID を入力し、[値] 列に選択した状態 **を** 次のように入力します。

   - Disable = 0
   - ブロック (ASR ルールを有効にする) = 1
   - 監査 = 2

   ![空の攻撃表面縮小ルール ID と値 1 を示すグループ ポリシー設定](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. ASR ルールからファイルとフォルダーを除外するには、[攻撃表面の縮小ルールからファイルとパスを除外する] 設定を選択し、オプションを [有効] に **設定します**。 [ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。 各 **アイテムの [** 値] **列に 0** を入力します。

> [!WARNING]
> [値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Intune、Configuration Manager、または別のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理すると、起動時に競合する PowerShell 設定が管理ソフトウェアによって上書きされます。 PowerShell を使用して値を定義するには、管理プラットフォームのルールに "User Defined" オプションを使用します。

1. [ **スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    監査モードで ASR ルールを有効にするには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    ASR ルールをオフにするには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > ルールごとに状態を個別に指定する必要がありますが、コンマ区切りのリストでルールと状態を組み合わせて使用できます。
    >
    > 次の例では、最初の 2 つのルールが有効になり、3 番目のルールが無効になり、4 番目のルールが監査モードで有効になります。
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    PowerShell 動詞を使用 `Add-MpPreference` して、既存のリストに新しいルールを追加することもできます。

    > [!WARNING]
    > `Set-MpPreference` ルールの既存のセットは常に上書きされます。 既存のセットに追加する場合は、代わりに使用する `Add-MpPreference` 必要があります。
    > を使用して、ルールとその現在の状態の一覧を取得できます `Get-MpPreference` 。

3. ASR ルールからファイルとフォルダーを除外するには、次のコマンドレットを使用します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにファイルとフォルダーを追加します。

    > [!IMPORTANT]
    > リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

## <a name="related-articles"></a>関連記事

- [攻撃表面の縮小ルールを使用して攻撃表面を削減する](attack-surface-reduction.md)

- [攻撃表面の縮小を評価する](evaluate-attack-surface-reduction.md)

- [攻撃面の減少の FAQ](attack-surface-reduction.md)
