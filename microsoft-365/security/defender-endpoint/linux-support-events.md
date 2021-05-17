---
title: Linux 上の Microsoft Defender for Endpoint の不足しているイベントまたはアラートの問題のトラブルシューティング
description: Linux 上の Microsoft Defender for Endpoint のイベントやアラートの問題が見つからない場合のトラブルシューティングを行います。
keywords: microsoft、defender、Microsoft Defender for Endpoint、Linux、イベント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933315"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="05f6e-104">Linux 上の Microsoft Defender for Endpoint の不足しているイベントまたはアラートの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="05f6e-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05f6e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="05f6e-105">**Applies to:**</span></span>

- [<span data-ttu-id="05f6e-106">Linux 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="05f6e-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="05f6e-107">この記事では、セキュリティ センター ポータルで不足しているイベントやアラートを軽減するための一般的 [な手順について説明](https://securitycenter.windows.com/) します。</span><span class="sxs-lookup"><span data-stu-id="05f6e-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="05f6e-108">**Microsoft Defender for Endpoint** がデバイスに正しくインストールされると、ポータルにデバイス ページが生成されます。 </span><span class="sxs-lookup"><span data-stu-id="05f6e-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="05f6e-109">記録されたイベントはすべて、デバイス ページの [タイムライン] タブ、または高度な検索ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="05f6e-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="05f6e-110">このセクションでは、一部またはすべての予期されるイベントが見つからない場合のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="05f6e-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="05f6e-111">たとえば、すべての _CreatedFile_ イベントが見つからない場合です。</span><span class="sxs-lookup"><span data-stu-id="05f6e-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="05f6e-112">ネットワークイベントとログイン イベントが見つからない</span><span class="sxs-lookup"><span data-stu-id="05f6e-112">Missing network and login events</span></span>

<span data-ttu-id="05f6e-113">Microsoft Defender for Endpoint では、ネットワーク `audit` とログインアクティビティを追跡するために Linux からフレームワークを利用しました。</span><span class="sxs-lookup"><span data-stu-id="05f6e-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="05f6e-114">監査フレームワークが機能している必要があります。</span><span class="sxs-lookup"><span data-stu-id="05f6e-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="05f6e-115">予期される出力:</span><span class="sxs-lookup"><span data-stu-id="05f6e-115">expected output:</span></span>

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. <span data-ttu-id="05f6e-116">停止 `auditd` 済みとしてマークされている場合は、開始します。</span><span class="sxs-lookup"><span data-stu-id="05f6e-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="05f6e-117">**SLES システムでは** 、SYSCALL 監査は既定で無効になっている可能性があります。イベントが見つからない `auditd` 場合は考慮できます。</span><span class="sxs-lookup"><span data-stu-id="05f6e-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="05f6e-118">SYSCALL 監査が無効でなかっているのを検証するには、現在の監査ルールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="05f6e-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="05f6e-119">次の行が存在する場合は、削除するか編集して、Microsoft Defender for Endpoint が特定の SYSCALL を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="05f6e-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="05f6e-120">監査ルールは 、 に位置します `/etc/audit/rules.d/audit.rules` 。</span><span class="sxs-lookup"><span data-stu-id="05f6e-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="05f6e-121">ファイル イベントが見つからない</span><span class="sxs-lookup"><span data-stu-id="05f6e-121">Missing file events</span></span>

<span data-ttu-id="05f6e-122">ファイル イベントはフレームワークで収集 `fanotify` されます。</span><span class="sxs-lookup"><span data-stu-id="05f6e-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="05f6e-123">一部またはすべてのファイル イベントが見つからない場合は、デバイスで有効になっているか、ファイル システムが `fanotify` サポートされている必要 [があります](microsoft-defender-endpoint-linux.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="05f6e-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="05f6e-124">コンピューター上のファイルシステムを次のコマンドで一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="05f6e-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
