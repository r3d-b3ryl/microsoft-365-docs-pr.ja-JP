---
title: Microsoft Defender for Endpointでデバイスで応答アクションを実行する
description: デバイスの分離、調査パッケージの収集、タグの管理、AV スキャンの実行、アプリの実行の制限など、デバイスに対して応答アクションを実行します。
keywords: 応答、分離、デバイスの分離、調査パッケージの収集、アクション センター、制限、タグの管理、AV スキャン、アプリの制限
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 65799821ab4d6b2ad8076c68c9991074465d1435
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387223"
---
# <a name="take-response-actions-on-a-device"></a>デバイスの対応措置を講じる

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint プラン 1 と 2](defender-endpoint-plan-1-2.md)
- [Microsoft Defender for Business](/microsoft-365/security/defender-business/mdb-overview)

[!INCLUDE [Prerelease information](../../includes/prerelease.md)]

検出された攻撃に迅速に対応するには、デバイスを分離するか、調査パッケージを収集します。 デバイスでアクションを実行した後、アクション センターでアクティビティの詳細を確認できます。

応答アクションは、特定のデバイス ページの上部に沿って実行され、次のものが含まれます。

- タグの管理
- 自動調査を開始する
- ライブ応答セッションを開始する
- 調査パッケージの収集
- ウイルス対策スキャンの実行
- アプリの実行を制限する
- デバイスの分離
- デバイスを含む
- 脅威のエキスパートに相談する
- アクション センター

