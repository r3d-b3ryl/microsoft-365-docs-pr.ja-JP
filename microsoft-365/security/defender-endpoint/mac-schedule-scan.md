---
title: macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする方法
description: 組織の資産をより保護するために、macOS の Microsoft Defender for Endpoint の自動スキャン時間をスケジュールする方法について説明します。
keywords: microsoft、defender、Microsoft Defender for Endpoint、mac、スキャン、ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 629db5fc343d100913d631f59a680fc9160713ed
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765998"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint を使用していつでも脅威スキャンを開始することができますが、企業はスケジュールされたスキャンや時間指定スキャンのメリットを得る可能性があります。 たとえば、すべての作業日または週の初めにスキャンを実行するスケジュールを設定できます。 

## <a name="schedule-a-scan-with-launchd"></a>起動したスキャンを *スケジュールする*

macOS デバイスで起動されたデーモンを使用 *してスキャン スケジュール* を作成できます。

ここで使用する *.plist ファイル* 形式の詳細については、Apple の公式開発者向け Web サイトの「 [情報プロパティ リスト](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) ファイルについて」を参照してください。

### <a name="schedule-a-quick-scan"></a>クイック スキャンをスケジュールする

次のコードは、クイック スキャンをスケジュールするために使用する必要があるスキーマを示しています。 

1. テキスト エディターを開き、この例を独自のスケジュールされたスキャン ファイルのガイドとして使用します。

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

2. ファイルを *com.microsoft.wdav.schedquickscan.plist として保存します*。

### <a name="schedule-a-full-scan"></a>フル スキャンをスケジュールする

1. テキスト エディターを開き、フル スキャンにこの例を使用します。

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedfullscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan full</string>
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
            <integer>50</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. ファイルを *com.microsoft.wdav.schedfullscan.plist として保存します*。
 
### <a name="load-your-file"></a>ファイルを読み込む

1. ターミナルを **開きます**。
2. ファイルを読み込むには、次のコマンドを入力します。

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

3. スケジュールされたスキャンは、p リストで定義した日付、時刻、および頻度で実行されます。 前の例では、スキャンは毎週金曜日の午前 2 時 50 分に実行されます。 

    - 値 `Weekday` は、 `StartCalendarInterval` 週の 5 日目または金曜日を示すために整数を使用します。 範囲は 0 ~ 7 で、7 は日曜日を表します。
    - 値 `Day` は、 `StartCalendarInterval` 月の 3 日目を示すために整数を使用します。 範囲は 1 ~ 31 です。
    - 値 `Hour` は、 `StartCalendarInterval` 1 日の 2 時間目を示すために整数を使用します。 範囲は 0 ~ 24 です。
    値 `Minute` は、 `StartCalendarInterval` 1 時間の 50 分を示す整数を使用します。 範囲は 0 ~ 59 です。
    
    
 > [!IMPORTANT]
 > 起動済みで *実行された* エージェントは、デバイスがスリープ状態の間、スケジュールされた時刻に実行されません。 デバイスがスリープ モードから再開すると、代わりに実行されます。
 >
 > デバイスがオフになっている場合、スキャンは次のスケジュールされたスキャン時間に実行されます。

## <a name="schedule-a-scan-with-intune"></a>Intune でスキャンをスケジュールする

また、スキャンをスケジュールすることもできます。Microsoft Intune。 Microsoft [Defender](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) [for Endpoint runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) 使用可能なシェル スクリプトは、デバイスがスリープ モードから再開しても保持されます。 

エンタープライズ [でこのスクリプトを使用する](/mem/intune/apps/macos-shell-scripts) 方法の詳細については、「Intune の macOS デバイスでシェル スクリプトを使用する」を参照してください。
