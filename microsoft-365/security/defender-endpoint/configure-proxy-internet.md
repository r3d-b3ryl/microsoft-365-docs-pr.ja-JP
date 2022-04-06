---
title: 情報保護のためにデバイス プロキシとインターネット接続の設定を構成する
description: クラウド サービスとの Microsoft Defender for Endpoint を有効にするには、プロキシとインターネットの設定を構成します。
keywords: configure, proxy, internet, internet connectivity, settings, proxy settings, netsh, winhttp, proxy server, 構成, インターネット接続, 設定, プロキシ設定, netsh, winhttp, プロキシ サーバー
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
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cf68afff79a2d719435e9df3d53400584f162618
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507347"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>デバイス プロキシとインターネット接続の設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。 埋め込まれた Defender for Endpoint センサーは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。 センサーは Microsoft Windows HTTP サービス (WinHTTP) を使用して、Defender for Endpoint クラウド サービスとの通信を有効にします。

> [!TIP]
> インターネットへのゲートウェイとして転送プロキシを使用する組織では、ネットワーク保護を使用して[転送プロキシの背後を調査できます](investigate-behind-proxy.md)。

WinHTTP の構成設定は、Windows Internet （WinINet） のインターネット閲覧用プロキシの設定とは独立しており ([WinINet vs. WinHTTP](/windows/win32/wininet/wininet-vs-winhttp) を参照)、以下の自動検出手法でのみプロキシ サーバーを検出することができます。

- 自動検出メソッド:

  - 透過プロキシ
  
  - Web プロキシ自動発見プロトコル (WPAD)

    > [!NOTE]
    > ネットワーク トポロジで透過プロキシまたは WPAD を使用している場合は、特別な構成は必要ありません。 プロキシでの Defender for Endpoint URL 除外の詳細については、「[プロキシ サーバーで Defender for Endpoint サービス URL へのアクセスを有効にする](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)」を参照してください。

- 手動の静的プロキシの構成:

  - レジストリ ベースの構成
  
  - netsh コマンドを使用して構成された WinHTTP – 安定したトポロジのデスクトップ (同じプロキシの背後にある企業ネットワークのデスクトップなど) だけに適しています。

> [!NOTE]
> Defender ウイルス対策 EDR プロキシは個別に設定できます。  以下のセクションでは、これらの違いに注意してください。

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。

コンピューターがインターネットへの接続を許可されていない場合は、診断データを報告し、Defender for Endpoint サービスと通信するために Defender for Endpoint 検出および応答 (EDR) センサー用のレジストリ ベースの静的プロキシを構成します。

> [!NOTE]
> Windows 10、Windows 11、Windows Server 2019、または Windows Server 2022 でこのオプションを使用する場合は、次のビルド (またはそれ以降) と累積的な更新プログラムのロールアップを使用してください。
>
> - Windows 11
> - Windows 10 Version 1809 または Windows Server 2019、または Windows Server 2022 -<https://support.microsoft.com/kb/5001384>
> - Windows 10 バージョン1909 - <https://support.microsoft.com/kb/4601380>
> - Windows 10 Education Version 2004 - <https://support.microsoft.com/kb/4601382>
> - Windows 10 Version 20H2 - <https://support.microsoft.com/kb/4601382>
>
> これらの更新プログラムは、CnC (Command and Control) チャネルの接続性と信頼性を向上しさせます。

静的プロキシはグループ ポリシー (GP) を使用して構成できます。EDR を使用するには、グループ ポリシー値の下の両方の設定をプロキシ サーバーに構成する必要があります。 グループ ポリシーは、[管理用テンプレート] で使用できます。

- **[管理用テンプレート]、[Windows コンポーネント]、[データの収集とプレビュー ビルド]、[接続ユーザー エクスペリエンスとテレメトリ サービス用に認証済みプロキシの使用を構成する]** の順に進みます。

  **[有効]** に設定し、**[認証済みプロキシの使用を無効にする]** を選択します。

  :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="[グループ ポリシー設定 1 の状態] ウィンドウ" lightbox="images/atp-gpo-proxy1.png":::

- **[管理用テンプレート]、[Windows コンポーネント]、[データの収集とプレビュー ビルド]、[接続ユーザーのエクスペリエンスと利用統計情報を構成する]** の順に進みます:

  プロキシを構成します。

  :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="[グループ ポリシー設定 2 の状態] ウィンドウ" lightbox="images/atp-gpo-proxy2.png":::


