---
title: Azure Virtual Desktop で Windows デバイスをオンボードする
description: Azure Virtual Desktop で Windows デバイスを Defender for Endpoint にオンボードする方法について説明します
keywords: Azure Virtual Desktop、AVD、Microsoft Defender、エンドポイント、オンボード
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 63966b84fc2d5a57f9c8b405a97d61ba17450dfb
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822137"
---
# <a name="onboard-windows-devices-in-azure-virtual-desktop"></a>Azure Virtual Desktop で Windows デバイスをオンボードする

読み取り時間 6 分

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Azure Virtual Desktop (AVD) で実行されている Windows マルチセッション
- [Windows 10 Enterpriseマルチセッション](/microsoft-365/security/defender-endpoint/azure-server-integration)

Microsoft Defender for Endpointでは、VDI セッションと Azure Virtual Desktop セッションの両方の監視がサポートされます。 組織のニーズによっては、従業員が管理されていないデバイス、リモートの場所、または同様のシナリオから企業データやアプリにアクセスできるように、VDI または Azure Virtual Desktop セッションを実装することが必要になる場合があります。 Microsoft Defender for Endpointを使用すると、これらの仮想マシンで異常なアクティビティを監視できます。

## <a name="before-you-begin"></a>はじめに

[非永続的 VDI に関する考慮事項](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)について理解します。 [Azure Virtual Desktop](/azure/virtual-desktop/overview) には非永続化オプションは用意されていませんが、新しいホストのプロビジョニングとマシンの再デプロイに使用できるゴールデン Windows イメージを使用する方法が提供されます。 これにより、環境の揮発性が高まり、Microsoft Defender for Endpoint ポータルで作成および管理されるエントリに影響を与え、セキュリティ アナリストの可視性が低下する可能性があります。

> [!NOTE]
> オンボード方法の選択に応じて、デバイスは次のようにポータルMicrosoft Defender for Endpoint表示できます。
>
> - 仮想デスクトップごとに 1 つのエントリ
> - 仮想デスクトップごとに複数のエントリ

Microsoft では、仮想デスクトップごとに 1 つのエントリとして Azure Virtual Desktop をオンボードすることをお勧めします。 これにより、Microsoft Defender for Endpoint ポータルでの調査エクスペリエンスが、マシン名に基づいて 1 つのデバイスのコンテキストに確実に存在します。 AVD ホストを頻繁に削除して再デプロイする組織は、同じコンピューターの複数のオブジェクトがMicrosoft Defender for Endpoint ポータルで作成されないようにするため、この方法の使用を強く検討する必要があります。 これにより、インシデントを調査するときに混乱が生じる可能性があります。 テスト環境または不揮発性環境の場合は、別の方法を選択することもできます。

Microsoft では、AVD ゴールデン イメージにMicrosoft Defender for Endpointオンボード スクリプトを追加することをお勧めします。 こうすることで、このオンボード スクリプトが最初の起動時にすぐに実行されるようにすることができます。 これは、AVD ゴールデン イメージからプロビジョニングされたすべての AVD マシンで最初の起動時にスタートアップ スクリプトとして実行されます。 ただし、ギャラリー イメージの 1 つを変更せずに使用している場合は、スクリプトを共有の場所に配置し、ローカル またはドメイン グループ ポリシーから呼び出します。

> [!NOTE]
> AVD ゴールデン イメージ上の VDI オンボードスタートアップ スクリプトの配置と構成は、AVD の起動時に実行されるスタートアップ スクリプトとして構成されます。 実際の AVD ゴールデン イメージをオンボード **することは** お勧めしません。 もう 1 つの考慮事項は、スクリプトの実行に使用されるメソッドです。 スタートアップ/プロビジョニング プロセスのできるだけ早い段階で実行して、セッションの受信に使用できるマシンとサービスへのデバイスオンボードの間の時間を短縮する必要があります。 以下のシナリオ 1 とシナリオ 2 では、これを考慮に入れる必要があります。

### <a name="scenarios"></a>シナリオ

AVD ホスト マシンをオンボードするには、いくつかの方法があります。

- 起動時にゴールデン イメージ (または共有場所から) でスクリプトを実行します。
- 管理ツールを使用してスクリプトを実行します。
- [Microsoft Defender for Cloud との統合](azure-server-integration.md)を通じて

#### <a name="scenario-1-using-local-group-policy"></a>*シナリオ 1: ローカル グループ ポリシーの使用*

このシナリオでは、ゴールデン イメージにスクリプトを配置し、ローカル グループ ポリシーを使用してブート プロセスの早期に実行する必要があります。

[非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボードに関する](configure-endpoints-vdi.md)記事の手順を使用します。

手順に従って、デバイスごとに 1 つのエントリを入力します。

#### <a name="scenario-2-using-domain-group-policy"></a>*シナリオ 2: ドメイン グループ ポリシーの使用*

このシナリオでは、一元的に配置されたスクリプトを使用し、ドメイン ベースのグループ ポリシーを使用して実行します。 また、ゴールデン イメージにスクリプトを配置し、同じ方法で実行することもできます。

