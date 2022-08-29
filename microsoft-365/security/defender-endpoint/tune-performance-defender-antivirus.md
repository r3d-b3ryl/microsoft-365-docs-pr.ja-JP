---
title: Microsoft Defender ウイルス対策のパフォーマンス アナライザー
description: Microsoft Defender ウイルス対策のパフォーマンスを調整する手順について説明します。
keywords: tune, Performance, Microsoft Defender for endpoint, Defender ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 08/13/2022
manager: dansimp
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ac8bb15d38e7eb517911ba2c63e25a50e4918e7e
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67383856"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策のパフォーマンス アナライザー

**適用対象**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**

- Windows

## <a name="what-is-microsoft-defender-antivirus-performance-analyzer"></a>Microsoft Defender ウイルス対策パフォーマンス アナライザーとは

場合によっては、特定のファイルやフォルダーをスキャンするときに、Microsoft Defender ウイルス対策のパフォーマンスを調整することが必要になる場合があります。 パフォーマンス アナライザーは、個々のエンドポイントでパフォーマンスの問題を引き起こしている可能性があるファイル、ファイル拡張子、およびプロセスを特定するのに役立つ PowerShell コマンド ライン ツールです。 この情報は、パフォーマンスの問題をより適切に評価し、修復アクションを適用するために使用できます。

分析するオプションには、次のものがあります。

- スキャン時間に影響する上位パス
- スキャン時間に影響を与える上位ファイル
- スキャン時間に影響を与える上位プロセス
- スキャン時間に影響を与える上位のファイル拡張子
- 組み合わせ – たとえば、
  - 拡張子あたりの上位ファイル数
  - 拡張機能ごとの上位パス
  - パスあたりの上位プロセス数
  - ファイルあたりのトップ スキャン数
  - プロセスごとのファイルあたりの上位スキャン数
  
## <a name="running-performance-analyzer"></a>パフォーマンス アナライザーの実行

パフォーマンス アナライザーを実行するための高度なプロセスには、次の手順が含まれます。

1. パフォーマンス アナライザーを実行して、エンドポイント上の Microsoft Defender ウイルス対策イベントのパフォーマンス記録を収集します。

   > [!NOTE]
   > **Microsoft-Antimalware-Engine** 型の Microsoft Defender ウイルス対策イベントのパフォーマンスは、パフォーマンス アナライザーを介して記録されます。

2. 異なる記録レポートを使用してスキャン結果を分析します。

## <a name="using-performance-analyzer"></a>パフォーマンス アナライザーの使用

システム イベントの記録を開始するには、PowerShell を管理モードで開き、次の手順を実行します。

1. 次のコマンドを実行して記録を開始します。

   `New-MpPerformanceRecording -RecordTo <recording.etl>`

    ここで `-RecordTo` 、パラメーターはトレース ファイルを保存する完全なパスの場所を指定します。 コマンドレットの詳細については、 [Microsoft Defender ウイルス対策コマンドレットに関するページを](/powershell/module/defender)参照してください。

2. パフォーマンスに影響を与えると考えられるプロセスまたはサービスがある場合は、関連するタスクを実行して状況を再現します。

3. **Enter キー** を押して記録を停止して保存するか、**Ctrl + C キーを押** して記録を取り消します。

4. パフォーマンス アナライザーのパラメーターを使用して結果を `Get-MpPerformanceReport`分析します。 たとえば、コマンド `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10`を実行すると、パフォーマンスに影響を与える上位 3 つのファイルに対する上位 10 個のスキャンの一覧がユーザーに提供されます。

