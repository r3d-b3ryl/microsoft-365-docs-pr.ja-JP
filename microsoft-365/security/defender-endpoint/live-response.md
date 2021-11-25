---
title: Microsoft Defender for Endpoint でライブ応答を使用してデバイス上のエンティティを調査する
description: セキュリティで保護されたリモート シェル接続を使用してデバイスにアクセスし、調査作業を行い、デバイスに対してリアルタイムで即座に対応アクションを実行します。
keywords: リモート, シェル, 接続, ライブ, 応答, リアルタイム, コマンド, スクリプト, 修復, ハント, エクスポート, ログ, ドロップ, ダウンロード, ファイル,
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
ms.openlocfilehash: 1e5eafd86d3ce052655a72668bfc17083dff14f4
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166220"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>ライブ応答を使用してデバイス上のエンティティを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

ライブ応答により、セキュリティ運用チームはリモート シェル接続を使用してデバイス (マシンとも呼ばれます) に瞬時にアクセスできます。 これにより、詳細な調査作業を行い、即座に対応アクションを実行して、特定された脅威をリアルタイムで迅速に含めることができるようになります。

ライブ応答は、セキュリティ運用チームがフォレンジック データの収集、スクリプトの実行、分析のための疑わしいエンティティの送信、脅威の修復、新たな脅威の予防的な捜索を行えるようにして、調査を強化するように設計されています。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

ライブ 応答を使用すると、アナリストは次のすべてのタスクを実行できます。

- 基本的なコマンドと高度なコマンドを実行して、デバイスで調査作業を行います。
- マルウェア サンプルや PowerShell スクリプトの結果などのファイルをダウンロードします。
- バックグラウンドでファイルをダウンロードします (new!)。
- PowerShell スクリプトまたは実行可能ファイルをライブラリにアップロードし、テナント レベルからデバイスで実行します。
- 修復アクションを実行または元に戻します。

## <a name="before-you-begin"></a>はじめに

デバイスでセッションを開始する前に、次の要件を満たしていることを確認してください。