| グループ ポリシー | レジストリ キー | レジストリ エントリ | 値 |
|:---|:---|:---|:---|
| 接続されたユーザー エクスペリエンスとテレメトリ サービス用に認証されたプロキシ使用状況を構成する | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `DisableEnterpriseAuthProxy` | 1 (REG_DWORD) |
| 接続されたユーザー エクスペリエンスと利用統計情報を構成する | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `TelemetryProxyServer` | ```servername:port or ip:port``` <br> <br> 例: ```10.0.0.6:8080``` (REG_SZ) |

## <a name="configure-a-static-proxy-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の静的プロキシを構成する

Microsoft Defender ウイルス対策の[クラウドで提供される保護](cloud-protection-microsoft-defender-antivirus.md)では、新しい脅威や新たな脅威に対してほぼ瞬時に自動化された保護が提供されます。 Defender ウイルス対策がアクティブなマルウェア対策ソリューションである場合、[カスタム インジケーター](manage-indicators.md)には接続が必要であることに注意してください。 [ブロック モードの EDR ](edr-in-block-mode.md)の場合は、Microsoft 以外のソリューションを使用する際の主要なマルウェア対策ソリューションを備えています。

[管理用テンプレート] で使用できるグループ ポリシーを使用して静的プロキシを構成します:

1. **[管理用テンプレート] > [Windowsコンポーネント] > [Microsoft Defender ウイルス対策] > [ネットワークに接続するためのプロキシ サーバーを定義する]**。 

2. これを **[有効]** に 設定し、プロキシ サーバーを定義します。 URL には http:// または https:// が必要です。 https:// でサポートされているバージョンについては、「[Microsoft Defender ウイルス対策更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。

   :::image type="content" source="images/proxy-server-mdav.png" alt-text="Microsoft Defender ウイルス対策のプロキシ サーバー" lightbox="images/proxy-server-mdav.png":::

3. レジストリ キー `HKLM\Software\Policies\Microsoft\Windows Defender` の下で、ポリシーはレジストリ値 `ProxyServer` を REG_SZとして設定します。 

   レジストリ値 `ProxyServer` は、次の文字列形式を取ります:

    ```text
    <server name or ip>:<port>

    For example: http://10.0.0.6:8080
    ```

> [!NOTE]
>
> Microsoft Defender ウイルス対策は、回復力の目的とクラウドで提供される保護のリアルタイム性のために、最後に動作したことが確認されたプロキシをキャッシュします。 プロキシ ソリューションで SSL インスペクションが実行されていないことを確認します。 これにより、セキュリティで保護されたクラウド接続が壊れる可能性があります。 
>
> Microsoft Defender ウイルス対策は、更新プログラムをダウンロードするために、静的プロキシを使用して Windows Update または Microsoft Update に接続することはありません。 代わりに、[構成済みのフォールバック順序](manage-protection-updates-microsoft-defender-antivirus.md)に従って Windows Update または構成済みの内部更新プログラム ソースを使用するように構成されている場合は、システム全体のプロキシを使用します。 
>
> 必要に応じて、**[管理用テンプレート] > [Windowsコンポーネント] > [Microsoft Defender ウイルス対策] > [ネットワークに接続するためのプロキシ自動構成 (.pac)** の定義] を使用できます。 複数のプロキシを使用して高度な構成をセットアップする必要がある場合は、**[管理用テンプレート] > [Windows コンポーネント] > [Microsoft Defender ウイルス対策] > [アドレスの定義]** を使用してプロキシ サーバーをバイパスし、Microsoft Defender ウイルス対策がそれらの宛先にプロキシ サーバーを使用できないようにします。 
>
> PowerShell を `Set-MpPreference` コマンドレットと一緒に使用して、次のオプションを構成できます: 
>
> - ProxyBypass 
> - ProxyPacUrl 
> - ProxyServer 

> [!NOTE]
> プロキシを正しく使用するには、次の 3 つの異なるプロキシ設定を構成します:
>  - Microsoft Defender for Endpoint (MDE)
>  - AV (ウイルス対策)
>  - エンドポイントでの検出と応答 (EDR)

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>netsh コマンドを使用してプロキシ サーバーを手動で構成する

netsh を使用して、システム全体の静的プロキシを構成します。

> [!NOTE]
>
> - これは、既定のプロキシで WinHTTP を使用する Windows サービスを含むすべてのアプリケーションに影響します。</br>
> - トポロジを変更するノート PC (例えば、オフィスから自宅) が netsh で正しく動作しなくなります。 レジストリ ベースの静的プロキシの構成を使用します。

1. 管理者特権でコマンド プロンプトを開きます。
   1. **[スタート]** をクリックし、「**cmd**」と入力します。
   1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter** キーを押します。

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例: `netsh winhttp set proxy 10.0.0.6:8080`