コマンド ライン のパラメーターとオプションの詳細については、 [New-MpPerformanceRecording](#new-mpperformancerecording) と [Get-MpPerformanceReport](#get-mpperformancereport) を参照してください。

> [!NOTE]
> 記録を実行しているときに、「Windows パフォーマンス レコーダーが既に記録されているため、パフォーマンス記録を開始できません」というエラーが表示された場合は、次のコマンドを実行して、新しいコマンドで既存のトレースを停止します: **wpr -cancel -instancename MSFT_MpPerformanceRecording**

## <a name="performance-tuning-data-and-information"></a>パフォーマンスチューニングのデータと情報

クエリに基づいて、ユーザーはスキャン数、期間 (合計/最小/平均/最大/中央値)、パス、プロセス、および **スキャンの理由のデータを表示できます**。 次の図は、スキャンの影響を受けるための上位 10 ファイルの単純なクエリの出力例を示しています。

:::image type="content" source="images/example-output.png" alt-text="基本的な TopFiles クエリの出力例" lightbox="images/example-output.png":::

## <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>その他の機能: CSV と JSON へのエクスポートと変換

パフォーマンス アナライザーの結果をエクスポートして、CSV または JSON ファイルに変換することもできます。
サンプル コードを使用して "エクスポート" と "変換" のプロセスを記述する例については、以下を参照してください。

Defender バージョン 4.18.2206.X 以降では、ユーザーは "SkipReason" 列にスキャンスキップ理由情報を表示できます。 値は次のいずれかです。

1. スキップされない
1. 最適化 (通常はパフォーマンス上の理由により)
1. ユーザーがスキップされました (通常は、ユーザー セットの除外が原因)

### <a name="for-csv"></a>CSV の場合

- **エクスポートするには**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **変換するには**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

### <a name="for-json"></a>JSON の場合

- **変換するには**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

他のデータ処理システムでエクスポートするためのマシン読み取り可能な出力を確保するには、Get-MpPerformanceReport に -Raw パラメーターを使用することをお勧めします。 詳細については、以下を参照してください

## <a name="requirements"></a>要件

Microsoft Defender ウイルス対策パフォーマンス アナライザーには、次の前提条件があります。

- サポートされている Windows バージョン: Windows 10、Windows 11、Windows Server 2016以降
- プラットフォーム バージョン: 4.18.2108.7 以降
- PowerShell バージョン: PowerShell バージョン 5.1、PowerShell ISE、リモート PowerShell (4.18.2201.10 以降)、PowerShell 7.x (4.18.2201.10 以降)

## <a name="powershell-reference"></a>PowerShell リファレンス

Microsoft Defender ウイルス対策のパフォーマンスを調整するために使用される 2 つの新しい PowerShell コマンドレットがあります。

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)

### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

次のセクションでは、新しい PowerShell コマンドレット New-MpPerformanceRecording のリファレンスについて説明します。 このコマンドレットは、Microsoft Defender ウイルス対策スキャンのパフォーマンス記録を収集します。

#### <a name="syntax-new-mpperformancerecording"></a>構文: New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>説明: New-MpPerformanceRecording

