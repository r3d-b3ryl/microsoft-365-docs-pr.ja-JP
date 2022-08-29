---
title: Microsoft Defender ウイルス対策の診断データの収集
description: Microsoft Defender ウイルス対策のトラブルシューティングにデータを収集するツールを使用する
keywords: トラブルシューティング, エラー, 修正, 更新コンプライアンス, oms, 監視, レポート, Microsoft Defender av, グループ ポリシー オブジェクト, 設定, 診断データ, Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 017f4304b1d049a202da460cbf2f31a4fa8f955b
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387993"
---
# <a name="collect-microsoft-defender-antivirus-diagnostic-data"></a>Microsoft Defender ウイルス対策の診断データを収集する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

この記事では、Microsoft Defender ウイルス対策を使用するときに発生する可能性のある問題のトラブルシューティングに役立つ、Microsoft サポートおよびエンジニアリング チームが使用できる診断データを収集する方法について説明します。

> [!NOTE]
> 調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。 次の方法を使用します。 [デバイスから調査パッケージを収集します](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)。

同じ問題が発生している少なくとも 2 つのデバイスで、次の手順を実行して.cab診断ファイルを取得します。

1. コマンド プロンプトの管理者レベルのバージョンを次のように開きます。

    a. **[スタート]** メニューを開きます。

    b. **「cmd」と入力します**。 **コマンド プロンプト** を右クリックし、[**管理者として実行**] を選択します。

    c. 管理者の資格情報を指定するか、プロンプトを承認します。

2. Microsoft Defender ウイルス対策のディレクトリに移動します。 既定では `C:\Program Files\Windows Defender` です。

   > [!NOTE]
   > [更新された Microsoft Defender マルウェア対策プラットフォームのバージョン](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)を実行している場合は、次の場所`C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`から実行`MpCmdRun`してください。

3. 次のコマンドを入力し、**Enter** キーを押します。

    ```Dos
    mpcmdrun.exe -GetFiles
    ```

4. さまざまな診断ログを含む.cab ファイルが生成されます。 ファイルの場所は、コマンド プロンプトの出力で指定されます。 既定では、場所は `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` です。

   > [!NOTE]
   > cab ファイルを別のパスまたは UNC 共有にリダイレクトするには、次のコマンドを使用します。
   >
   > `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`
   >
   > 詳細については、「 [診断データを UNC 共有にリダイレクトする](#redirect-diagnostic-data-to-a-unc-share)」を参照してください。

5. Microsoft サポートからアクセスできる場所に、これらの.cab ファイルをコピーします。 たとえば、パスワードで保護された OneDrive フォルダーを使用すると、Microsoft と共有できます。

> [!NOTE]
> 更新プログラムのコンプライアンスに問題がある場合は、 <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance サポートの電子メール テンプレート</a>を使用して電子メールを送信し、テンプレートに次の情報を入力します。
>
> 更新プログラムコンプライアンスで Microsoft Defender ウイルス対策を使用すると、次の問題が発生します。
>
> 次の場所に少なくとも 2 つのサポート .cab ファイルを提供しました。
>
> \<accessible share, including access details such as password\>
>
> OMS ワークスペース ID は次のとおりです。
>
> 次の連絡先にお問い合わせください。

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>診断データを UNC 共有にリダイレクトする

中央リポジトリで診断データを収集するには、SupportLogLocation パラメーターを指定します。

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

診断データを指定したパスにコピーします。 パスが指定されていない場合、診断データはサポート ログの場所の構成で指定された場所にコピーされます。

SupportLogLocation パラメーターを使用すると、次のようなフォルダー構造が宛先パスに作成されます。

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

<br>

****

|フィールド|説明|
|---|---|
|path|コマンド ラインで指定するか、構成から取得したパス|
|MMDD|診断データが収集された月と日 (0530 など)|
|ホスト|診断データが収集されたデバイスのホスト名|
|HHMM|診断データが収集された時間と分 (1422 など)|
|

> [!NOTE]
> ファイル共有を使用する場合は、診断パッケージの収集に使用されるアカウントに共有への書き込みアクセス権があることを確認してください。

## <a name="specify-location-where-diagnostic-data-is-created"></a>診断データが作成される場所を指定する

また、グループ ポリシー オブジェクト (GPO) を使用して、診断.cab ファイルを作成する場所を指定することもできます。

1. ローカル グループ ポリシー エディターを開き、次の場所にある SupportLogLocation GPO を`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`見つけます。

2. **[サポート ログ ファイルをコピーするディレクトリ パスを定義する**] を選択します。

   :::image type="content" source="images/GPO1-SupportLogLocationDefender.png" alt-text="ローカル グループ ポリシー エディター" lightbox="images/GPO1-SupportLogLocationDefender.png":::

   :::image type="content" source="images/GPO2-SupportLogLocationGPPage.png" alt-text="ログ ファイルのパスを定義する設定" lightbox="images/GPO2-SupportLogLocationGPPage.png":::

   :::image type="content" source="images/GPO1-SupportLogLocationDefender.png" alt-text="ローカル グループ ポリシー エディター" lightbox="images/GPO1-SupportLogLocationDefender.png"::: 
        
   :::image type="content" source="images/GPO2-SupportLogLocationGPPage.png" alt-text="ログ ファイル設定を構成するための定義パス" lightbox="images/GPO2-SupportLogLocationGPPage.png":::
 
3. ポリシー エディター内で、[ **有効]** を選択します。

4. **[オプション**] フィールドで、サポート ログ ファイルをコピーするディレクトリ パスを指定します。
   :::image type="content" source="images/GPO3-SupportLogLocationGPPageEnabledExample.png" alt-text="[有効なディレクトリ パス] のカスタム設定" lightbox="images/GPO3-SupportLogLocationGPPageEnabledExample.png":::
5. **[OK] または [適用] を選択します**。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策レポートのトラブルシューティング](troubleshoot-reporting.md)