winhttp プロキシをリセットするには、次のコマンドを入力し、**Enter** キーを押します。

```PowerShell
netsh winhttp reset proxy
```

詳細については、「[Netsh コマンドの構文、コンテキスト、およびフォーマット](/windows-server/networking/technologies/netsh/netsh-contexts)」を参照してください。

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>プロキシ サーバー内の Microsoft Defender for Endpoint サービス URL へのアクセスを有効にします。

既定では、プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインのみを許可している場合は、ダウンロード可能なシートに一覧表示されているドメインを許可するドメインのリストに追加します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続可能である必要があるサービスとそれに関連付けられた URL のリストが表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター規則がないことを確認します。 必要に応じて、 *許可* 規則を作成する必要がある場合があります。

<br>

|ドメイン リストのスプレッドシート| 説明|
|---|---|
|商用顧客向けの Microsoft Defender for Endpoint の URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD 向けの Microsoft Defender for Endpoint の URL リスト | Gov/GCC/DoD のお客様向けのサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

プロキシまたはファイアウォールで HTTPS スキャン (SSL 検査) が有効になっている場合は、上記の表に示されているドメインを HTTPS スキャンから除外します。
ファイアウォールで、地理列が WW であるすべての URL を開きます。 地理列が WW ではない行の場合は、特定のデータの場所の URL を開きます。 データの場所の設定を確認するには、「[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/data-retention-settings) のデータ保存場所の確認とデータ保持設定の更新」を参照してください。

> [!NOTE]
> 1803 以前のバージョンで実行されている Windows デバイスには `settings-win.data.microsoft.com` が必要です。  <br>
>
> v20 を含む URL は、バージョン 1803 以降の Windows デバイスを使用している場合にのみ必要です。 たとえば、バージョン 1803 以降を実行し、米国の データ ストレージ地域にオンボードされている Windows デバイスには、`us-v20.events.data.microsoft.com` が必要です。
>

プロキシまたはファイアウォールが Defender for Endpoint センサーとして匿名トラフィックをブロックしていて、システム コンテキストから接続されている場合は、前述の URL で匿名トラフィックが許可されていることを確認します。

> [!NOTE]
> Microsoft はプロキシ サーバーを提供していません。 これらの URL には、構成したプロキシ サーバーを介してアクセスできます。

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) - 以前のバージョンの Windows クライアントまたは Windows Server のプロキシとファイアウォールの要件

プロキシとファイアウォールの構成情報のリストにある情報は、Windows 7 SP1、Windows 8.1、Windows Server 2008 R2* など、以前のバージョンの Windows の Log Analytics エージェント (Microsoft Monitoring Agent と呼ばれることがよくあります) と通信するために必要です。

<br>

****

|エージェント リソース|ポート|方向|HTTP 検査をバイパス|
|---|---|---|---|
|*.ods.opinsights.azure.com|ポート 443|送信|はい|
|*.oms.opinsights.azure.com|ポート 443|送信|はい|
|*.blob.core.windows.net|ポート 443|送信|はい|
|*.azure-automation.net|ポート 443|送信|はい|

> [!NOTE]
> *これらの接続要件は、MMA を必要とする Windows Server 2016 および Windows Server 2012 R2 の以前の Microsoft Defender for Endpoint に適用されます。 新しい統合ソリューションを使用してこれらのオペレーティング システムをオンボードする手順は、[Windows サーバーをオンボード](configure-server-endpoints.md)、または [Microsoft Defender for Endpoint の サーバー移行シナリオ](/microsoft-365/security/defender-endpoint/server-migration)で新しい統合ソリューションに移行する方法です。

> [!NOTE]
> クラウドベースのソリューションとして、IP 範囲が変更される可能性があります。 DNS 解決設定に移動する方法をお勧めします。

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Microsoft Monitoring Agent (MMA) サービス URL の要件を確認する 

 以前のバージョンの Windows で Microsoft Monitoring Agent (MMA) を使用する場合に、特定の環境でワイルドカード (*) の要件を排除するには、次のガイダンスを参照してください。

