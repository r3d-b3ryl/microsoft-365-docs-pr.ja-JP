---
title: パフォーマンスに関する問題のトラブルシューティング
description: Microsoft Defender for Endpointのリアルタイム保護サービスに関連する高い CPU 使用率のトラブルシューティングを行います。
keywords: トラブルシューティング、パフォーマンス、高い CPU 使用率、高い CPU 使用率、エラー、修正、更新プログラムのコンプライアンス、oms、監視、レポート、Microsoft Defender ウイルス対策
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
ms.date: 10/19/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: fbcad753d88b3ead3c6a9b37330f29b1b1fbb7a9
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66798107"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a>リアルタイム保護に関連するパフォーマンスの問題のトラブルシューティング


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

システムの CPU 使用率が高い場合や、Microsoft Defender for Endpointのリアルタイム保護サービスに関連するパフォーマンスの問題が発生している場合は、Microsoft サポートにチケットを送信できます。 [Microsoft Defender ウイルス対策診断データの収集](collect-diagnostic-data.md)の手順に従います。

管理者は、これらの問題のトラブルシューティングを自分で行うこともできます。

まず、問題が別のソフトウェアによって引き起こされているかどうかを確認することをお勧めします。 [ウイルス対策の除外については、「ベンダーに確認する」](#check-with-vendor-for-antivirus-exclusions)を参照してください。

それ以外の場合は、「 [Microsoft Protection ログの分析](#analyze-the-microsoft-protection-log)」の手順に従って、特定されたパフォーマンスの問題に関連するソフトウェアを特定できます。

次の手順に従って、Microsoft サポートへの提出に追加のログを提供することもできます。

- [プロセス モニターを使用してプロセス ログをキャプチャする](#capture-process-logs-using-process-monitor)
- [Windows パフォーマンス レコーダーを使用してパフォーマンス ログをキャプチャする](#capture-performance-logs-using-windows-performance-recorder)

## <a name="check-with-vendor-for-antivirus-exclusions"></a>ウイルス対策の除外をベンダーに確認する

システムのパフォーマンスに影響を与えるソフトウェアを簡単に特定できる場合は、ソフトウェア ベンダーのサポート情報またはサポート センターに移動します。 ウイルス対策の除外に関する推奨事項があるかどうかを検索します。 ベンダーの Web サイトにサポート チケットがない場合は、サポート チケットを開いて発行するように依頼できます。

ソフトウェア ベンダーは、 [誤検知を最小限に抑えるために、業界との提携](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)に関するさまざまなガイドラインに従うことをお勧めします。 ベンダーは、[Microsoft セキュリティ インテリジェンス ポータル](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)からソフトウェアを送信できます。

## <a name="analyze-the-microsoft-protection-log"></a>Microsoft Protection ログを分析する
Microsoft 保護ログ ファイルは **C:\ProgramData\Microsoft\Windows Defender\Support にあります**。

**MPLog-xxxxxxxx-xxxxxx.log** では、*EstimatedImpact* としてソフトウェアを実行した場合のパフォーマンスへの影響の推定情報を確認できます。

`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

<br>

****

|フィールド名|説明|
|---|---|
|ProcessImageName|プロセス イメージ名|
|TotalTime|このプロセスによってアクセスされたファイルのスキャンに費やされた累積時間 (ミリ秒単位)|
|カウント|このプロセスによってアクセスされたスキャンされたファイルの数|
|MaxTime|このプロセスによってアクセスされたファイルの最長 1 回のスキャンの期間 (ミリ秒単位)|
|MaxTimeFile|期間の最長スキャンが記録されたこのプロセスによってアクセスされたファイルの `MaxTime` パス|
|EstimatedImpact|このプロセスでスキャン アクティビティが発生した期間のうち、このプロセスによってアクセスされたファイルのスキャンに費やされた時間の割合。|
|

パフォーマンスへの影響が大きい場合は、「 [Microsoft Defender ウイルス対策スキャンの除外を構成して検証](collect-diagnostic-data.md)する」の手順に従って、パス/プロセスの除外にプロセスを追加してみてください。

前の手順で問題が解決しない場合は、次のセクションの [プロセス モニター](#capture-process-logs-using-process-monitor) または [Windows パフォーマンス レコーダー](#capture-performance-logs-using-windows-performance-recorder) を使用して詳細情報を収集できます。

## <a name="capture-process-logs-using-process-monitor"></a>プロセス モニターを使用してプロセス ログをキャプチャする

プロセス モニター (ProcMon) は、リアルタイムのプロセスを表示できる高度な監視ツールです。 これを使用して、発生しているパフォーマンスの問題をキャプチャできます。

1. [Process Monitor v3.89](/sysinternals/downloads/procmon) を次のような`C:\temp`フォルダーにダウンロードします。

2. ファイルの Web マークを削除するには:
    1. **ProcessMonitor.zip** 右クリックし、[**プロパティ**] を選択します。
    1. [ *全般* ] タブで、[セキュリティ] を探 *します*。
    1. [ **ブロック解除**] の横にあるチェック ボックスをオンにします。
    1. **[適用]** を選択します。

    :::image type="content" source="images/procmon-motw.png" alt-text="[MOTW の削除] ページ" lightbox="images/procmon-motw.png":::

3. フォルダーパス`C:\temp``C:\temp\ProcessMonitor`が表示されるようにファイルを解凍します。

4. トラブルシューティング **する**  Windows クライアントまたは Windows サーバーにProcMon.exeをコピーします。

5. ProcMon を実行する前に、CPU 使用率の高い問題に関連していない他のすべてのアプリケーションが閉じられていることを確認してください。 これを行うと、チェックするプロセスの数が最小限に抑えられます。

6. ProcMon を起動するには、2 つの方法があります。
    1. **ProcMon.exe** 右クリックし、[**管理者として実行**] を選択します。

        ログ記録は自動的に開始されるので、虫眼鏡アイコンを選択して現在のキャプチャを停止するか、キーボード ショートカット **Ctrl + E を** 使用します。

        :::image type="content" source="images/procmon-magglass.png" alt-text="虫眼鏡アイコン" lightbox="images/procmon-magglass.png":::

        キャプチャを停止したことを確認するには、虫眼鏡アイコンが赤い X で表示されているかどうかを確認します。

        :::image type="content" source="images/procmon-magglass-stop.png" alt-text="赤いスラッシュ" lightbox="images/procmon-magglass-stop.png":::

        次に、以前のキャプチャをクリアするには、消しゴム アイコンを選択します。

        :::image type="content" source="images/procmon-eraser-clear.png" alt-text="クリア アイコン" lightbox="images/procmon-eraser-clear.png":::

        または、キーボード ショートカット **Ctrl + X を使用します**。

    2. 2 番目の方法は、 **コマンド ライン** を管理者として実行し、プロセス モニター パスから次のように実行することです。

       :::image type="content" source="images/cmd-procmon.png" alt-text="cmd procmon" lightbox="images/cmd-procmon.png":::

        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```

        > [!TIP]
        > トレースを簡単に開始および停止できるように、データをキャプチャするときに ProcMon ウィンドウをできるだけ小さくします。
        >
        > :::image type="content" source="images/procmon-minimize.png" alt-text="最小化された Procmon を表示するページ" lightbox="images/procmon-minimize.png":::

7. 手順 6 のいずれかの手順に従うと、次にフィルターを設定するオプションが表示されます。 **[OK]** を選択します。 キャプチャが完了した後は、常に結果をフィルター処理できます。

   :::image type="content" source="images/procmon-filter-options.png" alt-text="フィルターアウト プロセス名としてシステム除外が選択されているページ" lightbox="images/procmon-filter-options.png":::

8. キャプチャを開始するには、虫眼鏡アイコンをもう一度選択します。

9. 問題を再現します。

    > [!TIP]
    > 問題が完全に再現されるのを待ってから、トレースが開始されたときにタイムスタンプをメモします。

10. CPU 使用率が高い状態でプロセス アクティビティが 2 ~ 4 分になったら、虫眼鏡アイコンを選択してキャプチャを停止します。

11. キャプチャを一意の名前で保存し、.pml 形式で保存するには、[ **ファイル** ] を選択し、[ **保存...** ] を選択します。ラジオ ボタン **[すべてのイベント** と **ネイティブ プロセス モニター形式 (PML)]** を選択してください。

    :::image type="content" source="images/procmon-savesettings1.png" alt-text="[保存設定] ページ" lightbox="images/procmon-savesettings1.png":::

12. 追跡を改善するには、既定のパスを次の場所に`C:\temp\ProcessMonitor\LogFile.PML``C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML`変更します。
    - `%ComputerName%` はデバイス名です
    - `MMDDYEAR` は月、日、年です
    - `Repro_of_issue` は、再現しようとしている問題の名前です

    > [!TIP]
    > 動作しているシステムがある場合は、比較するサンプル ログを取得する必要があります。

13. .pml ファイルを Zip 形式で圧縮し、Microsoft サポートに送信します。

## <a name="capture-performance-logs-using-windows-performance-recorder"></a>Windows パフォーマンス レコーダーを使用してパフォーマンス ログをキャプチャする

Windows パフォーマンス レコーダー (WPR) を使用して、Microsoft サポートへの提出に追加情報を含めることができます。 WPR は、Windows レコーディング用のイベント トレーシングを作成する強力な記録ツールです。

WPR は Windows Assessment and Deployment Kit (Windows ADK) の一部であり、 [Windows ADK のダウンロードとインストール](/windows-hardware/get-started/adk-install)からダウンロードできます。 Windows 10 [SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/) のWindows 10 ソフトウェア開発キットの一部としてダウンロードすることもできます。

WPR UI を使用してパフォーマンス ログをキャプチャする手順に従って [、WPR ユーザー インターフェイスを使用](#capture-performance-logs-using-the-wpr-ui)できます。

または、[WPR CLI](#capture-performance-logs-using-the-wpr-cli) を使用したパフォーマンス ログのキャプチャの手順に従 *って、Windows 8* 以降のバージョンで使用できるコマンド ライン ツールwpr.exeを使用することもできます。

### <a name="capture-performance-logs-using-the-wpr-ui"></a>WPR UI を使用してパフォーマンス ログをキャプチャする

> [!TIP]
> 複数のデバイスでこの問題が発生している場合は、RAM が最も多いデバイスを使用します。

1. WPR をダウンロードしてインストールします。

2. *Windows キット* で、**Windows パフォーマンス レコーダー** を右クリックします。

   :::image type="content" source="images/wpr-01.png" alt-text="[スタート] メニュー" lightbox="images/wpr-01.png":::

    **[その他**] を選択します。 [ **管理者として実行]** を選択します。

3. [ユーザー アカウント制御] ダイアログ ボックスが表示されたら、[ **はい**] を選択します。

   :::image type="content" source="images/wpt-yes.png" alt-text="UAC ページ" lightbox="images/wpt-yes.png":::

4. 次に、[Microsoft Defender for Endpoint分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)プロファイルをダウンロードし、次のような`C:\temp`フォルダーに保存`MDAV.wprp`します。

5. [WPR] ダイアログ ボックスで、[ **その他のオプション**] を選択します。

   :::image type="content" source="images/wpr-03.png" alt-text="その他のオプションを選択できるページ" lightbox="images/wpr-03.png":::


6. [ **プロファイルの追加]...** を選択し、ファイルのパスを `MDAV.wprp` 参照します。

7. その後、その下に[分析] という名前の *[カスタム測定値*] に新しいプロファイル セット *Microsoft Defender for Endpoint* 表示されます。

   :::image type="content" source="images/wpr-infile.png" alt-text="ファイル内" lightbox="images/wpr-infile.png":::

    > [!WARNING]
    > Windows Server に 64 GB 以上の RAM がある場合は、`Microsoft Defender for Endpoint analysis for large servers``Microsoft Defender for Endpoint analysis`. そうしないと、システムで大量の非ページ プール メモリまたはバッファーが消費され、システムが不安定になる可能性があります。 **[リソース分析**] を展開して、追加するプロファイルを選択できます。
    このカスタム プロファイルは、詳細なパフォーマンス分析に必要なコンテキストを提供します。

8. WPR UI でカスタム測定Microsoft Defender for Endpoint詳細分析プロファイルを使用するには、

    1. *第 1 レベルのトリアージ*、*リソース分析*、*およびシナリオ分析* グループでプロファイルが選択されていないことを確認します。
    2. [ **カスタム測定値] を選択します**。
    3. **Microsoft Defender for Endpoint分析を** 選択します。
    4. *詳細* レベルで **[詳細]** を選択します。
    5. ログ モードで **[ファイル** ] または [ **メモリ** ] を選択します。

    > [!IMPORTANT]
    > パフォーマンスの *問題をユーザー* が直接再現できる場合は、[ファイル] を選択してファイル ログ モードを使用する必要があります。 ほとんどの問題は、このカテゴリに該当します。 ただし、ユーザーが問題を直接再現できないが、問題が発生した後に簡単に認識できる場合は、メモリ ログ モードを使用するには *[メモリ* ] を選択する必要があります。 これにより、実行時間が長いためにトレース ログが過度に膨らまないようになります。

9. これで、データを収集する準備ができました。 パフォーマンスの問題の再現に関連しないすべてのアプリケーションを終了します。 [ **非表示] オプション** を選択すると、WPR ウィンドウの領域を小さく保つことができます。

   :::image type="content" source="images/wpr-08.png" alt-text="[非表示] オプション" lightbox="images/wpr-08.png":::

    > [!TIP]
    > トレースを整数秒で開始してみてください。 たとえば、01:30:00 です。 これにより、データの分析が容易になります。 また、問題が再現された正確なタイミングのタイムスタンプを追跡してみてください。

10. [**スタート**] を選択します。

    :::image type="content" source="images/wpr-09.png" alt-text="[レコード システム情報] ページ" lightbox="images/wpr-09.png":::

11. 問題を再現します。

    > [!TIP]
    > データ収集は 5 分以内にしてください。 大量のデータが収集されるため、2 分から 3 分は適切な範囲です。

12. **[保存]** を選択します。

    :::image type="content" source="images/wpr-10.png" alt-text="[保存] オプション" lightbox="images/wpr-10.png":::

13. **問題の詳細な説明を入力してください。問題** に関する情報と問題の再現方法を入力します。

    :::image type="content" source="images/wpr-12.png" alt-text="入力するウィンドウ" lightbox="images/wpr-12.png":::

    1. **[ファイル名]:** トレース ファイルを保存する場所を決定します。 既定では、.`%user%\Documents\WPR Files\`
    1. **[保存]** を選択します。

14. トレースがマージされている間待ちます。

    :::image type="content" source="images/wpr-13.png" alt-text="WPR 収集の一般的なトレース" lightbox="images/wpr-13.png":::

15. トレースが保存されたら、[フォルダーを **開く**] を選択します。

    :::image type="content" source="images/wpr-14.png" alt-text="WPR トレースが保存されたという通知を表示するページ" lightbox="images/wpr-14.png":::

    Microsoft サポートに提出するファイルとフォルダーの両方を含めます。

    :::image type="content" source="images/wpr-15.png" alt-text="ファイルとフォルダーの詳細" lightbox="images/wpr-15.png":::

### <a name="capture-performance-logs-using-the-wpr-cli"></a>WPR CLI を使用してパフォーマンス ログをキャプチャする

コマンド ライン ツール *wpr.exe* は、Windows 8 以降のオペレーティング システムの一部です。 コマンド ライン ツール wpr.exeを使用して WPR トレースを収集するには:

1. パフォーマンス トレース **[のMicrosoft Defender for Endpoint分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** プロファイルを、ローカル ディレクトリ内の名前の`MDAV.wprp`ファイル (.`C:\traces`

2. **スタート メニュー** アイコンを右クリックし **、Windows PowerShell (管理)** または **コマンド プロンプト (管理)** を選択して、管理コマンド プロンプト ウィンドウを開きます。

3. [ユーザー アカウント制御] ダイアログ ボックスが表示されたら、[ **はい**] を選択します。

4. 管理者特権のプロンプトで、次のコマンドを実行して、Microsoft Defender for Endpointパフォーマンス トレースを開始します。

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```

    > [!WARNING]
    > Windows Server に 64 GB 以上の RAM がある場合は、プロファイルではなく、`WDForLargeServers.Light``WDForLargeServers.Verbose`それぞれプロファイル`WD.Light`を`WD.Verbose`使用します。 そうしないと、システムで大量の非ページ プール メモリまたはバッファーが消費され、システムが不安定になる可能性があります。

5. 問題を再現します。

    > [!TIP]
    > データ収集は 5 分以内にしてください。 シナリオによっては、大量のデータが収集されるため、2 分から 3 分は適切な範囲です。

6. 管理者特権のプロンプトで、次のコマンドを実行してパフォーマンス トレースを停止し、問題と問題の再現方法に関する情報を必ず提供します。

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

7. トレースがマージされるまで待ちます。

8. Microsoft サポートへの提出にファイルとフォルダーの両方を含めます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策の診断データを収集する](collect-diagnostic-data.md)
- [Microsoft Defender ウイルス対策スキャンの除外を構成して検証する](configure-exclusions-microsoft-defender-antivirus.md)
