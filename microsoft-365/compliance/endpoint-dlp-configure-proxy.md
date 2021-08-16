---
title: エンドポイント DLP のデバイス プロキシとインターネット接続の構成
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: エンドポイント DLP のデバイス プロキシとインターネット接続の構成方法について説明します。
ms.openlocfilehash: a05afb4ac8d5c66e1bbcbba0e8cd8e13b3d8a6d46c73899ea40e5205898036e4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53886039"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a>エンドポイント DLP のデバイス プロキシとインターネット接続の構成

Microsoft エンドポイント DLP は、Microsoft Windows HTTP (WinHTTP) を使用してデータを報告し、Microsoft エンドポイント クラウド サービスと通信します。 埋め込まれた エンドポイント DLP は、LocalSystem アカウントを使用してシステム コンテキストで実行されます。

> [!TIP]
> インターネットへのゲートウェイとして転送プロキシを使用する組織では、ネットワーク保護を使用してプロキシの背後を調査できます。 詳細については、「[転送プロキシの背後で発生する接続イベントの調査](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)」を参照してください。

WinHTTP の構成設定は、Windows Internet （WinINet） のインターネット閲覧用プロキシの設定とは独立しており、以下の自動検出手法でのみプロキシ サーバーを検出することができます。

- 透過プロキシ
- Web プロキシ自動発見プロトコル (WPAD)

> [!NOTE]
> ネットワーク トポロジで透過プロキシまたは WPAD を使用している場合は、特別な構成は必要ありません。 プロキシでの Defender for Endpoint URL 除外の詳細については、「[プロキシ サーバーでエンドポイント DLP クラウド サービス URL へのアクセスを有効にする](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)」を参照してください。

- 手動の静的プロキシの構成:
  - レジストリ ベースの構成
  - netsh コマンドを使用して構成された WinHTTP – 安定したトポロジのデスクトップ (同じプロキシの背後にある企業ネットワークのデスクトップなど) だけに適しています。

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。

インターネットへの接続が許可されていないエンドポイント デバイスの場合は、レジストリ ベースの静的プロキシを構成する必要があります。 これを構成し、Microsoft エンドポイント DLP のみが診断データを報告し、Microsoft エンドポイント クラウド サービスと通信できるようにする必要があります。

静的プロキシは、グループ ポリシー (GP) を使用して構成できます。 グループ ポリシーは次の場所にあります。

1. **[管理用テンプレート]、[Windows コンポーネント]、[データの収集とプレビュー ビルド]、[接続ユーザー エクスペリエンスとテレメトリ サービスでの認証済みプロキシの使用を構成する]** の順に開きます

2. **[有効]** に設定し、**[認証済みプロキシの使用を無効にする]** を選択します。

   ![グループ ポリシー設定の画像 1](../media/atp-gpo-proxy1.png)

3. **[管理用テンプレート]、[Windows コンポーネント]、[データの収集とプレビュー ビルド]、[接続ユーザーのエクスペリエンスと利用統計情報を構成する]** の順に開きます

   プロキシを構成する

   ![グループ ポリシー設定の画像 2](../media/atp-gpo-proxy2.png)

   このポリシーは、レジストリ キー `HKLM\Software\Policies\Microsoft\Windows\DataCollection` の下に 2 つのレジストリ値 `TelemetryProxyServer` を REG_SZ として、`DisableEnterpriseAuthProxy` を REG_DWORD として設定します。

   レジストリ値 TelemetryProxyServer の形式は \<server name or ip\>:\<port\> です。 例: **10.0.0.6:8080**

   レジストリ値 `DisableEnterpriseAuthProxy` を 1に設定する必要があります。

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>「netsh」コマンドを使用してプロキシ サーバーを手動で構成する

netsh を使用して、システム全体の静的プロキシを構成します。

> [!NOTE]
> これは、既定のプロキシで WinHTTP を使用する Windows サービスを含むすべてのアプリケーションに影響します。 - トポロジを変更するノート PC (例えば、オフィスから自宅へ) が netsh で正しく動作しない。 レジストリ ベースの静的プロキシの構成を使用します。

1. 管理者特権でコマンド プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力する
    2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter** キーを押します。

   `netsh winhttp set proxy <proxy>:<port>`

   例: **netsh winhttp set proxy 10.0.0.6:8080**

