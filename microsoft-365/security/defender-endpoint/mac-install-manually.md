---
title: macOSでのMicrosoft Defender for Endpointの手動デプロイ
description: コマンド ラインから手動でmacOSにMicrosoft Defender for Endpointをインストールします。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamf, macos, catalina, mojave, high sierra
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 68f91e4b8f789087aacea14b6b2a8a8b67262fd0
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159621"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>macOSでのMicrosoft Defender for Endpointの手動デプロイ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップ](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)します。

このトピックでは、macOSにMicrosoft Defender for Endpointを手動でデプロイする方法について説明します。 デプロイが正常に完了するには、次のすべての手順を完了する必要があります。

- [インストール パッケージとオンボード パッケージをダウンロードする](#download-installation-and-onboarding-packages)
- [アプリケーションのインストール (macOS 10.15)](#application-installation-macos-1015)
- [アプリケーションのインストール (macOS 11 以降のバージョン)](#application-installation-macos-11-and-newer-versions)
- [クライアント構成](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

作業を開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、[macOS ページのメイン](microsoft-defender-endpoint-mac.md) Microsoft Defender for Endpointを参照してください。

## <a name="download-installation-and-onboarding-packages"></a>インストール パッケージとオンボード パッケージをダウンロードする

Microsoft 365 Defender ポータルからインストール パッケージとオンボード パッケージをダウンロードします。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、**設定 > エンドポイント>デバイス管理>オンボードに** 移動します。
2. ページのセクション 1 で、オペレーティング システムを **macOS** に設定し、Deployment メソッドを **ローカル スクリプト** に設定します。
3. ページのセクション 2 で、[ **インストール パッケージのダウンロード**] を選択します。 wdav.pkg としてローカル ディレクトリに保存します。
4. ページのセクション 2 で、[ **オンボード パッケージのダウンロード**] を選択します。 同じディレクトリにWindowsDefenderATPOnboardingPackage.zipとして保存します。

   :::image type="content" source="images/portal-onboarding-macos.png" alt-text="インストール パッケージとオンボード パッケージをダウンロードするオプション" lightbox="images/portal-onboarding-macos.png":::

5. コマンド プロンプトから、2 つのファイルがあることを確認します。

## <a name="application-installation-macos-1015"></a>アプリケーションのインストール (macOS 10.15)

このプロセスを完了するには、デバイスに対する管理者特権が必要です。

1. Finder でダウンロードした wdav.pkg に移動し、開きます。

   :::image type="content" source="images/mdatp-28-appinstall.png" alt-text="アプリケーションのインストール" lightbox="images/mdatp-28-appinstall.png":::

2. **[続行]** を選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。

   :::image type="content" source="images/mdatp-29-appinstalllogin.png" alt-text="アプリケーションのインストール" lightbox="images/mdatp-29-appinstalllogin.png":::

   > [!IMPORTANT]
   > Microsoft のドライバーのインストールを許可するように求めるメッセージが表示されます ("システム拡張機能がブロックされました" または "インストールは保留中" か、またはその両方です)。 ドライバーのインストールを許可する必要があります。

     :::image type="content" source="images/mdatp-30-systemextension.png" alt-text="アプリケーションのインストール" lightbox="images/mdatp-30-systemextension.png":::

3. [ **セキュリティ環境設定を開く]** または [ **システム環境設定を開く] > [セキュリティ&プライバシー] を選択します**。 **[許可] を** 選択します。

   :::image type="content" source="images/mdatp-31-securityprivacysettings.png" alt-text="[セキュリティとプライバシー] ウィンドウ" lightbox="images/mdatp-31-securityprivacysettings.png":::

   インストールが続行されます。

   > [!CAUTION]
   > **[許可]** を選択しない場合、インストールは 5 分後に続行されます。 Microsoft Defender for Endpointが読み込まれますが、リアルタイム保護などの一部の機能は無効になります。 これを解決する方法については、「 [カーネル拡張機能の問題のトラブルシューティング](mac-support-kext.md) 」を参照してください。

> [!NOTE]
> macOSは、Microsoft Defender for Endpointの最初のインストール時にデバイスの再起動を要求する場合があります。 デバイスが再起動されるまで、リアルタイム保護は使用できません。

## <a name="application-installation-macos-11-and-newer-versions"></a>アプリケーションのインストール (macOS 11 以降のバージョン)

このプロセスを完了するには、デバイスに対する管理者特権が必要です。

1. Finder でダウンロードした wdav.pkg に移動し、開きます。

   :::image type="content" source="images/monterey-install-1.png" alt-text="アプリケーションのインストール プロセス" lightbox="images/monterey-install-1.png":::

2. **[続行]** を選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。

3. インストール プロセスの最後に、製品で使用されるシステム拡張機能を承認するように昇格されます。 [ **セキュリティ環境設定を開く] を選択します**。

   :::image type="content" source="images/monterey-install-2.png" alt-text="システム拡張機能の承認" lightbox="images/monterey-install-2.png":::

4. [ **セキュリティ&プライバシー** ] ウィンドウで、[ **許可**] を選択します。

   :::image type="content" source="images/monterey-install-3.png" alt-text="システム拡張機能のセキュリティ設定 1" lightbox="images/monterey-install-3.png":::

5. Mac でMicrosoft Defender for Endpointで配布されるすべてのシステム拡張機能について、手順 3 & 4 を繰り返します。

6. エンドポイント検出と応答機能の一環として、Mac のMicrosoft Defender for Endpointはソケット トラフィックを検査し、この情報をMicrosoft 365 Defender ポータルに報告します。 ネットワーク トラフィックをフィルター処理するためのアクセス許可Microsoft Defender for Endpoint付与するように求められたら、[許可] を選択 **します**。

   :::image type="content" source="images/monterey-install-4.png" alt-text="システム拡張機能のセキュリティ設定 2" lightbox="images/monterey-install-4.png":::

7. **システム環境設定** \> **のセキュリティ&プライバシー** を開き、[**プライバシー**] タブに移動します。**Microsoft Defender および Microsoft Defenders** **Endpoint Security 拡張機能** に **フル ディスク アクセス** 許可を付与します。

   :::image type="content" source="images/monterey-install-5.png" alt-text="フル ディスク アクセス" lightbox="images/monterey-install-5.png":::

## <a name="client-configuration"></a>クライアントの構成

1. macOSにMicrosoft Defender for Endpointを展開するデバイスに wdav.pkg と MicrosoftDefenderATPOnboardingMacOs.sh をコピーします。

    クライアント デバイスがorg_idに関連付けられていない。 *org_id* 属性は空白であることに注意してください。

    ```bash
    mdatp health --field org_id
    ```

2. Bash スクリプトを実行して、構成ファイルをインストールします。

    ```bash
    Sudo bash -x MicrosoftDefenderATPOnboardingMacOs.sh
    ```

3. デバイスが組織に関連付けられていることを確認し、有効な組織 ID を報告します。

    ```bash
    mdatp health --field org_id
    ```

    インストール後、右上隅のmacOSステータス バーに Microsoft Defender アイコンが表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mdatp-icon-bar.png" alt-text="ステータス バーの Microsoft Defender アイコン" lightbox="images/mdatp-icon-bar.png":::

## <a name="how-to-allow-full-disk-access"></a>フル ディスク アクセスを許可する方法

> [!CAUTION]
> macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれています。 このバージョン以降、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。 この同意がない場合、Microsoft Defender for Endpointはデバイスを完全に保護できません。

1. 同意を付与するには、**System Preferences** \> **Security & Privacy Privacy** \>  \> **Full Disk Access** を開きます。 ロック アイコンをクリックして変更を加えます (ダイアログ ボックスの下部)。 Microsoft Defender for Endpointを選択します。

2. AV 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。 新しくオンボードされたデバイスで次の手順を実行します。

    1. リアルタイム保護が有効になっていることを確認します (次のコマンドを実行した結果 1 で示されます)。

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. [ターミナル] ウィンドウを開きます。 次のコマンドをコピーして実行します。

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. ファイルは、Mac 上の Defender for Endpoint によって検疫されている必要があります。 次のコマンドを使用して、検出されたすべての脅威を一覧表示します。

        ```bash
        mdatp threat list
        ```

3. EDR検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。 新しくオンボードされたデバイスで次の手順を実行します。

   1. Mac や Safari のMicrosoft Edgeなど、ブラウザーで使用します。

   1. MDATP MacOS DIY.zipを https://aka.ms/mdatpmacosdiy ダウンロードして抽出します。

      次のメッセージが表示される場合があります。

      > "mdatpclientanalyzer.blob.core.windows.net" でダウンロードを許可しますか?<br/>
      > Web サイト環境設定でファイルをダウンロードできる Web サイトを変更できます。

4. **[許可]** をクリックします。

5. **ダウンロードを開きます**。

6. **MDATP MacOS DIY** が表示されます。

   > [!TIP]
   > ダブルクリックすると、次のメッセージが表示されます。
   >
   > > **開発者が検証ツールになれないため、"MDATP MacOS DIY" を開けません。**<br/>
   > > macOSこのアプリがマルウェアから解放されていることを確認できません。<br/>
   > > **\[ごみ箱\]****\[の取り消し\]** に移動する

7. [ **キャンセル**] をクリックします。

8. **MDATP MacOS DIY** を右クリックし、[**開く**] をクリックします。

    システムには次のメッセージが表示されます。

    > **macOS MDATP MacOS DIY の開発者を確認できません。開いてよければよか?**<br/>
    > このアプリを開くと、Mac に害を与えたり、プライバシーを侵害したりする可能性のあるマルウェアにコンピューターと個人情報を公開できるシステム セキュリティがオーバーライドされます。

9. [ **開く**] をクリックします。

    システムには次のメッセージが表示されます。

    > Microsoft Defender for Endpoint - MACOS EDR DIY テスト ファイル<br/>
    > 対応するアラートは、MDATP ポータルで利用できます。

10. [ **開く**] をクリックします。

    数分後に、"macOS EDR テスト アラート" という名前のアラートを発生させます。

11. Microsoft 365 Defender ポータル (https://security.microsoft.com/).

12. アラート キューに移動します。

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="重大度、カテゴリ、検出ソース、および折りたたまれたアクション のメニューを示すmacOS EDRテスト アラート" lightbox="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png":::

    アラートの詳細とデバイスのタイムラインを確認し、通常の調査手順を実行します。

## <a name="logging-installation-issues"></a>インストールの問題のログ記録

エラーが発生したときにインストーラーによって作成された自動的に生成されたログを見つける方法の詳細については、「 [インストールの問題のログ](mac-resources.md#logging-installation-issues) 記録」を参照してください。

## <a name="uninstallation"></a>アンインストール

クライアント デバイスからmacOSのMicrosoft Defender for Endpointを削除する方法の詳細については、「[アンインストール](mac-resources.md#uninstalling)」を参照してください。
