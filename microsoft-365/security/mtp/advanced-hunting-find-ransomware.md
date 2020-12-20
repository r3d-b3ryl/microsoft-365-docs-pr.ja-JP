---
title: 高度な検索でランサムウェアを検索する
description: 高度な検索を使用して、ランサムウェアによって影響を受ける可能性があるデバイスを探します。
keywords: 高度な検索、ランサムウェア、脅威の探し、サイバーの脅威を探す、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: aaee2af4b3df849b57b8e1c18ab330603042fe96
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422906"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="33ce6-104">ランサムウェアを探します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="33ce6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="33ce6-105">**Applies to:**</span></span>
- <span data-ttu-id="33ce6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33ce6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="33ce6-107">ランサムウェアは、個々のコンピュータユーザーに影響を与えるシンプルな汎用マルウェアから、業界や政府機関の組織に大きな影響を与えるエンタープライズ脅威に急速に発展しています。</span><span class="sxs-lookup"><span data-stu-id="33ce6-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="33ce6-108">[Microsoft 365 Defender](microsoft-threat-protection.md)には、ランサムウェアと関連する侵入活動を検出してブロックする多くの機能が用意されていますが、侵害の兆候を事前にチェックしておくと、ネットワークの保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-108">While [Microsoft 365 Defender](microsoft-threat-protection.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="33ce6-109">人間が操作するランサムウェアについて確認する</span><span class="sxs-lookup"><span data-stu-id="33ce6-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="33ce6-110">Microsoft 365 Defender での [高度な](advanced-hunting-overview.md) 検索では、ランサムウェアアクティビティに関連付けられた個々の成果物を検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="33ce6-111">また、アクティビティの兆候を検索し、それらの署名を比較して、すぐに注意が必要なデバイスを見つけることができる高度なクエリを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="33ce6-112">ランサムウェアのアクティビティの兆候</span><span class="sxs-lookup"><span data-stu-id="33ce6-112">Signs of ransomware activity</span></span>
<span data-ttu-id="33ce6-113">Microsoft のセキュリティ研究者は、高度な侵入者によって開始された多くのランサムウェア活動において、さまざまな共通の一般的な成果物を観察</span><span class="sxs-lookup"><span data-stu-id="33ce6-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="33ce6-114">これらの記号は、主にシステムツールを使用して、暗号化の準備、検出の防止、法的証拠のクリアを行います。</span><span class="sxs-lookup"><span data-stu-id="33ce6-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="33ce6-115">ランサムウェアアクティビティ</span><span class="sxs-lookup"><span data-stu-id="33ce6-115">Ransomware activity</span></span> | <span data-ttu-id="33ce6-116">共通ツール</span><span class="sxs-lookup"><span data-stu-id="33ce6-116">Common tools</span></span> | <span data-ttu-id="33ce6-117">Intent</span><span class="sxs-lookup"><span data-stu-id="33ce6-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="33ce6-118">プロセスを停止する</span><span class="sxs-lookup"><span data-stu-id="33ce6-118">Stop processes</span></span> | <span data-ttu-id="33ce6-119">_taskkill.exe_、 _net stop_</span><span class="sxs-lookup"><span data-stu-id="33ce6-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="33ce6-120">暗号化の対象となるファイルが、さまざまなアプリケーションによってロックされないようにします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="33ce6-121">サービスをオフにする</span><span class="sxs-lookup"><span data-stu-id="33ce6-121">Turn off services</span></span> | <span data-ttu-id="33ce6-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="33ce6-122">_sc.exe_</span></span> | <span data-ttu-id="33ce6-123">-暗号化の対象となるファイルが、さまざまなアプリケーションによってロックされないようにします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="33ce6-124">-セキュリティソフトウェアが暗号化やその他のランサムウェアの動作を中断させないようにします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="33ce6-125">-バックアップソフトウェアによる回復可能なコピーの作成を停止します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="33ce6-126">ログとファイルの削除</span><span class="sxs-lookup"><span data-stu-id="33ce6-126">Delete logs and files</span></span> | <span data-ttu-id="33ce6-127">_cipher.exe_、 _wevtutil_、 _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="33ce6-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="33ce6-128">法的証拠を削除します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="33ce6-129">シャドウコピーの削除</span><span class="sxs-lookup"><span data-stu-id="33ce6-129">Delete shadow copies</span></span>  | <span data-ttu-id="33ce6-130">_vsadmin.exe_、 _wmic.exe_</span><span class="sxs-lookup"><span data-stu-id="33ce6-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="33ce6-131">暗号化されたファイルの回復に使用できるドライブシャドウコピーを削除します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="33ce6-132">バックアップの削除と停止</span><span class="sxs-lookup"><span data-stu-id="33ce6-132">Delete and stop backups</span></span> | <span data-ttu-id="33ce6-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="33ce6-133">_wbadmin.exe_</span></span> | <span data-ttu-id="33ce6-134">既存のバックアップを削除して、スケジュールされたバックアップタスクを停止し、暗号化後の回復を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="33ce6-135">ブート設定を変更する</span><span class="sxs-lookup"><span data-stu-id="33ce6-135">Modify boot settings</span></span> | <span data-ttu-id="33ce6-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="33ce6-136">_bcdedit.exe_</span></span> | <span data-ttu-id="33ce6-137">暗号化プロセスによって発生する可能性のある起動エラー後に、警告と自動修復を無効にします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="33ce6-138">回復ツールをオフにする</span><span class="sxs-lookup"><span data-stu-id="33ce6-138">Turn off recovery tools</span></span> | <span data-ttu-id="33ce6-139">_schtasks.exe_、 _regedit.exe_、</span><span class="sxs-lookup"><span data-stu-id="33ce6-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="33ce6-140">[システムの復元] およびその他のシステム回復オプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="33ce6-141">ランサムウェアアクティビティの個々の兆候を確認する</span><span class="sxs-lookup"><span data-stu-id="33ce6-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="33ce6-142">前のセクションで説明したアクティビティを含む、ランサムウェアの動作を構成する多くのアクティビティは、害がありません。</span><span class="sxs-lookup"><span data-stu-id="33ce6-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="33ce6-143">次のクエリを使用してランサムウェアを探すときには、複数のクエリを実行して、同じデバイスがランサムウェアの可能性があるアクティビティの兆候を示しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="33ce6-144">_taskkill.exe_ を使用して複数のプロセスを停止する</span><span class="sxs-lookup"><span data-stu-id="33ce6-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="33ce6-145">このクエリは、 _taskkill.exe_ ユーティリティを使用して、少なくとも10個の個別のプロセスを停止する試みをチェックします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="33ce6-146">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="33ce6-147">_Net stop_ を使用したプロセスの停止</span><span class="sxs-lookup"><span data-stu-id="33ce6-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="33ce6-148">このクエリは、 _net stop_ コマンドを使用して、少なくとも10個の独立したプロセスを停止する試みをチェックします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="33ce6-149">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="33ce6-150">_cipher.exe_ を使用した複数ドライブ上のデータの削除</span><span class="sxs-lookup"><span data-stu-id="33ce6-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="33ce6-151">このクエリは _cipher.exe_ を使用して、複数のドライブのデータを削除しようとしているかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="33ce6-152">通常、このアクティビティは、暗号化後のデータの回復を防止するためにランサムウェアによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="33ce6-153">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

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

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="33ce6-154">_Wevtutil_ を使用してイベントログから法廷での証拠を消去する</span><span class="sxs-lookup"><span data-stu-id="33ce6-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="33ce6-155">このクエリは、 _wevtutil_ を使用して、イベントログから少なくとも10個のログエントリをクリアする試みをチェックします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="33ce6-156">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="33ce6-157">_sc.exe_ を使用したサービスの無効化</span><span class="sxs-lookup"><span data-stu-id="33ce6-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="33ce6-158">このクエリは _sc.exe_ を使用して、少なくとも10個の既存のサービスをオフにする試みをチェックします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="33ce6-159">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="33ce6-160">システムの復元の無効化</span><span class="sxs-lookup"><span data-stu-id="33ce6-160">Turning off System Restore</span></span>
<span data-ttu-id="33ce6-161">このクエリは、システムの復元を停止する試みを識別し、ランサムウェアで暗号化されたデータを回復するために使用できる復元ポイントを作成することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="33ce6-162">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

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

