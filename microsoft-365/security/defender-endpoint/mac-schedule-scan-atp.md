---
title: macOS 用 MDATP を使用してスキャンをスケジュールする方法
description: 組織の資産をより保護するために、macOS で Microsoft Defender ATP の自動スキャン時間をスケジュールする方法について説明します。
keywords: microsoft、Defender、atp、mac、スキャン、ウイルス対策
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4151513874d295e3033b1ed365f10fb576c4ac18
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066435"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="b1765-104">Microsoft Defender for Endpoint for Mac でのスキャンのスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="b1765-104">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1765-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b1765-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1765-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b1765-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b1765-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1765-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b1765-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b1765-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1765-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b1765-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b1765-110">Microsoft Defender for Endpoint を使用していつでも脅威スキャンを開始することができますが、企業はスケジュールされたスキャンや時間指定スキャンのメリットを得る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1765-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="b1765-111">たとえば、すべての作業日または週の初めにスキャンを実行するスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1765-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="b1765-112">起動したスキャンを *スケジュールする*</span><span class="sxs-lookup"><span data-stu-id="b1765-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="b1765-113">macOS デバイスで起動されたデーモンを使用 *してスキャン* スケジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b1765-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="b1765-114">次のコードは、スキャンをスケジュールするために使用する必要があるスキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="b1765-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="b1765-115">テキスト エディターを開き、この例を独自のスケジュールされたスキャン ファイルのガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b1765-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="b1765-116">ここで使用する *.plist ファイル* 形式の詳細については、Apple の公式開発者向け Web サイトの「 [情報プロパティ リスト](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) ファイルについて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1765-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="b1765-117">ファイルを *com.microsoft.wdav.schedquickscan.plist として保存します*。</span><span class="sxs-lookup"><span data-stu-id="b1765-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="b1765-118">クイック スキャンの代わりにフル スキャンを実行するには、行 12 を変更し、(つまり) の代わりにオプションを使用し、ファイルを `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched の代わりに com.microsoft.wdav.sched* full *scan.plist* として保存します。</span><span class="sxs-lookup"><span data-stu-id="b1765-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="b1765-119">ターミナルを **開きます**。</span><span class="sxs-lookup"><span data-stu-id="b1765-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="b1765-120">ファイルを読み込むには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b1765-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="b1765-121">スケジュールされたスキャンは、p リストで定義した日付、時刻、および頻度で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1765-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="b1765-122">この例では、スキャンは毎週金曜日の午前 2 時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1765-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="b1765-123">値 `Weekday` は、週の 5 日目または金曜日を示すために整数 `StartCalendarInterval` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1765-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="b1765-124">起動済みで *実行された* エージェントは、デバイスがスリープ状態の間、スケジュールされた時刻に実行されません。</span><span class="sxs-lookup"><span data-stu-id="b1765-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="b1765-125">デバイスがスリープ モードから再開すると、代わりに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1765-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="b1765-126">デバイスがオフになっている場合、スキャンは次のスケジュールされたスキャン時間に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1765-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="b1765-127">Intune でスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="b1765-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="b1765-128">Microsoft Intune でスキャンをスケジュールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1765-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="b1765-129">Microsoft [Defender](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) [for Endpoint runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh)使用可能なシェル スクリプトは、デバイスがスリープ モードから再開しても保持されます。</span><span class="sxs-lookup"><span data-stu-id="b1765-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="b1765-130">エンタープライズ [でこのスクリプトを使用する](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) 方法の詳細については、「Intune の macOS デバイスでシェル スクリプトを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1765-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
