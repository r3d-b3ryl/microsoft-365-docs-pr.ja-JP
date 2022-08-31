---
title: 高度な検索でランサムウェアを検索する
description: 高度な捜索を使用して、ランサムウェアの影響を受ける可能性のあるデバイスを見つけます。
keywords: 高度な捜索, ランサムウェア, 脅威の捜索, サイバー脅威の捜索, 検索, クエリ, テレメトリ, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-ransomware
- highpri
ms.topic: article
ms.openlocfilehash: e65655154cb326ddf6d4086b944afeb1a599aa64
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479039"
---
# <a name="hunt-for-ransomware"></a>ランサムウェアを探す

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

ランサムウェアは、個々のコンピューター ユーザーに影響を与える単純なコモディティ マルウェアから、業界や政府機関に大きな影響を与える企業の脅威へと急速に進化しています。 [Microsoft 365 Defender](microsoft-365-defender.md)には、ランサムウェアや関連する侵入アクティビティを検出してブロックする機能が多数用意されていますが、侵害の兆候を事前にチェックすると、ネットワークを保護し続けることができます。

> [人間が操作するランサムウェアについて読む](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

Microsoft 365 Defenderでの[高度な捜索](advanced-hunting-overview.md)では、ランサムウェア アクティビティに関連付けられている個々のアーティファクトを検索するクエリを作成できます。 さらに高度なクエリを実行して、アクティビティの兆候を検索し、それらの兆候を比較検討して、すぐに注意が必要なデバイスを見つけることもできます。

## <a name="signs-of-ransomware-activity"></a>ランサムウェア アクティビティの兆候
Microsoft のセキュリティ研究者は、高度な侵入者によって開始された多くのランサムウェア キャンペーンで、さまざまな一般的で微妙なアーティファクトを観察してきました。 これらの兆候には、主にシステム ツールを使用して、暗号化の準備、検出の防止、フォレンジック証拠のクリアが含まれます。

| ランサムウェアのアクティビティ | 一般的なツール | Intent |
|--|--|--|
| プロセスを停止する | _taskkill.exe_, _ネットストップ_ | 暗号化の対象となるファイルが、さまざまなアプリケーションによってロックされていないことを確認します。 |
| サービスを無効にする | _sc.exe_ | - 暗号化の対象となるファイルが、さまざまなアプリケーションによってロックされていないことを確認します。<br>- セキュリティ ソフトウェアが暗号化やその他のランサムウェア アクティビティを中断しないようにします。<br>- 回復可能なコピーの作成からバックアップ ソフトウェアを停止します。  |
| ログとファイルを削除する | _cipher.exe_, _wevtutil_, _fsutil.exe_ | フォレンジックな証拠を削除します。 |
| シャドウ コピーを削除する  | _vsadmin.exe_, _wmic.exe_ | 暗号化されたファイルの回復に使用できるドライブ シャドウ コピーを削除します。 |
| バックアップの削除と停止 | _wbadmin.exe_ | 既存のバックアップを削除し、スケジュールされたバックアップ タスクを停止し、暗号化後の復旧を防ぎます。 |
| ブート設定を変更する | _bcdedit.exe_ | 暗号化プロセスによって発生する可能性があるブート エラーの後に警告と自動修復をオフにします。 |
| 回復ツールを無効にする | _schtasks.exe_, _regedit.exe_, | [システムの復元] とその他のシステム回復オプションをオフにします。 |

## <a name="check-for-individual-signs-of-ransomware-activity"></a>ランサムウェア アクティビティの個々の兆候を確認する
前のセクションで説明したアクティビティを含め、ランサムウェアの動作を構成する多くのアクティビティは無害な場合があります。 次のクエリを使用してランサムウェアを見つける場合は、複数のクエリを実行して、同じデバイスがランサムウェアアクティビティの可能性のあるさまざまな兆候を示しているかどうかを確認します。

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a>_taskkill.exe_ を使用した複数のプロセスの停止
このクエリは、 _taskkill.exe_ ユーティリティを使用して、少なくとも 10 個の個別のプロセスを停止する試行をチェックします。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a>net stop を使用したプロセスの _停止_
このクエリは、net stop コマンドを使用して、少なくとも 10 個の個別のプロセスを _停止_ する試行をチェックします。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a>_cipher.exe_ を使用した複数のドライブ上のデータの削除
このクエリでは、 _cipher.exe_ を使用して複数のドライブ上のデータを削除しようとしているか確認します。 このアクティビティは、通常、暗号化後のデータの回復を防ぐためにランサムウェアによって行われます。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a>_wevtutil_ を使用したイベント ログからのフォレンジック証拠のクリア
このクエリでは、 _wevtutil_ を使用して、イベント ログから少なくとも 10 個のログ エントリをクリアしようとしていることを確認します。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a>_sc.exe_ を使用してサービスをオフにする
このクエリでは、sc.exeを使用して、少なくとも 10 個の既存のサービスを無効にする試行 _が_ チェックされます。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a>システムの復元をオフにする
このクエリは、システムの復元を停止し、システムが復元ポイントを作成できないようにする試行を識別します。これは、ランサムウェアによって暗号化されたデータを回復するために使用できます。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a>バックアップの削除
このクエリでは、暗号化前にシャドウ コピー スナップショットを削除するための _wmic.exe_ の使用を識別します。 [クエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a>ランサムウェア アクティビティの複数の兆候を確認する
複数のクエリを個別に実行する代わりに、ランサムウェア アクティビティの複数の兆候をチェックする包括的なクエリを使用して、影響を受けるデバイスを識別することもできます。 次の統合クエリ:
- ランサムウェア アクティビティの比較的具体的な兆候と微妙な兆候の両方を探します
- これらの兆候の存在を比較検討します
- ランサムウェアのターゲットになる可能性が高いデバイスを識別します 

この統合クエリを実行すると、複数の攻撃の兆候が見られたデバイスの一覧が返されます。 ランサムウェア アクティビティの種類ごとの数も表示されます。 この統合クエリを実行するには、 [高度なハンティング クエリ エディター](https://security.microsoft.com/advanced-hunting)に直接コピーします。 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a>クエリの結果を理解して調整する
統合クエリは、次の結果を返します。

- **DeviceId**—影響を受けるデバイスを識別します 
- **TimeStamp** — デバイスでランサムウェア アクティビティの兆候が初めて観察された場合
- **アクティビティの特定の兆候** - _BcdEdit_ や _FsUtil_ など、複数の列に表示される各記号の数
- **TotalEvidenceCount** - 観察された符号の数
- **UniqueEvidenceCount** - 観察された符号の種類の数

:::image type="content" source="../../media/advanced-hunting-ransomware-query.png" alt-text="Microsoft 365 Defender ポータルでのランサムウェア アクティビティに対する統合クエリの例" lightbox="../../media/advanced-hunting-ransomware-query.png":::

*影響を受けるデバイスとランサムウェア アクティビティのさまざまな兆候の数を示すクエリ結果*

既定では、クエリ結果には、2 種類を超えるランサムウェア アクティビティを持つデバイスのみが一覧表示されます。 ランサムウェア アクティビティの兆候があるすべてのデバイスを表示するには、次 `where` の演算子を変更し、数値をゼロ (0) に設定します。 表示されるデバイスの数を減らすには、より高い数を設定します。 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)

## <a name="more-ransomware-resources"></a>その他のランサムウェア リソース

Microsoft の主な情報:

- [ランサムウェアの脅威の増大](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/)、2021 年 7月 20 日付け Microsoft On the Issues のブログ投稿
- [人が操作するランサムウェア](/security/compass/human-operated-ransomware)
- [ランサムウェアや強要から迅速に保護する](/security/compass/protect-against-ransomware)
- [2021 Microsoft Digital Defense Report](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (10- 19 ページを参照ください)
- [ランサムウェア: Microsoft 365 Defender ポータルの脅威分析ノードの蔓延する継続的な脅威](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview)に関するレポート (これらの「ライセンス要件」 を参照ください)

Microsoft 365:

- [Microsoft 365 テナントにランサムウェア保護を展開する](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Azure と Microsoft 365 を使用してランサムウェアの回復性を最大化する](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [ランサムウェア攻撃から回復する](/microsoft-365/security/office-365-security/recover-from-ransomware)
- [マルウェアと ランサムウェアからの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [ランサムウェアから Windows PC を保護する](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [SharePoint Online でのランサムウェアの処理](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Microsoft 365 Defender](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)ポータルでのランサムウェアの脅威分析レポート

Microsoft Azure

- [ランサムウェア攻撃に対する Azure 防御](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Azure と Microsoft 365 を使用してランサムウェアの回復性を最大化する](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [ランサムウェアから保護するためのバックアップと復元の計画](/security/compass/backup-plan-to-protect-against-ransomware)
- [Microsoft Azure バックアップを使用してランサムウェアから保護する](https://www.youtube.com/watch?v=VhLOr2_1MCg) (26 分のビデオ)
- [体系的な ID 侵害からの回復](/azure/security/fundamentals/recover-from-identity-compromise)
- [Microsoft Sentinel での高度な多段階攻撃検出](/azure/sentinel/fusion#ransomware)
- [Microsoft Sentinel でのランサムウェアのフュージョン検出](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps

-  [Defender for Cloud Apps で異常検出ポリシーを作成する](/cloud-app-security/anomaly-detection-policy)

Microsoft Security チームのブログ投稿:

- [ランサムウェアを防止して回復するための 3 つの手順 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [人が操作するランサムウェアの対策ガイド: パート 1 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  Microsoft の検出対応チーム (DART) がランサムウェア インシデント調査を実施する方法に関する重要な手順。

- [人が操作するランサムウェアの対策ガイド: パート 2 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  推奨事項とベスト プラクティス。

- [サイバーセキュリティ リスクを理解することで回復力を高める パート 4—現在の脅威をナビゲートする(2021 年 5 月)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  「**ランサムウェア**」セクションを参照 してください。

- [人が操作するランサムウェア攻撃: 予防可能な災害 (2020 年 3 月)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  実際の攻撃の攻撃チェーン分析が含まれます。

- [ランサムウェアの応答 - 支払うべきか、支払わざるべきか? (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro のランサムウェア攻撃に対する透明性のある対応 (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
