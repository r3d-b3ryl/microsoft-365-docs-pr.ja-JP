---
title: macOS でMicrosoft Defender for Endpointでスキャンをスケジュールする方法
description: macOS のMicrosoft Defender for Endpointの自動スキャン時間をスケジュールして、組織の資産をより適切に保護する方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, スキャン, ウイルス対策
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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>macOS でMicrosoft Defender for Endpointを使用してスキャンをスケジュールする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpointを使用していつでも脅威スキャンを開始できますが、企業はスケジュールされたスキャンや時間指定されたスキャンの恩恵を受ける可能性があります。 たとえば、すべての稼働日または週の開始時に実行するようにスキャンをスケジュールできます。 

## <a name="schedule-a-scan-with-launchd"></a>*起動* されたスキャンをスケジュールする

macOS デバイスで *起動された* デーモンを使用して、スキャン スケジュールを作成できます。

ここで使用される *.plist* ファイル形式の詳細については、Apple の公式開発者向け Web サイトの [情報プロパティ リスト ファイルについて](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) を参照してください。

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

2. *ファイルを com.microsoft.wdav.schedquickscan.plist* として保存します。

### <a name="schedule-a-full-scan"></a>フル スキャンをスケジュールする

1. テキスト エディターを開き、この例をフル スキャンに使用します。

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

2. *ファイルを com.microsoft.wdav.schedfullscan.plist* として保存します。
 
### <a name="load-your-file"></a>ファイルを読み込む

1. **ターミナルを** 開きます。
2. 次のコマンドを入力してファイルを読み込みます。

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

3. スケジュールされたスキャンは、p リストで定義した日付、時刻、頻度で実行されます。 前の例では、毎週金曜日の午前 2 時 50 分にスキャンが実行されます。 

    - の値`StartCalendarInterval`は`Weekday`、整数を使用して週の 5 番目の日 (金曜日) を示します。 範囲は 0 ~ 7 で、7 は日曜日を表します。
    - の値`StartCalendarInterval`は`Day`、整数を使用して、月の 3 番目の日を示します。 範囲は 1 ~ 31 です。
    - 値`StartCalendarInterval`は`Hour`整数を使用して、1 日の 2 時間目を示します。 範囲は 0 ~ 24 です。
    `StartCalendarInterval`値は`Minute`整数を使用して、時間の 50 分を示します。 範囲は 0 ~ 59 です。
    
    
 > [!IMPORTANT]
 > *起動* された状態で実行されたエージェントは、デバイスがスリープ状態の間、スケジュールされた時刻には実行されません。 デバイスがスリープ モードから再開されると、代わりに実行されます。
 >
 > デバイスがオフになっている場合、スキャンは次のスケジュールされたスキャン時刻に実行されます。

## <a name="schedule-a-scan-with-intune"></a>Intuneを使用してスキャンをスケジュールする

Microsoft Intuneを使用してスキャンをスケジュールすることもできます。 [スクリプト for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP)で使用できる [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) シェル スクリプトは、デバイスがスリープ モードから再開されたときに保持されます。 

エンタープライズ[でこのスクリプトを使用する](/mem/intune/apps/macos-shell-scripts)方法の詳細な手順については、「Intuneの macOS デバイスでシェル スクリプトを使用する」を参照してください。
