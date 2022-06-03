---
title: Microsoft Defender ウイルス対策イベントの ID とエラー コード
description: Microsoft Defender ウイルス対策のイベントと ID のエラーの原因と解決策を調べる
keywords: イベント、エラー コード、siem、ログ、トラブルシューティング、wef、Windows イベント転送
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/02/2022
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 1a82f1fb6759bd3cfeaa5bc24154e7e030d08355
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872404"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策ソフトウェアの問題をトラブルシューティングするため、イベント ログとエラー コードをレビューする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策で問題が発生した場合は、このトピックの表を検索して、一致する問題と考えられる解決策を見つけることができます。

テーブルの一覧:

- [Microsoft Defender ウイルス対策イベントの ID](#windows-defender-av-ids) (これらは、Windows 10、Windows 11、およびWindows Server 2016 に適用されます)
- [Microsoft Defender ウイルス対策エラー コード](#error-codes)
- [内部 Microsoft Defender ウイルス対策クライアント エラー コード (開発およびテスト中に Microsoft が使用)](#internal-error-codes)

> [!TIP]
> Microsoft Defender for Endpoint のデモ Web サイト ([demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)) にアクセスして、次の機能が動作していることを確認することもできます:
> - クラウドによる保護
> - 高速学習 (一目でブロックを含む)
> - 望ましくない可能性があるアプリケーションのブロック

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender - ウイルス対策イベント ID

Microsoft Defender ウイルス対策は、Windows イベント ログにイベント ID を記録します。

イベント ログを直接表示するか、サードパーティのセキュリティ情報とイベント管理 (SIEM) ツールがある場合は、Microsoft Defender ウイルス対策 クライアント イベント [ID](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) を使用してエンドポイントから特定のイベントとエラーを確認することもできます。

主要な Microsoft Defender ウイルス対策 イベント ID の一覧をこのセクションの表に示します。可能であれば、エラーを修正または解決するためのおすすめの解決策を示します。

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Microsoft Defender ウイルス対策 イベントを表示するには

1. **イベント ビューアー** を開きます。
2. コンソール ツリーで、[**アプリケーションとサービス ログ**] を展開し、[**Microsoft**]、[**Windows**]、さらに [**Windows Defender**] の順に展開します。
3. [**運用中**] をダブルクリックします。
4. [詳細] ウィンドウで、個々のイベントのリストを表示して、イベントを検索します。
5. イベントをクリックすると、下部ウィンドウの [**全般**] タブと [**詳細**] タブの下に、イベントに関する特定の詳細が表示されます。

<table>
<tr>
<th colspan="2" >イベント ID: 1000</th>
</tr>
<tr>
<td>
シンボリック名:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策スキャンが開始されました。</b>
</td>
</tr>
<tr>
<td >
説明:
</td>
<td >
<dl>
<dt>Scan ID: &lt;関連するスキャンの ID 番号。&gt;</dt>
<dt>スキャンの種類: &lt;スキャンの種類&gt;、例:<ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
</ul>
</dt>
<dt>Scan Parameters: &lt;スキャン パラメーター&gt;、例:<ul>
<li>フル スキャン</li>
<li>クイック スキャン</li>
<li>顧客スキャン</li>
</ul>
</dt>
<dt>スキャン リソース: &lt;スキャンされたリソース (ファイル/ディレクトリ/BHO など)。&gt;</dt>
<dt>ユーザー: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1001</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策スキャンが完了しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
<dl>
<dt>Scan ID: &lt;関連するスキャンの ID 番号。&gt;</dt>
<dt>スキャンの種類: &lt;スキャンの種類&gt;、例:<ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
</ul>
</dt>
<dt>Scan Parameters: &lt;スキャン パラメーター&gt;、例:<ul>
<li>フル スキャン</li>
<li>クイック スキャン</li>
<li>顧客スキャン</li>
</ul>
</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Scan Time: &lt;スキャンの期間。&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1002</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策スキャンは終了する前に停止しました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
<dl>
<dt>Scan ID: &lt;関連するスキャンの ID 番号。&gt;</dt>
<dt>スキャンの種類: &lt;スキャンの種類&gt;、例:<ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
</ul>
</dt>
<dt>Scan Parameters: &lt;スキャン パラメーター&gt;、例:<ul>
<li>フル スキャン</li>
<li>クイック スキャン</li>
<li>顧客スキャン</li>
</ul>
</dt>
<dt>User: &lt;ドメイン&gt;&amp;lt;ユーザー&gt;</dt>
<dt>Scan Time: &lt;スキャンの期間。&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1003</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策スキャンが一時停止されました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
<dl>
<dt>Scan ID: &lt;関連するスキャンの ID 番号。&gt;</dt>
<dt>スキャンの種類: &lt;スキャンの種類&gt;、例:<ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
</ul>
</dt>
<dt>Scan Parameters: &lt;スキャン パラメーター&gt;、例:<ul>
<li>フル スキャン</li>
<li>クイック スキャン</li>
<li>顧客スキャン</li>
</ul>
</dt>
<dt>ユーザー: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1004</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策スキャンが再開されました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
<dl>
<dt>Scan ID: &lt;関連するスキャンの ID 番号。&gt;</dt>
<dt>スキャンの種類: &lt;スキャンの種類&gt;、例:<ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
</ul>
</dt>
<dt>Scan Parameters: &lt;スキャン パラメーター&gt;、例:<ul>
<li>フル スキャン</li>
<li>クイック スキャン</li>
<li>顧客スキャン</li>
</ul>
</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1005</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策スキャンに失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
<dl>
<dt>Scan ID: &lt;関連するスキャンの ID 番号。&gt;</dt>
<dt>スキャンの種類: &lt;スキャンの種類&gt;、例:<ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
</ul>
</dt>
<dt>Scan Parameters: &lt;スキャン パラメーター&gt;、例:<ul>
<li>フル スキャン</li>
<li>クイック スキャン</li>
<li>顧客スキャン</li>
</ul>
</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Error Code; &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
ウイルス対策クライアントでエラーが発生し、現在のスキャンが停止しました。 クライアント側の問題が原因でスキャンが失敗する可能性があります。 このイベント レコードには、スキャン ID、スキャンの種類 (Microsoft Defender ウイルス対策、スパイウェア対策、マルウェア対策)、スキャン パラメーター、スキャンを開始したユーザー、エラー コード、エラーの説明が含まれます。
このイベントをトラブルシューティングするには:
<ol>
<li>スキャンを再度実行します。</li>
<li>同じ方法で失敗した場合は、<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft サポートサイト</a>に移動し、[<b>検索</b>] ボックスにエラー番号を入力してエラー コードを探します。</li>
<li><a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1006</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンは、マルウェアや望ましくない可能性のある他のソフトウェアを検出しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Detection Origin: &lt;検出元&gt;、例:<ul>
<li>不明</li>
<li>ローカル コンピューター</li>
<li>ネットワーク共有</li>
<li>インターネット</li>
<li>受信トラフィック</li>
<li>送信トラフィック</li>
</ul>
</dt>
<dt>検出の種類: &lt;検出の種類&gt;、例:<ul>
<li>ヒューリスティック</li>
<li>Generic</li>
<li>コンクリート</li>
<li>動的署名</li>
</ul>
</dt>
<dt>Detection Source: &lt;検出ソース&gt;、例:<ul>
<li>ユーザー: ユーザー始動</li>
<li>システム: システム始動</li>
<li>リアルタイム: リアルタイム コンポーネント始動</li>
<li>IOAV: IE のダウンロードと Outlook Express の添付ファイル始動</li>
<li>NIS: ネットワーク検査システム</li>
<li>IEPROTECT: IE - IExtensionValidation; これにより、悪意のある Web ページ コントロールから保護されます。</li>
<li>早期起動マルウェア対策 (ELAM)。 これには、ブート シーケンスによって検出されたマルウェアが含まれます。</li>
<li>リモート構成証明</li>
</ul>マルウェア対策スキャン インターフェイス (AMSI)。 主にスクリプト (PowerShell、VBS) を保護するために使用しますが、サード パーティでも呼び出すことができます。
UAC</dt>
<dt> Status: &lt;状態&gt;</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Process Name: &lt;PID 内のプロセス&gt;</dt>
<dt>Signature version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID : 1007</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームにより、マルウェアなどの望ましくない可能性のあるソフトウェアからシステムを保護するためのアクションが実行されました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >Microsoft Defender ウイルス対策、マルウェアや望ましくない可能性のある他のソフトウェアからこのコンピューターを保護するための措置を取っています。詳細は次をご覧ください。<dl>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Name: &lt;脅威名&gt;</dt>
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Action: &lt;アクション&gt;、例:<ul>
<li>Clean: リソースがクリーンアップされました</li>
<li>Quarantine: リソースが検疫されました</li>
<li>Remove: リソースが削除されました</li>
<li>Allow: リソースの実行/存在が許可されました</li>
<li>User defined: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</li>
<li>No action: アクションなし</li>
<li>Block: リソースの実行がブロックされました</li>
</ul>
</dt>
<dt>Status: &lt;状態&gt;</dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID : 1008</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性があるソフトウェアからシステムを保護するためのアクションを実行しようとしましたが、アクションは失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >マルウェアやその他の望ましくない可能性のあるソフトウェアに対してアクションを実行するときに、Microsoft Defender ウイルス対策でエラーが発生しました。詳細については、次を参照してください。<dl>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Name: &lt;脅威名&gt;</dt>
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Action: &lt;アクション&gt;、例:<ul>
<li>Clean: リソースがクリーンアップされました</li>
<li>Quarantine: リソースが検疫されました</li>
<li>Remove: リソースが削除されました</li>
<li>Allow: リソースの実行/存在が許可されました</li>
<li>User defined: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</li>
<li>No action: アクションなし</li>
<li>Block: リソースの実行がブロックされました</li>
</ul>
</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Status: &lt;状態&gt;</dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID : 1009</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは、検疫からアイテムを復元しました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >Microsoft Defender ウイルス対策で検疫からアイテムを復元しました。詳細については、次を参照してください。<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID : 1010</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは検疫から項目を復元できませんでした。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >Microsoft Defender ウイルス対策で検疫からアイテムを復元しようとしてエラーが発生しました。詳細については、次を参照してください。<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Error Code &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt; マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1011</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームが検疫からアイテムを削除しました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策が検疫から項目を削除しました。<br/>詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID : 1012</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは検疫から項目を削除できませんでした。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >Microsoft Defender ウイルス対策検疫からアイテムを削除しようとしてエラーが発生しました。詳細については、次を参照してください。<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Error Code &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt; マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1013</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは、マルウェアやその他の望ましくない可能性のあるソフトウェアの履歴を削除しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は、マルウェアやその他の望ましくない可能性のあるソフトウェアの履歴を削除しました。
<dl>
<dt>Time: イベントが発生した時刻 (たとえば、履歴が削除された時刻)。このパラメーターは脅威イベントでは使用されないので、修復時間と感染時間の違いはありません。具体的には、アクション時間または検出時間と呼ぶ必要があります。</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1014</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
マルウェア対策プラットフォームは、マルウェアやその他の望ましくない可能性のあるソフトウェアの履歴を削除できませんでした。
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策で、マルウェアやその他の望ましくない可能性のあるソフトウェアの履歴を削除しようとしてエラーが発生しました。
<dl>
<dt>Time: イベントが発生した時刻 (たとえば、履歴が削除された時刻)。このパラメーターは脅威イベントでは使用されないので、修復時間と感染時間の違いはありません。具体的には、アクション時間または検出時間と呼ぶ必要があります。</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1015</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームが疑わしい動作を検出しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策が疑わしい動作を検出しました。<br/>詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Detection Origin: &lt;検出元&gt;、例:
<ul>
<li>不明</li>
<li>ローカル コンピューター</li>
<li>ネットワーク共有</li>
<li>インターネット</li>
<li>受信トラフィック</li>
<li>送信トラフィック</li>
</ul>
</dt>
<dt>検出の種類: &lt;検出の種類&gt;、例:<ul>
<li>ヒューリスティック</li>
<li>Generic</li>
<li>コンクリート</li>
<li>動的署名</li>
</ul>
</dt>
<dt>Detection Source: &lt;検出ソース&gt;、例:<ul>
<li>ユーザー: ユーザー始動</li>
<li>システム: システム始動</li>
<li>リアルタイム: リアルタイム コンポーネント始動</li>
<li>IOAV: IE のダウンロードと Outlook Express の添付ファイル始動</li>
<li>NIS: ネットワーク検査システム</li>
<li>IEPROTECT: IE - IExtensionValidation; これにより、悪意のある Web ページ コントロールから保護されます。</li>
<li>早期起動マルウェア対策 (ELAM)。 これには、ブート シーケンスによって検出されたマルウェアが含まれます。</li>
<li>リモート構成証明</li>
</ul>マルウェア対策スキャン インターフェイス (AMSI)。 主にスクリプト (PowerShell、VBS) を保護するために使用しますが、サード パーティでも呼び出すことができます。
UAC</dt>
<dt>Status: &lt;状態&gt;</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Process Name: &lt;PID 内のプロセス&gt;</dt>
<dt>Signature ID: 列挙一致の重大度。</dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;ファイル名&gt; ファイルの名前。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1116</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームがマルウェアなどの望ましくない可能性のあるソフトウェアを検出しました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は、マルウェアやその他の望ましくない可能性のあるソフトウェアを検出しました。<br/>詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Detection Origin: &lt;検出元&gt;、例:
<ul>
<li>不明</li>
<li>ローカル コンピューター</li>
<li>ネットワーク共有</li>
<li>インターネット</li>
<li>受信トラフィック</li>
<li>送信トラフィック</li>
</ul>
</dt>
<dt>検出の種類: &lt;検出の種類&gt;、例:<ul>
<li>ヒューリスティック</li>
<li>Generic</li>
<li>コンクリート</li>
<li>動的署名</li>
</ul>
</dt>
<dt>Detection Source: &lt;検出ソース&gt;、例:<ul>
<li>ユーザー: ユーザー始動</li>
<li>システム: システム始動</li>
<li>リアルタイム: リアルタイム コンポーネント始動</li>
<li>IOAV: IE のダウンロードと Outlook Express の添付ファイル始動</li>
<li>NIS: ネットワーク検査システム</li>
<li>IEPROTECT: IE - IExtensionValidation; これにより、悪意のある Web ページ コントロールから保護されます。</li>
<li>早期起動マルウェア対策 (ELAM)。 これには、ブート シーケンスによって検出されたマルウェアが含まれます。</li>
<li>リモート構成証明</li>
</ul>マルウェア対策スキャン インターフェイス (AMSI)。 主にスクリプト (PowerShell、VBS) を保護するために使用しますが、サード パーティでも呼び出すことができます。
UAC</dt>
<dt>User: &lt;ドメイン&gt;\&ltユーザー&gt;</dt>
<dt>Process Name: &lt;PID 内のプロセス&gt;</dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
何もする必要はありません。 Microsoft Defender ウイルス対策は、この脅威に対して一時停止し、ルーティン アクションを実行できます。 手動で脅威を削除する場合は、Microsoft Defender ウイルス対策のインターフェイスで、[<b>コンピューターをクリーン</b>] をクリックします。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1117</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームにより、マルウェアなどの望ましくない可能性のあるソフトウェアからシステムを保護するためのアクションが実行されました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策、マルウェアや望ましくない可能性のある他のソフトウェアからこのコンピューターを保護するための措置を取っています。<br/>詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Detection Origin: &lt;検出元&gt;、例:
<ul>
<li>不明</li>
<li>ローカル コンピューター</li>
<li>ネットワーク共有</li>
<li>インターネット</li>
<li>受信トラフィック</li>
<li>送信トラフィック</li>
</ul>
</dt>
<dt>検出の種類: &lt;検出の種類&gt;、例:<ul>
<li>ヒューリスティック</li>
<li>Generic</li>
<li>コンクリート</li>
<li>動的署名</li>
</ul>
</dt>
<dt>Detection Source: &lt;検出ソース&gt;、例:<ul>
<li>ユーザー: ユーザー始動</li>
<li>システム: システム始動</li>
<li>リアルタイム: リアルタイム コンポーネント始動</li>
<li>IOAV: IE のダウンロードと Outlook Express の添付ファイル始動</li>
<li>NIS: ネットワーク検査システム</li>
<li>IEPROTECT: IE - IExtensionValidation; これにより、悪意のある Web ページ コントロールから保護されます。</li>
<li>早期起動マルウェア対策 (ELAM)。 これには、ブート シーケンスによって検出されたマルウェアが含まれます。</li>
<li>リモート構成証明</li>
</ul>マルウェア対策スキャン インターフェイス (AMSI)。 主にスクリプト (PowerShell、VBS) を保護するために使用しますが、サード パーティでも呼び出すことができます。
UAC</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Process Name: &lt;PID 内のプロセス&gt;</dt>
<dt>Action: &lt;アクション&gt;、例:<ul>
<li>Clean: リソースがクリーンアップされました</li>
<li>Quarantine: リソースが検疫されました</li>
<li>Remove: リソースが削除されました</li>
<li>Allow: リソースの実行/存在が許可されました</li>
<li>User defined: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</li>
<li>No action: アクションなし</li>
<li>Block: リソースの実行がブロックされました</li>
</ul>
</dt>
<dt>Action Status: &lt;追加のアクションの説明&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;&gt;マルウェア対策エンジン バージョン</dt> メモ: Microsoft Defender ウイルス対策、Microsoft Security Essentials、悪意のあるソフトウェアの削除ツール、または Microsoft System Center Endpoint Protection がマルウェアを検出すると、マルウェアが変更された可能性のある次のシステム設定とサービスを復元します:<ul>
<li>既定の Internet Explorer または Microsoft Edge の設定</li>
<li>フィールド アクセス制御の設定</li>
<li>Chrome の設定</li>
<li>ブート コントロール データ</li>
<li>Regedit とタスク マネーカーのレジストリ設定</li>
<li>Windows Update、バックグラウンド インテリジェント転送サービス、およびリモート プロシージャ コール サービス</li>
<li>Windows オペレーティング システムのデータ</li></ul>
上記のコンテキストは、次のクライアントとサーバーのバージョンに適用されます:
<table>
<tr>
<th>オペレーティング システム</th>
<th>オペレーティング システムのバージョン</th>
</tr>
<tr>
<td>
クライアントのオペレーティング システム
</td>
<td>
Windows Vista (Service Pack 1、または Service Pack 2)、Windows 7 以降
</td>
</tr>
<tr>
<td>
サーバー オペレーティング システム
</td>
<td>
Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 および Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
操作は必要ありません。 Microsoft Defender ウイルス対策が脅威を削除または検疫しました。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1118</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは、マルウェアやその他の望ましくない可能性のあるソフトウェアからシステムを保護するアクションを実行しようとしましたが、操作は失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
マルウェアやその他の望ましくない可能性のあるソフトウェアに対してアクションを実行するときに、Microsoft Defender ウイルス対策で重大ではないエラーが発生しました。<br/>詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Detection Origin: &lt;検出元&gt;、例:
<ul>
<li>不明</li>
<li>ローカル コンピューター</li>
<li>ネットワーク共有</li>
<li>インターネット</li>
<li>受信トラフィック</li>
<li>送信トラフィック</li>
</ul>
</dt>
<dt>検出の種類: &lt;検出の種類&gt;、例:<ul>
<li>ヒューリスティック</li>
<li>Generic</li>
<li>コンクリート</li>
<li>動的署名</li>
</ul>
</dt>
<dt>Detection Source: &lt;検出ソース&gt;、例:<ul>
<li>ユーザー: ユーザー始動</li>
<li>システム: システム始動</li>
<li>リアルタイム: リアルタイム コンポーネント始動</li>
<li>IOAV: IE のダウンロードと Outlook Express の添付ファイル始動</li>
<li>NIS: ネットワーク検査システム</li>
<li>IEPROTECT: IE - IExtensionValidation; これにより、悪意のある Web ページ コントロールから保護されます。</li>
<li>早期起動マルウェア対策 (ELAM)。 これには、ブート シーケンスによって検出されたマルウェアが含まれます。</li>
<li>リモート構成証明</li>
</ul>マルウェア対策スキャン インターフェイス (AMSI)。 主にスクリプト (PowerShell、VBS) を保護するために使用しますが、サード パーティでも呼び出すことができます。
UAC</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Process Name: &lt;PID 内のプロセス&gt;</dt>
<dt>Action: &lt;アクション&gt;、例:<ul>
<li>Clean: リソースがクリーンアップされました</li>
<li>Quarantine: リソースが検疫されました</li>
<li>Remove: リソースが削除されました</li>
<li>Allow: リソースの実行/存在が許可されました</li>
<li>User defined: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</li>
<li>No action: アクションなし</li>
<li>Block: リソースの実行がブロックされました</li>
</ul>
</dt>
<dt>Action Status: &lt;追加のアクションの説明&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
操作は必要ありません。 Microsoft Defender ウイルス対策は、マルウェアの修復に関連するタスクを完了できませんでした。 これは重大なエラーではありません。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1119</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェアやその他の望ましくない可能性のあるソフトウェアに対してアクションを実行しようとしたときに、マルウェア対策プラットフォームで重大なエラーが発生しました。イベント メッセージに詳細があります。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
マルウェアやその他の望ましくない可能性のあるソフトウェアに対してアクションを実行するときに、Microsoft Defender ウイルス対策で重大なエラーが発生しました。<br/>詳細については、次のトピックを参照してください。
<dl>
<dt>Name: &lt;脅威名&gt;</dt> 
<dt>ID: &lt;脅威 ID&gt;</dt>
<dt>Severity: &lt;重大度:&gt;、例:<ul>
<li>低</li>
<li>中</li>
<li>高</li>
<li>重大</li>
</ul>
</dt>
<dt>Category: &lt;カテゴリの説明&gt; (脅威やマルウェアの種類など)。</dt>
<dt>Path: &lt;ファイル パス&gt;</dt>
<dt>Detection Origin: &lt;検出元&gt;、例:
<ul>
<li>不明</li>
<li>ローカル コンピューター</li>
<li>ネットワーク共有</li>
<li>インターネット</li>
<li>受信トラフィック</li>
<li>送信トラフィック</li>
</ul>
</dt>
<dt>検出の種類: &lt;検出の種類&gt;、例:<ul>
<li>ヒューリスティック</li>
<li>Generic</li>
<li>コンクリート</li>
<li>動的署名</li>
</ul>
</dt>
<dt>Detection Source: &lt;検出ソース&gt;、例:<ul>
<li>ユーザー: ユーザー始動</li>
<li>システム: システム始動</li>
<li>リアルタイム: リアルタイム コンポーネント始動</li>
<li>IOAV: IE のダウンロードと Outlook Express の添付ファイル始動</li>
<li>NIS: ネットワーク検査システム</li>
<li>IEPROTECT: IE - IExtensionValidation; これにより、悪意のある Web ページ コントロールから保護されます。</li>
<li>早期起動マルウェア対策 (ELAM)。 これには、ブート シーケンスによって検出されたマルウェアが含まれます。</li>
<li>リモート構成証明</li>
</ul>マルウェア対策スキャン インターフェイス (AMSI)。 主にスクリプト (PowerShell、VBS) を保護するために使用しますが、サード パーティでも呼び出すことができます。
UAC</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt> 
<dt>Process Name: &lt;PID 内のプロセス&gt;</dt>
<dt>Action: &lt;アクション&gt;、例:<ul>
<li>Clean: リソースがクリーンアップされました</li>
<li>Quarantine: リソースが検疫されました</li>
<li>Remove: リソースが削除されました</li>
<li>Allow: リソースの実行/存在が許可されました</li>
<li>User defined: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</li>
<li>No action: アクションなし</li>
<li>Block: リソースの実行がブロックされました</li>
</ul>
</dt>
<dt>Action Status: &lt;追加のアクションの説明&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
Microsoft Defender ウイルス対策 クライアントで重大な問題が発生したため、このエラーが発生しました。 エンドポイントが保護されていない可能性があります。 エラーの説明を確認し、以下の関連する <b>ユーザー アクション</b>の手順に従います。
<table>
<tr>
<th>Action</th>
<th>ユーザー操作</th>
</tr>
<tr>
<td>
<b>Remove</b>
</td>
<td>
定義を更新し、削除が成功したと確認します。
</td>
</tr>
<tr>
<td>
<b>Clean</b>
</td>
<td>
定義を更新し、修復が成功したと確認します。
</td>
</tr>
<tr>
<td>
<b>Quarantine</b>
</td>
<td>
定義を更新し、ユーザーが必要なリソースにアクセスするためのアクセス許可を持っている必要があります。
</td>
</tr>
<tr>
<td>
<b>Allow</b>
</td>
<td>
ユーザーが必要なリソースにアクセスするためのアクセス許可を持っている必要があります。
</td>
</tr>
</table>

このイベントが続く場合は、次の処理を行います:<ol>
<li>スキャンを再度実行します。</li>
<li>同じ方法で失敗した場合は、<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft サポートサイト</a>に移動し、[<b>検索</b>] ボックスにエラー番号を入力してエラー コードを探します。</li>
<li><a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1120</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>Microsoft Defender ウイルス対策は、脅威リソースのハッシュを推測しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は正常な状態で稼働しています。
<dl>
<dt>Current Platform Version: &lt;現在のプラットフォーム バージョン&gt;</dt>
<dt>Threat Resource Path: &lt;パス&gt;</dt>
<dt>Hashes: &lt;ハッシュ&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>メモ: このイベントは、次のポリシーが設定されている場合にのみログに記録されます: <b>ThreatFileHashLogging     unsigned</b>。</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1127</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_FOLDER_GUARD_SECTOR_BLOCK</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>フォルダー アクセス制御 (CFA) により、信頼されていないプロセスがメモリに変更を加えることができませんでした。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
フォルダー アクセスの制御により、信頼されていないプロセスによりディスク セクターを変更される可能性がブロックされました。
<br/> イベント レコードの詳細については、以下を参照してください。
<dl>
<dt>EventID: &lt;EventID&gt;、(例: 1127)</dt>
<dt>Version: &lt;バージョン&gt;、例: 0 </dt>
<dt>Level: &lt;レベル&gt;、例: win:Warning</dt>
<dt>TimeCreated: &lt;SystemTime&gt;、イベントが作成された時間</dt>
<dt>EventRecordID: &lt;EventRecordID&gt;、イベント ログでのイベントのインデックス番号</dt>
<dt>Execution ProcessID: &lt;Execution ProcessID&gt;、イベントを生成したプロセス</dt>
<dt>Channel: &lt;イベント チャネル&gt;、例: Microsoft-Windows-Windows Defender/Operational</dt>
<dt>Computer: &lt;コンピューター名&gt;</dt>
<dt>Security UserID: &lt;セキュリティ ユーザー ID&gt;</dt>
<dt>Product Name: &lt;製品名&gt;、例: Microsoft Defender Antivirus</dt>
<dt>Product Version: &lt;Product Version&gt;</dt>
<dt>Detection Time: &lt;検出時間&gt;、CFA が信頼されていないプロセスをブロックした時間</dt>
<dt>User: &lt;ドメイン&gt;\&;ltユーザー&gt;</dt>
<dt>Path: &lt;デバイス名&gt;</dt>、信頼されていないプロセスが変更のためにアクセスしたデバイスまたはディスクの名前 
<dt>Process Name: &lt;プロセス パス&gt;、変更のために CFA がdeviceやディスクにアクセスするのをブロックしたプロセス パス名</dt>
<dt>Security Intelligence Version: &lt;セキュリティ インテリジェンス バージョン&gt;</dt>
<dt>Engine Version: &lt;ウイルス対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
ユーザーは、Powershell または Windows セキュリティ Center を使用して、CFA の <i>許可されたプロセス</i> リストにブロックされたプロセスを追加できます。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 1150</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームが監視プラットフォームに状態を報告する場合、このイベントはマルウェア対策プラットフォームが実行中で正常な状態であることを示します。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は正常な状態で稼働しています。
<dl>
<dt>Platform Version: &lt;現在のプラットフォームバージョン&gt;</dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
操作は必要ありません。 Microsoft Defender ウイルス対策クライアントは正常な状態です。 このイベントは、1 時間単位で報告されます。
</td>
</tr>

<tr>
<th colspan="2">イベント ID: 1151</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>Endpoint Protection クライアント正常性レポート (UTC の時刻)</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
ウイルス対策クライアントの正常性レポート。
<dl>
<dt>Platform Version: &lt;現在のプラットフォーム バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジン&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;ネットワーク リアルタイム検査エンジン バージョン&gt;</dt>
<dt>Antivirus signature version: &lt;ウイルス対策署名バージョン&gt;</dt>
<dt>Antispyware Signature version: &lt;スパイウェア対策署名バージョン&gt;</dt>
<dt>Network Realtime Inspection Signature version: &lt;ネットワークリアルタイム検査署名バージョン&gt;</dt>
<dt>RTP state: &lt;リアルタイム保護状態&gt; (有効または無効)</dt>
<dt>OA state: &lt;アクセス時の状態&gt; (Enabled または Disabled)</dt>
<dt>IOAV state: &lt;IE ダウンロードと Outlook Express 添付ファイルの状態&gt;(有効または無効)</dt>
<dt>BM state: &lt;動作監視状態&gt; (有効または無効)</dt>
<dt>Antivirus signature age:&lt;ウイルス対策署名からの経時&gt; (日数)</dt>
<dt>Antispyware signature age: &lt;スパイウェア対策の署名からの経時&gt; (日数)</dt>
<dt>Last quick scan age: &lt;最後のクイック スキャンからの経時&gt; (日数)</dt>
<dt>Last full scan age: &lt;最後のフル スキャンからの経時&gt; (日数)</dt>
<dt>Antivirus signature creation time: ?&lt;ウイルス対策署名の作成時間&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;スパイウェア対策署名作成時間&gt;</dt>
<dt>Last quick scan start time: ?&lt;最後のクイック スキャンの開始時刻&gt;</dt>
<dt>Last quick scan end time: ?&lt;最後のクイック スキャン終了時刻&gt;</dt>
<dt>Last quick scan source: &lt;最後のクリック スキャン ソース&gt; (0 = スキャン未実行, 1 = ユーザー始動, 2 = システム始動)</dt>
<dt>Last full scan start time: ?&lt;最後のフル スキャン開始時間&gt;</dt>
<dt>Last full scan end time: ?&lt;最後のフル スキャン終了時間&gt;</dt>
<dt>Last full scan source: &lt;最後のフル スキャン ソース&gt; (0 = スキャン未実行, 1 = ユーザー始動, 2 = システム始動)</dt>
<dt>Product status: 内部トラブルシューティング用
</dl>
</td>
</tr>

<tr>
<th colspan="2">イベント ID: 2000</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策の定義が正常に更新されました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
ウイルス対策署名のバージョンが更新されました。
<dl>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
<dt>Previous Signature Version: &lt;以前の署名バージョン&gt;</dt>
<dt>Signature Type: &lt;署名の種類&gt;、例: <ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Update Type: &lt;更新プログラムの種類&gt; (フルまたは差分)。</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Current Engine Version: &lt;現在のエンジン バージョン&gt;</dt>
<dt>Previous Engine Version: &lt;以前のエンジン バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
操作は必要ありません。 Microsoft Defender ウイルス対策クライアントは正常な状態です。 このイベントは、署名が正常に更新されると報告されます。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2001</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>セキュリティ インテリジェンスの更新に失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策が署名更新でエラーが発生しました。
<dl>
<dt>New security intelligence version: &lt;新しいバージョン番号&gt;</dt>
<dt>Previous security intelligence version: &lt;以前のバージョン&gt;</dt>
<dt>Update Source: &lt;更新ソース&gt;、例:
<ul>
<li>セキュリティ インテリジェンス更新プログラムのフォルダー</li>
<li>内部セキュリティ インテリジェンス更新サーバー</li>
<li>Microsoft Update Services</li>
<li>ファイル共有</li>
<li>Microsoft Malware Protection Center (MMPC)</li>
</ul>
</dt>
<dt>更新ステージ: &lt;更新ステージ&gt;、例:
<ul>
<li>検索</li>
<li>ダウンロード</li>
<li>インストール</li>
</ul>
</dt>
<dt>ソース パス: ユニバーサル名前付け規則 (UNC) のファイル共有名、Windows Server Update Services (WSUS)/Microsoft Update/ADL のサーバー名。</dt>
<dt>Signature type: &lt;署名の種類&gt;、例: <ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Update Type: &lt;更新の種類&gt; (フルまたは 差分)。</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Engine Version: &lt;現在のエンジン バージョン&gt;</dt>
<dt>Previous Engine Version: &lt;以前のエンジン バージョン&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準 HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明。&gt; 当該エラーの説明。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >このエラーは、定義の更新中に問題が発生した場合に発生します。このイベントのトラブルシューティングを行うには:<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">定義を更新し</a>、エンドポイントで直接再スキャンを強制します。</li>
<li>このエラーの詳細については、%Windir%\WindowsUpdate.log ファイルのエントリを確認します。</li>
<li><a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2002</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンが正常に更新されました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策エンジンのバージョンが更新されました。
<dl>
<dt>Current Engine Version: &lt;現在のエンジンバージョン&gt;</dt>
<dt>Previous Engine Version: &lt;&gt;</dt> 以前のエンジン バージョン
<dt>Engine Type: &lt;&gt;マルウェア対策エンジンまたはネットワーク検査システム エンジン</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
操作は必要ありません。 Microsoft Defender ウイルス対策クライアントは正常な状態です。 このイベントは、マルウェア対策エンジンが正常に更新されると報告されます。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2003</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンの更新に失敗しました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策がエンジンの更新でエラーが発生しました。
<dl>
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;以前のエンジン バージョン&gt;</dt>
<dt>Engine Type: &lt;エンジンの種類&gt;、マルウェア対策エンジンまたはネットワーク検査システム エンジン。</dt>
<dt>User: &lt;ドメイン&gt;\&lt;ユーザー&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
Microsoft Defender ウイルス対策 クライアントの更新に失敗しました。 このイベントは、クライアントが更新自体に失敗した場合に発生します。 このイベントは、通常、更新中にネットワーク接続が中断された場合に発生します。
このイベントをトラブルシューティングするには:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">定義を更新し</a>、エンドポイントで直接再スキャンを強制します。</li>
<li><a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2004</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策定義の読み込み中に問題が発生しました。マルウェア対策エンジンは、最後に認識された適切な定義のセットの読み込みを試みます。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策で署名の読み込み中にエラーが発生したため、既知の適切な署名セットに戻そうとします。
<dl>
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Signature Version: &lt;定義バージョン&gt;</dt>
<dt>Engine Version: &lt;マルウェア対策エンジンのバージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
Microsoft Defender ウイルス対策 クライアントが最新の定義ファイルをダウンロードしてインストールしようとして失敗しました。 このエラーは、定義の読み込み中にクライアントでエラーが発生した場合、またはファイルが破損している場合に発生する可能性があります。 Microsoft Defender ウイルス対策は、既知の適切な定義セットに戻そうとします。
このイベントをトラブルシューティングするには:
<ol>
<li>コンピューターを再起動して、もう一度やり直してください。</li>
<li><a href="https://aka.ms/wdsi">Microsoft セキュリティ インテリジェンス サイト</a> から最新の定義をダウンロードします。注: サイトからダウンロードした定義ファイルのサイズは 60 MB を超える可能性があるため、定義を更新するための長期的なソリューションとして使用しないでください。</li>
<li><a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2005</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームが最新ではないため、マルウェア対策エンジンを読み込めませんでした。マルウェア対策プラットフォームは、最新の正常なマルウェア対策エンジンを読み込み、更新を試みます。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
現在のプラットフォーム バージョンがサポートされていないため、Microsoft Defender ウイルス対策がマルウェア対策エンジンを読み込めませんでした。 Microsoft Defender ウイルス対策は、最新の既知の正常なエンジンに戻り、プラットフォームの更新が試行されます。
<dl>
<dt>Current Platform Version: &lt;現在のプラットフォームのバージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2006</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>プラットフォームの更新に失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策を更新しようとしてエラーが発生しました。
<dl>
<dt>Current Platform Version: &lt;現在のプラットフォーム バージョン&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2007</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>プラットフォームは間もなく古くなります。最新の保護を維持するために、最新のプラットフォームをダウンロードします。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策マルウェア対策エンジンの将来のバージョンをサポートするには、間もなく新しいプラットフォーム バージョンが必要になります。 最新のセキュリティ Microsoft Defender ウイルス対策をダウンロードして、利用可能な最高レベルの保護を維持しましょう。
<dl>
<dt>Current Platform Version: &lt;現在のプラットフォームのバージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2010</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンは、動的署名サービスを使用して追加の定義を取得しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は、<i>動的署名サービス</i>を使用して、コンピューターの保護に役立つ追加の署名を取得しました。
<dl>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
<dt>Signature Type: &lt;署名の種類&gt;、例: <ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Current Engine Version: &lt;現在のエンジンバージョン&gt;</dt>
<dt>Dynamic Signature Type: &lt;動的署名の種類&gt;、例:
<ul>
<li>バージョン</li>
<li>Timestamp</li>
<li>無制限</li>
<li>期間</li>
</ul>
</dt>
<dt>Persistence Path: &lt;パス&gt;</dt>
<dt>Dynamic Signature Version: &lt;バージョン番号&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;タイムスタンプ&gt;</dt>
<dt>Persistence Limit Type: &lt;永続化制限&gt;、例:
<ul>
<li>VDM バージョン</li>
<li>Timestamp</li>
<li>無制限</li>
</ul>
</dt>
<dt>Persistence Limit: 高速パス署名の永続性の制限。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID : 2011</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>動的署名サービスにより、古い動的定義が削除されました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は、<i>動的署名サービス</i>を使用して、古い署名を破棄します。
<dl>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
<dt>Signature Type: &lt;署名の種類&gt;、例: <ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Current Engine Version: &lt;現在のエンジンバージョン&gt;</dt>
<dt>Dynamic Signature Type: &lt;動的署名の種類&gt;、例:
<ul>
<li>バージョン</li>
<li>Timestamp</li>
<li>無制限</li>
<li>期間</li>
</ul>
</dt>
<dt>Persistence Path: &lt;パス&gt;</dt>
<dt>Dynamic Signature Version: &lt;バージョン番号&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;タイムスタンプ&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;永続化制限の種類&gt;、例:
<ul>
<li>VDM バージョン</li>
<li>Timestamp</li>
<li>無制限</li>
</ul>
</dt>
<dt>Persistence Limit: 高速パス署名の永続性の制限。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
操作は必要ありません。 Microsoft Defender ウイルス対策クライアントは正常な状態です。 このイベントは、動的署名サービスが古い動的定義を正常に削除すると報告されます。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2012</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>動的署名サービスを使用しようとするときに、マルウェア対策エンジンでエラーが発生しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策が<i>動的署名サービス</i>を使用しようとしてエラーが発生しました。
<dl>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
<dt>Signature Type: &lt;署名の種類&gt;、例: <ul>
<li>ウイルス対策</li>
<li>スパイウェア対策</li>
<li>マルウェア対策</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Current Engine Version: &lt;現在のエンジンバージョン&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Dynamic Signature Type: &lt;動的署名の種類&gt;、例:
<ul>
<li>バージョン</li>
<li>Timestamp</li>
<li>無制限</li>
<li>期間</li>
</ul>
</dt>
<dt>Persistence Path: &lt;パス&gt;</dt>
<dt>Dynamic Signature Version: &lt;バージョン番号&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;タイムスタンプ&gt;</dt>
<dt>Persistence Limit Type: &lt;永続化制限&gt;、例:
<ul>
<li>VDM バージョン</li>
<li>Timestamp</li>
<li>無制限</li>
</ul>
</dt>
<dt>Persistence Limit: 高速パス署名の永続性の制限。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
インターネット接続の設定を確認します。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2013</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>動的署名サービスは、すべての動的定義を削除しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策が<i>すべての動的署名サービス</i>の署名を破棄しました。
<dl>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2020</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンがクリーン ファイルをダウンロードしました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策がクリーン ファイルをダウンロードしました。
<dl>
<dt>Filename: &lt;ファイル名&gt; ファイルの名前。</dt>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
<dt>Current Engine Version: &lt;現在のエンジンのバージョン&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2021</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンがクリーン ファイルのダウンロードに失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策がクリーン ファイルをダウンロードしようとしてエラーが発生しました。
<dl>
<dt>Filename: &lt;ファイル名&gt; ファイルの名前。</dt>
<dt>Current Signature Version: &lt;現在の署名バージョン&gt;</dt>
<dt>Current Engine Version: &lt;現在のエンジン バージョン&gt;</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
インターネット接続の設定を確認します。
Microsoft Defender ウイルス対策クライアントが、動的署名サービスを使用して最新の定義を特定の脅威に対してダウンロードするときにエラーが発生しました。 このエラーは、ネットワーク接続の問題が原因である可能性があります。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2030</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンがダウンロードされ、次のシステム再起動時にオフラインで実行するように構成されています。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策が次の再起動時に実行するようにオフライン ウイルス対策をダウンロードして構成しました。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2031</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンがオフライン スキャンをダウンロードして構成できませんでした。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策がウイルス対策をダウンロードしてオフラインで構成しようとしてエラーが発生しました。
<dl>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2040</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>このオペレーティング システム バージョンのマルウェア対策のサポートは間もなく終了します。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >お使いのオペレーティング システムのサポートは間もなく期限切れになります。サポート対象外のオペレーティング システムでMicrosoft Defender ウイルス対策を実行することは、脅威から保護するための適切なソリューションではありません。</td>
</tr>
<tr>
<th colspan="2">イベント ID : 2041</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>このオペレーティング システムのマルウェア対策のサポートは終了しました。継続的なサポートのためには、オペレーティング システムをアップグレードする必要があります。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >お使いのオペレーティング システムのサポートが期限切れになりました。サポート対象外のオペレーティング システムでMicrosoft Defender ウイルス対策を実行することは、脅威から保護するための適切なソリューションではありません。</td>
</tr>
<tr>
<th colspan="2">イベント ID: 2042</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンは、このオペレーティング システムをサポートしなくなったので、システムをマルウェアから保護しなくなりました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >お使いのオペレーティング システムのサポートが期限切れになりました。Microsoft Defender ウイルス対策はオペレーティング システムでサポートされなくなり、機能しなくなり、マルウェアの脅威から保護されていません。</td>
</tr>
<tr>
<th colspan="2">イベント ID: 3002</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>リアルタイム保護でエラーが発生し、失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策のリアルタイム保護機能でエラーが発生し、失敗しました。
<dl>
<dt>Feature: &lt;機能&gt;、例:
<ul>
<li>アクセス時</li>
<li>Internet Explorer ダウンロードと Microsoft Outlook Express 添付ファイル</li>
<li>動作の監視</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。 </dt>
<dt>Reason: Microsoft Defender ウイルス対策のリアルタイム保護機能により機能が再起動された理由。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
システムが一時保護されていない可能性がある場合は、システムを再起動してからフル スキャンを実行する必要があります。
Microsoft Defender ウイルス対策クライアントのリアルタイム保護機能で、サービスの 1 つを開始できなかったためエラーが発生しました。
その後に 3007 イベント ID が続く場合、エラーは一時的なもので、マルウェア対策クライアントはエラーから回復しました。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 3007</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>リアルタイム保護が障害から回復しました。このエラーが表示された場合は、フル システム スキャンを実行することをお勧めします。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >リアルタイム保護機能が再開されました。システムのフル スキャンを実行して、このエージェントの停止中に失われた可能性のある項目を検出することをお勧めします。<dl>
<dt>Feature: &lt;機能&gt;、例:
<ul>
<li>アクセス時</li>
<li>IE のダウンロードとOutlook Express の添付ファイル</li>
<li>動作の監視</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>Reason: Microsoft Defender ウイルス対策のリアルタイム保護により機能が再起動された理由。</dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
リアルタイム保護機能が再起動されました。 このイベントが再度発生した場合は、 <a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5000</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>リアルタイム保護は有効です。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策のマルウェアやその他の望ましくない可能性のあるソフトウェアのリアルタイム保護スキャンが有効になりました。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5001</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>リアルタイム保護が無効です</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策のマルウェアやその他の望ましくない可能性のあるソフトウェアのリアルタイム保護スキャンが無効になりました。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5004</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>リアルタイムの保護構成が変更されました。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策のリアルタイム保護機能の構成が変更されました。
<dl>
<dt>Feature: &lt;機能&gt;、例:
<ul>
<li>アクセス時</li>
<li>IE のダウンロードとOutlook Express の添付ファイル</li>
<li>動作の監視</li>
<li>ネットワーク検査システム</li>
</ul>
</dt>
<dt>構成: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5007</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームの構成が変更されました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >Microsoft Defender ウイルス対策構成が変更されました。これが予期しないイベントである場合は、マルウェアの結果である可能性があるため、設定を確認する必要があります。<dl>
<dt>Old value: &lt;古い値の番号&gt; 古いウイルス対策構成の値。</dt>
<dt>New value: &lt;新しい値の番号&gt; 新しいウイルス対策構成の値。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5008</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策エンジンでエラーが発生し、失敗しました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策エラーが原因でエンジンが終了しました。
<dl>
<dt>Failure Type: &lt;エラーの種類&gt; (たとえば、クラッシュまたはハンギング) </dt>
<dt>Exception Code: &lt;エラー コード&gt;</dt>
<dt>Resource: &lt;リソース&gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >
このイベントをトラブルシューティングするには:<ol>
<li>サービスを再起動してみてください。<ul>
<li>マルウェア対策、ウイルス対策、スパイウェアの場合は、管理者特権でコマンド プロンプトに「<b>net stop msmpsvc</b>」と入力し、「<b>net start msmpsvc</b>」と入力してマルウェア対策エンジンを再起動します。</li>
<li><i>ネットワーク検査システム</i>の場合は、管理者特権でのコマンド プロンプトに「<b>net start nissrv</b>」、さらに「<b>net start nissrv</b>」と入力して、NiSSRV.exe ファイルを使用して<i>ネットワーク検査システム</i> エンジンを再起動します。
</li>
</ul>
</li>
<li>同じようでエラーが発生した場合は、<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft サポート サイト</a>にアクセスし、[<b>検索</b>] ボックスにエラー番号を入力してエラー コードを検索し、<a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。</li>
</ol>
</td>
</tr>
<tr>
<td>
ユーザー操作:
</td>
<td >予期しないエラーが発生したため、Microsoft Defender ウイルス対策のクライアント エンジンが停止しました。このイベントのトラブルシューティングを行うには:<ol>
<li>スキャンを再度実行します。</li>
<li>同じ方法で失敗した場合は、<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft サポートサイト</a>に移動し、[<b>検索</b>] ボックスにエラー番号を入力してエラー コードを探します。</li>
<li><a href="/microsoft-365/admin/get-help-support">Microsoft テクニカル サポート</a>にお問い合わせください。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5009</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェアやその他の望ましくない可能性があるソフトウェアのスキャンが有効です。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策のマルウェアやその他の望ましくない可能性のあるソフトウェアのスキャンが有効になっています。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5010</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェアなどの望ましくない可能性があるソフトウェアのスキャンが無効です。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策のマルウェアやその他の望ましくない可能性のあるソフトウェアのスキャンが無効です。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5011</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>ウイルスのスキャンが有効です。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策スキャンが有効になっています。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5012</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>ウイルスのスキャンは無効になっています。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策スキャンが無効になっています。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5013</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>
</b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>改ざん防止によって、Microsoft Defender ウイルス対策がブロックされました。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
改ざん防止が有効になっている場合、Defender の設定を変更しようとするとブロックされ、イベント ID 5013 が生成され、どの設定の変更がブロックされたかが示されます。
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5100</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームは間もなく期限切れになります。 </b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策は猶予期間に入り、間もなく有効期限が切れます。 有効期限が切れると、このプログラムによるウイルス、スパイウェアやその他の望ましくない可能性のあるソフトウェアに対する保護が無効になります。
<dl>
<dt>Expiration ReasonMicrosoft Defender ウイルス対策の有効期限が切れる理由。</dt>
<dt>Expiration Date: Microsoft Defender ウイルス対策の有効期限が切れる日。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">イベント ID: 5101</th>
</tr>
<tr><td>
シンボリック名:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
メッセージ:
</td>
<td >
<b>マルウェア対策プラットフォームの有効期限が切れています。</b>
</td>
</tr>
<tr>
<td>
説明:
</td>
<td >
Microsoft Defender ウイルス対策の猶予期間の有効期限が切れています。 ウイルス、スパイウェア、その他の望ましくない可能性のあるソフトウェアに対する保護が無効です。
<dl>
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;エラー コード&gt; 脅威の状態に関連付けられている結果コード。標準の HRESULT 値です。</dt>
<dt>Error Description: &lt;エラーの説明&gt; 当該エラーの説明。</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
## Microsoft Defender ウイルス対策 クライアント エラー コード。Microsoft Defender ウイルス対策でなにか問題が発生した場合は、通常、問題のトラブルシューティングに役立つエラー コードが表示されます。 ほとんどの場合、エラーは更新プログラムのインストールに問題が発生したという意味です。
このセクションでは、Microsoft Defender ウイルス対策 クライアント エラーに関する次の情報を提供します。
- エラー コード - エラーの考えられる理由 - 今すぐ実行する操作に関するアドバイス

これらのテーブルの情報を使用して、Microsoft Defender ウイルス対策のエラー コードのトラブルシューティングに役立てます。


<table>
<tr>
<th colspan="2">エラーコード: 0x80508007</th>
</tr>
<tr>
<td>メッセージ</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
考えられる理由
</td>
<td>
このエラーは、メモリが使い果たされている可能性を示します。
</td>
</tr>
<tr>
<td>解決方法</td>
<td>
<ol>
<li>デバイスで使用可能なメモリを確認します。</li>
<li>実行中の未使用のアプリケーションを閉じて、デバイス上のメモリを解放します。</li>
<li>デバイスを再起動し、スキャンを再度実行します。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x8050800C</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、セキュリティ製品に問題がある可能性を示します。
</td>
</tr><tr><td>解決方法</td><td>
<ol>
<li>定義を更新します。 次のいずれかを行います:<ol>
<li>Windows セキュリティ アプリでセキュリティ インテリジェンスの更新プログラムを取得します。 <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>または、
</li>
<li><a href="https://aka.ms/wdsi">Microsoft セキュリティ インテリジェンス サイト</a> から最新の定義をダウンロードします。注: サイトからダウンロードした定義ファイルのサイズは 60 MB を超える可能性があるため、定義を更新するための長期的なソリューションとして使用しないでください。</li>
</ol>
</li>
<li>フル スキャンを実行します。
</li>
<li>デバイスを再起動して、もう一度やり直します。</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508020</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、エンジン構成エラーが発生している可能性を示します。一般に、これはエンジンが正しく機能しない入力データに関連しています。
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x805080211
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、Microsoft Defender ウイルス対策が脅威を検疫できなかったことを示します。
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508022
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、脅威の削除を完了するために再起動が必要なことを示します。
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、脅威がメディアに存在しなくなったか、マルウェアがデバイスのスキャンを阻止している可能性を示します。
</tr><tr><td>解決方法
</td>
<td>
<a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> を実行して、セキュリティ ソフトウェアを更新してから、もう一度お試しください。
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508024 </th></tr>
<tr>
<td>メッセージ</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、システム全体のスキャンが必要な可能性を示します。
</td></tr>
<tr>
<td>解決方法</td><td>
フル システム スキャンを実行します。
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508025
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、脅威の削除を完了するために手動の手順が必要であることを示します。
</td></tr><tr><td>解決方法</td><td>
<a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Center Encyclopedia</a> に記載されている手動修復手順に従います。 イベント履歴には、脅威に特化したリンクがあります。<br/></td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508026
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、コンテナーの種類内の削除がサポートされていない可能性があることを示します。
</td></tr><tr><td>解決方法</td><td>Microsoft Defender ウイルス対策は、アーカイブ内で検出された脅威を修復できません。検出されたリソースを手動で削除することを検討してください。</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508027
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、低および中規模の脅威の削除が無効になる可能性を示します。
</td></tr><tr><td>解決方法</td><td>
検出された脅威を確認し、必要に応じて解決します。
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508029
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、脅威の再スキャンが必要であることを示します。
</td></tr><tr><td>解決方法</td><td>
フル システム スキャンを実行します。
</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508030
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、オフライン スキャンが必要であることを示します。
</td></tr><tr><td>解決方法</td><td>オフライン Microsoft Defender ウイルス対策を実行します。これを行う方法については、「<a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">オフラインの Microsoft Defender ウイルス対策の記事</a>」 を参照してください。</td>
</tr>
<tr>
<th colspan="2">エラー コード: 0x80508031
</th>
</tr><tr><td>メッセージ</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>考えられる理由</td>
<td>
このエラーは、Microsoft Defender ウイルス対策が現在のバージョンのプラットフォームをサポートしておらず、新しいバージョンのプラットフォームが必要なことを示します。
</td></tr><tr><td>解決方法</td><td>
Windows 10 と Windows 11 でのみ Microsoft Defender ウイルス対策を使用できます。 Windows 8、Windows 7、および Windows Vista では、<a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a> を使用できます。<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a> 次のエラー コードは、Microsoft Defender ウイルス対策の内部テスト中に使用されます。

これらのエラーが表示された場合は、[定義を更新](manage-updates-baselines-microsoft-defender-antivirus.md)し、エンドポイントで直接再スキャンを実行できます。


<table>
<tr>
<th colspan="3">内部エラー コード</th>
</tr>
<tr>
<th><b>エラー コード</b></th>
<th>メッセージが表示されました</th>
<th>エラーと解決の考えられる理由</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
インターネット接続を確認してから、もう一度スキャンを実行してください。
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E
</td>
<td rowspan="34">
これは内部エラーです。 原因が明確に定義されていません。
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
これは内部エラーです。 マルウェアの削除が成功しなかった場合にトリガーされる可能性があります。
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
これは内部エラーです。 スキャンの完了に失敗したときにトリガーされた可能性があります。
</td>
</tr>
</table>

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)


## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策保護のレポート](report-monitor-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
