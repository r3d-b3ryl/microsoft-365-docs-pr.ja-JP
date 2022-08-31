---
title: 更新プログラムのコンプライアンスと Microsoft Defender ウイルス対策の診断データを収集する
description: Microsoft Defender ウイルス対策評価アドインを使用する場合は、ツールを使用してデータを収集し、Update Compliance の問題のトラブルシューティングを行います。
keywords: トラブルシューティング、エラー、修正、更新プログラムのコンプライアンス、oms、モニター、レポート、Microsoft Defender AV、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: b21201d5b3a24c570819ac903eb3a38058c362c8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479822"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Microsoft Defender ウイルス対策評価の更新プログラムコンプライアンス診断データを収集する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、Microsoft サポート チームとエンジニアリング チームが、更新プログラム コンプライアンス アドインの Microsoft Defender ウイルス対策評価セクションを使用するときに発生する可能性がある問題のトラブルシューティングに役立つ診断データを収集する方法について説明します。

このプロセスを試す前に、「 [Microsoft Defender ウイルス対策レポートのトラブルシューティング](troubleshoot-reporting.md)」を読み、前提条件をすべて満たしていることを確認し、その他推奨されるトラブルシューティング手順を実行します。

Update Compliance で報告または表示されていない少なくとも 2 つのデバイスで、次の手順を実行して.cab診断ファイルを取得します。

1. コマンド プロンプトの管理者レベルのバージョンを次のように開きます。

    a. **[スタート]** メニューを開きます。

    b. **「cmd」と入力します**。 **コマンド プロンプト** を右クリックし、[**管理者として実行**] を選択します。

    c. 管理者の資格情報を指定するか、プロンプトを承認します。

2. Windows Defender ディレクトリに移動します。 既定では `C:\Program Files\Windows Defender` です。

3. 次のコマンドを入力し、**Enter** キーを押します。

    ```Dos
    mpcmdrun -getfiles
    ```

4. さまざまな診断ログを含む.cab ファイルが生成されます。 ファイルの場所は、コマンド プロンプトの出力で指定されます。 既定では、場所は `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` です。

5. Microsoft サポートからアクセスできる場所に、これらの.cab ファイルをコピーします。 たとえば、パスワードで保護された OneDrive フォルダーを使用すると、Microsoft と共有できます。

6. <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">更新プログラムコンプライアンス サポートの電子メール テンプレート</a>を使用して電子メールを送信し、テンプレートに次の情報を入力します。

    ```text
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:

    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策レポートのトラブルシューティング](troubleshoot-reporting.md)