### <a name="backup-deletion"></a><span data-ttu-id="33ce6-163">バックアップの削除</span><span class="sxs-lookup"><span data-stu-id="33ce6-163">Backup deletion</span></span>
<span data-ttu-id="33ce6-164">このクエリは、暗号化の前にシャドウコピースナップショットを削除するために _wmic.exe_ を使用することを識別します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="33ce6-165">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="33ce6-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="33ce6-166">ランサムウェアのアクティビティの複数の兆候をチェックする</span><span class="sxs-lookup"><span data-stu-id="33ce6-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="33ce6-167">複数のクエリを別々に実行するのではなく、包括的なクエリを使用して、ランサムウェアのアクティビティの複数の兆候をチェックして、影響を受けるデバイスを特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="33ce6-168">次の統合クエリがあります。</span><span class="sxs-lookup"><span data-stu-id="33ce6-168">The following consolidated  query:</span></span>
- <span data-ttu-id="33ce6-169">ランサムウェアのアクティビティの比較的コンクリートおよび微妙な兆候を探します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="33ce6-170">これらの記号の存在を認識します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="33ce6-171">ランサムウェアの対象となる可能性の高いデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="33ce6-172">この統合クエリを実行すると、複数のアタックの兆候が発生しているデバイスの一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="33ce6-173">ランサムウェアアクティビティの種類の数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="33ce6-174">この統合クエリを実行するには、 [高度な検索クエリエディター](https://security.microsoft.com/advanced-hunting)に直接コピーします。</span><span class="sxs-lookup"><span data-stu-id="33ce6-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

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
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="33ce6-175">クエリ結果を理解し、微調整する</span><span class="sxs-lookup"><span data-stu-id="33ce6-175">Understand and tweak the query results</span></span>
<span data-ttu-id="33ce6-176">統合クエリは、次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="33ce6-177">**DeviceId**—影響を受けるデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="33ce6-178">**タイムスタンプ**: デバイスでランサムウェア処理のいずれかの兆候が発生したことを初めて確認したとき</span><span class="sxs-lookup"><span data-stu-id="33ce6-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="33ce6-179">**特定のアクティビティの兆候**— _BcdEdit_ または _FsUtil_ などの複数の列に表示される各記号の数</span><span class="sxs-lookup"><span data-stu-id="33ce6-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="33ce6-180">**TotalEvidenceCount**-観測サインの数</span><span class="sxs-lookup"><span data-stu-id="33ce6-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="33ce6-181">**UniqueEvidenceCount**—観測標識の種類の数</span><span class="sxs-lookup"><span data-stu-id="33ce6-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![ランサムウェアアクティビティのクエリ結果の画像](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="33ce6-183">*影響を受けるデバイスと、ランサムウェアアクティビティのさまざまな兆候の数を示すクエリ結果*</span><span class="sxs-lookup"><span data-stu-id="33ce6-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="33ce6-184">既定では、クエリ結果には、3つ以上の種類のランサムウェアアクティビティがあるデバイスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33ce6-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="33ce6-185">ランサムウェアのアクティビティのいずれかの符号を持つすべてのデバイスを表示するには、次の演算子を変更 `where` し、数値をゼロ (0) に設定します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="33ce6-186">より少ない数のデバイスを表示するには、大きい番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="33ce6-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="33ce6-187">関連トピック</span><span class="sxs-lookup"><span data-stu-id="33ce6-187">Related topics</span></span>
- [<span data-ttu-id="33ce6-188">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="33ce6-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="33ce6-189">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="33ce6-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="33ce6-190">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="33ce6-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="33ce6-191">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="33ce6-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="33ce6-192">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="33ce6-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="33ce6-193">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="33ce6-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)