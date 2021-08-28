---
title: Jamf の macOS ポリシーで Microsoft Defender for Endpoint をセットアップPro
description: Jamf サーバーで macOS ポリシーで Microsoft Defender for Endpoint をセットアップするPro
keywords: ポリシー、microsoft、Defender、Microsoft Defender for Endpoint、Mac、インストール、展開、アンインストール、intune、jamfpro、macos、catalina、mojave、high sierra
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
ms.openlocfilehash: 303b32499d73b14751ece094dfd6f900386cbba0
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58568302"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Jamf の macOS ポリシーで Microsoft Defender for Endpoint をセットアップPro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Defender for Endpoint on Mac](microsoft-defender-endpoint-mac.md)

このページでは、Jamf ポリシーで macOS ポリシーをセットアップするために必要な手順をPro。

次の手順を実行する必要があります。

1. [Microsoft Defender for Endpoint オンボーディング パッケージの取得](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [オンボード パッケージを使用して Jamf Pro構成プロファイルを作成する](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [エンドポイントの Microsoft Defender の設定を構成する](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Microsoft Defender for Endpoint 通知の設定を構成する](#step-4-configure-notifications-settings)

5. [Microsoft AutoUpdate (MAU) の構成](#step-5-configure-microsoft-autoupdate-mau)

6. [Microsoft Defender for Endpoint へのフル ディスク アクセスを許可する](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Microsoft Defender for Endpoint のカーネル拡張機能を承認する](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [エンドポイント用 Microsoft Defender のシステム拡張機能を承認する](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [ネットワーク拡張機能の構成](#step-9-configure-network-extension)

10. [macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [macOS での Microsoft Defender for Endpoint の展開](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)

## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>手順 1: Microsoft Defender for Endpoint オンボーディング パッケージを取得する

1. [[Microsoft Defender セキュリティ センター]](https://securitycenter.microsoft.com)で、[オンボーディング]**設定 >移動します**。

2. オペレーティング システムとして macOS を、展開方法として [モバイル デバイスMicrosoft Intuneを選択します。

    ![画像のMicrosoft Defender セキュリティ センター。](images/onboarding-macos.png)

3. [ **オンボード パッケージのダウンロード] (WindowsDefenderATPOnboardingPackage.zip)** を選択します。

4. 抽出 `WindowsDefenderATPOnboardingPackage.zip` .

5. ファイルを好みの場所にコピーします。 例: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>手順 2: オンボード パッケージを使用して Jamf Pro構成プロファイルを作成する

1. 前のセクション `WindowsDefenderATPOnboarding.plist` からファイルを探します。

   ![WindowsDefenderATPOnboarding ファイルのイメージ。](images/plist-onboarding-file.png)

2. Jamf Proで、[新規] を **選択します**。

    ![新しい Jamf ダッシュボードを作成Proイメージ。](images/jamf-pro-configure-profile.png)

3. 次の詳細を入力します。

   **全般**
   - 名前: macOS の MDATP オンボーディング
   - 説明: mDATP EDR macOS のオンボーディング
   - カテゴリ: なし
   - 配布方法: 自動的にインストールする
   - レベル: コンピューター レベル

4. [**アプリケーション の設定&カスタム 設定** 構成] を **選択します**。

    ![アプリとカスタム設定を構成するイメージ。](images/jamfpro-mac-profile.png)

5. **[アップロードファイル (PLIST ファイル) を選択し、[基本設定ドメイン]** **に次を** 入力します `com.microsoft.wdav.atp` 。

    ![jamfpro plist アップロード ファイルのイメージ。](images/jamfpro-plist-upload.png)

    ![アップロード ファイル プロパティリスト ファイルのイメージ。](images/jamfpro-plist-file.png)

6. [開 **く] を** 選択し、オンボーディング ファイルを選択します。

    ![オンボーディング ファイルのイメージ。](images/jamfpro-plist-file-onboard.png)

7. [アップロード]**を選択します**。

    ![plist ファイルのアップロードのイメージ。](images/jamfpro-upload-plist.png)

8. [スコープ] **タブを選択** します。

    ![[スコープ] タブの画像。](images/jamfpro-scope-tab.png)

9. ターゲット コンピューターを選択します。

    ![ターゲット コンピューターのイメージ。](images/jamfpro-target-computer.png)

    ![ターゲットのイメージ。](images/jamfpro-targets.png)

10. **[保存]** を選択します。

    ![展開対象のコンピューターのイメージ。](images/jamfpro-deployment-target.png)

    ![選択されているターゲット コンピューターのイメージ。](images/jamfpro-target-selected.png)

11. **[完了]** を選択します。

    ![ターゲット グループ コンピューターのイメージ。](images/jamfpro-target-group.png)

    ![構成プロファイルの一覧。](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>手順 3: エンドポイントの Microsoft Defender の設定を構成する

JAMF Pro GUI を使用して Microsoft Defender 構成の個々の設定を編集するか、テキスト エディターで構成 Plist を作成して JAMF Pro にアップロードすることで従来のメソッドを使用できます。

ユーザー設定ドメインとして正確に使用する必要があります。Microsoft Defender では、この名前のみを使用し、管理設定 `com.microsoft.wdav`  `com.microsoft.wdav.ext` を読み込む必要があります。

(GUI メソッドを使用する場合はまれにバージョンを使用できますが、スキーマにまだ追加されていない設定を構成する `com.microsoft.wdav.ext` 必要があります)。

### <a name="gui-method"></a>GUI メソッド

1. Defender schema.jsリポジトリからファイルにGitHub[し](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema)、ローカル ファイルに保存します。

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. [コンピューター- >構成プロファイル] の下に新しい構成プロファイルを作成し、[全般] タブに次の詳細を **入力** します。

    ![新しいプロファイル。](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - 名前: MDATP MDAV 構成設定
    - 説明:\<blank\>
    - カテゴリ: なし (既定)
    - レベル: コンピューター レベル (既定)
    - 配布方法: 自動インストール (既定)

3. 下にスクロールして 、[アプリケーション &**カスタム** 設定] タブをクリックし、[外部アプリケーション] を選択し、[追加] をクリックして、カスタム スキーマをソースとして使用して、基本設定ドメインに使用します。 

    ![カスタム スキーマを追加します。](images/4137189bc3204bb09eed3aabc41afd78.png)

4. [ `com.microsoft.wdav` 基本設定ドメイン] として入力し、[スキーマの追加] をクリックし **アップロード** 手順 1 でschema.jsを選択します。 **[保存]** をクリックします。

    ![アップロードスキーマ。](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. サポートされている Microsoft Defender 構成設定はすべて、以下の [基本設定ドメインのプロパティ] **の下に表示されます**。 [ **プロパティの追加と削除]** をクリックして、管理する設定を選択し **、[OK]** をクリックして変更を保存します。 (設定選択されていない場合、エンド ユーザーはそれらの設定を自分のコンピューターで構成できます。

    ![[管理設定] を選択します。](images/817b3b760d11467abe9bdd519513f54f.png)

6. 設定の値を目的の値に変更します。 [詳細] **をクリックすると、** 特定の設定のドキュメントを取得できます。 **([Plist プレビュー] をクリックして**、構成 plist の外観を確認できます。 [ **フォーム エディター] を** クリックしてビジュアル エディターに戻る)。

    ![設定の値を変更します。](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. [スコープ] **タブを選択** します。

    ![構成プロファイルのスコープ。](images/9fc17529e5577eefd773c658ec576a7d.png)

8. **[Contoso's Machine Group] を選択します**。

9. [追加 **] を** 選択し、[保存] **を選択します**。

    ![構成設定 - 追加。](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![構成設定 - 保存します。](images/6f093e42856753a3955cab7ee14f12d9.png)

10. **[完了]** を選択します。 新しい構成プロファイルが **表示されます**。

    ![構成設定 - 完了。](images/dd55405106da0dfc2f50f8d4525b01c8.png)

Microsoft Defender は、時間の間に新しい設定を追加します。 これらの新しい設定がスキーマに追加され、新しいバージョンが Github に発行されます。
更新を行う必要があるのは、更新されたスキーマのダウンロード、既存の構成プロファイルの編集、およびスキーマの編集を[アプリケーションの設定] タブで行&**する** 設定です。

### <a name="legacy-method"></a>従来のメソッド

1. 次の Microsoft Defender for Endpoint 構成設定を使用します。

    - enableRealTimeProtection
    - passiveMode

    > [!NOTE]
    > 既定ではオンにされません。macOS 用にサードパーティの AV を実行する予定の場合は、 に設定します `true` 。

    - 除外
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats

    > [!NOTE]
    > EICAR はサンプルに含め、概念実証を行う場合は、EICAR をテストする場合は特に削除してください。

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon

     詳細については [、「Jamf 構成プロファイルのプロパティ 一覧」を参照してください](mac-preferences.md#property-list-for-jamf-configuration-profile)。

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. ファイルをとして保存します `MDATP_MDAV_configuration_settings.plist` 。

3. Jamf Proで、[コンピューター] を **開** き、[**構成プロファイル] を開きます**。 [**New] をクリックし* 、[全般] タブ **に切り替** えます。

    ![新しいプロファイル。](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV 構成設定
    - 説明:\<blank\>
    - カテゴリ: なし (既定)
    - 配布方法: 自動インストール(既定)
    - Level: Computer Level(default)

    ![MDATP MDAV 構成設定のイメージ。](images/3160906404bc5a2edf84d1d015894e3b.png)

5. [**アプリケーション の設定&カスタム 設定** 構成] を **選択します**。

    ![アプリとカスタム設定のイメージ。](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. [**ファイルアップロード (PLIST ファイル) を選択します**。

    ![構成設定 plist ファイルのイメージ。](images/6f85269276b2278eca4bce84f935f87b.png)

7. [**基本設定ドメイン] で** `com.microsoft.wdav` 、「PLIST ファイル」と入力アップロード **選択します**。

    ![構成設定の基本設定ドメインのイメージ。](images/db15f147dd959e872a044184711d7d46.png)

8. [ファイル **の選択] を選択します**。

    ![構成設定のイメージは、ファイルを選択します。](images/526e978761fc571cca06907da7b01fd6.png)

9. **[MDATP_MDAV_configuration_settings.plist] を選択し、[** 開く] を **選択します**。

    ![mdatpmdav 構成設定のイメージ。](images/98acea3750113b8dbab334296e833003.png)

10. [アップロード]**を選択します**。

    ![構成設定のアップロードのイメージ。](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![構成設定アップロードイメージのイメージ。](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Intune ファイルをアップロードすると、次のようなエラー メッセージが表示されます。<br>
    >![構成設定 intune ファイルのアップロードのイメージ。](images/8e69f867664668796a3b2904896f0436.png)

11. **[保存]** を選択します。

    ![構成設定のイメージ イメージを保存します。](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. ファイルがアップロードされます。

    ![構成設定ファイルのアップロードされたイメージのイメージ。](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![アップロードされた構成設定ファイルのイメージ。](images/a422e57fe8d45689227e784443e51bd1.png)

13. [スコープ] **タブを選択** します。

    ![構成設定スコープのイメージ。](images/9fc17529e5577eefd773c658ec576a7d.png)

14. **[Contoso's Machine Group] を選択します**。

15. [追加 **] を** 選択し、[保存] **を選択します**。

    ![構成設定のイメージを追加します。](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![構成設定のイメージが追加を保存します。](images/6f093e42856753a3955cab7ee14f12d9.png)

16. **[完了]** を選択します。 新しい構成プロファイルが **表示されます**。

    ![構成設定の構成プロファイル イメージのイメージ。](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a>手順 4: 通知の設定を構成する

これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。

1. Jamf Proで、[コンピューター] 、[**構成** プロファイル]**の順に選択します**。

2. [ **新規] を** クリックし、[オプション] に次の詳細を **入力します**。

    - タブ **全般**:
        - **名前**: MDATP MDAV 通知の設定
        - **説明**: macOS 10.15 (Catalina) 以降
        - **カテゴリ**: なし *(既定)*
        - **配布方法**: 自動的にインストール *する (既定)*
        - **レベル**: コンピューター レベル *(既定)*

        ![新しい macOS 構成プロファイル画面のイメージ。](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - [タブ **通知]** をクリック **し、[追加**] をクリックし、次の値を入力します。
        - **バンドル ID**: `com.microsoft.wdav.tray`
        - **重大な通知**: [無効にする] **をクリックします。**
        - **通知**: [有効にする **] をクリックします。**
        - **バナー通知の種類**: [含める]**と [一時**]  *(既定) を選択します。*
        - **ロック画面の通知**: [非表示] **をクリックします。**
        - **通知センターの通知**: [表示] を **クリックします。**
        - **バッジ アプリのアイコン**: [表示] **をクリックします。**

        ![構成設定 mdatpmdav 通知トレイのイメージ。](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Tab **Notifications**, Click **Add more time,** scroll down to **new Notifications** 設定
        - **バンドル ID**: `com.microsoft.autoupdate2`
        - 残りの設定を上記と同じ値に構成する

        ![構成設定 mdatpmdav 通知 mau のイメージ。](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        通知構成が 2 つの 「テーブル」 に追加され、もう 1 つはバンドル ID : **com.microsoft.wdav.tray、** もう 1 つはバンドル **ID: com.microsoft.autoupdate2** です。 要件ごとにアラート設定を構成することもできますが、バンドル ID は前の説明とまったく同じにする必要があります。Include **スイッチは** 通知に対して **[オン] にする** 必要 **があります**。

3. [スコープ] **タブを選択** し、[追加] を **選択します**。

    ![構成設定スコープのイメージが追加されます。](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. **[Contoso's Machine Group] を選択します**。

5. [追加 **] を** 選択し、[保存] **を選択します**。

    ![構成設定 contoso machine grp の保存のイメージ。](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![構成設定のイメージは、保存を追加します。](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. **[完了]** を選択します。 新しい構成プロファイルが **表示されます**。
    ![img を実行した構成設定のイメージ。](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>手順 5: Microsoft AutoUpdate (MAU) を構成する

1. 次の Microsoft Defender for Endpoint 構成設定を使用します。

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. として保存します `MDATP_MDAV_MAU_settings.plist` 。

3. Jamf のダッシュボードでPro [全般] を **選択します**。

    ![構成設定の一般的なイメージのイメージ。](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV MAU の設定
    - 説明: MacOS 用 MDATP の Microsoft AutoUpdate 設定
    - カテゴリ: なし (既定)
    - 配布方法: 自動インストール(既定)
    - Level: Computer Level(default)

5. [**アプリケーション の設定&カスタム 設定** 構成] を **選択します**。

    ![構成設定アプリとカスタム設定のイメージ。](images/1f72e9c15eaafcabf1504397e99be311.png)

6. [**ファイルアップロード (PLIST ファイル) を選択します**。

    ![構成設定 plist のイメージ。](images/1213872db5833aa8be535da57653219f.png)

7. [**基本設定ドメイン]** に次 `com.microsoft.autoupdate2` を入力し、[PLIST **ファイルアップロードを選択します**。

    ![構成設定のプリフェッチ ドメインのイメージ。](images/1213872db5833aa8be535da57653219f.png)

8. [ファイル **の選択] を選択します**。

    ![構成設定の選択ファイルのイメージ。](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. **[MDATP_MDAV_MAU_settings.plist] を選択します**。

    ![構成設定 mdatpmdavmau 設定のイメージ。](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. [アップロード]**を選択します**。
    ![構成設定 uplimage のイメージ。](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![構成設定 uplimg のイメージ。](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. **[保存]** を選択します。

    ![構成設定 saveimg のイメージ。](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. [スコープ] **タブを選択** します。

     ![構成設定 scopetab のイメージ。](images/10ab98358b2d602f3f67618735fa82fb.png)

13. **[追加]** を選択します。

    ![構成設定 addimg1 のイメージ。](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![構成設定 addimg2 のイメージ。](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![構成設定 addimg3 のイメージ。](images/321ba245f14743c1d5d51c15e99deecc.png)

14. **[完了]** を選択します。

    ![構成設定 doneimage のイメージ。](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>手順 6: エンドポイント用 Microsoft Defender へのフル ディスク アクセスを許可する

1. Jamf Proダッシュボードで、[**構成プロファイル] を選択します**。

    ![構成設定の構成プロファイルのイメージ。](images/264493cd01e62c7085659d6fdc26dc91.png)

2. [+ **新規] を選択します**。

3. 次の詳細を入力します。

    **全般**
    - 名前: MDATP MDAV - ディスクおよび AV へのフル ディスク アクセスEDR付与する
    - 説明: macOS Catalina 以降では、新しいプライバシー設定ポリシーコントロール
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル


    ![構成設定全般のイメージ。](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. [ **プライバシー設定の構成] ポリシーコントロールで、[構成** ] を **選択します**。

    ![構成のプライバシー ポリシー制御のイメージ。](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. [ **プライバシー設定ポリシー制御] で、** 次の詳細を入力します。

    - 識別子: `com.microsoft.wdav`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![構成設定のプライバシー設定ポリシー制御の詳細のイメージ。](images/22cb439de958101c0a12f3038f905b27.png)

6. **[+ 追加]** を選択します。

    ![構成設定のイメージは、システム ポリシーのすべてのファイルを追加します。](images/bd93e78b74c2660a0541af4690dd9485.png)

    - [アプリまたはサービス] で **、SystemPolicyAllFiles に設定する**

    - [アクセス] の下: [許可] に **設定します。**

7. [ **保存]** を選択します (右下の保存は選択しない)。

    ![構成設定保存イメージのイメージ。](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. [アプリ アクセス `+` ] の横にある **記号をクリックして** 、新しいエントリを追加します。

    ![構成設定アプリアクセスのイメージ。](images/tcc-add-entry.png)

9. 次の詳細を入力します。

    - 識別子: `com.microsoft.wdav.epsext`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. **[+ 追加]** を選択します。

    ![構成設定 tcc epsext エントリのイメージ。](images/tcc-epsext-entry.png)

    - [アプリまたはサービス] で **、SystemPolicyAllFiles に設定する**

    - [アクセス] の下: [許可] に **設定します。**

11. [ **保存]** を選択します (右下の保存は選択しない)。

    ![構成設定 tcc epsext image2 のイメージ。](images/tcc-epsext-entry2.png)

12. [スコープ] **タブを選択** します。

    ![構成設定スコープのイメージ。](images/2c49b16cd112729b3719724f581e6882.png)

13. **[+ 追加]** を選択します。

    ![構成設定のイメージ addimage。](images/57cef926d1b9260fb74a5f460cee887a.png)

14. [ **グループ名]** > [コンピューター グループ] **を** 選択> **Contoso の MachineGroup を選択します**。

    ![構成設定 contoso machinegrp のイメージ。](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. **[追加]** を選択します。

16. **[保存]** を選択します。

17. **[完了]** を選択します。

    ![構成設定 donimg のイメージ。](images/809cef630281b64b8f07f20913b0039b.png)

    ![構成設定 donimg2 のイメージ。](images/6c8b406ee224335a8c65d06953dc756e.png)

または、「Jamf を使用したカスタム構成プロファイルの展開」の説明に従って[、fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)をダウンロードして JAMF 構成プロファイル[にアップロードPro|方法 2: アップロードプロファイルを Jamf ファイルにPro。](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>手順 7: Microsoft Defender for Endpoint のカーネル拡張機能を承認する

> [!CAUTION]
> Apple Silicon (M1) デバイスは KEXT をサポートしていない。 KEXT ポリシーからなる構成プロファイルのインストールは、これらのデバイスで失敗します。

1. [構成プロファイル **] で、[+** 新規 **] を選択します**。

    ![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット。](images/6c8b406ee224335a8c65d06953dc756e.png)

2. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV カーネル拡張機能
    - 説明: MDATP カーネル拡張機能 (kext)
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    ![構成設定 mdatpmdav カーネルのイメージ。](images/24e290f5fc309932cf41f3a280d22c14.png)

3. [承認済 **みカーネル拡張機能の構成] で、[構成** ] を **選択します**。

    ![構成設定承認済みカーネル ext のイメージ。](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

4. [ **承認済みカーネル拡張機能]** で、次の詳細を入力します。

    - 表示名: Microsoft Corp.
    - チーム ID: UBF8T346G9

    ![構成設定 appr カーネル拡張機能のイメージ。](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. [スコープ] **タブを選択** します。

    ![構成設定の範囲タブ img のイメージ。](images/0df36fc308ba569db204ee32db3fb40a.png)

6. **[+ 追加]** を選択します。

7. [ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。

8. **[+ 追加]** を選択します。

    ![構成設定のイメージは、イメージを追加します。](images/0dde8a4c41110dbc398c485433a81359.png)

9. **[保存]** を選択します。

    ![構成設定の saveimag のイメージ。](images/0add8019b85a453b47fa5c402c72761b.png)

10. **[完了]** を選択します。

    ![構成設定 doneimag のイメージ。](images/1c9bd3f68db20b80193dac18f33c22d0.png)

または、「Jamf を使用したカスタム構成プロファイルの展開」の説明に従って[、kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig)をダウンロードして JAMF 構成プロファイルに[アップロードPro|方法 2: アップロードプロファイルを Jamf ファイルにPro。](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>手順 8: エンドポイント用 Microsoft Defender のシステム拡張機能を承認する

1. [構成プロファイル **] で、[+** 新規 **] を選択します**。

    ![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット。](images/6c8b406ee224335a8c65d06953dc756e.png)

2. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV システム拡張機能
    - 説明: MDATP システム拡張機能
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    ![構成設定のイメージ sysext 新しい prof.](images/sysext-new-profile.png)

3. [ **システム拡張機能] で、[構成** ] を **選択します**。

   ![構成設定 sysext config のイメージ。](images/sysext-configure.png)

4. [System **Extensions] に次** の詳細を入力します。

   - 表示名: Microsoft Corp. System Extensions
   - システム拡張の種類: 許可されているシステム拡張機能
   - チーム識別子: UBF8T346G9
   - 許可されるシステム拡張機能:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![構成設定 sysextconfig2 のイメージ。](images/sysext-configure2.png)

5. [スコープ] **タブを選択** します。

    ![構成設定の scopeimage のイメージ。](images/0df36fc308ba569db204ee32db3fb40a.png)

6. **[+ 追加]** を選択します。

7. [ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。

8. **[+ 追加]** を選択します。

   ![構成設定 addima のイメージ。](images/0dde8a4c41110dbc398c485433a81359.png)

9. **[保存]** を選択します。

   ![構成設定 sysext スコープのイメージ。](images/sysext-scope.png)

10. **[完了]** を選択します。

    ![構成設定 sysext-final のイメージ。](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>手順 9: ネットワーク拡張機能を構成する

エンドポイント検出および応答機能の一環として、macOS 上の Microsoft Defender for Endpoint はソケット トラフィックを検査し、この情報をポータルMicrosoft Defender セキュリティ センターします。 次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。

これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。

1. Jamf Proで、[コンピューター] 、[**構成** プロファイル]**の順に選択します**。

2. [ **新規] を** クリックし、[オプション] に次の詳細を **入力します**。

    - タブ **全般**:
        - **名前**: Microsoft Defender ATP ネットワーク拡張機能
        - **説明**: macOS 10.15 (Catalina) 以降
        - **カテゴリ**: なし *(既定)*
        - **配布方法**: 自動的にインストール *する (既定)*
        - **レベル**: コンピューター レベル *(既定)*

    - タブ **コンテンツ フィルター**:
        - **フィルター名**: Microsoft Defender ATP コンテンツ フィルター
        - **識別子**: `com.microsoft.wdav`
        - サービス **アドレス 、****組織、****ユーザー名、** パスワード、**証明書** を空白のままにする **(Include** *は* 選択されません) 
        - **フィルターの順序**: Inspector
        - **ソケット フィルター**: `com.microsoft.wdav.netext`
        - **ソケット フィルターの指定要件**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - [ **ネットワーク フィルター] フィールド** を空白のままにします **([含** める *] は* 選択されません)

        識別子、 **ソケット フィルター** **、ソケット フィルター** の指定 **された** 要件の正確な値は、上記で指定したとおりです。

        ![構成設定 mdatpmdav のイメージ。](images/netext-create-profile.png)

3. [スコープ] **タブを選択** します。

   ![[構成設定] [sco] タブのイメージ。](images/0df36fc308ba569db204ee32db3fb40a.png)

4. **[+ 追加]** を選択します。

5. [ **グループ名]** > [コンピューター グループ] **を>** Contoso の [コンピューター グループ] **を選択します**。

6. **[+ 追加]** を選択します。

    ![構成設定 adim のイメージ。](images/0dde8a4c41110dbc398c485433a81359.png)

7. **[保存]** を選択します。

    ![構成設定のイメージ savimg netextscop。](images/netext-scope.png)

8. **[完了]** を選択します。

    ![構成設定 netextfinal のイメージ。](images/netext-final.png)

または、「Jamf を使用したカスタム構成プロファイルの展開」の説明に従って[、netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)をダウンロードして JAMF 構成プロファイル[にアップロードPro|方法 2: アップロードプロファイルを Jamf ファイルにPro。](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>手順 10: macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする

macOS の Microsoft Defender for Endpoint でスキャンをスケジュール [するの手順に従います](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>手順 11: macOS に Microsoft Defender for Endpoint を展開する

1. 保存した場所に移動します `wdav.pkg` 。

    ![ファイル エクスプローラー wdav pkg のイメージ。](images/8dde76b5463047423f8637c86b05c29d.png)

2. に名前を変更します `wdav_MDM_Contoso_200329.pkg` 。

    ![エクスプローラー 1 wdavmdmpkg のイメージ。](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Jamf ダッシュボードをProします。

    ![構成設定 jamfpro のイメージ。](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. コンピューターを選択し、上部の歯車アイコンをクリックし、[コンピューターの管理] **を選択します**。

    ![構成設定 compmgmt のイメージ。](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. [パッケージ **] で**、[+ **新規] を選択します**。
    ![Bird Description が自動的に生成されたパッケージ new を含む図。](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. [ **新しいパッケージ]** で、次の詳細を入力します。

    **[全般] タブ**
    - 表示名: 空白のままにしておきます。 pkg を選択するとリセットされます。
    - カテゴリ: なし (既定)
    - ファイル名: [ファイル] を選択します。

    ![構成設定の [全般] タブのイメージ。](images/21de3658bf58b1b767a17358a3f06341.png)

    ファイルを開き、またはをポイント `wdav.pkg` します `wdav_MDM_Contoso_200329.pkg` 。

    ![コンピューター画面のスクリーンショット 説明が自動的に生成されます。](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. [**開く**]を選択します。 [表示名 **] を**[Microsoft Defender Advanced Threat Protection] に設定 **し、Microsoft Defender ウイルス対策。**

    **マニフェスト ファイル** は必須ではありません。 Microsoft Defender for Endpoint はマニフェスト ファイルなしで動作します。

    **オプション タブ**<br> 既定値を保持します。

    **[制限] タブ**<br> 既定値を保持します。

     ![[構成設定の制限] タブのイメージ。](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. **[保存]** を選択します。 パッケージは Jamf ファイルにアップロードPro。

   ![構成設定パック upl jamf pro のイメージ。](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   パッケージを展開に使用するには数分かかる場合があります。

   ![構成設定パック upl のイメージ。](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. [ポリシー] **ページに移動** します。

    ![構成設定のポロのイメージ。](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. [+ **新規] を** 選択して新しいポリシーを作成します。

    ![構成設定の新しいポリシーのイメージ。](images/847b70e54ed04787e415f5180414b310.png)


11. [ **全般]** 次の詳細を入力します。

    - 表示名: MDATP Onboarding Contoso 200329 v100.86.92 以降

    ![構成設定mdatponboardのイメージ。](images/625ba6d19e8597f05e4907298a454d28.png)

12. [ **定期的なチェックイン] を選択します**。

    ![構成設定の再チェック インのイメージ。](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

13. **[保存]** を選択します。

14. [パッケージ **] を選択>構成します**。

    ![構成設定パック構成のイメージ。](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. [Microsoft **Defender Advanced Threat** Protection] の横にある [追加] ボタンを **選択し、Microsoft Defender ウイルス対策。**

    ![MDATP と MDA の構成設定のイメージを追加します。](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. **[保存]** を選択します。

    ![構成設定のイメージsavimg。](images/9d6e5386e652e00715ff348af72671c6.png)

17. [スコープ] **タブを選択** します。

    ![構成設定 scptab のイメージ。](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. ターゲット コンピューターを選択します。

    ![構成設定 tgtcomp のイメージ。](images/6eda18a64a660fa149575454e54e7156.png)

    **スコープ**

    **[追加]** を選択します。

    ![構成設定 ad1img のイメージ。](images/1c08d097829863778d562c10c5f92b67.png)

    ![構成設定 ad2img のイメージ。](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **セルフサービス**

    ![構成設定セルフサービスのイメージ。](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. **[完了]** を選択します。

    ![構成設定 do1img のイメージ。](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![構成設定 do2img のイメージ。](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)
