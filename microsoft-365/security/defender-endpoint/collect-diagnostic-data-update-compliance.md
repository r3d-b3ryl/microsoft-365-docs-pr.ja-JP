---
title: 更新コンプライアンスと更新プログラムの診断データをMicrosoft Defender ウイルス対策
description: ツールを使用してデータを収集し、評価アドインで更新コンプライアンスMicrosoft Defender ウイルス対策トラブルシューティングします。
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
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 9e368f2cb3cecf9359c4aed5e727aef2ee21c02b
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171679"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>更新プログラムのコンプライアンス診断データを収集して、Microsoft Defender ウイルス対策する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、Microsoft サポートチームとエンジニアリング チームが使用できる診断データを収集して、更新コンプライアンス アドインの Microsoft Defender ウイルス対策 Assessment セクションを使用するときに発生する可能性がある問題のトラブルシューティングに役立つ方法について説明します。

このプロセスを試す前に、「レポートのトラブルシューティング」[を](troubleshoot-reporting.md)Microsoft Defender ウイルス対策、すべての必須コンポーネントを満たしていることを確認し、その他の推奨されるトラブルシューティング手順を実行してください。

Update Compliance でレポートまたは表示されていない少なくとも 2 つのデバイスで、次の手順を実行して、.cab診断ファイルを取得します。

1. 次のように、管理者レベルのバージョンのコマンド プロンプトを開きます。

    a. [スタート] **メニューを開** きます。

    b. cmd **と入力します**。 [コマンド プロンプト] を右 **クリックし、[** 管理者として **実行] を選択します**。

    c. 管理者の資格情報を指定するか、プロンプトを承認します。

2. ディレクトリに移動Windows Defenderします。 既定では `C:\Program Files\Windows Defender` です。

3. 次のコマンドを入力し、Enter キーを **押します。**

    ```Dos
    mpcmdrun -getfiles
    ```

4. さまざまな.cabを含むファイルが生成されます。 ファイルの場所は、コマンド プロンプトの出力で指定されます。 既定では、場所は `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. これらのファイル.cab、Microsoft サポートからアクセスできる場所にコピーします。 たとえば、パスワードで保護されたフォルダー OneDrive共有できるフォルダーがあります。

6. 更新コンプライアンス サポート メール テンプレートを使用して電子メールを <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">送信し</a>、テンプレートに次の情報を入力します。

    ```text
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:

    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>関連項目

- [レポートのMicrosoft Defender ウイルス対策トラブルシューティング](troubleshoot-reporting.md)
