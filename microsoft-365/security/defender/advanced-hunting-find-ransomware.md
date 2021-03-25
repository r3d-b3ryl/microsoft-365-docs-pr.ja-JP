---
title: 高度な検索でランサムウェアを検索する
description: 高度な検索を使用して、ランサムウェアの影響を受ける可能性のあるデバイスを見つける。
keywords: 高度な狩猟、ランサムウェア、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2f283008e90dbe5dadc0e1e04db589d89a15a8b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068332"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="ebbfa-104">ランサムウェアを探す</span><span class="sxs-lookup"><span data-stu-id="ebbfa-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ebbfa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ebbfa-105">**Applies to:**</span></span>
- <span data-ttu-id="ebbfa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebbfa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ebbfa-107">ランサムウェアは、個々のコンピューター ユーザーに影響を与える単純なコモディティ マルウェアから、業界や政府機関に深刻な影響を与える企業の脅威に急速に進化しています。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="ebbfa-108">[Microsoft 365 Defender](microsoft-365-defender.md)には、ランサムウェアや関連する侵入アクティビティを検出およびブロックする多くの機能が備え付けられている一方で、侵害の兆候を事前に確認すると、ネットワークの保護を維持できます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-108">While [Microsoft 365 Defender](microsoft-365-defender.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="ebbfa-109">人が操作するランサムウェアについて読む</span><span class="sxs-lookup"><span data-stu-id="ebbfa-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="ebbfa-110">Microsoft [](advanced-hunting-overview.md) 365 Defender での高度な検索を使用すると、ランサムウェア アクティビティに関連付けられた個々のアーティファクトを検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="ebbfa-111">また、より高度なクエリを実行して、アクティビティの兆候を探し、それらの兆候の重さを量って、すぐに注意を必要とするデバイスを見つけられます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="ebbfa-112">ランサムウェアアクティビティの兆候</span><span class="sxs-lookup"><span data-stu-id="ebbfa-112">Signs of ransomware activity</span></span>
<span data-ttu-id="ebbfa-113">Microsoft のセキュリティ研究者は、高度な侵入者によって立ち上げられた多くのランサムウェア キャンペーンで、さまざまな一般的でありながら微妙なアーティファクトを観察しています。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="ebbfa-114">これらの兆候は、主にシステム ツールを使用して暗号化の準備、検出の防止、および明らかな法医学証拠を含む。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="ebbfa-115">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="ebbfa-115">Ransomware activity</span></span> | <span data-ttu-id="ebbfa-116">一般的なツール</span><span class="sxs-lookup"><span data-stu-id="ebbfa-116">Common tools</span></span> | <span data-ttu-id="ebbfa-117">Intent</span><span class="sxs-lookup"><span data-stu-id="ebbfa-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="ebbfa-118">プロセスの停止</span><span class="sxs-lookup"><span data-stu-id="ebbfa-118">Stop processes</span></span> | <span data-ttu-id="ebbfa-119">_taskkill.exe_、 _ネットストップ_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="ebbfa-120">暗号化の対象となるファイルが、さまざまなアプリケーションによってロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="ebbfa-121">サービスをオフにする</span><span class="sxs-lookup"><span data-stu-id="ebbfa-121">Turn off services</span></span> | <span data-ttu-id="ebbfa-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-122">_sc.exe_</span></span> | <span data-ttu-id="ebbfa-123">- 暗号化対象のファイルがさまざまなアプリケーションによってロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="ebbfa-124">- セキュリティ ソフトウェアが暗号化や他のランサムウェアのアクティビティを中断するのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="ebbfa-125">- バックアップ ソフトウェアが回復可能なコピーを作成するのを停止します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="ebbfa-126">ログとファイルの削除</span><span class="sxs-lookup"><span data-stu-id="ebbfa-126">Delete logs and files</span></span> | <span data-ttu-id="ebbfa-127">_cipher.exe_、 _wevtutil_ _、_ fsutil.exe</span><span class="sxs-lookup"><span data-stu-id="ebbfa-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="ebbfa-128">証拠を削除します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="ebbfa-129">シャドウ コピーの削除</span><span class="sxs-lookup"><span data-stu-id="ebbfa-129">Delete shadow copies</span></span>  | <span data-ttu-id="ebbfa-130">_vsadmin.exe_ _、_ wmic.exe</span><span class="sxs-lookup"><span data-stu-id="ebbfa-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="ebbfa-131">暗号化されたファイルの回復に使用できるドライブ シャドウ コピーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="ebbfa-132">バックアップの削除と停止</span><span class="sxs-lookup"><span data-stu-id="ebbfa-132">Delete and stop backups</span></span> | <span data-ttu-id="ebbfa-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-133">_wbadmin.exe_</span></span> | <span data-ttu-id="ebbfa-134">既存のバックアップを削除し、スケジュールされたバックアップ タスクを停止し、暗号化後の回復を防止します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="ebbfa-135">ブート設定の変更</span><span class="sxs-lookup"><span data-stu-id="ebbfa-135">Modify boot settings</span></span> | <span data-ttu-id="ebbfa-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-136">_bcdedit.exe_</span></span> | <span data-ttu-id="ebbfa-137">暗号化プロセスによって発生する可能性があるブートエラー後の警告と自動修復をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="ebbfa-138">回復ツールをオフにする</span><span class="sxs-lookup"><span data-stu-id="ebbfa-138">Turn off recovery tools</span></span> | <span data-ttu-id="ebbfa-139">_schtasks.exe_ _、_ regedit.exe、</span><span class="sxs-lookup"><span data-stu-id="ebbfa-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="ebbfa-140">[システムの復元] などのシステム回復オプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="ebbfa-141">ランサムウェアアクティビティの個々の兆候を確認する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="ebbfa-142">前のセクションで説明したアクティビティを含め、ランサムウェアの動作を構成する多くのアクティビティは、良性である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="ebbfa-143">次のクエリを使用してランサムウェアを検索する場合は、複数のクエリを実行して、同じデバイスがランサムウェアアクティビティの可能性についてさまざまな兆候を示しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="ebbfa-144">プロセスを使用して複数のプロセス _をtaskkill.exe_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="ebbfa-145">このクエリは、アプリケーション ユーティリティを使用して少なくとも 10 の個別のプロセスを停止 _taskkill.exeします。_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="ebbfa-146">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="ebbfa-147">net stop を使用したプロセス _の停止_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="ebbfa-148">このクエリは、net stop コマンドを使用して少なくとも 10 つの個別のプロセスを停止 _しようとする試みをチェック_ します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="ebbfa-149">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="ebbfa-150">複数のドライブのデータを削除 _するには_、cipher.exe</span><span class="sxs-lookup"><span data-stu-id="ebbfa-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="ebbfa-151">このクエリでは、複数のドライブのデータを削除する試行が、cipher.exe。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="ebbfa-152">このアクティビティは、通常、暗号化後のデータの回復を防ぐためにランサムウェアによって行われます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="ebbfa-153">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

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

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="ebbfa-154">_wevtutil_ を使用したイベント ログからの証拠のクリア</span><span class="sxs-lookup"><span data-stu-id="ebbfa-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="ebbfa-155">このクエリは _、wevtutil_ を使用してイベント ログから少なくとも 10 のログ エントリをクリアする試行をチェックします。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="ebbfa-156">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="ebbfa-157">サーバーを使用してサービスを _オフsc.exe_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="ebbfa-158">このクエリは、このクエリを使用して少なくとも 10 の既存のサービスをオフに _sc.exe。_</span><span class="sxs-lookup"><span data-stu-id="ebbfa-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="ebbfa-159">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="ebbfa-160">システムの復元をオフにする</span><span class="sxs-lookup"><span data-stu-id="ebbfa-160">Turning off System Restore</span></span>
<span data-ttu-id="ebbfa-161">このクエリは、システムの復元を停止し、システムが復元ポイントを作成し、ランサムウェアによって暗号化されたデータを回復するために使用できる復元ポイントを作成する試みを識別します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="ebbfa-162">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

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