このコマンドレットは `New-MpPerformanceRecording` 、Microsoft Defender ウイルス対策スキャンのパフォーマンス記録を収集します。 これらのパフォーマンス記録には、Microsoft-Antimalware-Engine および NT カーネル プロセス イベントが含まれており、 [Get-MpPerformanceReport](#get-mpperformancereport) コマンドレットを使用してコレクション後に分析できます。

この `New-MpPerformanceRecording` コマンドレットは、Microsoft Defender ウイルス対策のパフォーマンスが低下する可能性がある問題のあるファイルに関する分析情報を提供します。 このツールは "AS IS" として提供され、除外に関する提案を提供することを目的としていません。 除外すると、エンドポイントの保護レベルが低下する可能性があります。 除外がある場合は、慎重に定義する必要があります。

パフォーマンス アナライザーの詳細については、[パフォーマンス アナライザードキュメントを](/windows-hardware/test/wpt/windows-performance-analyzer)参照してください。

> [!IMPORTANT]
> このコマンドレットには管理者特権が必要です。

**サポートされている OS バージョン**:

Windows バージョン 10 以降。

> [!NOTE]
> この機能は、プラットフォーム バージョン 4.18.2108.X 以降で使用できます。

#### <a name="examples-new-mpperformancerecording"></a>例: New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>例 1: パフォーマンス記録を収集して保存する

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

上記のコマンドは、パフォーマンス記録を収集し、指定されたパス **(.\Defender-scan.etl**) に保存します。

##### <a name="example-2-collect-a-performance-recording-for-remote-powershell-session"></a>例 2: リモート PowerShell セッションのパフォーマンス記録を収集する

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
New-MpPerformanceRecording -RecordTo C:\LocalPathOnServer02\trace.etl -Session $s
```

上記のコマンドは、Server02 でパフォーマンス記録を収集し (パラメーター セッションの引数$sで指定)、指定されたパス **(Server02 の C:\LocalPathOnServer02\trace.etl** ) に保存します。

##### <a name="example-3-collect-a-performance-recording-in-non-interactive-mode"></a>例 3: 非対話型モードでパフォーマンス記録を収集する

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl -Seconds 60
```

上記のコマンドは、パラメーター -Seconds で指定された期間のパフォーマンス記録を秒単位で収集します。 これは、対話やプロンプトを必要としないバッチ コレクションを実行するユーザーに推奨されます。

#### <a name="parameters-new-mpperformancerecording"></a>パラメーター: New-MpPerformanceRecording

##### <a name="-recordto"></a>-RecordTo

Microsoft Defender マルウェア対策のパフォーマンス記録を保存する場所を指定します。

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-session"></a>-Session

Microsoft Defender ウイルス対策のパフォーマンス記録を作成して保存する PSSession オブジェクトを指定します。 このパラメーターを使用すると、RecordTo パラメーターはリモート コンピューター上のローカル パスを参照します。 Defender プラットフォーム バージョン 4.18.2201.10 で使用できます。

```yaml
Type: PSSession[]
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-seconds"></a>-Seconds

パフォーマンス記録の継続時間を秒単位で指定します。 これは、対話やプロンプトを必要としないバッチ コレクションを実行するユーザーに推奨されます。

```yaml
Type: Int32
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

次のセクションでは、Get-MpPerformanceReport PowerShell コマンドレットについて説明します。 Microsoft Defender ウイルス対策のパフォーマンス記録に関する分析とレポート。

#### <a name="syntax-get-mpperformancereport"></a>構文: Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
    [-TopScans [<Int32>]]
    [-TopPaths [<Int32>] [-TopPathsDepth [<Int32>]]]
            [-TopScansPerPath [<Int32>]]
            [-TopFilesPerPath [<Int32>]
                    [-TopScansPerFilePerPath [<Int32>]]
                    ]
            [-TopExtensionsPerPath [<Int32>]
                    [-TopScansPerExtensionPerPath [<Int32>]]
                    ]
            [-TopProcessesPerPath [<Int32>]
                    [-TopScansPerProcessPerPath [<Int32>]]
                    ]
            ]
    [-TopFiles [<Int32>]
            [-TopScansPerFile [<Int32>]]
            [-TopProcessesPerFile [<Int32>]
                    [-TopScansPerProcessPerFile [<Int32>]]
                    ]
            ]
    [-TopExtensions [<Int32>]
            [-TopScansPerExtension [<Int32>]
            [-TopPathsPerExtension [<Int32>] [-TopPathsDepth [<Int32>]]
                    [-TopScansPerPathPerExtension [<Int32>]]
                    ]
            [-TopProcessesPerExtension [<Int32>]
                    [-TopScansPerProcessPerExtension [<Int32>]]
                    ]
            [-TopFilesPerExtension [<Int32>]
                    [-TopScansPerFilePerExtension [<Int32>]]
                    ]
            ]
    [-TopProcesses [<Int32>]
            [-TopScansPerProcess [<Int32>]]
            [-TopExtensionsPerProcess [<Int32>]
                    [-TopScansPerExtensionPerProcess [<Int32>]]
                    ]
            [-TopPathsPerProcess [<Int32>] [-TopPathsDepth [<Int32>]]
                    [-TopScansPerPathPerProcess [<Int32>]]
                    ]
            [-TopFilesPerProcess [<Int32>]
                    [-TopScansPerFilePerProcess [<Int32>]]
                    ]
            ]
    [-MinDuration <String>]
    [-Raw]

```

#### <a name="description-get-mpperformancereport"></a>説明: Get-MpPerformanceReport

このコマンドレットは `Get-MpPerformanceReport` 、以前に収集された Microsoft Defender ウイルス対策のパフォーマンス記録 ([New-MpPerformanceRecording](#new-mpperformancerecording)) を分析し、Microsoft Defender ウイルス対策スキャンに最も大きな影響を与えるファイル パス、ファイル拡張子、プロセスを報告します。

パフォーマンス アナライザーは、Microsoft Defender ウイルス対策のパフォーマンスの低下を引き起こす可能性のある問題のあるファイルに関する分析情報を提供します。 このツールは "AS IS" として提供され、除外に関する提案を提供することを目的としていません。 除外すると、エンドポイントの保護レベルが低下する可能性があります。 除外がある場合は、慎重に定義する必要があります。

パフォーマンス アナライザーの詳細については、[パフォーマンス アナライザードキュメントを](/windows-hardware/test/wpt/windows-performance-analyzer)参照してください。

**サポートされている OS バージョン**:

Windows バージョン 10 以降。

> [!NOTE]
> この機能は、プラットフォーム バージョン 4.18.2108.X 以降で使用できます。

#### <a name="examples-get-mpperformancereport"></a>例: Get-MpPerformanceReport

##### <a name="example-1-single-query"></a>例 1: 単一クエリ

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:20
```

##### <a name="example-2-multiple-queries"></a>例 2: 複数のクエリ

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10
```

##### <a name="example-3-nested-queries"></a>例 3: 入れ子になったクエリ

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3 -TopScansPerExtensionPerProcess:3
```

##### <a name="example-4-using--minduration-parameter"></a>例 4: -MinDuration パラメーターを使用する

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:100 -MinDuration:100ms
```

##### <a name="example-5-using--raw-parameter"></a>例 5: -Raw パラメーターの使用

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10 -Raw | ConvertTo-Json
```

上記のコマンドで Raw を使用すると \-、出力をコンピューターで読み取り可能にし、JSON などのシリアル化形式に簡単に変換できるように指定します。

#### <a name="parameters-get-mpperformancereport"></a>パラメーター: Get-MpPerformanceReport

##### <a name="-toppaths"></a>-TopPaths

最上位パス レポートを要求し、出力する上位パスの数を "Duration" で並べ替えて指定します。 パスとディレクトリに基づいてスキャンを集計します。 ユーザーは、各レベルに表示するディレクトリの数と選択の深さを指定できます。

- 型: Int32
- 位置: 名前付き
- 既定値: なし
- パイプライン入力を受け入れる: False
- ワイルドカード文字を受け入れる: False

##### <a name="-toppathsdepth"></a>-TopPathsDepth

集約されたパスの結果をグループ化して表示するために使用する再帰深度を指定します。 たとえば、"C:\" は深度 1 に対応し、"C:\Users\Foo" は深度 3 に対応します。

このフラグは、他のすべての [トップ パス] オプションと一緒に使用できます。 不足している場合は、既定値の 3 が想定されます。 値を 0 にすることはできません。

- 型: Int32
- 位置: 名前付き
- 既定値: 3
- パイプライン入力を受け入れる: False
- ワイルドカード文字を受け入れる: False

| flag | definition |
|:---|:---|  
|  -**TopScansPerPath** | トップ パスごとにトップ スキャンを指定する方法を指定します。 |
|  -**TopFilesPerPath** | 各トップ パスに対して上位ファイルを指定する方法を指定します。 |
|  -**TopScansPerFilePerPath** | 上部パスごとに出力する上位スキャンの数を指定し、"Duration" で並べ替えます。 |
|  -**TopExtensionsPerPath** | 上位パスごとに出力する上位拡張機能の数を指定します。 |
|  -**TopScansPerExtensionPerPath** | 各トップ パスの上位拡張機能に対して出力するトップ スキャンの数を指定します |
|  -**TopProcessesPerPath** | 上位パスごとに出力する上位プロセスの数を指定します。 |
|  -**TopScansPerProcessPerPath** | 各トップ パスの上位プロセスごとに出力するトップ スキャンの数を指定します。 |
|  -**TopPathsPerExtension** | 上位拡張機能ごとに出力する上位パスの数を指定します。 |
|  -**TopScansPerPathPerExtension** | 各上位拡張機能の上位パスごとに出力するトップ スキャンの数を指定します。 |
|  -**TopPathsPerProcess** | 上位プロセスごとに出力する上位パスの数を指定します。 |
|  -**TopScansPerPathPerProcess** | 各トップ プロセスの上位パスごとに出力するトップ スキャンの数を指定します |

##### <a name="-minduration"></a>-MinDuration

レポートに含まれるファイル、拡張機能、およびプロセスのスキャンまたは合計スキャン期間の最小期間を指定します。は  **、0.1234567sec**、 **0.1234ms**、 **0.1us**、または有効な TimeSpan などの値を受け入れます。

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-path"></a>-Path

1 つ以上の場所へのパスを指定します。

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

##### <a name="-raw"></a>-Raw

パフォーマンス記録の出力をコンピューターで読み取り可能にし、JSON などのシリアル化形式に容易に変換できるようにする必要があることを指定します (たとえば、Convert-to-JSON コマンドを使用)。 これは、他のデータ処理システムでのバッチ処理に関心があるユーザーに推奨されます。

```yaml
Type: <SwitchParameter>
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topextensions"></a>-TopExtensions

出力する上位の拡張機能の数を指定します。"Duration" で並べ替えられます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess

"Duration" で並べ替えられた各上位プロセスの出力する上位拡張機能の数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfiles"></a>-TopFiles

上位ファイル レポートを要求し、出力する上位ファイルの数を "Duration" で並べ替えて指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfilesperextension"></a>-TopFilesPerExtension

上部の拡張子ごとに出力する上位ファイルの数を指定します。"Duration" で並べ替えられます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfilesperprocess"></a>-TopFilesPerProcess

"Duration" で並べ替えられた各トップ プロセスの出力する上位ファイルの数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocesses"></a>-TopProcesses

最上位プロセス レポートを要求し、出力する上位プロセスの数を "Duration" で並べ替えて指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension

上位拡張機能ごとに出力する上位プロセスの数を指定します。"Duration" で並べ替えられます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocessesperfile"></a>-TopProcessesPerFile

上位ファイルごとに出力する上位プロセスの数を指定し、"Duration" で並べ替えて指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscans"></a>-TopScans

トップ スキャン レポートを要求し、出力する上位スキャンの数を "期間" で並べ替えて指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperextension"></a>-TopScansPerExtension

上位拡張機能ごとに出力するトップ スキャンの数を指定し、"Duration" で並べ替えます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess

上位プロセスごとに出力する上位スキャンの数を指定し、"Duration" で並べ替えます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfile"></a>-TopScansPerFile

"Duration" で並べ替えられた各トップ ファイルの出力するトップ スキャンの数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension

上位の拡張子ごとに出力する上位スキャンの数を指定し、"Duration" で並べ替えます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess

"Duration" で並べ替えられた、各トップ プロセスの上位ファイルごとの出力のトップ スキャンの数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocess"></a>-TopScansPerProcess

上位プロセス レポートの上位プロセスごとに出力する上位スキャンの数を指定し、"期間" で並べ替えます。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension

"Duration" で並べ替えられた各上位プロセスの出力のトップ スキャンの数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile

"Duration" で並べ替えられた各トップ ファイルの上位プロセスごとの出力のトップ スキャンの数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## <a name="additional-resources"></a>その他のリソース

他のプラットフォームのウイルス対策に関連する情報を探している場合は、次を参照してください。

- [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
- [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
- [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
- [Android の機能で Defender for Endpoint を構成する](android-configure.md)- [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)
