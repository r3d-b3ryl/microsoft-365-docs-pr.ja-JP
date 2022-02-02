---
title: 攻撃面の減少を理解して使用する
ms.reviewer: ''
description: Microsoft Defender for Endpoint の攻撃表面の縮小機能について説明します。
keywords: asr, 攻撃表面の縮小, Microsoft Defender for Endpoint, microsoft Defender, ウイルス対策, av, Windows Defender
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
ms.collection: m365initiative-m365-defender
ms.date: 1/18/2022
ms.openlocfilehash: 5878b29b5d40076cd515dde6737a4e7c7d70ab56
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62320981"
---
# <a name="understand-and-use-attack-surface-reduction-capabilities"></a>攻撃表面の縮小機能の理解と使用

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

攻撃表面は、組織がサイバー脅威や攻撃に対して脆弱なすべての場所です。 Defender for Endpoint には、攻撃の表面を減らすのに役立ついくつかの機能が含まれています。 攻撃表面の縮小の詳細については、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="configure-attack-surface-reduction-capabilities"></a>攻撃面の減少機能を構成する

環境で攻撃表面の縮小を構成するには、次の手順を実行します。

1. [ハードウェア ベースの分離を有効にMicrosoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。

2. アプリケーション制御を有効にする。

   1. [基本ポリシー] を [Windows] で確認します。 「 [基本ポリシーの例」を参照してください](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。
   2. 「アプリケーション コントロール[Windows Defenderガイド」を参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。
   3. 「アプリケーション[制御 (WDAC) Windows Defenderの展開」を参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。

3. [フォルダー アクセスの制御を有効にする](enable-controlled-folders.md)。

4. [[ネットワーク保護] をオンにする](enable-network-protection.md)。

5. [エクスプロイト保護を有効にする](enable-exploit-protection.md)。

6. [攻撃表面の縮小ルールを展開します](attack-surface-reduction-rules-deployment.md)。

7. ネットワーク ファイアウォールを設定します。

   1. 高度なセキュリティを備Windows Defender[ファイアウォールの概要を確認します](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
   2. ファイアウォール ポリシー [Windows Defenderする](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)方法を決定するには、「ファイアウォールの設計ガイド」を使用します。
   3. 高度なセキュリティ[Windows Defender組織](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)のファイアウォールをセットアップするには、「ファイアウォールの展開ガイド」を使用します。

> [!TIP]
> ほとんどの場合、攻撃表面の縮小機能を構成する場合、次の方法から選択できます。
>
> - Microsoft エンドポイント マネージャー (現在は、Microsoft IntuneとMicrosoft Endpoint Configuration Manager)
> - グループ ポリシー
> - PowerShell コマンドレット

## <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>エンドポイント向け Microsoft Defender の攻撃表面の縮小をテストする

組織のセキュリティ チームの一部として、監査モードで実行する攻撃表面の縮小機能を構成して、その動作を確認できます。 監査モードでは、次の機能を有効にできます。

- 攻撃面の減少ルール
- エクスプロイト保護
- ネットワーク保護
- 監査モードでのフォルダー アクセスの制御

監査モードでは、機能を有効にした場合に何が起こったかの記録を確認できます。

機能の動作をテストするときに監査モードを有効にできます。 テスト専用の監査モードを有効にすると、監査モードが業務用アプリに影響を与えなくるのを防ぐのに役立ちます。 また、一定の期間に発生する疑わしいファイル変更の試行回数を確認できます。

この機能は、アプリ、スクリプト、またはファイルが変更されるのをブロックまたは防止できません。 ただし、イベント ログWindows機能が完全に有効になっている場合と同様にイベントが記録されます。 監査モードを使用すると、イベント ログを確認して、機能が有効になっている場合の影響を確認できます。

監査されたエントリを見つけるには、「**Applications and Services** **Microsoft** \>  \>  \> Windows \> Windows Defender **してください**。

Defender for Endpoint を使用して、各イベントの詳細を取得します。 これらの詳細は、攻撃表面の縮小ルールを調査する場合に特に役立ちます。 Defender for Endpoint コンソールを使用すると、アラートタイムラインと調査シナリオの一部として問題 [を調査できます](investigate-alerts.md)。

グループ ポリシー、PowerShell、および構成サービス プロバイダー (CSP) を使用して監査モードを有効にできます。

> [!TIP]
> また、テストグラウンドの[Windows Defenderにアクセス](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)して demo.wd.microsoft.com 機能を確認し、機能の動作を確認できます。

| 監査オプション | 監査モードを有効にする方法 | イベントを表示する方法 |
|---|---|---|
| 監査はすべてのイベントに適用されます | [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md) | [フォルダー アクセスイベントの制御](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer) |
| 監査は個々のルールに適用されます | [手順 1: 監査を使用して ASR ルールをテストする](attack-surface-reduction-rules-deployment-phase-2.md#step-1-test-asr-rules-using-audit) | [手順 2: [攻撃表面の縮小ルール] レポート ページについて](attack-surface-reduction-rules-deployment-phase-2.md#step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal) |
| 監査はすべてのイベントに適用されます | [ネットワーク保護を有効にする](enable-network-protection.md) | [ネットワーク保護イベント](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer) |
| 監査は個々の軽減策に適用されます | [エクスプロイト保護を有効にする](enable-exploit-protection.md) | [エクスプロイト保護イベント](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer) |

## <a name="view-attack-surface-reduction-events"></a>攻撃面の減少イベントを表示する

イベント ビューアーで攻撃表面の縮小イベントを確認し、動作しているルールや設定を監視します。 また、設定が "ノイズ" すぎるか、毎日のワークフローに影響を与えるかどうかを判断することもできます。

イベントのレビューは、機能を評価するときに便利です。 機能または設定の監査モードを有効にし、完全に有効にした場合の動作を確認できます。

このセクションでは、すべてのイベント、関連する機能または設定を一覧表示し、特定のイベントにフィルター処理するカスタム ビューを作成する方法について説明します。

E5 サブスクリプションをお持ちで、[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) を使用している場合は、Windows セキュリティの一部としてイベント、ブロック、および警告に関する詳細なレポートを取得します。

### <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>カスタム ビューを使用して攻撃表面の縮小機能を確認する

イベント ビューアーにカスタム ビュー Windows特定の機能と設定のイベントのみを表示します。 最も簡単な方法は、カスタム ビューを XML ファイルとしてインポートすることです。 このページから XML を直接コピーできます。

また、機能に対応するイベント領域に手動で移動することもできます。

#### <a name="import-an-existing-xml-custom-view"></a>既存の XML カスタム ビューをインポートする

1. 空の.txtファイルを作成し、使用するカスタム ビューの XML をそのファイルに.txtします。 使用するカスタム ビューごとにこれを行います。 ファイルの名前を次のように変更します (種類を次のように変更.txt.xml)。
    - フォルダー アクセス イベントのカスタム ビューの制御: *cfa-events.xml*
    - エクスプロイト保護イベントのカスタム ビュー: *ep-events.xml*
    - 攻撃表面の縮小イベントのカスタム ビュー: *asr-events.xml*
    - ネットワーク/保護イベントのカスタム ビュー: *np-events.xml*

2. [**イベント ビューアー] と** 入力し、[スタート メニュービューアー **] を開きます**。

3. [アクション **のインポート** \> **] [カスタム ビュー...] を選択します。**

   > [!div class="mx-imgBorder"]
   > ![[Even ビューアー] ウィンドウの左側にあるカスタム ビューのインポートを強調表示するアニメーション。](images/events-import.gif)

4. 必要なカスタム ビューの XML ファイルを抽出した場所に移動し、選択します。

5. [**開く**]を選択します。

6. その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。

#### <a name="copy-the-xml-directly"></a>XML を直接コピーする

1. [**イベント ビューアー]** を [スタート メニュー入力して、[イベント ビューアー] Windows **開きます**。

2. 左側のパネルの [アクション] **で、[** カスタム ビュー **の作成]を選択します。**

   > [!div class="mx-imgBorder"]
   > ![イベント ビューアー ウィンドウでカスタム ビューの作成オプションを強調表示するアニメーション。](images/events-create.gif)

3. [XML] タブに移動し、[クエリの手動編集 **] を選択します**。 XML オプションを使用すると、[フィルター] タブを使用してクエリを編集できないという警告が表示されます。 **[はい]** を選択します。

4. イベントをフィルター処理する機能の XML コードを XML セクションに貼り付けます。

5. [**OK**] を選択します。 フィルターの名前を指定します。 これにより、その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。

#### <a name="xml-for-attack-surface-reduction-rule-events"></a>攻撃表面の縮小ルール イベントの XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-controlled-folder-access-events"></a>フォルダー アクセスイベントを制御するための XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-exploit-protection-events"></a>エクスプロイト保護イベントの XML

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

### <a name="list-of-attack-surface-reduction-events"></a>攻撃表面の縮小イベントの一覧

すべての攻撃表面の縮小イベントは、**Microsoft >** > Windows の [アプリケーションとサービス ログ] の下にあり、次の表に示すフォルダーまたはプロバイダーにあります。

これらのイベントには、次のイベント ビューアー Windowsアクセスできます。

1. [スタート] **メニューを** 開き、イベント **ビューアーと入力** し、イベント ビューアーの **結果を選択** します。
2. [**アプリケーションとサービス ログ] > Microsoft** > Windows展開し、次の表の [プロバイダー **/** ソース] の下にあるフォルダーに移動します。
3. サブアイテムをダブルクリックすると、イベントが表示されます。 イベントをスクロールして、探しているイベントを見つける。

   ![イベント ビューアーを使用して表示されるアニメーション。](images/event-viewer.gif)

<br>

****

|特徴|プロバイダー/ソース|イベント ID|説明|
|---|---|:---:|---|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|1|ACG の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|2|ACG の実施|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|3|[Do not allow child processes] (子プロセスを許可しない) 監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|4|[Do not allow child processes] (子プロセスを許可しない) ブロック|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|5|[Block low integrity images] (整合性が低いイメージのブロック) 監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|6 |[Block low integrity images] (整合性が低いイメージのブロック) ブロック|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|7 |[Block remote images] (リモート イメージのブロック) 監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|8 |[Block remote images] (リモート イメージのブロック) ブロック|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|9 |[Disable win32k system calls] (win32k システム呼び出しの無効化) 監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|10|[Disable win32k system calls] (win32k システム呼び出しの無効化) ブロック|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|11|[Code integrity guard] (コードの整合性の保護) 監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|12 |[Code integrity guard] (コードの整合性の保護) ブロック|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|13|EAF の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|14 |EAF の実施|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|15 |EAF+ の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|16|EAF+ の実施|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|17 |IAF の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|18 |IAF の実施|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|19|ROP StackPivot の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|20|ROP StackPivot の実施|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)| 21|ROP CallerCheck の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|22|ROP CallerCheck の実施|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|23|ROP SimExec の監査|
|エクスプロイト保護|Security-Mitigations (カーネル モード/ユーザー モード)|24|ROP SimExec の実施|
|エクスプロイト保護|WER-Diagnostics|5|CFG のブロック|
|エクスプロイト保護|Win32K (運用)|260|信頼されていないフォント|
|ネットワーク保護|Windows Defender (運用)|5007|設定が変更された場合のイベント|
|ネットワーク保護|Windows Defender (運用)|1125|監査モードでネットワーク保護が発生した場合のイベント|
|ネットワーク保護|Windows Defender (運用)|1126|ブロック モードでネットワーク保護が発生した場合のイベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|5007|設定が変更された場合のイベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1124|監査された制御フォルダー アクセス イベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1123|ブロックされたフォルダー アクセスイベントの制御|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1127|ブロックされたフォルダー アクセスのセクター書き込みブロック イベント|
|コントロールされたフォルダー アクセス|Windows Defender (運用)|1128|監査された制御フォルダー アクセス セクター書き込みブロック イベント|
|攻撃面の縮小|Windows Defender (運用)|5007|設定が変更された場合のイベント|
|攻撃面の縮小|Windows Defender (運用)|1122|監査モードでルールが発生した場合のイベント|
|攻撃面の縮小|Windows Defender (運用)|1121|ブロック モードでルールが発生した場合のイベント|

>[!NOTE]
> ユーザーの観点から見ると、ASR Warn モード通知は、攻撃表面の縮小ルールWindowsトースト通知として行います。
>
> ASR では、ネットワーク保護は監査モードとブロック モードのみを提供します。

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a>攻撃表面の縮小について詳しくは、リソースを参照してください。

ビデオで説明したように、Defender for Endpoint には、いくつかの攻撃表面の縮小機能が含まれています。 詳細については、次のリソースを使用します。

| 記事 | 説明 |
|:---|:---|
| [ハードウェア ベースの分離](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | システムの開始と実行中のシステムの整合性を保護し、維持します。 ローカル構成証明とリモート構成証明を使用してシステムの整合性を検証します。 悪意のある web サイトからMicrosoft Edgeを保護するために、コンテナーの分離を使用します。 |
| [アプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | アプリケーション制御を使用して、アプリケーションを実行するために信頼を得る必要があります。 |
| [制御されたフォルダー アクセス](controlled-folders.md) | 悪意のあるアプリや疑わしいアプリ (ファイル暗号化ランサムウェア マルウェアを含む) がキー システム フォルダー内のファイルに変更を加えるのを防ぐのに役立ちます (Microsoft Defender ウイルス対策) |
| [ネットワーク保護](network-protection.md) | 組織のデバイス上のネットワーク トラフィックと接続に対する保護を拡張します。 (必要なMicrosoft Defender ウイルス対策) |
| [エクスプロイト保護](exploit-protection.md) | 組織が使用するオペレーティング システムとアプリが悪用されるのを保護するのに役立ちます。 エクスプロイト保護は、サードパーティのウイルス対策ソリューションでも機能します。 |
| [攻撃面の減少ルール](attack-surface-reduction.md) | マルウェアの阻止に役立つインテリジェントなルールを使用して、アプリケーションの脆弱性 (攻撃面) を減らします。 (必要なMicrosoft Defender ウイルス対策)。 |
| [デバイス コントロール](device-control-report.md) | 組織内のリムーバブル ストレージや USB ドライブなどのデバイスで使用されるメディアを監視および制御することにより、データ損失から保護します。 |
