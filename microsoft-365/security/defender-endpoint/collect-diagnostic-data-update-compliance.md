---
title: 更新コンプライアンスと Microsoft Defender ウイルス対策の診断Windows Defender収集する
description: Microsoft Defender ウイルス対策評価アドインを使用する場合は、ツールを使用してデータを収集して更新コンプライアンスの問題をトラブルシューティングする
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、モニター、レポート、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3975a18c2986ac7766664194a6d4b80ee1a503b1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691102"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a>Microsoft Defender AV 評価の更新コンプライアンス診断データを収集する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、Microsoft サポートチームとエンジニアリング チームが使用できる診断データを収集して、更新コンプライアンス アドインの Microsoft Defender AV Assessment セクションを使用するときに発生する可能性がある問題のトラブルシューティングに役立つ方法について説明します。

このプロセスを試す前に [、「Microsoft Defender ウイルス](troubleshoot-reporting.md)対策レポートのトラブルシューティング」を読み、すべての必須コンポーネントを満たしていることを確認し、その他の推奨されるトラブルシューティング手順を実行してください。

Update Compliance でレポートまたは表示されていない少なくとも 2 つのデバイスで、次の手順を実行して .cab 診断ファイルを取得します。

1. 次のように、管理者レベルのバージョンのコマンド プロンプトを開きます。
        
    a. [スタート] **メニューを開** きます。

    b. cmd **と入力します**。 [コマンド プロンプト] を右 **クリックし、[** 管理者として **実行] をクリックします**。

    c. 管理者の資格情報を入力するか、プロンプトを承認します。
        
2. ディレクトリに移動Windows Defenderします。 既定では `C:\Program Files\Windows Defender` です。

3. 次のコマンドを入力し、Enter キーを **押します。**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. さまざまな診断ログを含む .cab ファイルが生成されます。 ファイルの場所は、コマンド プロンプトの出力で指定されます。 既定では、場所は `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. これらの .cab ファイルを、Microsoft サポートからアクセスできる場所にコピーします。 たとえば、パスワードで保護された OneDrive フォルダーを使用して共有できます。

6. [コンプライアンスの更新] サポート メール テンプレートを使用して電子メールを <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">送信し</a>、テンプレートに次の情報を入力します。
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルスWindows Defenderレポートのトラブルシューティング](troubleshoot-reporting.md)