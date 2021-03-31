---
title: エンドポイント用 Microsoft Defender の最小要件
description: デバイスをサービスにオンボーディングする場合のライセンス要件と要件を理解する
keywords: 最小要件、ライセンス、比較表
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1b203a29083aaa4a1f86abcd7e2c7b24bd63f186
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445746"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>エンドポイント用 Microsoft Defender の最小要件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


サービスへのデバイスのオンボーディングには、いくつかの最小要件があります。 サービスにデバイスをオンボードするライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。

> [!TIP]
> - Defender for Endpoint: Defender for Endpoint Tech Community の [最新の機能強化について説明します](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。
> - Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。 読み取り: [MITRE ATT および CK&評価からの分析情報](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

## <a name="licensing-requirements"></a>ライセンスの要件
エンドポイント用 Microsoft Defender には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Windows 10 Enterprise E5 を含む Microsoft 365 E5 (M365 E5)
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 Security
- Microsoft Defender for Endpoint

> [!NOTE]
> 対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。
> Microsoft Defender for Endpoint は、クラウド ソリューション プロバイダー (CSP) から購入できます。
> RDSH VM では、エンドポイント 用の個別の Defender ライセンスは必要とできません。

Microsoft Defender for Endpoint for servers には、次のいずれかのライセンス オプションが必要です。

- [Azure Defender が有効になっている Azure セキュリティ センター](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender for Endpoint for Server (対象サーバーごとに 1 つ)

> [!NOTE]
> お客様は、以下のユーザー ライセンスの 1 つ以上に対して最低 50 ライセンスを合計している場合、Microsoft Defender for Endpoint for Servers のサーバー ライセンス (対象サーバーのオペレーティング システム環境 (OSE) ごとに 1 つ) を取得できます。
>
> * Microsoft Defender for Endpoint
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 セキュリティ

ライセンスの詳細については、「 [製品](https://www.microsoft.com/licensing/terms/) 条項」サイトを参照し、アカウント チームと一緒に使用して、契約条件の詳細について説明します。

Windows 10 エディションの機能の配列の詳細については [、「Compare Windows 10 editions」を参照してください](https://www.microsoft.com/windowsforbusiness/compare)。

Windows 10 商用エディションの比較の詳細な比較表については、比較 PDF を [参照してください](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)。

## <a name="browser-requirements"></a>ブラウザー要件
Defender for Endpoint へのアクセスはブラウザーを介して行われ、次のブラウザーをサポートします。

- Microsoft Edge
- Google Chrome

> [!NOTE]
> 他のブラウザーが動作する場合は、前述のブラウザーがサポートされています。


## <a name="hardware-and-software-requirements"></a>ハードウェア要件とソフトウェア要件

### <a name="supported-windows-versions"></a>サポートされている Windows バージョン
- Windows 7 SP1エンタープライズ ([サポートには ESU が必要です](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。)
- Windows 7 SP1 Pro ([サポートには ESU が必要](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)です。)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows サーバー
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server バージョン 1803 以降
  - Windows Server 2019
- Windows Virtual Desktop

ネットワーク上のデバイスで、これらのエディションのいずれかを実行している必要があります。

デバイス上の Defender for Endpoint のハードウェア要件は、サポートされているエディションで同じです。

> [!NOTE]
> モバイル バージョンの Windows を実行しているコンピューター (Windows CE Windows 10 Mobile など) はサポートされていません。
>
> Windows 10 Enterprise 2016 LTSB を実行している仮想マシンは、Microsoft 以外の仮想化プラットフォームで実行すると、パフォーマンスの問題が発生する可能性があります。
>
> 仮想環境では、Windows 10 Enterprise LTSC 2019 以降を使用することをお勧めします。


### <a name="other-supported-operating-systems"></a>その他のサポートされているオペレーティング システム
- Android
- iOS
- Linux
- macOS

> [!NOTE]
> 統合が機能するには、Defender for Endpoint と互換性がある Android、iOS、macOS の Linux ディストリビューションとバージョンを確認する必要があります。



### <a name="network-and-data-storage-and-configuration-requirements"></a>ネットワークとデータのストレージと構成の要件
オンボーディング ウィザードを初めて実行する場合は、Microsoft Defender for Endpoint 関連情報の保存場所 (欧州連合、英国、または米国のデータセンター) を選択する必要があります。

> [!NOTE]
> - 初回セットアップ後にデータストレージの場所を変更することはできません。
> - Microsoft が [データを保存する](data-storage-privacy.md) 場所と方法の詳細については、Microsoft Defender for Endpoint のデータ ストレージとプライバシーを確認してください。


### <a name="diagnostic-data-settings"></a>診断データの設定

> [!NOTE]
> Microsoft Defender for Endpoint は、有効になっている限り、特定の診断レベルを必要としません。

組織内のすべてのデバイスで診断データ サービスが有効になっているか確認します。
既定では、このサービスは有効になっています。 センサー データを取得する方法を確認する方法をお試しください。

**コマンド ラインを使用して、Windows 10 診断データ サービスのスタートアップの種類を確認します**。

1. デバイスで管理者特権のコマンド ライン プロンプトを開きます。

   1.  **[スタート]** をクリックし、「**cmd**」と入力します。

   1.  **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力し、Enter キーを **押します**。

   ```console
   sc qc diagtrack
   ```

   サービスが有効になっている場合、結果は次のスクリーンショットのようになります。

   ![diagtrack の sc クエリ コマンドの結果](images/windefatp-sc-qc-diagtrack.png)


サービスが自動的に開始に設定されている場合は、START_TYPEに設定する **必要AUTO_START。**


**コマンド ラインを使用して、Windows 10 診断データ サービスを自動的に開始する設定を行います。**

1.  エンドポイントで管理者特権のコマンド ライン プロンプトを開きます。

    1. **[スタート]** をクリックし、「**cmd**」と入力します。

    1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2.  次のコマンドを入力し、Enter キーを **押します**。

    ```console
    sc config diagtrack start=auto
    ```

3.  成功メッセージが表示されます。 次のコマンドを入力して変更を確認し、Enter キーを **押します**。

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>インターネット接続
デバイス上のインターネット接続は、直接またはプロキシ経由で必要です。

Defender for Endpoint センサーは、1 日の平均帯域幅 5 MB を使用して Defender for Endpoint クラウド サービスと通信し、サイバー データを報告できます。 ファイルのアップロードや調査パッケージ コレクションなどの 1 回限りでのアクティビティは、この 1 日の平均帯域幅には含まれません。

追加のプロキシ構成設定の詳細については、「デバイス プロキシとインターネット接続の設定 [を構成する」を参照してください](configure-proxy-internet.md)。

デバイスをオンボードする前に、診断データ サービスを有効にする必要があります。 このサービスは、Windows 10 で既定で有効になっています。


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender ウイルス対策の構成要件
Defender for Endpoint エージェントは、Microsoft Defender Antivirus がファイルをスキャンし、ファイルに関する情報を提供する機能に依存します。

Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかを問う場合は、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成します。 詳細については [、「Manage Microsoft Defender Antivirus updates and apply baselines」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

Microsoft Defender Antivirus が組織内のアクティブなマルウェア対策ではない場合、Defender for Endpoint サービスを使用すると、Microsoft Defender ウイルス対策はパッシブ モードになります。

組織でグループ ポリシーなどの方法で Microsoft Defender Antivirus を無効にしている場合は、オンボードされているデバイスをこのグループ ポリシーから除外する必要があります。

サーバーをオンボーディングしている場合に、Microsoft Defender Antivirus がサーバー上のアクティブなマルウェア対策ではない場合は、パッシブ モードに切り替わるかアンインストールするように Microsoft Defender ウイルス対策を構成する必要があります。 構成はサーバーのバージョンに依存します。 詳細については [、「Microsoft Defender ウイルス対策の互換性」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。

> [!NOTE]
> 通常のグループ ポリシーはタンパー プロテクションには適用されません。タンパー プロテクションがオンの場合、Microsoft Defender ウイルス対策設定の変更は無視されます。


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender ウイルス対策早期起動マルウェア対策 (ELAM) ドライバーが有効になっている
Microsoft Defender Antivirus をデバイスのプライマリマルウェア対策製品として実行している場合、Defender for Endpoint エージェントは正常にオンボードされます。

サードパーティのマルウェア対策クライアントを実行し、モバイル デバイス管理ソリューションまたは Microsoft Endpoint Manager (現在のブランチ) を使用する場合は、Microsoft Defender ウイルス対策 ELAM ドライバーが有効になっている必要があります。 詳細については、「ポリシーによって Microsoft Defender ウイルス対策が無効にされていないか確認 [する」を参照してください](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。


## <a name="related-topics"></a>関連項目
- [Microsoft Defender for Endpoint の展開をセットアップする](production-deployment.md)
- [オンボード デバイス](onboard-configure.md)
