---
title: 攻撃面の縮小 (ASR) を理解して使用する
ms.reviewer: ''
description: Microsoft Defender for Endpointの攻撃面の縮小機能について説明します。
keywords: asr, 攻撃面の縮小, 攻撃面の縮小ルール, Microsoft Defender for Endpoint, microsoft defender, ウイルス対策, av, Windows Defender
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: 05/16/2022
ms.openlocfilehash: 0bcc45907cc5d57b592f96296282f65cc3e3d772
ms.sourcegitcommit: c314e989202dc1c9c260fffd459d53bc1f08514e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66717152"
---
# <a name="understand-and-use-attack-surface-reduction-capabilities"></a>攻撃面の縮小機能を理解して使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

攻撃面は、組織がサイバー脅威や攻撃に対して脆弱なすべての場所です。 Defender for Endpoint には、攻撃面を減らすのに役立ついくつかの機能が含まれています。 攻撃面の縮小の詳細については、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="configure-attack-surface-reduction-capabilities"></a>攻撃面の減少機能を構成する

環境で攻撃面の削減を構成するには、次の手順に従います。

1. [Microsoft Edge のハードウェア ベースの分離を有効にします](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。

2. アプリケーション制御を有効にします。

   1. Windows で基本ポリシーを確認します。 [基本ポリシーの例を](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)参照してください。
   2. [Windows Defenderアプリケーション コントロールの設計ガイドを](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)参照してください。
   3. [Windows Defenderアプリケーション制御 (WDAC) ポリシーのデプロイ](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)に関するページを参照してください。

3. [フォルダー アクセスの制御を有効にします](enable-controlled-folders.md)。

4. [ネットワーク保護を有効にします](enable-network-protection.md)。

5. [エクスプロイト保護を有効にします](enable-exploit-protection.md)。

6. [攻撃対象の縮小ルールをデプロイします](attack-surface-reduction-rules-deployment.md)。

7. ネットワーク ファイアウォールを設定します。

   1. [高度なセキュリティを備えたWindows Defender ファイアウォール](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)の概要を確認します。
   2. [Windows Defender ファイアウォール設計ガイド](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)を使用して、ファイアウォール ポリシーを設計する方法を決定します。
   3. [Windows Defender ファイアウォール展開ガイド](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)を使用して、高度なセキュリティで組織のファイアウォールを設定します。

> [!TIP]
> ほとんどの場合、攻撃面の縮小機能を構成するときに、いくつかの方法から選択できます。
>
> - Microsoft エンドポイント マネージャー (Microsoft Intuneと Microsoft Endpoint Configuration Managerが含まれるようになりました)
> - グループ ポリシー
> - PowerShell コマンドレット

## <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでの攻撃面の減少をテストする

組織のセキュリティ チームの一部として、監査モードで実行する攻撃面の縮小機能を構成して、それらがどのように機能するかを確認できます。 監査モードでは、次の ASR セキュリティ機能を有効にすることができます。

- 攻撃面の減少ルール
- エクスプロイト保護
- ネットワーク保護
- フォルダーへのアクセスの制御

監査モードを使用すると、機能を有効にした場合 *に発生した* 結果のレコードを確認できます。

機能の動作をテストするときに監査モードを有効にすることができます。 テストに対してのみ監査モードを有効にすると、監査モードが基幹業務アプリに影響を与えるのを防ぐことができます。 また、特定の期間に発生する疑わしいファイル変更の試行回数を把握することもできます。

この機能は、アプリ、スクリプト、またはファイルの変更をブロックまたは禁止しません。 ただし、Windows イベント ログは、機能が完全に有効になっているかのようにイベントを記録します。 監査モードでは、イベント ログを確認して、機能が有効になっている場合にどのような影響を与えたかを確認できます。

監査対象のエントリを見つけるには、**アプリケーションとサービス** \> **Microsoft** \> **Windows** \> **Windows Defender** \> Operational に移動 **します**。

Defender for Endpoint を使用して、各イベントの詳細を取得します。 これらの詳細は、攻撃面の縮小ルールを調査する場合に特に役立ちます。 Defender for Endpoint コンソールを使用すると、 [アラート タイムラインと調査シナリオの一部として問題を調査できます](investigate-alerts.md)。

グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にすることができます。

| 監査オプション | 監査モードを有効にする方法 | イベントを表示する方法 |
|---|---|---|
| 監査はすべてのイベントに適用されます | [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md) | [フォルダー アクセスイベントの制御](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer) |
| 監査は個々のルールに適用されます | [手順 1: 監査モードを使用して ASR ルールをテストする](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit) | [手順 2: [攻撃対象の縮小ルール] レポート ページについて](attack-surface-reduction-rules-deployment-test.md#step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal) |
| 監査はすべてのイベントに適用されます | [ネットワーク保護を有効にする](enable-network-protection.md) | [ネットワーク保護イベント](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer) |
| 監査は個々の軽減策に適用されます | [エクスプロイト保護を有効にする](enable-exploit-protection.md) | [エクスプロイト保護イベント](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer) |

### <a name="attack-surface-reduction-asr-rules"></a>攻撃面の減少 (ASR) ルール

攻撃面の縮小 (ASR) ルールは、一般的な既知の攻撃面を強化するために事前に定義されています。 攻撃表面の縮小ルールを実装するために使用できる方法はいくつかあります。 推奨される方法については、次の攻撃面縮小 (ASR) ルールの展開に関するトピックを参照してください。

- [攻撃面の縮小 (ASR) ルールの展開の概要](attack-surface-reduction-rules-deployment.md)
- [攻撃面の縮小 (ASR) ルールの展開を計画する](attack-surface-reduction-rules-deployment-plan.md)
- [攻撃面の減少 (ASR) ルールをテストする](attack-surface-reduction-rules-deployment-test.md)
- [攻撃面の減少 (ASR) ルールを有効にする](attack-surface-reduction-rules-deployment-implement.md)
- [攻撃面の減少 (ASR) ルールの運用化](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="view-attack-surface-reduction-events"></a>攻撃面の減少イベントを表示する

イベント ビューアーの攻撃対象の縮小イベントを確認して、動作しているルールまたは設定を監視します。 また、設定が "ノイズ" すぎるか、日常のワークフローに影響を与えているかどうかを判断することもできます。

機能を評価する場合は、イベントを確認すると便利です。 機能または設定の監査モードを有効にし、完全に有効にした場合に何が発生したかを確認できます。

このセクションでは、すべてのイベント、関連する機能または設定を一覧表示し、カスタム ビューを作成して特定のイベントにフィルター処理する方法について説明します。

E5 サブスクリプションを持ち、[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)を使用している場合は、Windows セキュリティの一部として、イベント、ブロック、警告に関する詳細なレポートを取得します。

### <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>カスタム ビューを使用して攻撃面の縮小機能を確認する

Windows イベント ビューアーでカスタム ビューを作成し、特定の機能と設定のイベントのみを表示します。 最も簡単な方法は、カスタム ビューを XML ファイルとしてインポートすることです。 このページから XML を直接コピーできます。

また、機能に対応するイベント領域に手動で移動することもできます。

#### <a name="import-an-existing-xml-custom-view"></a>既存の XML カスタム ビューをインポートする

1. 空の.txt ファイルを作成し、使用するカスタム ビューの XML を.txt ファイルにコピーします。 これは、使用するカスタム ビューごとに行います。 ファイルの名前を次のように変更します (種類を.txtから.xmlに変更してください)。
    - フォルダー アクセス イベントのカスタム ビューの制御: *cfa-events.xml*
    - エクスプロイト保護イベントのカスタム ビュー: *ep-events.xml*
    - 攻撃対象の縮小イベントのカスタム ビュー: *asr-events.xml*
    - ネットワーク/保護イベントのカスタム ビュー: *np-events.xml*

2. [スタート] メニューに **「イベント ビューアー**」と入力し **、イベント ビューアー** を開きます。

3. **[アクション** \> **インポート カスタム ビュー]を選択します。..**

   > [!div class="mx-imgBorder"]
   > ![[偶数] ビューアー ウィンドウの左側にある [カスタム ビューのインポート] を強調表示するアニメーション。](images/events-import.gif)

4. 目的のカスタム ビューの XML ファイルを抽出した場所に移動し、選択します。

5. [**開く**]を選択します。

6. その機能に関連するイベントのみを表示するようにフィルター処理するカスタム ビューが作成されます。

#### <a name="copy-the-xml-directly"></a>XML を直接コピーする

1. [スタート] メニューに **「イベント ビューアー**」と入力し、Windows イベント ビューアーを開 **きます**。

2. 左側のパネルの [**アクション]** で、[**カスタム ビューの作成**] を選択します。

   > [!div class="mx-imgBorder"]
   > ![イベント ビューアー ウィンドウでカスタム ビューの作成オプションを強調表示するアニメーション。](images/events-create.gif)

3. [XML] タブに移動し、[ **クエリを手動で編集]** を選択します。 XML オプションを使用する場合、[ **フィルター** ] タブを使用してクエリを編集できないという警告が表示されます。 [**はい**] を選択します。

4. イベントをフィルター処理する機能の XML コードを XML セクションに貼り付けます。

5. **[OK]** を選択します。 フィルターの名前を指定します。 これにより、その機能に関連するイベントのみを表示するようにフィルター処理するカスタム ビューが作成されます。

#### <a name="xml-for-attack-surface-reduction-rule-events"></a>攻撃表面の縮小ルール イベント用の XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-controlled-folder-access-events"></a>制御されたフォルダー アクセス イベントの XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-exploit-protection-events"></a>エクスプロイト保護イベント用の XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-network-protection-events"></a>ネットワーク保護イベントの XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

### <a name="list-of-attack-surface-reduction-events"></a>攻撃面の縮小イベントの一覧

すべての攻撃対象軽減イベントは、次の表に示すように、 **Microsoft > Windows >アプリケーションログとサービス ログ** の下に配置され、次の表に示すようにフォルダーまたはプロバイダーに配置されます。

Windows イベント ビューアーでは、次のイベントにアクセスできます。

1. **[スタート]** メニューを開き、「**イベント ビューアー**」と入力し、**イベント ビューアー** 結果を選択します。
2. **Microsoft > Windows >アプリケーションとサービス ログ** を展開し、次の表の [**プロバイダー/ソース]** の下にあるフォルダーに移動します。
3. サブ項目をダブルクリックすると、イベントが表示されます。 イベントをスクロールして探しているイベントを見つけます。

   ![イベント ビューアーを使用して示すアニメーション。](images/event-viewer.gif)

<br>

****

|機能|プロバイダー/ソース|イベント ID|説明|
|---|---|:---:|---|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|1|ACG の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|2|ACG の実施|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|3|[Do not allow child processes] (子プロセスを許可しない) 監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|4|[Do not allow child processes] (子プロセスを許可しない) ブロック|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|5|[Block low integrity images] (整合性が低いイメージのブロック) 監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|6 |[Block low integrity images] (整合性が低いイメージのブロック) ブロック|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|7 |[Block remote images] (リモート イメージのブロック) 監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|8 |[Block remote images] (リモート イメージのブロック) ブロック|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|9 |[Disable win32k system calls] (win32k システム呼び出しの無効化) 監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|10|[Disable win32k system calls] (win32k システム呼び出しの無効化) ブロック|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|11|[Code integrity guard] (コードの整合性の保護) 監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|12 |[Code integrity guard] (コードの整合性の保護) ブロック|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|13|EAF の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|14|EAF の実施|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|15|EAF+ の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|16|EAF+ の実施|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|17 |IAF の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|18 |IAF の実施|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|19|ROP StackPivot の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|20|ROP StackPivot の実施|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)| 21|ROP CallerCheck の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|22|ROP CallerCheck の実施|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|23|ROP SimExec の監査|
|エクスプロイト保護|セキュリティ軽減策 (カーネル モード/ユーザー モード)|24|ROP SimExec の実施|
|エクスプロイト保護|WER-Diagnostics|5|CFG のブロック|
|エクスプロイト保護|Win32K (運用)|260|信頼されていないフォント|
|ネットワーク保護|Windows Defender (運用)|5007|設定が変更された場合のイベント|
|ネットワーク保護|Windows Defender (運用)|1125|ネットワーク保護が監査モードで起動した場合のイベント|
|ネットワーク保護|Windows Defender (運用)|1126|ブロック モードでネットワーク保護が発生した場合のイベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|5007|設定が変更された場合のイベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1124|監査されたフォルダー アクセスの制御イベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1123|ブロックされたフォルダー アクセス イベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1127|ブロックされたフォルダー アクセス セクター書き込みブロック イベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1128|監査されたフォルダー アクセス セクター書き込みブロック イベント|
|攻撃面の縮小|Windows Defender (運用)|5007|設定が変更された場合のイベント|
|攻撃面の縮小|Windows Defender (運用)|1122|監査モードでルールが起動した場合のイベント|
|攻撃面の縮小|Windows Defender (運用)|1121|ブロック モードでルールが起動した場合のイベント|

>[!NOTE]
> ユーザーの観点から見ると、ASR 警告モードの通知は、攻撃表面の縮小ルールの Windows トースト通知として行われます。
>
> ASR では、Network Protection は監査モードとブロック モードのみを提供します。

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a>攻撃面の縮小の詳細を確認するためのリソース

ビデオで説明したように、Defender for Endpoint には、いくつかの攻撃面縮小機能が含まれています。 詳細については、次のリソースを使用してください。

| 記事 | 説明 |
|:---|:---|
| [ハードウェア ベースの分離](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | システムの起動時と実行中に、システムの整合性を保護および維持します。 ローカル構成証明とリモート構成証明を使用してシステムの整合性を検証します。 悪意のある Web サイトから保護するには、Microsoft Edge のコンテナー分離を使用します。 |
| [アプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | アプリケーション制御を使用して、アプリケーションを実行するために信頼を得る必要があります。 |
| [制御されたフォルダー アクセス](controlled-folders.md) | 悪意のあるアプリや疑わしいアプリ (ファイル暗号化ランサムウェア マルウェアを含む) が、キー システム フォルダー内のファイルに変更を加えないようにするのに役立ちます (Microsoft Defender ウイルス対策が必要です)。 |
| [ネットワーク保護](network-protection.md) | 組織のデバイス上のネットワーク トラフィックと接続に対する保護を拡張します。 (Microsoft Defender ウイルス対策が必要です)。 |
| [エクスプロイト保護](exploit-protection.md) | 組織が使用するオペレーティング システムとアプリが悪用されないように保護します。 エクスプロイト保護は、サードパーティのウイルス対策ソリューションでも機能します。 |
| [デバイス コントロール](device-control-report.md) | 組織内のリムーバブル ストレージや USB ドライブなどのデバイスで使用されるメディアを監視および制御することで、データ損失から保護します。 |
| [攻撃面の縮小 (ASR) ルールの展開ガイド](attack-surface-reduction-rules-deployment.md) | 攻撃表面の縮小ルールを展開するための概要情報と前提条件について説明します。 |
| [攻撃面の縮小 (ASR) ルールの展開を計画する](attack-surface-reduction-rules-deployment-plan.md) | 攻撃表面縮小ルールの展開に推奨される手順を一覧表示します。 |
| [攻撃面の減少 (ASR) ルールをテストする](attack-surface-reduction-rules-deployment-test.md) | 監査モードを使用して、攻撃表面の縮小ルールをテストする手順について説明します。 |
| [攻撃面の減少 (ASR) ルールを有効にする](attack-surface-reduction-rules-deployment-implement.md) | 攻撃表面縮小ルールをテスト (監査) モードからアクティブで有効な (ブロック) モードに移行する手順を示します。 |
| [攻撃面の減少 (ASR) ルールの運用化](attack-surface-reduction-rules-deployment-operationalize.md) | 日常のレビューとメンテナンスアクティビティに関する情報を提供します。 |
| [攻撃面の減少 (ASR) ルールの参照](attack-surface-reduction-rules-reference.md) | 各攻撃対象領域の縮小ルールの詳細を提供します。 |
| [攻撃面の減少ルール](attack-surface-reduction.md) | マルウェアの阻止に役立つインテリジェントなルールを使用して、アプリケーションの脆弱性 (攻撃面) を減らします。 (Microsoft Defender ウイルス対策が必要です)。 |