##### <a name="download-the-windowsdefenderatponboardingpackagezip-file-from-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルからWindowsDefenderATPOnboardingPackage.zip ファイルをダウンロードする

1. VDI 構成パッケージ .zip ファイルを開く (WindowsDefenderATPOnboardingPackage.zip)

    1. Microsoft 365 Defender ポータルナビゲーション ウィンドウで、(**デバイス管理** の下で) **[設定** \> **エンドポイント** \> **のオンボード**] を選択します。
    1. オペレーティング システムとしてWindows 10またはWindows 11を選択します。
    1. **[展開方法]** フィールドで、非永続的エンドポイントの VDI オンボード スクリプトを選択します。
    1. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 **OptionalParamsPolicy** という名前のフォルダーと **、WindowsDefenderATPOnboardingScript.cmd** と **Onboard-NonPersistentMachine.ps1** ファイルがあります。

##### <a name="use-group-policy-management-console-to-run-the-script-when-the-virtual-machine-starts"></a>グループ ポリシー管理コンソールを使用して、仮想マシンの起動時にスクリプトを実行する

1. グループ ポリシー管理コンソール (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、**［編集］** をクリックします。

2. グループ ポリシー管理エディターで、[**コンピューター構成** \> **の基本設定]** **コントロール パネル** の\>設定に移動します。

3. **[スケジュールされたタスク**] を右クリックし、[**新規**] をクリックし、[**イミディエイト タスク** ] (少なくとも Windows 7) をクリックします。

4. 開いた [タスク] ウィンドウで、[ **全般** ] タブに移動します。[ **セキュリティ オプション** ] で[ **ユーザーまたはグループの変更** ] をクリックし、「SYSTEM」と入力します。 [ **名前の確認]** をクリックし、[OK] をクリックします。 NT AUTHORITY\SYSTEM は、タスクを実行するユーザー アカウントとして表示されます。

5. **［ユーザーがログオンしているかどうかに関係なく実行する］** を選択し、**［最高の権限で実行する］** チェックボックスをオンにします。

6. **[アクション]** タブに移動し、[**新規**] をクリックします。 [アクション **] フィールドで [プログラムの開始** ] が選択されていることを確認します。 次の情報を入力します。

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   次に **、[OK] を** 選択し、開いている GPMC ウィンドウを閉じます。

#### <a name="scenario-3-onboarding-using-management-tools"></a>*シナリオ 3: 管理ツールを使用したオンボード*

管理ツールを使用してマシンを管理する予定がある場合は、Microsoft Endpoint Configuration Managerを使用してデバイスをオンボードできます。

詳細については、「[Configuration Managerを使用して Windows デバイスをオンボードする](configure-endpoints-sccm.md)」を参照してください。

> [!WARNING]
> [攻撃表面縮小ルールリファレンス](attack-surface-reduction-rules-reference.md)を使用する予定の場合は、Microsoft Endpoint Configuration Managerを使用した管理と互換性がないため、ルール "[PSExec および WMI コマンドから発信されるプロセスの作成をブロック](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands)する" ルールを使用しないでください。 この規則は、Configuration Manager クライアントが正しく機能するために使用する WMI コマンドをブロックします。

> [!TIP]
> デバイスをオンボードした後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認することができます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)」 を参照してください。

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>ゴールデン イメージを構築するときにマシンにタグを付ける

オンボードの一環として、Microsoft Security Center で AVD マシンをより簡単に区別するようにマシン タグを設定することを検討する必要がある場合があります。 詳細については、「 [レジストリ キー値を設定してデバイス タグを追加する」を](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)参照してください。

#### <a name="other-recommended-configuration-settings"></a>その他の推奨構成設定

ゴールデン イメージを構築する場合は、初期保護設定も構成することをお勧めします。 詳細については、「 [その他の推奨構成設定](configure-endpoints-gp.md#other-recommended-configuration-settings)」を参照してください。

また、FSlogix ユーザー プロファイルを使用している場合は、次のファイルを常時オン保護から除外することをお勧めします。

**ファイルを除外する:**

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**プロセスを除外する:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>ライセンスの要件

ライセンスに関する注意: Windows Enterprise マルチセッションを使用する場合は、要件に応じて、Microsoft Defender for Endpoint (ユーザーごと)、Windows Enterprise E5、Microsoft 365 セキュリティ、またはMicrosoft 365 E5を通じてすべてのユーザーにライセンスを付与するか、Microsoft Defender for Cloud を通じて VM のライセンスを付与するかを選択できます。
Microsoft Defender for Endpointのライセンス要件については、「[ライセンス要件」を参照してください](minimum-requirements.md#licensing-requirements)。

### <a name="known-issues-and-limitations"></a>既知の問題と制限事項

マルチセッションでの Web フィルター処理では、Microsoft Edge のみがサポートWindows 10。

#### <a name="related-links"></a>関連リンク

[PowerShell を使用して Defender for Endpoint の除外を追加する](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-microsoft-defender-by-using-powershell)
