---
title: 攻撃表面の縮小イベントの表示
description: カスタム ビューをインポートして、攻撃表面の縮小イベントを表示します。
keywords: イベント ビュー、exploit guard、監査、レビュー、イベント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: de605a667284c1218a3efe6e388d99b26b42e333
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068579"
---
# <a name="view-attack-surface-reduction-events"></a>攻撃表面の縮小イベントの表示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

イベント ビューアーで攻撃表面の縮小イベントを確認し、動作しているルールや設定を監視します。 また、設定が "ノイズ" すぎるか、毎日のワークフローに影響を与えるかどうかを判断することもできます。

イベントのレビューは、機能を評価するときに便利です。 機能または設定の監査モードを有効にし、完全に有効にした場合の動作を確認できます。

この記事では、すべてのイベント、関連する機能または設定を一覧表示し、特定のイベントにフィルター処理するカスタム ビューを作成する方法について説明します。

E5 サブスクリプションを持ち、Microsoft Defender for Endpoint を使用している場合は、Windows セキュリティの一部としてイベントやブロックに関する詳細なレポート [を取得します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>カスタム ビューを使用して攻撃表面の縮小機能を確認する

Windows イベント ビューアーでカスタム ビューを作成して、特定の機能と設定のイベントのみを表示します。 最も簡単な方法は、カスタム ビューを XML ファイルとしてインポートすることです。 このページから XML を直接コピーできます。

また、機能に対応するイベント領域に手動で移動することもできます。

### <a name="import-an-existing-xml-custom-view"></a>既存の XML カスタム ビューをインポートする

1. 空の .txt ファイルを作成し、使用するカスタム ビューの XML を .txt ファイルにコピーします。 使用するカスタム ビューごとにこれを行います。 ファイルの名前を次のように変更します (型を .txt から .xml に変更してください)。
    - フォルダー アクセス イベントのカスタム ビューの制御: *cfa-events.xml*
    - エクスプロイト保護イベントのカスタム ビュー: *ep-events.xml*
    - 攻撃表面の縮小イベントのカスタム ビュー: *asr-events.xml*
    - ネットワーク/保護イベントのカスタム ビュー: *np-events.xml*

2. [スタート **] メニューに** イベント ビューアーを入力し、[イベント ビューアー] **を開きます**。

3. [アクション **の**  >  **インポート] [カスタム ビュー...] を選択します。**

    ![[Even ビューアー] ウィンドウの左側にあるカスタム ビューのインポートを強調表示するアニメーション](/windows/security/threat-protection/images/events-import)

4. 必要なカスタム ビューの XML ファイルを抽出した場所に移動し、選択します。

5. [**開く**]を選択します。

6. その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。

### <a name="copy-the-xml-directly"></a>XML を直接コピーする

1. [ **スタート] メニューに** イベント ビューアーを入力し、Windows イベント ビューアー **を開きます**。

2. 左側のパネルの [アクション] で **、[** カスタム ビューの **作成]を選択します。**

    ![イベント ビューアー ウィンドウでカスタム ビューの作成オプションを強調表示するアニメーション](/windows/security/threat-protection/images/events-create)

3. [XML] タブに移動し、[クエリの手動編集 **] を選択します**。 XML オプションを使用すると、[フィルター] タブを使用してクエリを編集できないという警告が表示されます。 **[はい]** を選択します。

4. イベントをフィルター処理する機能の XML コードを XML セクションに貼り付けます。

5. **[OK]** をクリックします。 フィルターの名前を指定します。

6. その機能に関連するイベントのみを表示するためにフィルター処理するカスタム ビューが作成されます。

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

すべての攻撃表面の縮小イベントは、[アプリケーションとサービス ログ] > **Microsoft > Windows** の下にあり、次の表に示すフォルダーまたはプロバイダーです。

Windows イベント ビューアーで次のイベントにアクセスできます。

1. [スタート] **メニューを** 開き、イベント **ビューアーと入力** し、イベント ビューアーの **結果を選択** します。
2. [ **アプリケーションとサービス** ログ] > Microsoft > Windows を展開し、次の表の [プロバイダー **/** ソース] の一覧にあるフォルダーに移動します。
3. サブアイテムをダブルクリックすると、イベントが表示されます。 イベントをスクロールして、探しているイベントを見つける。

   ![イベント ビューアーを使用したアニメーションの表示](/windows/security/threat-protection/images/event-viewer)

機能 | プロバイダー/ソース | イベント ID | 説明
:-|:-|:-:|:-
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 1 | ACG 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 2 | ACG の強制
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 3 | 子プロセスの監査を許可しない
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 4 | 子プロセスブロックを許可しない
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 5 | 低整合性イメージの監査をブロックする
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 6 | 低整合性イメージ ブロックをブロックする
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 7 | リモート イメージの監査をブロックする
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 8 | [リモート イメージのブロック] ブロック
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 9 | win32k システム呼び出しの監査を無効にする
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 10 | win32k システム呼び出しブロックを無効にする
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 11 | コード整合性ガードの監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 12  | コード整合性ガード ブロック
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 13 | EAF 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 14  | EAF の強制
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 15  | EAF+ 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 16  | EAF+ の強制
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 17  | IAF 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 18  | IAF の強制
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 19 | ROP StackPivot 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 20 | ROP StackPivot の強制
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) |  21 | ROP CallerCheck 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 22 | ROP CallerCheck の強制
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 23 | ROP SimExec 監査
エクスプロイト保護 | Security-Mitigations (カーネル モード/ユーザー モード) | 24 | ROP SimExec の強制
エクスプロイト保護 | WER-Diagnostics | 5 | CFG ブロック
エクスプロイト保護 | Win32K (運用) | 260 | 信頼されていないフォント
ネットワーク保護 | Windows Defender (運用) | 5007 | 設定が変更された場合のイベント
ネットワーク保護 | Windows Defender (運用) | 1125 | 監査モードでネットワーク保護が発生した場合のイベント
ネットワーク保護 | Windows Defender (運用) | 1126 | ブロック モードでネットワーク保護が発生した場合のイベント
フォルダー アクセスの制御 | Windows Defender (運用) | 5007 | 設定が変更された場合のイベント
フォルダー アクセスの制御 | Windows Defender (運用) | 1124 | 監査された制御フォルダー アクセス イベント
フォルダー アクセスの制御 | Windows Defender (運用) | 1123 | ブロックされたフォルダー アクセスイベントの制御
フォルダー アクセスの制御 | Windows Defender (運用) | 1127 | ブロックされたフォルダー アクセスのセクター書き込みブロック イベント
フォルダー アクセスの制御 | Windows Defender (運用) | 1128 | 監査された制御フォルダー アクセス セクター書き込みブロック イベント
攻撃面の縮小 | Windows Defender (運用) | 5007 | 設定が変更された場合のイベント
攻撃面の縮小 | Windows Defender (運用) | 1122 | 監査モードでルールが発生した場合のイベント
攻撃面の縮小 | Windows Defender (運用) | 1121 | ブロック モードでルールが発生した場合のイベント