1. Microsoft Monitoring Agent (MMA) を使用して以前のオペレーティング システムを Defender for Endpoint にオンボードします (詳細については、「[Defender for Endpoint で以前のバージョンの Windows をオンボードする](https://go.microsoft.com/fwlink/p/?linkid=2010326)」および「 [Windows サーバーのオンボード](configure-server-endpoints.md)」を参照してください)。

2. コンピューターが Microsoft 365 Defender ポータルに正常にレポートされていることを確認します。

3. "C:\Program Files\Microsoft Monitoring Agent\Agent" から TestCloudConnection.exe ツールを実行して、接続を検証し、特定のワークスペースに必要な URL を取得します。

4. お使いの地域の要件の完全なリストについては、Microsoft Defender for Endpoint URL のリストを確認してください (サービス URL の[スプレッドシート](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)を参照)。

   :::image type="content" source="images/admin-powershell.png" alt-text="Windows PowerShell の管理者" lightbox="images/admin-powershell.png":::

\*.ods.opinsights.azure.com、\*.oms.opinsights.azure.com、\*.agentsvc.azure-automation.net の URL エンドポイントで使用されるワイルドカード (\*) は、特定のワークスペース ID に置き換えることができます。 ワークスペース ID は、お客様の環境とワークスペースに固有です。 これは、Microsoft 365 Defender ポータル内のテナントの [オンボード] セクションにあります。

\* blob.core.windows.net URL エンドポイントは、テスト結果の "ファイアウォール ルール: \*.blob.core.windows.net" セクションに示されている URL に置き換え可能です。

> [!NOTE]
> Microsoft Defender for Cloud 経由でオンボードする場合は、複数のワークスペースを使用できます。 各ワークスペースからオンボードされたマシンで TestCloudConnection.exe プロシージャを実行する必要があります (ワークスペース間で *.blob.core.windows.net URL に変更があるかどうかを判断するため)。

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Microsoft Defender for Endpoint サービス URL へのクライアント接続を確認する

プロキシ構成が正常に完了したことを確認します。WinHTTP は環境内のプロキシ サーバーを介して検出および通信でき、プロキシ サーバーは Defender for Endpoint サービス URL へのトラフィックを許可します。

1. [Microsoft Defender for Endpoint Client Analyzer ツール](https://aka.ms/mdeanalyzer)を、Defender for Endpoint センサーが実行されている PC にダウンロードします。 ダウンレベル サーバーの場合は、[Microsoft Defender for Endpoint Client Analyzer ツール Beta](https://aka.ms/BetaMDEAnalyzer) をダウンロードできる最新のプレビュー エディションを使用できます。

2. デバイス上の MDEClientAnalyzer.zip の内容を抽出します。

3. 管理者特権でコマンド プロンプトを開きます。
   1. **[スタート]** をクリックし、「**cmd**」と入力します。
   1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

4. 次のコマンドを入力して、**Enter** キーを押します。

    ```PowerShell
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    *HardDrivePath* を MDEClientAnalyzer ツールがダウンロードされたパスに置き換えます。例えば：

    ```PowerShell
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. このツールは、*HardDrivePath* で使用するフォルダーに *MDEClientAnalyzerResult.zip* ファイルを作成して抽出します。

6. *MDATPClientAnalyzerResult.txt* を開き、プロキシ構成の手順を実行して、サーバーの検出とサービス URL へのアクセスを有効にしたことを確認します。

   このツールは、Defender for Endpoint サービス URL の接続を確認します。 Defender for Endpoint クライアントが対話するように構成されていることを確認します。 このツールは、Defender for Endpoint サービスとの通信に使用できる可能性がある URL ごとに、*MDEClientAnalyzerResult.txt* ファイルに結果を出力します。 次に例を示します。

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

少なくとも 1 つの接続オプションが (200) 状態を返した場合、Defender for Endpoint クライアントはこの接続方法を使用してテスト済み URL と正しく通信できます。

ただし、接続を確認した結果が失敗を示している場合は、HTTP エラーが表示されます (「HTTP ステータス コード」を参照)。 次に、「[プロキシ サーバーで Defender for Endpoint サービス URL へのアクセスを有効にする](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)」に示されている表の URL を使用できます。 使用する URL は、オンボーディング手順で選択した地域によって異なります。

> [!NOTE]
> 接続アナライザー ツールのクラウド接続チェックは、攻撃面の縮小ルール "[PSExec および WMI コマンドから生成されたプロセスの作成をブロック](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands)" とは互換性がありません。 接続ツールを実行するには、この規則を一時的に無効にする必要があります。 または、アナライザーの実行中に [ASR 除外](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules)を一時的に追加できます。
>
> TelemetryProxyServer がレジストリまたはグループ ポリシー経由で設定されている場合、Defender for Endpoint はフォールバックし、定義されたプロキシへのアクセスに失敗します。

## <a name="related-articles"></a>関連記事

- [グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する](use-group-policy-microsoft-defender-antivirus.md)
- [Windows デバイスのオンボード](configure-endpoints.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