- **サポートされているバージョンの Windows** を実行していることを確認します。

  デバイスは、次のいずれかのバージョンの Windows を実行している必要があります

  - **Windows 10 & 11**
    - [バージョン 1909](/windows/whats-new/whats-new-windows-10-version-1909) 以降
    - [バージョン 1903](/windows/whats-new/whats-new-windows-10-version-1903)と[KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [バージョン1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809)と [kb4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [ 1803 (バージョンRS 4)](/windows/whats-new/whats-new-windows-10-version-1803) と [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [バージョン1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) と[KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **macOS** - パブリック プレビューにのみ適用され、最低限必要なバージョン: 101.43.84 
  
  - **Linux** - パブリック プレビューにのみ適用され、最低限必要なバージョン: 101.45.13 
    
  - **Windows Server 2012 R2** - と [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)
  
  - **Windows Server 2016** - と [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2019**
    - バージョン 1903 以降 ( [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)) 以降
    - バージョン 1809 ( [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818))
    
  - **Windows Server 2022**

       

- **[詳細設定] ページからライブ応答を有効にします**。

  [ [の高度な機能の設定]](advanced-features.md) ページで、ライブ応答機能を有効にする必要があります。

  > [!NOTE]
  > これらの設定を編集できるのは、セキュリティ管理ロールまたはグローバル管理者ロールを持つユーザーのみです。

- **詳細設定ページ** (推奨) からサーバーのライブ応答を有効にします。

  > [!NOTE]
  > これらの設定を編集できるのは、セキュリティ管理ロールまたはグローバル管理者ロールを持つユーザーのみです。

- **デバイスに Automation Remediation レベルが割り当てられていることを確認**。

  少なくとも、特定のデバイス グループの最小修復レベルを有効にする必要があります。 そうしないと、そのグループのメンバーに対するライブ応答セッションを確立できません。

  次のエラーが表示されます。

  ![エラー メッセージの画像。](images/live-response-error.png)

- **ライブ応答の署名されていないスクリプト実行** を有効にします (省略可能)。

  >[!IMPORTANT]
  >署名の検証は、PowerShell スクリプトにのみ適用されます。 

  > [!WARNING]
  > 署名されていないスクリプトの使用を許可すると、脅威にさらされる可能性があります。

  署名されていないスクリプトは、脅威にさらされる可能性があるため、実行することはお勧めしません。 ただし、それらを使用する必要がある場合は、 [の [高度な機能の設定]](advanced-features.md) ページで設定を有効にする必要があります。

- **適切なアクセス許可があることを確認します**。

  適切なアクセス許可を使用してプロビジョニングされたユーザーのみがセッションを開始できます。 ロールの割り当ての詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

  > [!IMPORTANT]
  > ライブラリにファイルをアップロードするオプションは、"セキュリティ設定の管理" アクセス許可を持つユーザーのみが使用できます。
  > 委任されたアクセス許可のみを持つユーザーの場合、ボタンは灰色表示されます。

  付与されているロールに応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。 ユーザーのアクセス許可は RBAC カスタム ロールによって制御されます。

## <a name="live-response-dashboard-overview"></a>ライブ応答ダッシュボードの概要

デバイスでライブ応答セッションを開始すると、ダッシュボードが開きます。 ダッシュボードには、次のようなセッションに関する情報が表示されます。

- セッションを作成したユーザー
- セッションが開始されたとき
- セッションの継続時間

ダッシュボードでは、次の項目にもアクセスできます。

- セッションを切断する
- ライブラリにファイルをアップロードする
- コマンドコンソール
- コマンド ログ

## <a name="initiate-a-live-response-session-on-a-device"></a>デバイスでライブ応答セッションを開始する

1. Defender ポータルMicrosoft 365サインインします。

2. **Endpoints > Device inventory** に移動し、調査するデバイスを選択します。 [デバイス] ページが開きます。

3. [**ライブ応答セッションの開始**]を選択して、ライブ応答セッションを起動します。 コマンド コンソールが表示されます。 セッションがデバイスに接続するまで待ちます。

4. 組み込みコマンドを使用して調査作業を行います。 詳細については、「[ライブ応答コマンド](#live-response-commands)」を参照してください。

5. 調査が完了したら、[**セッション切断**] を選択し、[**確認**]を選択します。

## <a name="live-response-commands"></a>ライブ応答コマンド

付与されているロールに応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。 ユーザーのアクセス許可は RBAC カスタム ロールによって制御されます。 ロールの割り当ての詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

> [!NOTE]
> ライブ応答はクラウドベースの対話型シェルです。そのため、エンド ユーザーとターゲット デバイス間のネットワーク品質とシステム負荷に応じて、特定のコマンド エクスペリエンスが応答時間で異なる場合があります。

### <a name="basic-commands"></a>基本コマンド

次のコマンドは、**基本的な** ライブ応答コマンド実行する権限が付与されているユーザー ロールで使用できます。 ロールの割り当ての詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

<br>

****
| コマンド  | 説明  | Windows および Windows Server  | macOS  | Linux  |
|---|---|---|---|---|
| cd  | 現在のディレクトリを変更します。  | Y  | Y | Y |
| cls  | コンソール画面をクリアします。  | Y  | Y  | Y  |
| connect  | デバイスへのライブ応答セッションを開始します。  | Y  | Y  | Y  |
| connections  | すべてのアクティブな接続を表示します。  | Y  | N | N |
| dir  | ディレクトリ内のファイルとサブディレクトリの一覧を表示します。  | Y  | Y  |Y  |
| drivers  | デバイスにインストールされているすべてのドライバーが表示されます。  | Y |  N | N  |
| fg `<command ID>`  | 指定したジョブをフォアグラウンドのフォアグラウンドに配置し、現在のジョブにします。  注: pid ではなくジョブから使用可能な 'コマンド ID' を取得します。  | Y  | Y  | Y  |
| fileinfo  | ファイルに関する情報を取得します。  |Y  | Y  | Y  |
| findfile  | デバイス上の特定の名前でファイルを検索します。  | Y | Y  | Y  |
| Getfile <file_path>  | ファイルをダウンロードします。  | Y  | Y  | Y  |
| help  | ライブ応答コマンドのヘルプ情報を提供します。  |Y  | Y | Y  |
| jobs  | 現在実行中のジョブ、その ID と状態を表示します。  | Y  | Y | Y |
| persistence  | デバイス上のすべての既知の永続化メソッドを表示します。  | Y  | N | N |
| processes  | デバイスで実行されているすべてのプロセスが表示されます。  | Y  | Y  | Y  |
| registry  | レジストリ値を表示します。  | Y  | N | N |
| scheduledtasks  | デバイス上のすべてのスケジュールされたタスクを表示します。  | Y | N | N |
| services  | デバイス上のすべてのサービスを表示します。  | Y  | N | N |
| trace  | ターミナルのログ モードをデバッグに設定します。  | Y  | Y  |Y  |

### <a name="advanced-commands"></a>高度なコマンド

次のコマンドは、**高度な** ライブ応答コマンド実行する権限が付与されているユーザー ロールで使用できます。 ロールの割り当ての詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

<br>

****

| コマンド  | 説明  | Windows および Windows Server  | macOS  | Linux  |
|---|---|---|---|---|
| analyze  | さまざまな解析エンジンを使用してエンティティを分析し、判定に達します。  | Y  | N  | N  |
| collect  | コンピューターからフォレンジクス パッケージを収集します  | N  | Y  | Y  |
| isolate  | Defender for Endpoint サービスへの接続を維持しながら、デバイスをネットワークから切断します  | N  | Y  | N  |
| release  | ネットワーク分離からデバイスを解放する  | N  | Y  | N  |
| run  | デバイス上のライブラリから PowerShell スクリプトを実行します。  | Y  | Y  | Y  |
| library  | ライブ応答ライブラリにアップロードされたファイルを一覧表示します。  | Y  | Y  | Y  |
| putfile  | ライブラリからデバイスにファイルを書き込みます。 ファイルは作業フォルダーに保存され、デバイスが既定で再起動すると削除されます。  | Y  | Y  | Y  |
| remediate  | デバイス上のエンティティを修復します。 修復アクションは、エンティティの種類によって異なります: ファイル: プロセスの削除: 停止、イメージ ファイルの削除 サービス: 停止、イメージ ファイルの削除 レジストリ エントリ: スケジュールされたタスクの削除: スタートアップ フォルダー項目の削除: ファイルの削除 注意: このコマンドには前提条件のコマンドがあります。 -auto コマンドを修復と組み合わせて使用して、前提条件のコマンドを自動的に実行できます。  | Y  | Y  | Y  |
| scan  | Defender for Endpoint サービスへの接続を維持しながら、デバイスをネットワークから切断します  | N  | Y  | Y  |
| undo  | 修復されたエンティティを復元します。  | Y  | Y  | Y  |


## <a name="use-live-response-commands"></a>ライブ応答コマンドを使用する

コンソールで使用できるコマンドは、[Windows コマンド](/windows-server/administration/windows-commands/windows-commands#BKMK_c)と同様原則に従います。

高度なコマンドは、ファイルのダウンロードとアップロード、デバイスでのスクリプトの実行、エンティティに対する修復アクションなど、より強力なアクションを実行できる、より堅牢な一連のアクションを提供します。

### <a name="get-a-file-from-the-device"></a>デバイスからファイルを取得する

調査しているデバイスからファイルを取得するシナリオでは、 `getfile` コマンドを使用できます。 これにより、詳細な調査のためにデバイスからファイルを保存できます。

> [!NOTE]
> 次のファイル サイズ制限が適用されます。
>
> - `getfile` 制限: 3 GB
> - `fileinfo` 制限: 10 GB
> - `library` 制限: 250 MB

### <a name="download-a-file-in-the-background"></a>バックグラウンドでファイルをダウンロードする

セキュリティ運用チームが影響を受けるデバイスの調査を続行できるように、ファイルをバックグラウンドでダウンロードできるようになりました。

- バックグラウンドでファイルをダウンロードするには、ライブ応答コマンド コンソールで、「`download <file_path> &`」と 入力します。
- ファイルがダウンロードされるのを待っている場合は、Ctrl + Z キーを押してバックグラウンドに移動できます。
- ファイルのダウンロードをフォアグラウンドにするには、ライブ応答コマンド コンソールで、「`fg <command_id>`」と 入力します。

次に、いくつかの例を示します:

<br>

****

|コマンド|機能|
|---|---|
|`getfile "C:\windows\some_file.exe" &`|*some_file.exe* という名前のファイルのバックグラウンドでのダウンロードを開始します。|
|`fg 1234`|コマンド ID *1234* のダウンロードをフォアグラウンドに返します。|
|

### <a name="put-a-file-in-the-library"></a>ライブラリにファイルを配置する

ライブ応答には、ファイルを配置できるライブラリがあります。 ライブラリには、テナント レベルでライブ応答セッションで実行できるファイル (スクリプトなど) が格納されます。

ライブ応答を使用すると、PowerShell スクリプトを実行できますが、ファイルを実行する前に、まずライブラリにファイルを配置する必要があります。

ライブ応答セッションを開始するデバイスで実行できる PowerShell スクリプトのコレクションを用意できます。

#### <a name="to-upload-a-file-in-the-library"></a>ライブラリにファイルをアップロードするには

1. [ **ファイルをライブラリにアップロード**] をクリックします。

2. [**参照**]をクリックし、ファイルを選択します。

3. 簡単な説明を入力します。

4. 同じ名前のファイルを上書きするかどうかを指定します。

5. スクリプトに必要なパラメーターを知るには、[スクリプト パラメーター] チェック ボックスをオンにします。 テキスト フィールドに、例と説明を入力します。

6. [**確認**]をクリックします。

7. (省略可能)ファイルがライブラリにアップロードされたことを確認するには、 `library` コマンドを実行します。

### <a name="cancel-a-command"></a>コマンドを取り消す

セッション中はいつでも、Ctrl + C キーを押してコマンドを取り消すことができます。

> [!WARNING]
> このショートカットを使用すると、エージェント側でコマンドが停止されることはありません。 ポータルでコマンドを取り消すだけです。 そのため、コマンドが取り消されている間は、"修復" などの操作の変更が続行される可能性があります。

## <a name="run-a-script"></a>スクリプトを実行する

PowerShell/Bash スクリプトを実行する前に、まずライブラリにアップロードする必要があります。

スクリプトをライブラリにアップロードしたら、 `run` コマンドを使用してスクリプトを実行します。

セッションで署名されていない PowerShell スクリプトを使用する場合は、 [[高度な機能の設定](advanced-features.md)] ページで設定を有効にする必要があります。

> [!WARNING]
> 署名されていないスクリプトの使用を許可すると、脅威にさらされる可能性があります。

## <a name="apply-command-parameters"></a>コマンド パラメーターを適用する

- コマンド パラメーターの詳細については、コンソールのヘルプを参照してください。 個々のコマンドについて学習するには、次を実行します。

  ```powershell
  help <command name>
  ```

- コマンドにパラメーターを適用する場合、パラメーターは固定された順序に基づいて処理されることに注意してください。

  ```powershell
  <command name> param1 param2
  ```

- 固定順序以外のパラメーターを指定する場合は、値を指定する前に、パラメーターの名前をハイフンで指定します。

  ```powershell
  <command name> -param2_name param2
  ```

- 前提条件となるコマンドを含むコマンドを使用する場合は、フラグを使用できます。

  ```powershell
  <command name> -type file -id <file path> - auto
  ```

  または

  ```powershell
  remediate file <file path> - auto`
  ```

## <a name="supported-output-types"></a>サポートされている出力の種類

ライブ応答では、テーブルと JSON 形式の出力の種類がサポートされています。 コマンドごとに、既定の出力動作があります。 次のコマンドを使用して、好みの出力形式で出力を変更できます。

- `-output json`
- `-output table`

> [!NOTE]
> スペースが限られているため、テーブル形式で表示されるフィールドが少なくなります。 出力の詳細を表示するには、JSON 出力コマンドを使用して詳細を表示できます。

## <a name="supported-output-pipes"></a>サポートされている出力パイプ

ライブ応答では、CLI とファイルへの出力パイプ処理がサポートされています。 CLI は既定の出力動作です。 [command] > [filename].txt コマンドを使用して、出力をファイルにパイプ処理できます。

例:

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>コマンド ログを表示する

**コマンド ログ** タブを選択すると、セッション中にデバイスで使用されたコマンドが表示されます。 各コマンドは、次のような完全な詳細で追跡されます。

- ID
- コマンド ライン
- 期間
- 状態と入力または出力のサイド バー

## <a name="limitations"></a>制限事項

- ライブ応答セッションは、一度に 25 個のライブ応答セッションに制限されます。
- ライブ応答セッションの非アクティブタイムアウト値は 30 分です。
- ユーザーは、最大 10 個の同時セッションを開始できます。
- デバイスは一度に 1 つのセッションにのみ存在できます。
- 次のファイル サイズ制限が適用されます。
  - `getfile` 制限: 3 GB
  - `fileinfo` 制限: 10 GB
  - `library` 制限: 250 MB

## <a name="related-article"></a>関連記事

- [ライブ応答コマンドの例](live-response-command-examples.md)