### <a name="backup-deletion"></a><span data-ttu-id="ebbfa-163">バックアップの削除</span><span class="sxs-lookup"><span data-stu-id="ebbfa-163">Backup deletion</span></span>
<span data-ttu-id="ebbfa-164">このクエリは、 _暗号化の前_ にwmic.exeシャドウ コピー スナップショットを削除する方法の使用を識別します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="ebbfa-165">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ebbfa-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="ebbfa-166">ランサムウェアアクティビティの複数の兆候を確認する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="ebbfa-167">複数のクエリを個別に実行する代わりに、ランサムウェア アクティビティの複数の兆候をチェックする包括的なクエリを使用して、影響を受けるデバイスを特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="ebbfa-168">次の統合クエリ:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-168">The following consolidated  query:</span></span>
- <span data-ttu-id="ebbfa-169">ランサムウェアアクティビティの比較的具体的な兆候と微妙な兆候の両方を探す</span><span class="sxs-lookup"><span data-stu-id="ebbfa-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="ebbfa-170">これらの兆候の存在の重み付け</span><span class="sxs-lookup"><span data-stu-id="ebbfa-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="ebbfa-171">ランサムウェアのターゲットになる可能性が高いデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="ebbfa-172">この統合クエリを実行すると、複数の攻撃の兆候が発生したデバイスの一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="ebbfa-173">ランサムウェアの各種類のアクティビティの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="ebbfa-174">この統合クエリを実行するには、高度な検索クエリ エディター [に直接コピーします](https://security.microsoft.com/advanced-hunting)。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

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
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="ebbfa-175">クエリ結果の理解と調整</span><span class="sxs-lookup"><span data-stu-id="ebbfa-175">Understand and tweak the query results</span></span>
<span data-ttu-id="ebbfa-176">統合クエリは、次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="ebbfa-177">**DeviceId**—影響を受けるデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="ebbfa-178">**TimeStamp**—デバイスでランサムウェアアクティビティの兆候が初めて観察された場合</span><span class="sxs-lookup"><span data-stu-id="ebbfa-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="ebbfa-179">**アクティビティの特定の兆候** _—BcdEdit_ や _FsUtil_ など、複数の列に表示される各記号の数</span><span class="sxs-lookup"><span data-stu-id="ebbfa-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="ebbfa-180">**TotalEvidenceCount**—観測された兆候の数</span><span class="sxs-lookup"><span data-stu-id="ebbfa-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="ebbfa-181">**UniqueEvidenceCount**—観測された兆候の種類の数</span><span class="sxs-lookup"><span data-stu-id="ebbfa-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![ランサムウェア アクティビティのクエリ結果のイメージ](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="ebbfa-183">*影響を受けるデバイスを示すクエリ結果と、ランサムウェアアクティビティのさまざまな兆候の数*</span><span class="sxs-lookup"><span data-stu-id="ebbfa-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="ebbfa-184">既定では、クエリ結果には、2 つ以上の種類のランサムウェア アクティビティを持つデバイスだけが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="ebbfa-185">ランサムウェア アクティビティの兆候があるすべてのデバイスを表示するには、次の演算子を変更し、数値を `where` ゼロ (0) に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="ebbfa-186">表示するデバイスの数を少なくするには、数値を大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="ebbfa-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebbfa-187">Related topics</span></span>
- [<span data-ttu-id="ebbfa-188">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="ebbfa-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ebbfa-189">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ebbfa-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ebbfa-190">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ebbfa-191">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ebbfa-192">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ebbfa-193">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)