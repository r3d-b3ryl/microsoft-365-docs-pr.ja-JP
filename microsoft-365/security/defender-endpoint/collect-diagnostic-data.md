---
title: データの診断データを収集Microsoft Defender ウイルス対策
description: ツールを使用してデータを収集し、データのトラブルシューティングMicrosoft Defender ウイルス対策
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、モニター、レポート、Microsoft Defender av、グループ ポリシー オブジェクト、設定、診断データ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8a016ab0e73af99ce47c30b598daade864e041eb
ms.sourcegitcommit: ea4bc3b005d86b029700e56015a47b8cc6dca2a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "58510027"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a>Microsoft Defender AV 診断データの収集

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、Microsoft Defender AV を使用するときに発生する可能性がある問題のトラブルシューティングに役立つ Microsoft サポートチームとエンジニアリング チームが使用できる診断データを収集する方法について説明します。

> [!NOTE]
> 調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。 次の方法: デバイスから [調査パッケージを収集します](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)。

同じ問題が発生している少なくとも 2 つのデバイスで、次.cabを実行して診断ファイルを取得します。

1. 次のように、管理者レベルのバージョンのコマンド プロンプトを開きます。

    a. [スタート] **メニューを開** きます。

    b. cmd **と入力します**。 [コマンド プロンプト] を右 **クリックし、[** 管理者として **実行] を選択します**。

    c. 管理者の資格情報を指定するか、プロンプトを承認します。

2. Microsoft Defender ディレクトリに移動します。 既定では `C:\Program Files\Windows Defender` です。

   > [!NOTE]
   > 更新された Microsoft [Defender プラットフォーム](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)バージョンを実行している場合は、次の `MpCmdRun` 場所から実行してください `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 。

3. 次のコマンドを入力し、Enter キーを **押します。**

    ```Dos
    mpcmdrun.exe -GetFiles
    ```

4. さまざまな.cabを含むファイルが生成されます。 ファイルの場所は、コマンド プロンプトの出力で指定されます。 既定では、場所は `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .

   > [!NOTE]
   > cab ファイルを別のパスまたは UNC 共有にリダイレクトするには、次のコマンドを使用します。 `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`  <br/>詳細については、「診断データ [を UNC 共有にリダイレクトする」を参照してください](#redirect-diagnostic-data-to-a-unc-share)。

5. これらのファイル.cab、Microsoft サポートからアクセスできる場所にコピーします。 たとえば、パスワードで保護されたフォルダー OneDrive共有できるフォルダーがあります。

> [!NOTE]
> 更新コンプライアンスに問題がある場合は、更新コンプライアンス サポート メール<a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>テンプレートを使用して電子メールを送信し、テンプレートに次の情報を入力します。
>
> Update Compliance で更新プログラムを使用するときに、次Microsoft Defender ウイルス対策が発生します。
>
> 次の場所に少なくとも 2 つのサポート .cabファイルを提供しました。
>
> \<accessible share, including access details such as password\>
>
> OMS ワークスペース ID は次の値です。
>
> 以下の連絡先にお問い合わせください。

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>診断データを UNC 共有にリダイレクトする

中央リポジトリの診断データを収集するには、SupportLogLocation パラメーターを指定します。

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

診断データを指定したパスにコピーします。 パスを指定しない場合、診断データはサポート ログの場所構成で指定された場所にコピーされます。

SupportLogLocation パラメーターを使用すると、次のようなフォルダー構造が移動先パスに作成されます。

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

<br>

****

|フィールド|説明|
|---|---|
|path|コマンド ラインで指定されたパス、または構成から取得されたパス|
|MMDD|診断データが収集された月と日 (たとえば、0530)|
|ホスト名|診断データが収集されたデバイスのホスト名|
|HHMM|診断データが収集された時間と分 (たとえば、1422)|
|

> [!NOTE]
> ファイル共有を使用する場合は、診断パッケージの収集に使用されるアカウントが共有への書き込みアクセス権を持っている必要があります。

## <a name="specify-location-where-diagnostic-data-is-created"></a>診断データの作成場所を指定する

グループ ポリシー オブジェクト (GPO) を使用.cabファイルを作成する場所を指定することもできます。

1. ローカル グループ ポリシー エディターを開き、SupportLogLocation GPO を次の場所で検索します `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation` 。

2. [サポート **ログ ファイルをコピーするディレクトリ パスを定義する] を選択します**。

   ![ローカル グループ ポリシー エディターのスクリーンショット](images/GPO1-SupportLogLocationDefender.png)

   ![ログ ファイルの定義パス設定のスクリーンショット](images/GPO2-SupportLogLocationGPPage.png)

3. ポリシー エディター内で、[有効] を **選択します**。

4. サポート ログ ファイルをコピーするディレクトリ パスを [オプション] フィールドに **指定** します。

   ![有効なディレクトリ パスのカスタム設定のスクリーンショット](images/GPO3-SupportLogLocationGPPageEnabledExample.png)

5. **[OK] または [** 適用]**を選択します**。

## <a name="see-also"></a>関連項目

- [レポートのMicrosoft Defender ウイルス対策トラブルシューティング](troubleshoot-reporting.md)