[![応答アクションの画像。](images/response-actions.png)](images/response-actions.png#lightbox)

> [!IMPORTANT]
> [Defender for Endpoint Plan 1](defender-endpoint-plan-1.md) と[Microsoft Defender for Business](../defender-business/mdb-overview.md)には、次の手動応答アクションのみが含まれます。
> - ウイルス対策スキャンの実行
> - デバイスの分離
> - ファイルを停止して検疫する
> - ファイルをブロックまたは許可するインジケーターを追加する サブスクリプションには、この記事で説明したすべての応答アクションを持つ Defender for Endpoint Plan 2 を含める必要があります。

 デバイス ページは、次のいずれかのビューから確認できます。

- **セキュリティ操作ダッシュボード** - リスクがあるデバイス カードからデバイス名を選択します。
- **アラート キュー** - アラート キューからデバイス アイコンの横にあるデバイス名を選択します。
- **デバイスの一覧** - デバイスの一覧からデバイス名の見出しを選択します。
- **検索ボックス** - ドロップダウン メニューから [デバイス] を選択し、デバイス名を入力します。

> [!IMPORTANT]
> - これらの応答アクションは、Windows 10 バージョン 1703 以降、Windows 11、Windows Server 2019、Windows Server 2022 のデバイスでのみ使用できます。
> - Windows 以外のプラットフォームの場合、応答機能 (デバイスの分離など) はサード パーティの機能に依存します。
> - Microsoft ファースト パーティ エージェントの場合は、OS の最小要件については、各機能の下にある 「詳細情報」のリンクを参照してください。

## <a name="manage-tags"></a>タグの管理

タグを追加または管理して、論理グループの所属を作成します。 デバイス タグはネットワークの適切なマッピングをサポートし、さまざまなタグを添付してコンテキストをキャプチャし、インシデントの一部として動的リストを作成できるようにします。

デバイスタグ付けの詳細については、「 [デバイス タグの作成と管理](machine-tags.md)」を参照してください。

## <a name="initiate-automated-investigation"></a>自動調査を開始する

必要に応じて、デバイスで新しい汎用自動調査を開始できます。 調査の実行中、デバイスから生成されたその他のアラートは、その調査が完了するまで、進行中の自動調査に追加されます。 さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。

自動調査の詳細については、「 [自動調査の概要](automated-investigations.md)」を参照してください。

## <a name="initiate-live-response-session"></a>ライブ応答セッションを開始する

ライブ応答は、リモート シェル接続を使用してデバイスに瞬時にアクセスできる機能です。 これにより、詳細な調査作業を行い、即座に対応アクションを実行して、特定された脅威をリアルタイムで迅速に含めることができるようになります。

ライブ応答は、フォレンジック データの収集、スクリプトの実行、分析のための疑わしいエンティティの送信、脅威の修復、新たな脅威の予防的な捜索を可能にすることで、調査を強化するように設計されています。

ライブ応答の詳細については、「ライブ応答 [を使用してデバイス上のエンティティを調査する」を](live-response.md)参照してください。

## <a name="collect-investigation-package-from-devices"></a>デバイスから調査パッケージを収集する

調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。 調査パッケージを収集することで、デバイスの現在の状態を特定し、攻撃者が使用するツールと手法をさらに理解できます。

> [!IMPORTANT]
> これらのアクションは、macOS または Linux を実行しているデバイスでは現在サポートされていません。 ライブ応答を使用してアクションを実行します。 ライブ応答の詳細については、「ライブ応答[を使用してデバイス上のエンティティを調査する」を](live-response.md)参照してください。

パッケージ (Zip ファイル) をダウンロードし、デバイスで発生したイベントを調査するには

1. デバイス ページの上部にある応答アクションの行から [ **調査パッケージの収集** ] を選択します。

2. テキスト ボックスで、このアクションを実行する理由を指定します。 **[確認]** を選択します。

3. zip ファイルがダウンロードされます

別の方法:

1. デバイス ページの [応答アクション] セクションから [ **アクション センター** ] を選択します。

   :::image type="content" source="images/action-center-package-collection.png" alt-text="アクション センター オプション" lightbox="images/action-center-package-collection.png":::

2. アクション センターのポップアップで、zip ファイルをダウンロード **するために使用できるパッケージ コレクション パッケージ** を選択します。

   :::image type="content" source="images/collect-package.png" alt-text="パッケージのダウンロード オプション" lightbox="images/collect-package.png":::

パッケージには、次のフォルダーが含まれています。

|フォルダー|説明|
|---|---|
|Autoruns|既知の自動開始エントリ ポイント (ASEP) のレジストリの内容を表すファイルのセットが含まれています。デバイス上の攻撃者の持続性を識別するのに役立ちます。 <p> <div class="alert"><b>メモ：</b> レジストリ キーが見つからない場合、ファイルには次のメッセージが含まれます:"エラー: システムは、指定したレジストリ キーまたは値を見つけることができませんでした。<div>|
|インストールされているプログラム|この.CSV ファイルには、デバイスに現在インストールされているものを識別するのに役立つインストール済みプログラムの一覧が含まれています。 詳細については、「 [Win32_Product クラス](https://go.microsoft.com/fwlink/?linkid=841509)」を参照してください。|
|ネットワーク接続|このフォルダーには、疑わしい URL、攻撃者のコマンドと制御 (C&C) インフラストラクチャ、横方向の移動、またはリモート接続への接続を識別するのに役立つ接続情報に関連する一連のデータ ポイントが含まれています。 <ul><li>ActiveNetConnections.txt: プロトコルの統計情報と現在の TCP/IP ネットワーク接続を表示します。 プロセスによって行われた疑わしい接続を検索する機能を提供します。</li><li>Arp.txt: すべてのインターフェイスの現在のアドレス解決プロトコル (ARP) キャッシュ テーブルを表示します。 ARP キャッシュは、内部攻撃の実行に使用された可能性のあるネットワーク上の侵害されたシステムまたは疑わしいシステムがネットワーク上の他のホストを明らかにすることができます。</il><li>DnsCache.txt: DNS クライアント リゾルバー キャッシュの内容を表示します。これには、ローカルホスト ファイルから事前に読み込まれたエントリと、コンピューターによって解決された名前クエリの最近取得したリソース レコードの両方が含まれます。 これは、疑わしい接続を識別するのに役立ちます。</li><li>IpConfig.txt: すべてのアダプターの完全な TCP/IP 構成を表示します。 アダプターは、インストールされているネットワーク アダプターなどの物理インターフェイス、またはダイヤルアップ接続などの論理インターフェイスを表すことができます。</li><li>FirewallExecutionLog.txtと pfirewall.log</li></ul><p><div class="alert"><b>メモ：</b> 調査パッケージに含まれるように、pfirewall.log ファイルは %windir%\system32\logfiles\firewall\pfirewall.log に存在する必要があります。 ファイアウォール ログ ファイルの作成の詳細については、「[高度なセキュリティ ログを使用してWindows Defenderファイアウォールを構成](/windows/security/threat-protection/windows-firewall/configure-the-windows-firewall-log)する」を参照してください。<div>|
|プリフェッチ ファイル|Windows プリフェッチ ファイルは、アプリケーションの起動プロセスを高速化するように設計されています。 これは、システムで最近使用されたすべてのファイルを追跡し、削除された可能性があるアプリケーションのトレースを検索するために使用できますが、プリフェッチ ファイルの一覧にはまだ見つかります。 <ul><li>プリフェッチ フォルダー: `%SystemRoot%\Prefetch`. 注: プリフェッチ ファイルを表示するには、プリフェッチ ファイル ビューアーをダウンロードすることをお勧めします。</li><li>PrefetchFilesList.txt: プリフェッチ フォルダーへのコピーエラーがあったかどうかを追跡するために使用できる、コピーされたすべてのファイルの一覧が含まれます。</li></ul>|
|プロセス|実行中のプロセスを一覧表示する.CSV ファイルを含み、デバイスで実行されている現在のプロセスを識別する機能を提供します。 これは、疑わしいプロセスとその状態を識別するときに役立ちます。|
|スケジュールされたタスク|スケジュールされたタスクを一覧表示する.CSV ファイルが含まれています。このファイルを使用すると、選択したデバイスで自動的に実行されるルーチンを識別し、自動的に実行するように設定された疑わしいコードを検索できます。|
|セキュリティ イベント ログ|システムの監査ポリシーによって指定されたログインまたはログアウト アクティビティのレコード、またはその他のセキュリティ関連イベントを含むセキュリティ イベント ログが含まれます。 <p><div class="alert"><b>メモ：</b> イベント ビューアーを使用してイベント ログ ファイルを開きます。</div>|
|サービス|サービスとその状態を一覧表示する.CSV ファイルが含まれています。|
|Windows Server メッセージ ブロック (SMB) セッション|ファイル、プリンター、シリアル ポートへの共有アクセスと、ネットワーク上のノード間のその他の通信を一覧表示します。 これは、データ流出または横移動を識別するのに役立ちます。 <p> SMBInboundSession と SMBOutboundSession のファイルが含まれています。 <p> <div class="alert"><b>メモ：</b> セッション (受信または送信) がない場合は、SMB セッションが見つからないことを示すテキスト ファイルが表示されます。</div>|
|システム情報|OS バージョンやネットワーク カードなどのシステム情報を一覧表示するSystemInformation.txt ファイルが含まれています。|
|Temp ディレクトリ|システム内のすべてのユーザーの %Temp% にあるファイルを一覧表示するテキスト ファイルのセットが含まれています。 <p> これにより、攻撃者がシステムにドロップした可能性のある疑わしいファイルを追跡できます。 <p> <div class="alert"><b>メモ：</b> ファイルに "指定されたパスが見つかりません" というメッセージが含まれている場合は、このユーザーの一時ディレクトリがないことを意味し、ユーザーがシステムにログインしなかったことが原因である可能性があります。</div>|
|ユーザーとグループ|それぞれがグループとそのメンバーを表すファイルの一覧を提供します。|
|WdSupportLogs|MpCmdRunLog.txtとMPSupportFiles.cabを提供します  <p> <div class="alert"><b>メモ：</b>このフォルダーは、2020 年 2 月の更新プログラムロールアップ以降がインストールされた、Windows 10 バージョン 1709 以降でのみ作成されます。 <ul><li>Win10 1709 (RS3) ビルド 16299.1717: [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</li><li>Win10 1803 (RS4) ビルド 17134.1345: [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</li><li>Win10 1809 (RS5) ビルド 17763.1075: [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</li><li>Win10 1903/1909 (19h1/19h2) ビルド 18362.693 および 18363.693: [KB4535996](https://support.microsoft.com/help/4535996/windows-10-update-kb4535996)</li></ul> </div>|
|CollectionSummaryReport.xls|このファイルは調査パッケージコレクションの概要であり、データ ポイントの一覧、データの抽出に使用されるコマンド、実行状態、エラーが発生した場合のエラー コードが含まれます。 このレポートを使用して、パッケージに必要なすべてのデータが含まれているかどうかを追跡し、エラーが発生したかどうかを特定できます。|
|

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>デバイスで Microsoft Defender ウイルス対策スキャンを実行する

調査または応答プロセスの一環として、ウイルス対策スキャンをリモートで開始して、侵害されたデバイスに存在する可能性のあるマルウェアを特定して修復することができます。

> [!IMPORTANT]
> - このアクションは、macOS と Linux では現在サポートされていません。 ライブ応答を使用してアクションを実行します。 ライブ応答の詳細については、「ライブ応答[を使用してデバイス上のエンティティを調査する」を](live-response.md)参照してください。
> - Microsoft Defender ウイルス対策スキャンは、Microsoft Defender ウイルス対策がアクティブなウイルス対策ソリューションであるかどうかに関係なく、他のウイルス対策ソリューションと共に実行できます。 Microsoft Defender ウイルス対策はパッシブ モードにすることができます。 詳細については、「[Microsoft Defender ウイルス対策の互換性](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility)」を参照してください。

**[ウイルス対策スキャンの実行**] を選択した後、実行するスキャンの種類 (クイックまたはフル) を選択し、スキャンを確認する前にコメントを追加します。

:::image type="content" source="images/run-antivirus.png" alt-text="クイック スキャンまたはフル スキャンを選択してコメントを追加する通知" lightbox="images/run-antivirus.png":::

アクション センターにスキャン情報が表示され、デバイスのタイムラインには、デバイスにスキャン アクションが送信されたことを反映した新しいイベントが含まれます。 Microsoft Defender ウイルス対策アラートには、スキャン中に表示されたすべての検出が反映されます。

> [!NOTE]
> Defender for Endpoint 応答アクションを使用してスキャンをトリガーする場合、Microsoft Defender ウイルス対策 'ScanAvgCPULoadFactor' の値は引き続き適用され、スキャンの CPU への影響が制限されます。
> ScanAvgCPULoadFactor が構成されていない場合、既定値はスキャン中の最大 CPU 負荷の 50% の制限です。
> 詳細については、「 [configure-advanced-scan-types-microsoft-defender-antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus)」を参照してください。

## <a name="restrict-app-execution"></a>アプリの実行を制限する

悪意のあるプロセスを停止して攻撃を封じ込めることに加えて、デバイスをロックダウンし、悪意のある可能性のあるプログラムの後続の試行が実行されないようにすることもできます。

> [!IMPORTANT]
> - この操作は、Windows 10 バージョン 1709 以降、Windows 11、Windows Server 2019 以降のデバイスで使用できます。 
> - この機能は、組織で Microsoft Defender ウイルス対策を使用している場合に使用できます。
> - このアクションは、Windows Defenderアプリケーション制御コード整合性ポリシーの形式と署名の要件を満たす必要があります。 詳細については、「 [コード整合性ポリシーの形式と署名](/windows/security/threat-protection/windows-defender-application-control/use-code-signing-to-simplify-application-control-for-classic-windows-applications)」を参照してください。

アプリケーションの実行を制限するために、Microsoft 発行の証明書によって署名されている場合にのみファイルを実行できるようにするコード整合性ポリシーが適用されます。 この制限方法は、攻撃者が侵害されたデバイスを制御し、さらに悪意のあるアクティビティを実行するのを防ぐのに役立ちます。

> [!NOTE]
> アプリケーションの制限をいつでも実行から取り消すことができるようになります。 デバイス ページのボタンが [ **アプリの制限の削除]** に変わり、アプリの実行を制限するのと同じ手順を実行します。

デバイス ページで **[アプリの実行を制限** する] を選択したら、コメントを入力し、[ **確認**] を選択します。 アクション センターにスキャン情報が表示され、デバイスのタイムラインに新しいイベントが含まれます。

:::image type="content" source="images/restrict-app-execution.png" alt-text="アプリケーション制限の通知" lightbox="images/restrict-app-execution.png":::

### <a name="notification-on-device-user"></a>デバイス ユーザーに対する通知

アプリが制限されると、次の通知が表示され、アプリの実行が制限されていることをユーザーに通知します。

:::image type="content" source="images/atp-app-restriction.png" alt-text="アプリケーション制限メッセージ" lightbox="images/atp-app-restriction.png":::

> [!NOTE]
> 通知は、Windows Server 2016および Windows Server 2012 R2 では使用できません。

## <a name="isolate-devices-from-the-network"></a>ネットワークからデバイスを分離する

攻撃の重大度とデバイスの機密性に応じて、デバイスをネットワークから分離することもできます。 このアクションは、攻撃者が侵害されたデバイスを制御し、データ流出や横移動などのさらなるアクティビティを実行するのを防ぐのに役立ちます。

> [!IMPORTANT]
> - ネットワークからのデバイスの分離は、macOS または Linux を実行しているデバイスでは現在サポートされていません。 ライブ応答を使用してアクションを実行します。 ライブ応答の詳細については、「ライブ応答 [を使用してデバイス上のエンティティを調査する」を](live-response.md)参照してください。
> - 完全な分離は、Windows 11、Windows 10、バージョン 1703 以降、Windows Server 2022、Windows Server 2019、Windows Server 2016を実行しているデバイスで使用できます。
> - 選択的分離は、Windows 10、バージョン 1709 以降、およびWindows 11を実行しているデバイスで使用できます。
> - デバイスを分離する場合は、特定のプロセスと宛先のみが許可されます。 そのため、完全な VPN トンネルの背後にあるデバイスは、デバイスが分離された後、Microsoft Defender for Endpoint クラウド サービスに到達できません。 Microsoft Defender for Endpointおよび Microsoft Defender ウイルス対策クラウドベースの保護関連トラフィックには、分割トンネリング VPN を使用することをお勧めします。

このデバイス分離機能は、侵害されたデバイスをネットワークから切断すると同時に、Defender for Endpoint サービスへの接続を保持します。デバイスの監視は続行されます。

Windows 10バージョン 1709 以降では、ネットワーク分離レベルをより細かく制御できます。 Outlook、Microsoft Teams、およびSkype for Business接続 (a.k.a "選択的分離") を有効にすることもできます。

> [!NOTE]
> デバイスはいつでもネットワークに再接続できます。 デバイス ページのボタンが [ **分離からのリリース**] に変わり、デバイスの分離と同じ手順を実行します。

デバイス ページで **[デバイスの分離** ] を選択したら、コメントを入力して [ **確認**] を選択します。 アクション センターにスキャン情報が表示され、デバイスのタイムラインに新しいイベントが含まれます。

:::image type="content" source="images/isolate-device.png" alt-text="分離されたデバイスの詳細ページ" lightbox="images/isolate-device.png":::

> [!NOTE]
> デバイスは、ネットワークから分離されている場合でも、Defender for Endpoint サービスに接続されたままになります。 Outlook とSkype for Business通信を有効にすることを選択した場合は、デバイスの分離中にユーザーと通信できるようになります。

### <a name="notification-on-device-user"></a>デバイス ユーザーに対する通知

デバイスが分離されると、次の通知が表示され、デバイスがネットワークから分離されていることをユーザーに通知します。

:::image type="content" source="images/atp-notification-isolate.png" alt-text="ネットワーク接続メッセージなし" lightbox="images/atp-notification-isolate.png":::

## <a name="contain-devices-from-the-network"></a>ネットワークからデバイスを格納する
 
> [!NOTE]
> 含まれる機能は現在パブリック プレビュー段階です。 Microsoft 365 Defender プレビュー リリースの新機能について学習し、プレビュー エクスペリエンスを有効にして今後の機能を最初に試す方法については、「[Micrsoft 365 Defender のプレビュー機能](../defender/preview.md)」を参照してください。

侵害された、または侵害された可能性のある非管理対象デバイスを特定した場合は、そのデバイスをネットワークから含めることができます。 デバイスを含めると、オンボードされたデバイスMicrosoft Defender for Endpoint、そのデバイスとの送受信通信がブロックされます。 このアクションは、セキュリティ運用アナリストが侵害されたデバイスの脅威を検出、識別、修復するときに、近隣のデバイスが侵害されるのを防ぐのに役立ちます。

> [!NOTE]
> "包含" デバイスとの送受信通信のブロックは、オンボードされたMicrosoft Defender for Endpoint Windows 10および Windows Server 2019 以降のデバイスでサポートされています。

### <a name="how-to-contain-a-device"></a>デバイスを含める方法
 
1. **[デバイス インベントリ**] ページに移動し、含めるデバイスを選択します。

2. デバイス ポップアップの [アクション] メニューから [デバイスを **含む** ] を選択します。

:::image type="content" alt-text="デバイスが含まれているポップアップ メッセージのスクリーンショット。" source="../../media/defender-endpoint/contain_device.png" lightbox="../../media/defender-endpoint/contain_device.png":::

3. デバイスを含むポップアップで、コメントを入力し、[ **確認**] を選択します。

:::image type="content" alt-text="デバイスを含むメニュー項目のスクリーンショット。" source="../../media/defender-endpoint/contain_device_popup.png" lightbox="../../media/defender-endpoint/contain_device_popup.png":::

### <a name="contain-a-device-from-the-device-page"></a>デバイス ページからデバイスを含む

デバイスは、アクション バーから [デバイスを含む] を選択して **、デバイス** ページから含めることもできます。

:::image type="content" alt-text="デバイス ページの [デバイスを含む] メニュー項目のスクリーンショット。" source="../../media/defender-endpoint/contain_device_page.png" lightbox="../../media/defender-endpoint/contain_device_page.png":::

> [!NOTE]
> 新しく含まれるデバイスの詳細がオンボードされたデバイスに到達するまでに最大 5 分Microsoft Defender for Endpointかかることがあります。

> [!IMPORTANT]
> - 包含デバイスが IP アドレスを変更した場合、オンボードされているすべてのデバイスMicrosoft Defender for Endpointこれを認識し、新しい IP アドレスとの通信のブロックを開始します。 元の IP アドレスはブロックされなくなります (これらの変更を確認するには、最大 5 分かかる場合があります)。  
> - 包含デバイスの IP がネットワーク上の別のデバイスによって使用されている場合は、デバイスの格納中に警告が表示され、高度なハンティングへのリンクが表示されます (事前設定されたクエリを使用)。 これにより、同じ IP を使用して他のデバイスに可視性が提供され、デバイスの格納を続行する場合に意識的な決定を下すのに役立ちます。
> - 包含デバイスがネットワーク デバイスである場合、警告が表示され、ネットワーク接続の問題が発生する可能性があることを示すメッセージが表示されます (たとえば、既定のゲートウェイとして機能するルーターが含まれています)。 この時点で、デバイスを含めるかどうかを選択できます。

デバイスを含めた後、動作が期待どおりにない場合は、Defender for Endpoint オンボード デバイスで基本フィルター エンジン (BFE) サービスが有効になっていることを確認します。

### <a name="stop-containing-a-device"></a>デバイスの格納を停止する

デバイスの格納はいつでも停止できます。

1. **デバイス インベントリ** からデバイスを選択するか、デバイス ページを開きます。

2. アクション メニュー **から [包含からのリリース** ] を選択します。 この操作により、このデバイスのネットワークへの接続が復元されます。

## <a name="consult-a-threat-expert"></a>脅威のエキスパートに相談する

侵害された可能性のあるデバイスや既に侵害されたデバイスに関するより多くの分析情報については、Microsoft の脅威の専門家に問い合わせてください。 Microsoft 脅威エキスパートは、適時かつ正確な対応のために、Microsoft 365 Defender内から直接関与させることができます。 専門家は、侵害される可能性のあるデバイスに関する分析情報だけでなく、複雑な脅威、取得する標的型攻撃通知、またはアラートに関する詳細情報やポータル ダッシュボードに表示される脅威インテリジェンス コンテキストが必要な場合の理解を深めるためにも、分析情報を提供します。

詳細については、 [Microsoft Threat Expert](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) に問い合わせてください。

## <a name="check-activity-details-in-action-center"></a>アクション センターでアクティビティの詳細を確認する

**アクション センター** は、デバイスまたはファイルで実行されたアクションに関する情報を提供します。 次の詳細を表示できます。

- 調査パッケージコレクション
- ウイルス対策スキャン
- アプリの制限
- デバイスの分離

その他のすべての関連する詳細 (送信日時、ユーザーの送信、アクションが成功または失敗した場合など) も表示されます。

:::image type="content" source="images/action-center-details.png" alt-text="情報を含むアクション センター" lightbox="images/action-center-details.png":::


## <a name="see-also"></a>関連項目

- [ファイルの対応措置を講じる](respond-file-alerts.md)
- [Microsoft Defender for Endpoint プラン 1 の手動応答アクション](defender-endpoint-plan-1.md#manual-response-actions)
- [レポートの不正確さ](/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
