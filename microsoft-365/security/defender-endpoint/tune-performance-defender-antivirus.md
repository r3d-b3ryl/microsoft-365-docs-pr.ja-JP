---
title: パフォーマンス アナライザー (Microsoft Defender ウイルス対策
description: パフォーマンスを調整する手順について説明Microsoft Defender ウイルス対策。
keywords: tune, performance, microsoft Defender for endpoint, Defender Antivirus
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 00e03927696d32eb72991a5eaa82643325b59925
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110441"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>パフォーマンス アナライザー (Microsoft Defender ウイルス対策

**パフォーマンス アナライザー Microsoft Defender ウイルス対策とは**

場合によっては、特定のファイルやフォルダーをスキャンする際に、Microsoft Defender ウイルス対策のパフォーマンスを調整する必要があります。 パフォーマンス アナライザーは PowerShell コマンド ライン ツールであり、個々のエンドポイントでパフォーマンスの問題を引き起こしている可能性があるファイル、ファイル拡張子、およびプロセスを特定するのに役立ちます。 この情報は、パフォーマンスの問題をより適切に評価し、修復アクションを適用するために使用できます。

分析するオプションには、次のものがあります。

- スキャン時間に影響を与える上位ファイル
- スキャン時間に影響を与える上位プロセス
- スキャン時間に影響を与える上位のファイル拡張子
- 組み合わせ – たとえば、拡張子ごとの上位ファイル、ファイルごとの上位スキャン、プロセスごとのファイルごとの上位スキャン

## <a name="running-performance-analyzer"></a>パフォーマンス アナライザーの実行

パフォーマンス アナライザーを実行するための高レベルのプロセスには、次の手順が含まれます。

1. パフォーマンス アナライザーを実行して、エンドポイント上のイベントMicrosoft Defender ウイルス対策記録を収集します。

   > [!NOTE]
   > **Microsoft-antimalware-Engine** Microsoft Defender ウイルス対策のイベントのパフォーマンスは、パフォーマンス アナライザーによって記録されます。

2. さまざまな記録レポートを使用してスキャン結果を分析します。

## <a name="using-performance-analyzer"></a>パフォーマンス アナライザーの使用

システム イベントの記録を開始するには、管理モードで PowerShell を開き、次の手順を実行します。

1. 次のコマンドを実行して、記録を開始します。

   `New-MpPerformanceRecording -RecordTo <recording.etl>`
 
    where `-RecordTo` パラメーターは、トレース ファイルが保存される完全なパスの場所を指定します。 コマンドレットの詳細については、「Microsoft Defender ウイルス対策[コマンドレット」を参照してください](/powershell/module/defender)。

2. パフォーマンスに影響を与えるプロセスまたはサービスがある場合は、関連するタスクを実行して状況を再現します。

3. Enter **キーを押** して録音を停止して保存するか **、Ctrl + C キーを押して録音** をキャンセルします。

4. パフォーマンス アナライザーのパラメーターを使用して結果を分析 `Get-MpPerformanceReport` します。 たとえば、コマンドを実行すると、パフォーマンスに影響を与える上位 3 つのファイルに対する上位 10 回のスキャンの一覧 `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10` がユーザーに提供されます。 

コマンド ライン パラメーターとオプションの詳細については [、「New-MpPerformanceRecording」](#new-mpperformancerecording) および [「Get-MpPerformanceReport」を参照してください](#get-mpperformancereport)。

> [!NOTE]
> 記録を実行するときに、「Windows Performance Recorder が既に記録されているため、パフォーマンス記録を開始できません」というエラーが表示された場合は、次のコマンドを実行して、新しいコマンドを使用して既存のトレースを停止します **。wpr -cancel -instancename** MSFT_MpPerformanceRecording

### <a name="performance-tuning-data-and-information"></a>パフォーマンスチューニングのデータと情報

クエリに基づいて、ユーザーはスキャンカウント、期間 (total/min/average/max/median)、パス、プロセス、およびスキャンの理由のデータを表示できます。 次の図は、スキャンに影響を与える上位 10 ファイルの簡単なクエリの出力例を示しています。 

:::image type="content" source="images/example-output.png" alt-text="基本的な TopFiles クエリの出力例":::

### <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>その他の機能: CSV および JSON へのエクスポートと変換

パフォーマンス アナライザーの結果をエクスポートし、CSV または JSON ファイルに変換できます。
サンプル コードによる "エクスポート" と "変換" のプロセスを説明する例については、以下を参照してください。

#### <a name="for-csv"></a>CSV の場合

- **エクスポートするには**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **変換するには**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

#### <a name="for-json"></a>JSON の場合

- **変換するには**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

### <a name="requirements"></a>Requirements
Microsoft Defender ウイルス対策アナライザーには、次の前提条件があります。

- サポートされているWindowsバージョン: Windows 10、Windows 11、Windows Server 2016以上
- プラットフォーム バージョン: 4.18.2108.7+
- PowerShell バージョン: PowerShell バージョン 5.1

## <a name="powershell-reference"></a>PowerShell リファレンス
次の 2 つの新しい PowerShell コマンドレットを使用して、パフォーマンスを調整Microsoft Defender ウイルス対策。 

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)


### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

次のセクションでは、新しい PowerShell コマンドレット New-MpPerformanceRecording の参照について説明します。 このコマンドレットは、スキャンのパフォーマンス記録をMicrosoft Defender ウイルス対策します。

#### <a name="syntax-new-mpperformancerecording"></a>構文: New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>説明: New-MpPerformanceRecording
コマンドレット `New-MpPerformanceRecording` は、スキャンのパフォーマンス記録をMicrosoft Defender ウイルス対策します。 これらのパフォーマンス記録には、Microsoft-Antimalware-Engine および NT カーネル プロセス イベントが含まれているので [、Get-MpPerformanceReport](#get-mpperformancereport) コマンドレットを使用してコレクション後に分析できます。

この `New-MpPerformanceRecording` コマンドレットは、問題のあるファイルに関する分析情報を提供し、問題のあるファイルのパフォーマンスが低下するMicrosoft Defender ウイルス対策。 このツールは "AS IS" で提供され、除外に関する提案を提供することを意図したツールではありません。 除外によって、エンドポイントの保護レベルが低下する可能性があります。 除外がある場合は、慎重に定義する必要があります。

パフォーマンス アナライザーの詳細については [、「Performance Analyzer docs」を参照](/windows-hardware/test/wpt/windows-performance-analyzer) してください。

> [!IMPORTANT]
> このコマンドレットには、管理者特権が必要です。

**サポートされている OS のバージョン**

Windows 10 以降を参照してください。

> [!NOTE]
> この機能は、プラットフォーム バージョン 4.18.2108.X 以降で使用できます。

#### <a name="examples-new-mpperformancerecording"></a>例: New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>例 1: パフォーマンス記録を収集して保存する

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

上記のコマンドは、パフォーマンス記録を収集し、指定されたパスに保存します **。.\Defender-scans.etl**。

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

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

次のセクションでは、PowerShell コマンドレットGet-MpPerformanceReport説明します。 MDAV (MDAV) Microsoft Defender ウイルス対策記録に関する分析とレポート。

#### <a name="syntax-get-mpperformancereport"></a>構文: Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
[-TopScans <Int32>]
[-TopFiles  <Int32>
    [-TopScansPerFile <Int32>]
    [-TopProcessesPerFile  <Int32>  
        [-TopScansPerProcessPerFile <Int32>]
    ]
] 
[-TopExtensions  <Int32>
    [-TopScansPerExtension <Int32>]
    [-TopProcessesPerExtension <Int32>
        [-TopScansPerProcessPerExtension <Int32>]
        ]
    [-TopFilesPerExtension  <Int32>
        [-TopScansPerFilePerExtension <Int32>]
        ]
    ] 
]
[-TopProcesses  <Int32>
    [-TopScansPerProcess <Int32>]
    [-TopExtensionsPerProcess <Int32>
        [-TopScansPerExtensionPerProcess <Int32>]
    ]
]
[-TopFilesPerProcess  <Int32>
    [-TopScansPerFilePerProcess <Int32>]
]
[-MinDuration <String>]
```

#### <a name="description-get-mpperformancereport"></a>説明: Get-MpPerformanceReport
このコマンドレットは、以前に収集された Microsoft Defender ウイルス対策 パフォーマンス記録 `Get-MpPerformanceReport` [(New-MpPerformanceRecording)](#new-mpperformancerecording)を分析し、Microsoft Defender ウイルス対策 スキャンに最も大きな影響を与えるファイル パス、ファイル拡張子、およびプロセスを報告します。

パフォーマンス アナライザーは、問題のあるファイルに関する分析情報を提供し、問題のあるファイルのパフォーマンスが低下するMicrosoft Defender ウイルス対策。 このツールは"AS IS" で提供され、除外に関する提案を提供することを意図したツールではありません。 除外によって、エンドポイントの保護レベルが低下する可能性があります。 除外がある場合は、慎重に定義する必要があります。

パフォーマンス アナライザーの詳細については [、「Performance Analyzer docs」を参照](/windows-hardware/test/wpt/windows-performance-analyzer) してください。

**サポートされている OS のバージョン**

Windows 10 以降を参照してください。

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

##### <a name="example-4-using--minduration-parameter"></a>例 4: -MinDuration パラメーターの使用

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:100 -MinDuration:100ms
```

#### <a name="parameters-get-mpperformancereport"></a>パラメーター: Get-MpPerformanceReport

##### <a name="-minduration"></a>-MinDuration
レポートに含まれるファイル、拡張機能、およびプロセスのスキャン期間または合計スキャン期間の最小期間を指定します。**0.1234567sec、0.1234ms、0.1us、** または有効な TimeSpan のような値を受け入れる。  

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

### <a name="-topextensions"></a>-TopExtensions 
"Duration" で並べ替えた、出力する上位拡張機能の数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess 
トップ プロセスごとに出力する上位拡張機能の数を "Duration" で並べ替えた数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfiles"></a>-TopFiles
トップ ファイル レポートを要求し、出力する上位ファイルの数を "Duration" で並べ替えた数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperextension"></a>-TopFilesPerExtension 
"Duration" で並べ替え、各上位拡張子に対して出力する上位ファイルの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperprocess"></a>-TopFilesPerProcess
トップ プロセスごとに出力する上位ファイルの数を "Duration" で並べ替えた数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocesses"></a>-TopProcesses
トップ プロセス レポートを要求し、出力する上位プロセスの数を "Duration" で並べ替えた数を指定します。

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension 
"Duration" で並べ替え、各上位拡張機能に対して出力する上位プロセスの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topprocessesperfile"></a>-TopProcessesPerFile
トップ ファイルごとに出力する上位プロセスの数を "Duration" で並べ替えた数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscans"></a>-TopScans
トップ スキャン レポートを要求し、出力するトップ スキャンの数を "Duration" で並べ替えた数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextension"></a>-TopScansPerExtension
"Duration" で並べ替えた、上位の拡張機能ごとに出力するトップ スキャンの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess 
トップ プロセスごとに出力するトップ スキャンの数を "Duration" で並べ替えた上位プロセスごとに指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfile"></a>-TopScansPerFile
トップ ファイルごとに出力するトップ スキャンの数を "Duration" で並べ替えた数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension 
"Duration" で並べ替え、各トップ 拡張子の各トップ ファイルに対して出力するトップ スキャンの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess 
各トップ プロセスのトップ ファイルの出力を "Duration" で並べ替えた上位スキャンの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperprocess"></a>-TopScansPerProcess 
トップ プロセス レポートの上位プロセスごとに出力するトップ スキャンの数を "Duration" で並べ替えた数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension
"Duration" で並べ替え、各上位の拡張機能の各上位プロセスの出力のトップ スキャンの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile
"Duration" で並べ替えた各トップ ファイルの上位プロセスごとに出力をスキャンする上位スキャンの数を指定します。


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
