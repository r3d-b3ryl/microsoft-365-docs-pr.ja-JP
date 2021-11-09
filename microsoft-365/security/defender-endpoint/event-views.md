---
title: 攻撃面の減少イベントを表示する
description: カスタム ビューをインポートして、攻撃表面の縮小イベントを表示します。
keywords: イベント ビュー、exploit guard、監査、レビュー、イベント
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 7dccc8992d808b5f9cea2b190a9b40cdf75f3392
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883175"
---
# <a name="view-attack-surface-reduction-events"></a>攻撃面の減少イベントを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

イベント ビューアーで攻撃表面の縮小イベントを確認し、動作しているルールや設定を監視します。 また、設定が "ノイズ" すぎるか、毎日のワークフローに影響を与えるかどうかを判断することもできます。

イベントのレビューは、機能を評価するときに便利です。 機能または設定の監査モードを有効にし、完全に有効にした場合の動作を確認できます。

この記事では、すべてのイベント、関連する機能または設定を一覧表示し、特定のイベントにフィルター処理するカスタム ビューを作成する方法について説明します。

E5 サブスクリプションを持っている場合は、Windows セキュリティ、イベント、ブロック、警告に関する詳細なレポートを取得し[、Microsoft Defender for Endpoint を使用します](microsoft-defender-endpoint.md)。

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>カスタム ビューを使用して攻撃表面の縮小機能を確認する

イベント ビューアーにカスタム ビュー Windows特定の機能と設定のイベントのみを表示します。 最も簡単な方法は、カスタム ビューを XML ファイルとしてインポートすることです。 このページから XML を直接コピーできます。

また、機能に対応するイベント領域に手動で移動することもできます。

### <a name="import-an-existing-xml-custom-view"></a>既存の XML カスタム ビューをインポートする

1. 空の.txtファイルを作成し、使用するカスタム ビューの XML をそのファイルに.txtします。 使用するカスタム ビューごとにこれを行います。 ファイルの名前を次のように変更します (種類を次のように変更.txt.xml)。
    - フォルダー アクセス イベントのカスタム ビューの制御: *cfa-events.xml*
    - エクスプロイト保護イベントのカスタム ビュー: *ep-events.xml*
    - 攻撃表面の縮小イベントのカスタム ビュー: *asr-events.xml*
    - ネットワーク/保護イベントのカスタム ビュー: *np-events.xml*

2. [**イベント ビューアー] と** 入力し、[スタート メニュー ビューアー]**を開きます**。

3. [アクション **の** \> **インポート] [カスタム ビュー...] を選択します。**

   > [!div class="mx-imgBorder"]
   > ![[Even ビューアー] ウィンドウの左側にあるカスタム ビューのインポートを強調表示するアニメーション。](images/events-import.gif)

4. 必要なカスタム ビューの XML ファイルを抽出した場所に移動し、選択します。

5. [**開く**]を選択します。

6. その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。

### <a name="copy-the-xml-directly"></a>XML を直接コピーする

1. [**イベント ビューアー]** を [スタート メニュー入力して、[イベント ビューアー] Windows **開きます**。

2. 左側のパネルの [アクション] で **、[** カスタム ビューの **作成]を選択します。**

   > [!div class="mx-imgBorder"]
   > ![イベント ビューアー ウィンドウでカスタム ビューの作成オプションを強調表示するアニメーション。](images/events-create.gif)

3. [XML] タブに移動し、[クエリの手動編集 **] を選択します**。 XML オプションを使用すると、[フィルター] タブを使用してクエリを編集できないという警告が表示されます。 **[はい]** を選択します。

4. イベントをフィルター処理する機能の XML コードを XML セクションに貼り付けます。

5. **[OK]** を選択します。 フィルターの名前を指定します。 これにより、その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。

### <a name="xml-for-attack-surface-reduction-rule-events"></a>攻撃表面の縮小ルール イベントの XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>フォルダー アクセスイベントを制御するための XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>エクスプロイト保護イベントの XML

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

### <a name="xml-for-network-protection-events"></a>ネットワーク保護イベントの XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>攻撃表面の縮小イベントの一覧

すべての攻撃表面の縮小イベントは **、Microsoft** > > Windows の [アプリケーションとサービス ログ] の下にあり、次の表に示すフォルダーまたはプロバイダーにあります。

これらのイベントには、次のイベント ビューアー Windowsアクセスできます。

1. [スタート] **メニューを** 開き、イベント **ビューアーと入力** し、イベント ビューアーの **結果を選択** します。
2. [**アプリケーションとサービス ログ]** > Microsoft > Windows展開し、次の表の [**プロバイダー/** ソース] の下にあるフォルダーに移動します。
3. サブアイテムをダブルクリックすると、イベントが表示されます。 イベントをスクロールして、探しているイベントを見つける。

   ![イベント ビューアーを使用して表示されるアニメーション。](images/event-viewer.gif)

<br>

****

|機能|プロバイダー/ソース|イベント ID|説明|
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