3. winhttp プロキシをリセットするには、次のコマンドを入力し、**Enter** キーを押します。

   `netsh winhttp reset proxy`

詳細については、「[Netsh コマンドの構文、コンテキスト、およびフォーマット](/windows-server/networking/technologies/netsh/netsh-contexts)」を参照してください。

## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a>プロキシ サーバーのエンドポイント DLP クラウド サービス URL へのアクセスを有効にします。

プロキシまたはファイアウォールが既定ですべてのトラフィックをブロックし、特定のドメインの通過だけを許可している場合は、ダウンロード可能シートに記載されているドメインを許可ドメインのリストに追加します。

この[ダウンロード可能なスプレッドシート](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)には、ネットワークが接続可能である必要があるサービスとそれに関連付けられた URL の一覧が表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター処理ルールがないことを確認する必要があります。そうでない場合、URL 専用の許可ルールを作成する必要があります。

プロキシまたはファイアウォールで HTTPS スキャン (SSL 検査) が有効になっている場合は、上記の表に示されているドメインを HTTPS スキャンから除外します。
エンドポイント DLP がシステム コンテキストから接続しているため、プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、前述の URL で匿名トラフィックが許可されていることを確認してください。

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a>Microsoft クラウド サービス URL へのクライアント接続を確認する

プロキシ構成が正常に完了したことを確認します。WinHTTP は環境内のプロキシ サーバーを介して検出および通信でき、プロキシ サーバーは Defender for Endpoint サービス URL へのトラフィックを許可します。

1. エンドポイント DLP が実行されている PC に、[MDATP クライアント アナライザー ツール](https://aka.ms/mdatpanalyzer)をダウンロードします。
2. デバイス上に MDATPClientAnalyzer.zip のコンテンツを抽出します。
3. 管理者特権でコマンド プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力します。
    1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。
4. 次のコマンドを入力して、**Enter** キーを押します。

   `HardDrivePath\MDATPClientAnalyzer.cmd`

   *HardDrivePath* を、たとえば MDATPClientAnalyzer ツールがダウンロードされたパスに置き換えます

   **C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**

5. ツールによって作成された **MDATPClientAnalyzerResult.zip** _ ファイルを _HardDrivePath* で使用されているフォルダーに解凍します。

6. **MDATPClientAnalyzerResult.txt** を開き、プロキシ構成の手順を実行して、サーバーの検出とサービス URL へのアクセスを有効にしたことを確認します。  このツールは、Defender for Endpoint クライアントが相互作用するように構成されている Defender for Endpoint サービス URL の接続を確認します。 次に、Defender for Endpoint サービスとの通信に使用できる URL ごとに、結果を **MDATPClientAnalyzerResult.txt** ファイルに出力します。 次に例を示します。

   ```DOS
   Testing URL: https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command-line proxy: Doesn't exist
   ```

少なくとも 1 つの接続オプションが (200) ステータスを返した場合、Defender for Endpoint クライアントはこの接続方法を使用してテスト済み URL と正しく通信できます。

ただし、接続を確認した結果が失敗を示している場合は、HTTP エラーが表示されます (「HTTP ステータス コード」を参照)。 次に、「[プロキシ サーバーでエンドポイント DLP クラウド サービス URL へのアクセスを有効にする](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)」に示されている表の URL を使用できます。 使用する URL は、オンボーディング手順で選択した地域によって異なります。

> [!NOTE]
>
> 接続アナライザー ツールは、ASR ルールと互換性がありません [PSExec および WMI コマンドから発生するプロセスの作成をブロックします](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。 接続ツールを実行するには、この規則を一時的に無効にする必要があります。
>
> TelemetryProxyServer がレジストリまたはグループ ポリシー経由で設定されている場合、Defender for Endpoint は、定義されたプロキシにアクセスできないと、ダイレクトにフォールバックします。関連トピック:
>
> - Windows 10 デバイスのオンボード
> - Microsoft エンドポイント DLP のオンボード問題のトラブルシューティング

## <a name="see-also"></a>関連項目

- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 マシン用のオンボーディングツールとメソッド](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD に参加しているデバイス](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
