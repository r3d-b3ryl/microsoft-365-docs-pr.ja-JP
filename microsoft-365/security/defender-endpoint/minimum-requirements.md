---
title: Microsoft Defender for Endpoint の最小要件
description: デバイスをサービスにオンボードするためのライセンス要件と要件について説明します
keywords: 最小要件, ライセンス, 比較表
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 355fc0f367c415ae679259195e18ff3920812f4a
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65670160"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の最小要件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-minreqs-abovefoldlink)

デバイスをサービスにオンボードするための最小要件がいくつかあります。 デバイスをサービスにオンボードするための、ライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。

> [!TIP]
>
> - この記事では、Microsoft Defender for Endpoint プラン 2 の最小要件について説明します。 Defender for Endpoint プラン 1 に関する情報をお探しの場合は、「[Defender for Endpoint プラン 1 の要件](mde-p1-setup-configuration.md#review-the-requirements)」を参照してください。
> - Defender for Endpoint の最新の機能拡張については、[Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced) の情報を参照してください。
> - 最近の MITRE 評価において、Defender for Endpoint の業界をリードする分析力と検出能力が示されました。詳しくは、「[MITRE ATT&CK ベース評価の分析](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)」を参照してください。

## <a name="licensing-requirements"></a>ライセンスの要件
Microsoft Defender for Endpoint のライセンス要件の詳細については、[Microsoft Defender for Endpoint のライセンス情報](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-defender-for-endpoint)を参照してください。


詳細なライセンス情報については、[製品条項サイト](https://www.microsoft.com/licensing/terms/)を参照し、アカウント チームと協力して使用条件の詳細を確認してください。

Windows エディションの機能の詳細については、「[Windows エディションの比較](https://www.microsoft.com/windowsforbusiness/compare)」を参照してください。

## <a name="browser-requirements"></a>ブラウザー要件

Defender for Endpoint へのアクセスはブラウザーを介して行われます。以下のブラウザーがサポートされています。

- Microsoft Edge
- Google Chrome

> [!NOTE]
> 他のブラウザーでも動作する場合がありますが、サポートされているブラウザーは上記のブラウザーです。

## <a name="hardware-and-software-requirements"></a>ハードウェア要件とソフトウェア要件

### <a name="supported-windows-versions"></a>サポート対象の Windows バージョン

- Windows 7 SP1 Enterprise ([サポートには ESU が必要です](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。)
- Windows 7 SP1 Pro ([サポートには ESU が必要です](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 11 Enterprise
- Windows 11 Education
- Windows 11 Pro
- Windows 11 Pro Education
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 以降](/windows/whats-new/ltsc/)
- Windows 10 Enterprise IoT

    >[!NOTE]
    >Windows 10 IoT Enterprise は、Microsoft Defender for Endpoint でサポートされている OS であり、OEM/ODM による製品またはソリューションの一部としての配布が可能ですが、ユーザーはホストベースのインストール済みソフトウェアとサポートに関する OEM/OEM のガイダンスに従う必要があります。

- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Server
  - Windows Server 2008 R2 SP1 ([サポートには ESU が必要です](/windows-server/get-started/extended-security-updates-deploy))
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server バージョン 1803 以降
  - Windows Server 2019
  - Windows Server 2022
- Windows Virtual Desktop
- Windows 365

ネットワーク上のデバイスは、これらのエディションのいずれかを実行している必要があります。

デバイス上の Defender for Endpoint のハードウェア要件は、サポートされているエディションで共通です。

> コア: 2 (最小)、4 (推奨) メモリ: 1 GB (最小)、4 GB (推奨)

サポートされているバージョンの Windows 10 の詳細については、(/windows/release-health/release-information) を参照してください。

> [!NOTE]
> モバイル バージョンの Windows (Windows CE や Windows 10 Mobile など) を実行しているコンピューターはサポートされていません。
>
> Windows 10 Enterprise 2016 LTSB を実行している仮想マシンは、Microsoft 以外の仮想化プラットフォームで実行すると、パフォーマンスの問題が発生する場合があります。
>
> 仮想環境の場合は、Windows 10 Enterprise LTSC 2019 以降を使用することをお勧めします。

コンポーネントが Microsoft Windows オペレーティング システムで最新の状態にある場合、Microsoft Defender for Endpoint のサポートは、それぞれのオペレーティング システムのライフサイクルに従います。 詳細については、「[ライフサイクルに関する FAQ](/lifecycle/faq/general-lifecycle)」を参照してください。 新機能は、通常、ライフサイクルの終了にまだ達していないオペレーティング システムでのみ提供されます。 セキュリティ インテリジェンスの更新プログラム (定義とエンジンの更新) と検出ロジックは、少なくとも次の時点まで引き続き提供されます。

- [サポート終了日](/lifecycle/products/) (拡張セキュリティ更新プログラム (ESU) がないオペレーティング システムの場合)。
- [ESU の終了日](/lifecycle/faq/extended-security-updates) (ESU プログラムがあるオペレーティング システムの場合)。



### <a name="other-supported-operating-systems"></a>サポートされているその他のオペレーティング システム

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [ Linux ](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> 統合を機能させるには、Linux ディストリビューションと Android、iOS、macOS のバージョンが Defender for Endpoint と互換性があることを確認する必要があります。

### <a name="network-and-data-storage-and-configuration-requirements"></a>ネットワークとデータ ストレージと構成の要件

オンボード ウィザードを初めて実行する場合は、Microsoft Defender for Endpoint 関連の情報を保存する場所 (欧州連合、英国、または米国のデータセンター) を選択する必要があります。

> [!NOTE]
>
> - 初回セットアップ後にデータ ストレージの場所を変更することはできません。
> - Microsoft がデータを保存する場所と方法の詳細については、「[Microsoft Defender for Endpoint のデータ ストレージとプライバシー](data-storage-privacy.md)」を確認してください。

### <a name="diagnostic-data-settings"></a>診断データの設定

> [!NOTE]
> Microsoft Defender for Endpoint が有効になっていれば、特定の診断レベルは必要ありません。

組織内のすべてのデバイスで診断データ サービスが有効になっていることを確認してください。
既定では、このサービスは有効になっています。 それらからセンサー データを取得できることを確認しておくことをお勧めします。

#### <a name="use-the-command-line-to-check-the-windows-diagnostic-data-service-startup-type"></a>コマンド ラインを使用して、Windows 診断データ サービスのスタートアップの種類を確認する

1. デバイスで管理者特権のコマンド ライン プロンプトを開きます。
   1. **[スタート]** をクリックし、「**cmd**」と入力します。
   2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter キー** を押します。

   ```console
   sc qc diagtrack
   ```

   サービスが有効になっている場合、結果は次のスクリーンショットのようになります。

   :::image type="content" source="images/windefatp-sc-qc-diagtrack.png" alt-text="diagtrack の sc クエリ コマンドの結果。" lightbox="images/windefatp-sc-qc-diagtrack.png":::

**START_TYPE** が **AUTO_START** に設定されていない場合は、サービスを自動的に開始するように設定する必要があります。

#### <a name="use-the-command-line-to-set-the-windows-diagnostic-data-service-to-automatically-start"></a>コマンド ラインを使用して、Windows 診断データ サービスを自動的に開始するように設定する

1. エンドポイントで管理者特権のコマンド ライン プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力します。
    2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter キー** を押します。

    ```console
    sc config diagtrack start=auto
    ```

3. 成功メッセージが表示されます。次のコマンドを入力して変更を確認し、**Enterキー** を押します。

    ```console
    sc qc diagtrack
    ```

#### <a name="internet-connectivity"></a>インターネット接続

デバイスのインターネット接続は、直接またはプロキシ経由で行う必要があります。

Defender for Endpoint センサーは、1 日の平均帯域幅 5 MB を使用して Defender for Endpoint クラウド サービスと通信し、サイバー データを報告できます。 ファイルのアップロードや調査パッケージの収集などの 1 回限りのアクティビティは、この 1 日の平均帯域幅には含まれません。

追加のプロキシ構成設定の詳細については、「[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)」を参照してください。

デバイスをオンボードする前に、診断データ サービスを有効にする必要があります。 このサービスは、Windows 10 と Windows 11 では既定で有効になっています。

## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender ウイルス対策の構成要件

Defender for Endpoint エージェントは、ファイルをスキャンし、それらに関する情報を提供する Microsoft Defender ウイルス対策の機能によって異なります。

Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかに関係なく、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成します。 詳細については、「[Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)」を参照してください。

Microsoft Defender ウイルス対策が組織のアクティブなマルウェア対策ではなく、Defender for Endpoint サービスを使用している場合、Microsoft Defender ウイルス対策はパッシブ モードになります。

組織がグループ ポリシーまたはその他の方法で Microsoft Defender ウイルス対策をオフにしている場合は、オンボードされているデバイスをこのグループ ポリシーから除外する必要があります。

サーバーをオンボードしていて、Microsoft Defender ウイルス対策がサーバーのアクティブなマルウェア対策ではない場合、Microsoft Defender ウイルス対策をパッシブ モードに移行するように構成するか、アンインストールする必要があります。 構成はサーバーのバージョンによって異なります。 詳細については、「[Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。

> [!NOTE]
> 通常のグループ ポリシーは改ざん防止には適用されません。改ざん防止が有効になっている場合、Microsoft Defender ウイルス対策の設定に対する変更は無視されます。

## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender ウイルス対策の起動時マルウェア対策 (ELAM) ドライバーが有効になっている

デバイスでプライマリ マルウェア対策製品として Microsoft Defender ウイルス対策を実行している場合、Defender for Endpoint エージェントは正常にオンボードされます。

サード パーティ製のマルウェア対策クライアントを実行していて、Mobile デバイス管理 ソリューションまたは Microsoft エンドポイント マネージャー (Current Branch) を使用している場合は、Microsoft Defender ウイルス対策 ELAM ドライバーが有効になっていることを確認する必要があります。詳細については、「 [ポリシーでMicrosoft Defender ウイルス対策が無効になっていないことを確認する](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)」を参照してください。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint 展開の設定](production-deployment.md)
- [デバイスのオンボード](onboard-configure.md)
