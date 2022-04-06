---
title: Jamf サーバーで macOS ポリシーで Microsoft Defender for Endpoint をPro
description: Jamf の MacOS ポリシーで Microsoft Defender for Endpoint をセットアップする方法について説明Pro
keywords: ポリシー、microsoft、Defender、Microsoft Defender for Endpoint、Mac、インストール、展開、アンインストール、intune、jamfpro、macos、catalina、mojave、high sierra
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
ms.openlocfilehash: 6e3a31343468b79ff1117a60eca6a87825562778
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466787"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Jamf サーバーで macOS ポリシーで Microsoft Defender for Endpoint をPro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Defender for Endpoint on Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

このページでは、Jamf ポリシーで macOS ポリシーを設定するために必要な手順をPro。

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

1. [[Microsoft 365 Defender](https://security.microsoft.com)] で、[オンボーディング **設定 >エンドポイント>移動します**。

2. オペレーティング システムとして macOS を選択し、展開方法として [モバイル デバイスMicrosoft Intuneを選択します。

   :::image type="content" source="images/onboarding-macos.png" alt-text="ページ設定ページMicrosoft Defender セキュリティ センター" lightbox="images/onboarding-macos.png":::

3. [ **オンボード パッケージのダウンロード] (WindowsDefenderATPOnboardingPackage.zip** ) を選択します。

4. 抽出 `WindowsDefenderATPOnboardingPackage.zip`.

5. ファイルを好みの場所にコピーします。 たとえば、「 `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist` 」のように入力します。

## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>手順 2: オンボード パッケージを使用して Jamf Pro構成プロファイルを作成する

1. 前のセクションから `WindowsDefenderATPOnboarding.plist` ファイルを探します。

   :::image type="content" source="images/plist-onboarding-file.png" alt-text="ATP Windows Defenderファイル" lightbox="images/plist-onboarding-file.png":::

2. Jamf にサインインしPro **ComputersConfiguration** >  プロファイルに移動し、[新規] を選択 **します**。

   :::image type="content" source="images/jamf-pro-configure-profile.png" alt-text="新しい Jamf ダッシュボードを作成するProページ" lightbox="images/jamf-pro-configure-profile.png":::

3. 次の詳細を入力します。

   **全般**:

   - 名前: macOS の MDE オンボーディング
   - 説明: mDE EDR macOS のオンボーディング
   - カテゴリ: なし
   - 配布方法: 自動的にインストールする
   - レベル: コンピューター レベル

4.  [アプリケーション] **ページに移動&、[** 設定追加] **をアップロード** > **します**。

   :::image type="content" source="images/jamfpro-mac-profile.png" alt-text="アプリとカスタム設定の構成" lightbox="images/jamfpro-mac-profile.png":::

5. [アップロード **ファイル (PLIST ファイル) を選択し、[基本設定ドメイン]** に **次を** 入力します。 `com.microsoft.wdav.atp`

   :::image type="content" source="images/jamfpro-plist-upload.png" alt-text="jamfpro plist アップロード ファイル" lightbox="images/jamfpro-plist-upload.png":::

   :::image type="content" source="images/jamfpro-plist-file.png" alt-text="アップロード ファイル プロパティ リスト ファイル" lightbox="images/jamfpro-plist-file.png":::

6. [開 **く] を** 選択し、オンボーディング ファイルを選択します。

   :::image type="content" source="images/jamfpro-plist-file-onboard.png" alt-text="オンボーディング ファイル" lightbox="images/jamfpro-plist-file-onboard.png":::

7. [アップロード] **を選択します**。

   :::image type="content" source="images/jamfpro-upload-plist.png" alt-text="plist ファイルのアップロード" lightbox="images/jamfpro-upload-plist.png":::

8. [スコープ] **タブを選択** します。

   :::image type="content" source="images/jamfpro-scope-tab.png" alt-text="[スコープ] タブ" lightbox="images/jamfpro-scope-tab.png":::

9. ターゲット コンピューターを選択します。

   :::image type="content" source="images/jamfpro-target-computer.png" alt-text="ターゲット コンピューター" lightbox="images/jamfpro-target-computer.png":::

   :::image type="content" source="images/jamfpro-targets.png" alt-text="ターゲット" lightbox="images/jamfpro-targets.png":::

10. **[保存]** を選択します。

   :::image type="content" source="images/jamfpro-deployment-target.png" alt-text="ターゲット コンピューターの展開" lightbox="images/jamfpro-deployment-target.png":::

   :::image type="content" source="images/jamfpro-target-selected.png" alt-text="ターゲット コンピューターの選択" lightbox="images/jamfpro-target-selected.png":::

11. [**完了**] を選択します。

    :::image type="content" source="images/jamfpro-target-group.png" alt-text="ターゲット グループのコンピューター" lightbox="images/jamfpro-target-group.png":::

    :::image type="content" source="images/jamfpro-configuration-policies.png" alt-text="構成プロファイルの一覧" lightbox="images/jamfpro-configuration-policies.png":::

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>手順 3: エンドポイントの Microsoft Defender の設定を構成する

JAMF Pro GUI を使用して、Microsoft Defender for Endpoint 構成の個々の設定を編集するか、テキスト エディターで構成 Plist を作成して JAMF Pro にアップロードすることで従来の方法を使用できます。

Preference ドメインとして正確に使用`com.microsoft.wdav`する必要があります。Microsoft Defender for Endpoint `com.microsoft.wdav.ext` では、この名前のみを使用し、管理設定を読み込む必要があります。

(GUI `com.microsoft.wdav.ext` メソッドを使用する場合はまれにバージョンを使用できますが、スキーマにまだ追加されていない設定を構成する必要があります)。

### <a name="gui-method"></a>GUI メソッド

1. Defender のリポジトリから schema.json ファイル[をGitHubローカル](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) ファイルに保存します。

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. [コンピューター- >構成プロファイル] の下に新しい構成プロファイルを作成し、[全般] タブで次の詳細 **を入力** します。

   :::image type="content" source="images/644e0f3af40c29e80ca1443535b2fe32.png" alt-text="新しいプロファイル" lightbox="images/644e0f3af40c29e80ca1443535b2fe32.png":::

    - 名前: MDATP MDAV 構成設定
    - 説明:\<blank\>
    - カテゴリ: なし (既定)
    - レベル: コンピューター レベル (既定)
    - 配布方法: 自動インストール (既定)

3. 下にスクロールして、[アプリケーション & カスタム 設定] タブまでスクロールし、[外部アプリケーション] **を** 選択し、[追加] をクリックし、[カスタム スキーマをソースとして使用] をクリックして、基本設定ドメインに使用します。

   :::image type="content" source="images/4137189bc3204bb09eed3aabc41afd78.png" alt-text="カスタム スキーマの追加" lightbox="images/4137189bc3204bb09eed3aabc41afd78.png":::

4. [基本`com.microsoft.wdav`設定ドメイン] として入力し、[スキーマの追加] をクリックアップロード手順 1 でダウンロードした schema.json ファイルを選択します。 **[保存]** をクリックします。

   :::image type="content" source="images/a6f9f556037c42fabcfdcb1b697244cf.png" alt-text="アップロードスキーマ" lightbox="images/a6f9f556037c42fabcfdcb1b697244cf.png":::

5. サポートされている Microsoft Defender for Endpoint 構成設定は、以下の [基本設定ドメインのプロパティ **] で確認できます**。 [ **プロパティの追加と削除]** をクリックして、管理する設定を選択し、[ **OK** ] をクリックして変更を保存します。 (設定選択されていない場合、エンド ユーザーはそれらの設定を自分のコンピューターで構成できます。

   :::image type="content" source="images/817b3b760d11467abe9bdd519513f54f.png" alt-text="選択した管理設定" lightbox="images/817b3b760d11467abe9bdd519513f54f.png":::

6. 設定の値を目的の値に変更します。 [詳細] **をクリックすると、** 特定の設定のドキュメントを取得できます。 ([ **Plist プレビュー] をクリックして** 、構成 plist の外観を確認できます。 [ **フォーム エディター] を** クリックしてビジュアル エディターに戻る)。

   :::image type="content" source="images/a14a79efd5c041bb8974cb5b12b3a9b6.png" alt-text="設定値を変更するページ" lightbox="images/a14a79efd5c041bb8974cb5b12b3a9b6.png":::

7. [スコープ] **タブを選択** します。

   :::image type="content" source="images/9fc17529e5577eefd773c658ec576a7d.png" alt-text="構成プロファイルのスコープ" lightbox="images/9fc17529e5577eefd773c658ec576a7d.png":::

8. [ **Contoso' s Machine Group] を選択します**。

9. [追加 **] を** 選択し、[保存] **を選択します**。

   :::image type="content" source="images/cf30438b5512ac89af1d11cbf35219a6.png" alt-text="構成設定を追加できるページ" lightbox="images/cf30438b5512ac89af1d11cbf35219a6.png":::

   :::image type="content" source="images/6f093e42856753a3955cab7ee14f12d9.png" alt-text="構成設定を保存できるページ" lightbox="images/6f093e42856753a3955cab7ee14f12d9.png":::

10. [**完了**] を選択します。 新しい構成プロファイルが **表示されます**。

    :::image type="content" source="images/dd55405106da0dfc2f50f8d4525b01c8.png" alt-text="構成設定を完了するページ" lightbox="images/dd55405106da0dfc2f50f8d4525b01c8.png":::

Microsoft Defender for Endpoint は、時間の間に新しい設定を追加します。 これらの新しい設定がスキーマに追加され、新しいバージョンが Github に発行されます。
更新を行う必要があるのは、更新されたスキーマのダウンロード、既存の構成プロファイルの編集、およびスキーマの編集を [アプリケーション の設定] タブ&**行** 設定です。

### <a name="legacy-method"></a>従来のメソッド

1. 次の Microsoft Defender for Endpoint 構成設定を使用します。

    - enableRealTimeProtection
    - passiveMode

    > [!NOTE]
    > 既定ではオンにされません。macOS 用にサードパーティの AV を実行する予定の場合は、 に設定します `true`。

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

     詳細については、「 [JAMF 完全構成プロファイルのプロパティ 一覧」を参照してください](mac-preferences.md#property-list-for-jamf-full-configuration-profile)。

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

2. ファイルをとして保存します `MDATP_MDAV_configuration_settings.plist`。

3. Jamf Proで、[コンピューター] と **[** 構成プロファイル **] を開きます**。 [新規 **] を** クリックし、[全般] タブ **に切り替** えます。

   :::image type="content" source="images/644e0f3af40c29e80ca1443535b2fe32.png" alt-text="新しいプロファイルを表示するページ" lightbox="images/644e0f3af40c29e80ca1443535b2fe32.png":::

4. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV 構成設定
    - 説明:\<blank\>
    - カテゴリ: なし (既定)
    - 配布方法: 自動インストール(既定)
    - Level: Computer Level(default)

    :::image type="content" source="images/3160906404bc5a2edf84d1d015894e3b.png" alt-text="MDATP MDAV 構成設定" lightbox="images/3160906404bc5a2edf84d1d015894e3b.png":::

5. [**アプリケーションとカスタム &] で、[設定** 構成] を **選択します**。

   :::image type="content" source="images/e1cc1e48ec9d5d688087b4d771e668d2.png" alt-text="アプリケーションとカスタム設定" lightbox="images/e1cc1e48ec9d5d688087b4d771e668d2.png":::

6. [ファイル **アップロード (PLIST ファイル) を選択します**。

   :::image type="content" source="images/6f85269276b2278eca4bce84f935f87b.png" alt-text="構成設定 plist ファイル" lightbox="images/6f85269276b2278eca4bce84f935f87b.png":::

7. [**基本設定ドメイン] で**、「PLIST `com.microsoft.wdav`ファイル」**と入力アップロード選択します**。

   :::image type="content" source="images/db15f147dd959e872a044184711d7d46.png" alt-text="構成設定の基本設定ドメイン" lightbox="images/db15f147dd959e872a044184711d7d46.png":::

8. [ファイル **の選択] を選択します**。

    :::image type="content" source="images/526e978761fc571cca06907da7b01fd6.png" alt-text="plist ファイルを選択するプロンプト" lightbox="images/526e978761fc571cca06907da7b01fd6.png":::

9. [ **MDATP_MDAV_configuration_settings.plist] を選択し、[** 開く] を **選択します**。

   :::image type="content" source="images/98acea3750113b8dbab334296e833003.png" alt-text="mdatpmdav 構成設定" lightbox="images/98acea3750113b8dbab334296e833003.png":::

10. [アップロード] **を選択します**。

    :::image type="content" source="images/0adb21c13206861ba9b30a879ade93d3.png" alt-text="構成設定のアップロード" lightbox="images/0adb21c13206861ba9b30a879ade93d3.png":::

    :::image type="content" source="images/f624de59b3cc86e3e2d32ae5de093e02.png" alt-text="構成設定に関連する画像をアップロードするプロンプト" lightbox="images/f624de59b3cc86e3e2d32ae5de093e02.png":::

    > [!NOTE]
    > Intune ファイルをアップロードすると、次のようなエラー メッセージが表示されます。
    >
    > :::image type="content" source="images/8e69f867664668796a3b2904896f0436.png" alt-text="構成設定に関連する intune ファイルをアップロードするプロンプト" lightbox="images/8e69f867664668796a3b2904896f0436.png":::

11. **[保存]** を選択します。

    :::image type="content" source="images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png" alt-text="構成設定に関連するイメージを保存するオプション" lightbox="images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png":::

12. ファイルがアップロードされます。

    :::image type="content" source="images/33e2b2a1611fdddf6b5b79e54496e3bb.png" alt-text="構成設定に関連するアップロードされたファイル" lightbox="images/33e2b2a1611fdddf6b5b79e54496e3bb.png":::

    :::image type="content" source="images/a422e57fe8d45689227e784443e51bd1.png" alt-text="[構成設定] ページ" lightbox="images/a422e57fe8d45689227e784443e51bd1.png":::

13. [スコープ] **タブを選択** します。

    :::image type="content" source="images/9fc17529e5577eefd773c658ec576a7d.png" alt-text="構成設定のスコープ" lightbox="images/9fc17529e5577eefd773c658ec576a7d.png":::

14. [ **Contoso' s Machine Group] を選択します**。

15. [追加 **] を** 選択し、[保存] **を選択します**。

    :::image type="content" source="images/cf30438b5512ac89af1d11cbf35219a6.png" alt-text="構成設定の addsav" lightbox="images/cf30438b5512ac89af1d11cbf35219a6.png":::

    :::image type="content" source="images/6f093e42856753a3955cab7ee14f12d9.png" alt-text="構成設定の通知" lightbox="images/6f093e42856753a3955cab7ee14f12d9.png":::

16. [**完了**] を選択します。 新しい構成プロファイルが **表示されます**。

    ![構成設定の構成プロファイル イメージのイメージ。](images/dd55405106da0dfc2f50f8d4525b01c8.png)
    :::image type="content" source="images/dd55405106da0dfc2f50f8d4525b01c8.png" alt-text="構成プロファイルの設定" lightbox="images/dd55405106da0dfc2f50f8d4525b01c8.png":::

## <a name="step-4-configure-notifications-settings"></a>手順 4: 通知の設定を構成する

これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。

1. Jamf Proで、[コンピューター **] 、[構成** プロファイル **] の順に選択します**。

2. [ **新規] を** クリックし、[オプション] に次の詳細を **入力します**。

    - タブ **全般**:
        - **名前**: MDATP MDAV 通知の設定
        - **説明**: macOS 10.15 (Catalina) 以降
        - **カテゴリ**: なし *(既定)*
        - **配布方法**: 自動インストール *(既定)*
        - **レベル**: コンピューター レベル *(既定)*

        :::image type="content" source="images/c9820a5ff84aaf21635c04a23a97ca93.png" alt-text="新しい macOS 構成プロファイル ページ" lightbox="images/c9820a5ff84aaf21635c04a23a97ca93.png":::

    - [タブ **通知**] をクリック **し、[追加**] をクリックし、次の値を入力します。
        - **バンドル ID**: `com.microsoft.wdav.tray`
        - **重大な通知**: [無効にする] **をクリックします。**
        - **通知**: [有効にする] **をクリックします。**
        - **バナー通知の種類**: [含める] **と [一時**] *(既定) を選択します。* 
        - **ロック画面の通知: [** 非表示] **をクリックします。**
        - **通知センターの通知: [** 表示] を **クリックします。**
        - **バッジ アプリのアイコン:** [表示] **をクリックします。**

        :::image type="content" source="images/7f9138053dbcbf928e5182ee7b295ebe.png" alt-text="構成設定 mdatpmdav 通知トレイ" lightbox="images/7f9138053dbcbf928e5182ee7b295ebe.png":::

    - [**タブ通知**] で、[**もう 1** 回追加] をクリックし、[新しい通知] ウィンドウまで **下にスクロール設定**
        - **バンドル ID**: `com.microsoft.autoupdate2`
        - 残りの設定を上記と同じ値に構成する

        :::image type="content" source="images/4bac6ce277aedfb4a674f2d9fcb2599a.png" alt-text="構成設定 mdatpmdav 通知 mau" lightbox="images/4bac6ce277aedfb4a674f2d9fcb2599a.png":::

        通知構成が 2 つの 「テーブル」 に追加され、もう 1 つはバンドル **ID :com.microsoft.wdav.tray**、もう 1 つはバンドル **ID: com.microsoft.autoupdate2** です。 要件ごとにアラート設定を構成することもできますが、バンドル ID は前の説明とまったく同じにする必要があります。 **Include スイッチは** 通知に対して **[オン] にする** 必要 **があります**。

3. [スコープ] **タブを選択** し、[追加] を **選択します**。

   :::image type="content" source="images/441aa2ecd36abadcdd8aed03556080b5.png" alt-text="構成設定の値を追加できるページ" lightbox="images/441aa2ecd36abadcdd8aed03556080b5.png":::

4. [ **Contoso' s Machine Group] を選択します**。

5. [追加 **] を** 選択し、[保存] **を選択します**。

   :::image type="content" source="images/09a275e321268e5e3ac0c0865d3e2db5.png" alt-text="構成設定 contoso マシン グループの値を保存できるページ" lightbox="images/09a275e321268e5e3ac0c0865d3e2db5.png":::

   :::image type="content" source="images/4d2d1d4ee13d3f840f425924c3df0d51.png" alt-text="構成設定の完了通知を表示するページ" lightbox="images/4d2d1d4ee13d3f840f425924c3df0d51.png":::

6. [**完了**] を選択します。 新しい構成プロファイルが **表示されます**。

   :::image type="content" source="images/633ad26b8bf24ec683c98b2feb884bdf.png" alt-text="完了した構成設定" lightbox="images/633ad26b8bf24ec683c98b2feb884bdf.png":::

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

2. として保存します `MDATP_MDAV_MAU_settings.plist`。

3. Jamf ダッシュボードPro[全般] を **選択します**。

   :::image type="content" source="images/eaba2a23dd34f73bf59e826217ba6f15.png" alt-text="構成設定" lightbox="images/eaba2a23dd34f73bf59e826217ba6f15.png":::

4. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV MAU の設定
    - 説明: MacOS 用 MDATP の Microsoft AutoUpdate 設定
    - カテゴリ: なし (既定)
    - 配布方法: 自動インストール(既定)
    - Level: Computer Level(default)

5. [**アプリケーションとカスタム &] で、[設定** 構成] を **選択します**。

   :::image type="content" source="images/1f72e9c15eaafcabf1504397e99be311.png" alt-text="構成設定アプリケーションとカスタム設定" lightbox="images/1f72e9c15eaafcabf1504397e99be311.png":::

6. [ファイル **アップロード (PLIST ファイル) を選択します**。

7. [**基本設定ドメイン]** に「:`com.microsoft.autoupdate2`」と入力し、[**PLIST ファイルアップロード選択します**。

   :::image type="content" source="images/1213872db5833aa8be535da57653219f.png" alt-text="構成設定の基本設定ドメイン" lightbox="images/1213872db5833aa8be535da57653219f.png":::
    

8. [ファイル **の選択] を選択します**。

   :::image type="content" source="images/335aff58950ce62d1dabc289ecdce9ed.png" alt-text="構成設定に関するファイルを選択するプロンプト" lightbox="images/335aff58950ce62d1dabc289ecdce9ed.png":::

9. [ **MDATP_MDAV_MAU_settings.plist] を選択します**。

   :::image type="content" source="images/a26bd4967cd54bb113a2c8d32894c3de.png" alt-text="mdatpmdavmau の設定" lightbox="images/a26bd4967cd54bb113a2c8d32894c3de.png":::

10. [アップロード] **を選択します**。
    :::image type="content" source="images/4239ca0528efb0734e4ca0b490bfb22d.png" alt-text="構成設定に関するファイルのアップロード" lightbox="images/4239ca0528efb0734e4ca0b490bfb22d.png":::

    :::image type="content" source="images/4ec20e72c8aed9a4c16912e01692436a.png" alt-text="構成設定に関するファイルのアップロード オプションを表示するページ" lightbox="images/4ec20e72c8aed9a4c16912e01692436a.png":::

11. **[保存]** を選択します。

    :::image type="content" source="images/253274b33e74f3f5b8d475cf8692ce4e.png" alt-text="構成設定に関するファイルの保存オプションを表示するページ" lightbox="images/253274b33e74f3f5b8d475cf8692ce4e.png":::

12. [スコープ] **タブを選択** します。

    :::image type="content" source="images/10ab98358b2d602f3f67618735fa82fb.png" alt-text="構成設定の [スコープ] タブ" lightbox="images/10ab98358b2d602f3f67618735fa82fb.png":::

13. **[追加]** を選択します。

    :::image type="content" source="images/56e6f6259b9ce3c1706ed8d666ae4947.png" alt-text="展開ターゲットを追加するオプション" lightbox="images/56e6f6259b9ce3c1706ed8d666ae4947.png":::

    :::image type="content" source="images/38c67ee1905c4747c3b26c8eba57726b.png" alt-text="構成設定に値を追加するページ" lightbox="images/38c67ee1905c4747c3b26c8eba57726b.png":::

    :::image type="content" source="images/321ba245f14743c1d5d51c15e99deecc.png" alt-text="構成設定に値を追加できるページ" lightbox="images/321ba245f14743c1d5d51c15e99deecc.png":::

14. [**完了**] を選択します。

    :::image type="content" source="images/ba44cdb77e4781aa8b940fb83e3c21f7.png" alt-text="構成設定に関する完了通知" lightbox="images/ba44cdb77e4781aa8b940fb83e3c21f7.png":::

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>手順 6: エンドポイント用 Microsoft Defender へのフル ディスク アクセスを許可する

1. Jamf の [Pro] ダッシュボードで、[**構成プロファイル] を選択します**。

   :::image type="content" source="images/264493cd01e62c7085659d6fdc26dc91.png" alt-text="設定を構成するプロファイル" lightbox="images/264493cd01e62c7085659d6fdc26dc91.png":::

2. [ **+ 新規] を選択します**。

3. 次の詳細を入力します。

    **全般**
    - 名前: MDATP MDAV - ディスクおよび AV へのフル ディスク アクセスEDR付与する
    - 説明: macOS Catalina 以降では、新しいプライバシー設定ポリシーコントロール
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    :::image type="content" source="images/ba3d40399e1a6d09214ecbb2b341923f.png" alt-text="構成設定全般" lightbox="images/ba3d40399e1a6d09214ecbb2b341923f.png":::
    

4. [プライバシー **設定の構成] ポリシーコントロールで、[構成** ] を **選択します**。

   :::image type="content" source="images/715ae7ec8d6a262c489f94d14e1e51bb.png" alt-text="構成のプライバシー ポリシー制御" lightbox="images/715ae7ec8d6a262c489f94d14e1e51bb.png":::

5. [ **プライバシー設定ポリシー制御] で、** 次の詳細を入力します。

    - 識別子: `com.microsoft.wdav`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

    :::image type="content" source="images/22cb439de958101c0a12f3038f905b27.png" alt-text="構成設定のプライバシー設定ポリシー制御の詳細" lightbox="images/22cb439de958101c0a12f3038f905b27.png":::

6. **[+ 追加]** を選択します。

   :::image type="content" source="images/bd93e78b74c2660a0541af4690dd9485.png" alt-text="[構成設定] [システム ポリシーのすべてのファイルの追加] オプション" lightbox="images/bd93e78b74c2660a0541af4690dd9485.png":::

    - [アプリまたはサービス] で、 **SystemPolicyAllFiles に設定する**

    - [アクセス] の下: [許可] に **設定します。**

7. [ **保存]** を選択します (右下の保存は選択しない)。

   :::image type="content" source="images/6de50b4a897408ddc6ded56a09c09fe2.png" alt-text="構成設定の保存操作" lightbox="images/6de50b4a897408ddc6ded56a09c09fe2.png":::

8. [アプリ アクセス] `+` の横にある **記号をクリックして** 、新しいエントリを追加します。

   :::image type="content" source="images/tcc-add-entry.png" alt-text="構成設定に関連する保存操作" lightbox="images/tcc-add-entry.png":::

9. 次の詳細を入力します。

    - 識別子: `com.microsoft.wdav.epsext`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. **[+ 追加]** を選択します。

    :::image type="content" source="images/tcc-epsext-entry.png" alt-text="構成設定 tcc epsext エントリ" lightbox="images/tcc-epsext-entry.png":::

    - [アプリまたはサービス] で、 **SystemPolicyAllFiles に設定する**

    - [アクセス] の下: [許可] に **設定します。**

11. [ **保存]** を選択します (右下の保存は選択しない)。

    :::image type="content" source="images/tcc-epsext-entry2.png" alt-text="構成設定 tcc epsext の他のインスタンス" lightbox="images/tcc-epsext-entry2.png":::

12. [スコープ] **タブを選択** します。

    :::image type="content" source="images/2c49b16cd112729b3719724f581e6882.png" alt-text="構成設定の範囲を示すページ" lightbox="images/2c49b16cd112729b3719724f581e6882.png":::

13. **[+ 追加]** を選択します。

    :::image type="content" source="images/57cef926d1b9260fb74a5f460cee887a.png" alt-text="構成設定を示すページ" lightbox="images/57cef926d1b9260fb74a5f460cee887a.png":::

14. [ **グループ名]** > [コンピューター グループ] **>** **Contoso の MachineGroup を選択します**。

    :::image type="content" source="images/368d35b3d6179af92ffdbfd93b226b69.png" alt-text="contoso コンピューター グループの構成設定" lightbox="images/368d35b3d6179af92ffdbfd93b226b69.png":::

15. **[追加]** を選択します。

16. **[保存]** を選択します。

17. [**完了**] を選択します。

    :::image type="content" source="images/809cef630281b64b8f07f20913b0039b.png" alt-text="contoso machine-group の構成設定" lightbox="images/809cef630281b64b8f07f20913b0039b.png":::

    :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="構成設定の図" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

または、「Jamf を使用したカスタム構成プロファイルの展開」の説明に従って、[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) をダウンロードして JAMF 構成プロファイルに[アップロードPro|方法 2: アップロードプロファイルを Jamf ファイルにPro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>手順 7: Microsoft Defender for Endpoint のカーネル拡張機能を承認する

> [!CAUTION]
> Apple Silicon (M1) デバイスは KEXT をサポートしていない。 KEXT ポリシーからなる構成プロファイルのインストールは、これらのデバイスで失敗します。

1. [構成プロファイル **] で、[+** 新規] **を選択します**。

   :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="ソーシャル メディア投稿の説明が自動的に生成される" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

2. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV カーネル拡張機能
    - 説明: MDATP カーネル拡張機能 (kext)
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    :::image type="content" source="images/24e290f5fc309932cf41f3a280d22c14.png" alt-text="構成設定 mdatpmdav カーネル" lightbox="images/24e290f5fc309932cf41f3a280d22c14.png":::

3. [承認済 **みカーネル拡張機能の構成] で、[構成** ] を **選択します**。

   :::image type="content" source="images/30be88b63abc5e8dde11b73f1b1ade6a.png" alt-text="構成設定の承認済みカーネル拡張機能を表示するページ" lightbox="images/30be88b63abc5e8dde11b73f1b1ade6a.png":::

4. [ **承認済みカーネル拡張機能] で、** 次の詳細を入力します。

    - 表示名: Microsoft Corp.
    - チーム ID: UBF8T346G9

    :::image type="content" source="images/39cf120d3ac3652292d8d1b6d057bd60.png" alt-text="[承認済みカーネル拡張機能] ウィンドウ" lightbox="images/39cf120d3ac3652292d8d1b6d057bd60.png":::

5. [スコープ] **タブを選択** します。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="構成の [スコープ] タブ" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

6. **[+ 追加]** を選択します。

7. [ **グループ名]** **> [コンピューター** グループ] を選択> **Contoso の [コンピューター グループ] を選択します**。

8. **[+ 追加]** を選択します。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="構成設定の追加の値を定義するページ" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

9. **[保存]** を選択します。

   :::image type="content" source="images/0add8019b85a453b47fa5c402c72761b.png" alt-text="MDATP MDAV カーネル拡張機能" lightbox="images/0add8019b85a453b47fa5c402c72761b.png":::

10. [**完了**] を選択します。

    :::image type="content" source="images/1c9bd3f68db20b80193dac18f33c22d0.png" alt-text="[構成プロファイルの詳細] ページ" lightbox="images/1c9bd3f68db20b80193dac18f33c22d0.png":::

または、「Jamf を使用したカスタム構成プロファイルの展開」の説明に従って[、kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) をダウンロードして JAMF 構成プロファイルに[アップロードPro|方法 2: アップロードプロファイルを Jamf ファイルにPro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>手順 8: エンドポイント用 Microsoft Defender のシステム拡張機能を承認する

1. [構成プロファイル **] で、[+** 新規] **を選択します**。

   :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="自動的に生成されたソーシャル メディア投稿の説明" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

2. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV システム拡張機能
    - 説明: MDATP システム拡張機能
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    :::image type="content" source="images/sysext-new-profile.png" alt-text="構成設定 sysext 新しいプロファイル" lightbox="images/sysext-new-profile.png":::

3. [ **システム拡張機能] で、[構成** ] を **選択します**。

   :::image type="content" source="images/sysext-configure.png" alt-text="システム拡張機能の [構成] オプションを含むウィンドウ" lightbox="images/sysext-configure.png":::

4. [ **System Extensions] に次** の詳細を入力します。

   - 表示名: Microsoft Corp. System Extensions
   - システム拡張の種類: 許可されているシステム拡張機能
   - チーム識別子: UBF8T346G9
   - 許可されるシステム拡張機能:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    :::image type="content" source="images/sysext-configure2.png" alt-text="[MDATP MDAV システム拡張機能] ウィンドウ" lightbox="images/sysext-configure2.png":::

5. [スコープ] **タブを選択** します。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="[ターゲット コンピューター] 選択ウィンドウ" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

6. **[+ 追加]** を選択します。

7. [ **グループ名]** **> [コンピューター** グループ] を選択> **Contoso の [コンピューター グループ] を選択します**。

8. **[+ 追加]** を選択します。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="[新しい macOS 構成プロファイル] ウィンドウ" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

9. **[保存]** を選択します。

   :::image type="content" source="images/sysext-scope.png" alt-text="MDATP MDAV システム拡張機能に関するオプションの表示" lightbox="images/sysext-scope.png":::

10. [**完了**] を選択します。

    :::image type="content" source="images/sysext-final.png" alt-text="構成設定 sysext - final" lightbox="images/sysext-final.png":::

## <a name="step-9-configure-network-extension"></a>手順 9: ネットワーク拡張機能を構成する

エンドポイント検出および応答機能の一環として、macOS 上の Microsoft Defender for Endpoint はソケット トラフィックを検査し、この情報をポータルMicrosoft 365 Defenderします。 次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。

これらの手順は、macOS 10.15 (Catalina) 以降に適用できます。

1. Jamf Proで、[コンピューター **] 、[構成** プロファイル **] の順に選択します**。

2. [ **新規] を** クリックし、[オプション] に次の詳細を **入力します**。

    - タブ **全般**:
        - **名前**: Microsoft Defender Network Extension
        - **説明**: macOS 10.15 (Catalina) 以降
        - **カテゴリ**: なし *(既定)*
        - **配布方法**: 自動インストール *(既定)*
        - **レベル**: コンピューター レベル *(既定)*

    - タブ **コンテンツ フィルター**:
        - **フィルター名**: Microsoft Defender コンテンツ フィルター
        - **識別子**: `com.microsoft.wdav`
        - サービス **アドレス、組織****、ユーザー****名**、**パスワード**、**証明書** を空白のままにする (**Include** *は* 選択されません)
        - **フィルターの順序**: Inspector
        - **ソケット フィルター**: `com.microsoft.wdav.netext`
        - **ソケット フィルター指定要件**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - [**ネットワーク フィルター] フィールド** は空白のままにします (**[含***める] は* 選択されません)

        識別子、 **ソケット** フィルター **、ソケット フィルター** は、上記 **で指定した要件の** 正確な値を指定します。

        :::image type="content" source="images/netext-create-profile.png" alt-text="mdatpmdav 構成設定" lightbox="images/netext-create-profile.png":::

3. [スコープ] **タブを選択** します。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="[構成設定] [sco] タブ" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

4. **[+ 追加]** を選択します。

5. [ **グループ名]** **> [コンピューター** グループ] を選択> **Contoso の [コンピューター グループ] を選択します**。

6. **[+ 追加]** を選択します。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="構成設定 adim" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

7. **[保存]** を選択します。

   :::image type="content" source="images/netext-scope.png" alt-text="[コンテンツ フィルター] ウィンドウ" lightbox="images/netext-scope.png":::

8. [**完了**] を選択します。

   :::image type="content" source="images/netext-final.png" alt-text="構成設定 netext - final" lightbox="images/netext-final.png":::

または、「Jamf を使用したカスタム構成プロファイルの展開」の説明に従って、[netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) をダウンロードして JAMF 構成プロファイル[にアップロードPro|方法 2: アップロードプロファイルを Jamf ファイルにPro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>手順 10: macOS で Microsoft Defender for Endpoint でスキャンをスケジュールする

[macOS の Microsoft Defender for Endpoint でスキャンをスケジュールするの手順に従います](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>手順 11: macOS に Microsoft Defender for Endpoint を展開する

1. 保存した場所に移動します `wdav.pkg`。

   :::image type="content" source="images/8dde76b5463047423f8637c86b05c29d.png" alt-text="エクスプローラー wdav パッケージ" lightbox="images/8dde76b5463047423f8637c86b05c29d.png":::

2. に名前を変更します `wdav_MDM_Contoso_200329.pkg`。

   :::image type="content" source="images/fb2220fed3a530f4b3ef36f600da0c27.png" alt-text="エクスプローラー 1 wdavmdm パッケージ" lightbox="images/fb2220fed3a530f4b3ef36f600da0c27.png":::

3. Jamf ダッシュボードをProします。

   :::image type="content" source="images/990742cd9a15ca9fdd37c9f695d1b9f4.png" alt-text="jamfpro の構成設定" lightbox="images/990742cd9a15ca9fdd37c9f695d1b9f4.png":::

4. コンピューターを選択し、上部にある歯車アイコンをクリックし、[コンピューターの管理] **を選択します**。

   :::image type="content" source="images/b6d671b2f18b89d96c1c8e2ea1991242.png" alt-text="構成設定 - コンピューターの管理" lightbox="images/b6d671b2f18b89d96c1c8e2ea1991242.png":::

5. [パッケージ **] で**、[+ **新規] を選択します**。
   :::image type="content" source="images/57aa4d21e2ccc65466bf284701d4e961.png" alt-text="自動生成されたパッケージの鳥の説明" lightbox="images/57aa4d21e2ccc65466bf284701d4e961.png":::

6. [ **新しいパッケージ]** で、次の詳細を入力します。

    **[全般] タブ**
    - 表示名: 空白のままにしておきます。 pkg を選択するとリセットされます。
    - カテゴリ: なし (既定)
    - ファイル名: [ファイル] を選択します。

    :::image type="content" source="images/21de3658bf58b1b767a17358a3f06341.png" alt-text="構成設定の [全般] タブ" lightbox="images/21de3658bf58b1b767a17358a3f06341.png":::

    ファイルを開き、またはをポイント `wdav.pkg` します `wdav_MDM_Contoso_200329.pkg`。

    :::image type="content" source="images/1aa5aaa0a387f4e16ce55b66facc77d1.png" alt-text="自動生成されたパッケージの説明を表示するコンピューター画面" lightbox="images/1aa5aaa0a387f4e16ce55b66facc77d1.png":::

7. [**開く**]を選択します。 [表示名 **] を** **[Microsoft Defender Advanced Threat Protection] に設定し**、Microsoft Defender ウイルス対策。

    **マニフェスト ファイル** は必須ではありません。 Microsoft Defender for Endpoint はマニフェスト ファイルなしで動作します。

    **[オプション] タブ**: 既定値を保持します。

    **[制限] タブ**: 既定値を保持します。

    :::image type="content" source="images/56dac54634d13b2d3948ab50e8d3ef21.png" alt-text="構成設定の [制限] タブ" lightbox="images/56dac54634d13b2d3948ab50e8d3ef21.png":::

8. **[保存]** を選択します。 パッケージは Jamf ファイルにアップロードPro。

   :::image type="content" source="images/33f1ecdc7d4872555418bbc3efe4b7a3.png" alt-text="構成設定に関連するパッケージの構成設定パックのアップロード プロセス" lightbox="images/33f1ecdc7d4872555418bbc3efe4b7a3.png":::

   パッケージを展開に使用するには数分かかる場合があります。

   :::image type="content" source="images/1626d138e6309c6e87bfaab64f5ccf7b.png" alt-text="構成設定用にパッケージをアップロードするインスタンス" lightbox="images/1626d138e6309c6e87bfaab64f5ccf7b.png":::

9. [ポリシー] **ページに移動** します。

   :::image type="content" source="images/f878f8efa5ebc92d069f4b8f79f62c7f.png" alt-text="構成設定ポリシー" lightbox="images/f878f8efa5ebc92d069f4b8f79f62c7f.png":::

10. [ **+ 新規] を** 選択して新しいポリシーを作成します。

    :::image type="content" source="images/847b70e54ed04787e415f5180414b310.png" alt-text="構成設定の新しいポリシー" lightbox="images/847b70e54ed04787e415f5180414b310.png":::


11. [ **全般]** 次の詳細を入力します。

    - 表示名: MDATP Onboarding Contoso 200329 v100.86.92 以降

      :::image type="content" source="images/625ba6d19e8597f05e4907298a454d28.png" alt-text="構成設定 - MDATP オンボード" lightbox="images/625ba6d19e8597f05e4907298a454d28.png":::

12. [ **定期的なチェックイン] を選択します**。

    :::image type="content" source="images/68bdbc5754dfc80aa1a024dde0fce7b0.png" alt-text="構成設定の定期的なチェックイン" lightbox="images/68bdbc5754dfc80aa1a024dde0fce7b0.png":::

13. **[保存]** を選択します。

14. [パッケージ **] を選択>構成します**。

    :::image type="content" source="images/8fb4cc03721e1efb4a15867d5241ebfb.png" alt-text="パッケージを構成するオプション" lightbox="images/8fb4cc03721e1efb4a15867d5241ebfb.png":::

15. [Microsoft **Defender Advanced Threat** Protection] の横にある [追加 **] ボタンを選択し、Microsoft Defender ウイルス対策**。

    :::image type="content" source="images/526b83fbdbb31265b3d0c1e5fbbdc33a.png" alt-text="MDATP MDA に設定を追加するオプション" lightbox="images/526b83fbdbb31265b3d0c1e5fbbdc33a.png":::

16. **[保存]** を選択します。

    :::image type="content" source="images/9d6e5386e652e00715ff348af72671c6.png" alt-text="構成設定の保存オプション" lightbox="images/9d6e5386e652e00715ff348af72671c6.png":::

17. [スコープ] **タブを選択** します。

    :::image type="content" source="images/8d80fe378a31143db9be0bacf7ddc5a3.png" alt-text="構成設定に関連する [スコープ] タブ" lightbox="images/8d80fe378a31143db9be0bacf7ddc5a3.png":::

18. ターゲット コンピューターを選択します。

    :::image type="content" source="images/6eda18a64a660fa149575454e54e7156.png" alt-text="コンピューター グループを追加するオプション" lightbox="images/6eda18a64a660fa149575454e54e7156.png":::

    **スコープ**

    **[追加]** を選択します。

    :::image type="content" source="images/1c08d097829863778d562c10c5f92b67.png" alt-text="構成設定 - ad1" lightbox="images/1c08d097829863778d562c10c5f92b67.png":::

    :::image type="content" source="images/216253cbfb6ae738b9f13496b9c799fd.png" alt-text="構成設定 - ad2" lightbox="images/216253cbfb6ae738b9f13496b9c799fd.png":::

    **セルフサービス**

    :::image type="content" source="images/c9f85bba3e96d627fe00fc5a8363b83a.png" alt-text="構成設定の [セルフサービス] タブ" lightbox="images/c9f85bba3e96d627fe00fc5a8363b83a.png":::

19. [**完了**] を選択します。

    :::image type="content" source="images/99679a7835b0d27d0a222bc3fdaf7f3b.png" alt-text="Contoso のオンボーディングの状態と、それを完了するオプション" lightbox="images/99679a7835b0d27d0a222bc3fdaf7f3b.png":::

    :::image type="content" source="images/632aaab79ae18d0d2b8e0c16b6ba39e2.png" alt-text="[ポリシー] ページ" lightbox="images/632aaab79ae18d0d2b8e0c16b6ba39e2.png":::
