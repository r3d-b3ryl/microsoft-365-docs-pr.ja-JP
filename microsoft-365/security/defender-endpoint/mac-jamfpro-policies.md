---
title: Jamf Pro で macOS ポリシーのMicrosoft Defender for Endpointを設定する
description: Jamf Proで macOS ポリシーでMicrosoft Defender for Endpointを設定する方法について説明します
keywords: ポリシー, microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 8d248eef175da6de3e329b4ec9b75b1111c668a6
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824720"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Jamf Pro で macOS ポリシーのMicrosoft Defender for Endpointを設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Mac 上の Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

このページでは、Jamf Proで macOS ポリシーを設定するために必要な手順について説明します。

次の手順を実行する必要があります。

1. [Microsoft Defender for Endpointオンボード パッケージを取得する](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)
2. [オンボード パッケージを使用して Jamf Proで構成プロファイルを作成する](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)
3. [Microsoft Defender for Endpoint設定を構成する](#step-3-configure-microsoft-defender-for-endpoint-settings)
4. [Microsoft Defender for Endpoint通知設定を構成する](#step-4-configure-notifications-settings)
5. [Microsoft AutoUpdate (MAU) の構成](#step-5-configure-microsoft-autoupdate-mau)
6. [Microsoft Defender for Endpointへのフル ディスク アクセスを許可する](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)
7. [Microsoft Defender for Endpointのカーネル拡張機能を承認する](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)
8. [Microsoft Defender for Endpointのシステム拡張機能を承認する](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)
9. [ネットワーク拡張機能を構成する](#step-9-configure-network-extension)
10. [macOS でMicrosoft Defender for Endpointを使用してスキャンをスケジュールする](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)
11. [macOS にMicrosoft Defender for Endpointを展開する](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)

## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>手順 1: Microsoft Defender for Endpointオンボード パッケージを取得する

1. [Microsoft 365 Defender](https://security.microsoft.com)で、**設定 > エンドポイント>オンボード** に移動します。

2. オペレーティング システムとして macOS を選択し、展開方法として Mobile デバイス管理/Microsoft Intuneを選択します。

   :::image type="content" source="images/onboarding-macos.png" alt-text="Microsoft Defender セキュリティ センターの [設定] ページ" lightbox="images/onboarding-macos.png":::

3. [ **オンボード パッケージのダウンロード** (WindowsDefenderATPOnboardingPackage.zip)] を選択します。

4. 抽出 `WindowsDefenderATPOnboardingPackage.zip`.

5. ファイルを任意の場所にコピーします。 たとえば、「 `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist` 」のように入力します。

## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>手順 2: オンボード パッケージを使用して Jamf Proで構成プロファイルを作成する

1. 前のセクションからファイル `WindowsDefenderATPOnboarding.plist` を見つけます。

   :::image type="content" source="images/plist-onboarding-file.png" alt-text="Windows Defender ATP オンボード ファイル" lightbox="images/plist-onboarding-file.png":::

2. Jamf Proにサインインし、**ComputersConfiguration** >  プロファイルに移動して、[**新規**] を選択します。

   :::image type="content" source="images/jamf-pro-configure-profile.png" alt-text="新しい Jamf Pro ダッシュボードを作成するページ" lightbox="images/jamf-pro-configure-profile.png":::

3. 次の詳細を入力します。

   **全般**:

   - 名前: macOS の MDE オンボード
   - 説明: macOS の MDE EDRオンボード
   - カテゴリ: なし
   - 配布方法: 自動的にインストールする
   - レベル: コンピューター レベル

4.  **[アプリケーション & カスタム 設定**] ページに移動し、**アップロード** > **Add** を選択します。

   :::image type="content" source="images/jamfpro-mac-profile.png" alt-text="構成されたアプリとカスタム設定" lightbox="images/jamfpro-mac-profile.png":::

5. **[アップロード ファイル (PLIST ファイル)** を選択し、**基本設定ドメイン** で次のように入力します`com.microsoft.wdav.atp`。

   :::image type="content" source="images/jamfpro-plist-upload.png" alt-text="jamfpro plist アップロード ファイル" lightbox="images/jamfpro-plist-upload.png":::

   :::image type="content" source="images/jamfpro-plist-file.png" alt-text="アップロード ファイル プロパティリスト ファイル" lightbox="images/jamfpro-plist-file.png":::

6. **[開く**] を選択し、オンボード ファイルを選択します。

   :::image type="content" source="images/jamfpro-plist-file-onboard.png" alt-text="オンボード ファイル" lightbox="images/jamfpro-plist-file-onboard.png":::

7. [**アップロード**] を選択します。

   :::image type="content" source="images/jamfpro-upload-plist.png" alt-text="アップロードする plist ファイル" lightbox="images/jamfpro-upload-plist.png":::

8. [ **スコープ** ] タブを選択します。

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

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>手順 3: Microsoft Defender for Endpoint設定を構成する

JAMF Pro GUI を使用してMicrosoft Defender for Endpoint構成の個々の設定を編集するか、テキスト エディターで構成 Plist を作成し、JAMF Proにアップロードしてレガシ メソッドを使用できます。

**ユーザー設定ドメイン** とまったく同じように`com.microsoft.wdav`使用する必要があることに注意してください。Microsoft Defender for Endpointこの名前のみを使用し、`com.microsoft.wdav.ext`管理設定を読み込みます。

(このバージョンは `com.microsoft.wdav.ext` 、GUI メソッドを使用する場合にまれに使用される場合がありますが、スキーマにまだ追加されていない設定も構成する必要があります)。

### <a name="gui-method"></a>GUI メソッド

1. [Defender のGitHub リポジトリ](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema)から schema.json ファイルをダウンロードし、ローカル ファイルに保存します。

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. [コンピューター- >構成プロファイル] で新しい構成プロファイルを作成し、[ **全般** ] タブに次の詳細を入力します。

   :::image type="content" source="images/644e0f3af40c29e80ca1443535b2fe32.png" alt-text="新しいプロファイル" lightbox="images/644e0f3af40c29e80ca1443535b2fe32.png":::

    - 名前: MDATP MDAV 構成設定
    - 説明：\<blank\>
    - カテゴリ: なし (既定)
    - レベル: コンピューター レベル (既定)
    - 配布方法: 自動インストール (既定)

3. **[アプリケーション & カスタム 設定**] タブまで下にスクロールし、[**外部アプリケーション**] を選択し、[**追加**] をクリックし、[**カスタム スキーマ** をソースとして使用] をクリックして、基本設定ドメインに使用します。

   :::image type="content" source="images/4137189bc3204bb09eed3aabc41afd78.png" alt-text="カスタム スキーマを追加する" lightbox="images/4137189bc3204bb09eed3aabc41afd78.png":::

4. 基本設定ドメインとして入力`com.microsoft.wdav`し、[スキーマの **追加]** をクリックし、手順 1 でダウンロードした schema.json ファイルを **アップロード** します。 **[保存]** をクリックします。

   :::image type="content" source="images/a6f9f556037c42fabcfdcb1b697244cf.png" alt-text="アップロード スキーマ" lightbox="images/a6f9f556037c42fabcfdcb1b697244cf.png":::

5. サポートされているすべてのMicrosoft Defender for Endpoint構成設定は、[**基本設定ドメインのプロパティ]** で確認できます。 [ **プロパティの追加と削除]** をクリックして管理する設定を選択し、[ **OK]** をクリックして変更を保存します。 (設定未選択のままでは、マネージド構成に含まれません。エンド ユーザーは、それらの設定を自分のマシンで構成できるようになります)。

   :::image type="content" source="images/817b3b760d11467abe9bdd519513f54f.png" alt-text="選択した管理設定" lightbox="images/817b3b760d11467abe9bdd519513f54f.png":::

6. 設定の値を目的の値に変更します。 [ **詳細情報** ] をクリックすると、特定の設定のドキュメントを取得できます。 ( **Plist プレビュー** をクリックして、構成 plist の外観を調べることができます。 **[フォーム エディター]** をクリックしてビジュアル エディターに戻ります)。

   :::image type="content" source="images/a14a79efd5c041bb8974cb5b12b3a9b6.png" alt-text="設定値を変更するページ" lightbox="images/a14a79efd5c041bb8974cb5b12b3a9b6.png":::

7. [ **スコープ** ] タブを選択します。

   :::image type="content" source="images/9fc17529e5577eefd773c658ec576a7d.png" alt-text="構成プロファイルスコープ" lightbox="images/9fc17529e5577eefd773c658ec576a7d.png":::

8. **Contoso のマシン グループを選択します**。

9. [ **追加]** を選択し、[保存] を選択 **します**。

   :::image type="content" source="images/cf30438b5512ac89af1d11cbf35219a6.png" alt-text="構成設定を追加できるページ" lightbox="images/cf30438b5512ac89af1d11cbf35219a6.png":::

   :::image type="content" source="images/6f093e42856753a3955cab7ee14f12d9.png" alt-text="構成設定を保存できるページ" lightbox="images/6f093e42856753a3955cab7ee14f12d9.png":::

10. [**完了**] を選択します。 新しい **構成プロファイル** が表示されます。

    :::image type="content" source="images/dd55405106da0dfc2f50f8d4525b01c8.png" alt-text="構成設定を完了するページ" lightbox="images/dd55405106da0dfc2f50f8d4525b01c8.png":::

Microsoft Defender for Endpoint時間の経過と共に新しい設定が追加されます。 これらの新しい設定がスキーマに追加され、新しいバージョンが Github に発行されます。
更新を行うには、[**アプリケーション &カスタム** 設定] タブで、更新されたスキーマのダウンロード、既存の構成プロファイルの **編集、スキーマの編集** を行う必要があります。

### <a name="legacy-method"></a>レガシ メソッド

1. 次のMicrosoft Defender for Endpoint構成設定を使用します。

    - enableRealTimeProtection
    - passiveMode

    > [!NOTE]
    > macOS 用のサード パーティ製の AV を実行する予定の場合は、既定ではオンになっていない場合は、次のように `true`設定します。

    - 除外
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats

    > [!NOTE]
    > EICAR はサンプルに含まれています。概念実証を実行する場合は、特に EICAR をテストしている場合は削除します。

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon

     詳細については、「 [JAMF 完全構成プロファイルのプロパティ一覧」を参照してください](mac-preferences.md#property-list-for-jamf-full-configuration-profile)。

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

2. ファイル `MDATP_MDAV_configuration_settings.plist`を .

3. Jamf Pro ダッシュボードで、[**コンピューター**] とその **構成プロファイル** を開きます。 [ **新規]** をクリックし、[ **全般** ] タブに切り替えます。

   :::image type="content" source="images/644e0f3af40c29e80ca1443535b2fe32.png" alt-text="新しいプロファイルを表示するページ" lightbox="images/644e0f3af40c29e80ca1443535b2fe32.png":::

4. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV 構成設定
    - 説明：\<blank\>
    - カテゴリ: なし (既定)
    - 配布方法: 自動的にインストールする(既定)
    - レベル: コンピューター レベル(既定値)

    :::image type="content" source="images/3160906404bc5a2edf84d1d015894e3b.png" alt-text="MDATP MDAV 構成設定" lightbox="images/3160906404bc5a2edf84d1d015894e3b.png":::

5. **[アプリケーション & カスタム 設定**] で [構成] を選択 **します**。

   :::image type="content" source="images/e1cc1e48ec9d5d688087b4d771e668d2.png" alt-text="アプリケーションとカスタム設定" lightbox="images/e1cc1e48ec9d5d688087b4d771e668d2.png":::

6. **アップロード ファイル (PLIST ファイル)を** 選択します。

   :::image type="content" source="images/6f85269276b2278eca4bce84f935f87b.png" alt-text="構成設定 plist ファイル" lightbox="images/6f85269276b2278eca4bce84f935f87b.png":::

7. **[基本設定ドメイン]** に「`com.microsoft.wdav`**PLIST ファイルアップロード** 選択します。

   :::image type="content" source="images/db15f147dd959e872a044184711d7d46.png" alt-text="構成設定の基本設定ドメイン" lightbox="images/db15f147dd959e872a044184711d7d46.png":::

8. [ **ファイルの選択] を選択します**。

    :::image type="content" source="images/526e978761fc571cca06907da7b01fd6.png" alt-text="plist ファイルを選択するプロンプト" lightbox="images/526e978761fc571cca06907da7b01fd6.png":::

9. **MDATP_MDAV_configuration_settings.plist** を選択し、[**開く**] を選択します。

   :::image type="content" source="images/98acea3750113b8dbab334296e833003.png" alt-text="mdatpmdav 構成設定" lightbox="images/98acea3750113b8dbab334296e833003.png":::

10. [**アップロード**] を選択します。

    :::image type="content" source="images/0adb21c13206861ba9b30a879ade93d3.png" alt-text="構成設定のアップロード" lightbox="images/0adb21c13206861ba9b30a879ade93d3.png":::

    :::image type="content" source="images/f624de59b3cc86e3e2d32ae5de093e02.png" alt-text="構成設定に関連するイメージをアップロードするプロンプト" lightbox="images/f624de59b3cc86e3e2d32ae5de093e02.png":::

    > [!NOTE]
    > Intune ファイルをアップロードすると、次のエラーが発生します。
    >
    > :::image type="content" source="images/8e69f867664668796a3b2904896f0436.png" alt-text="構成設定に関連する intune ファイルをアップロードするプロンプト" lightbox="images/8e69f867664668796a3b2904896f0436.png":::

11. **[保存]** を選択します。

    :::image type="content" source="images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png" alt-text="構成設定に関連するイメージを保存するオプション" lightbox="images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png":::

12. ファイルがアップロードされます。

    :::image type="content" source="images/33e2b2a1611fdddf6b5b79e54496e3bb.png" alt-text="構成設定に関連するアップロードされたファイル" lightbox="images/33e2b2a1611fdddf6b5b79e54496e3bb.png":::

    :::image type="content" source="images/a422e57fe8d45689227e784443e51bd1.png" alt-text="[構成設定] ページ" lightbox="images/a422e57fe8d45689227e784443e51bd1.png":::

13. [ **スコープ** ] タブを選択します。

    :::image type="content" source="images/9fc17529e5577eefd773c658ec576a7d.png" alt-text="構成設定のスコープ" lightbox="images/9fc17529e5577eefd773c658ec576a7d.png":::

14. **Contoso のマシン グループを選択します**。

15. [ **追加]** を選択し、[保存] を選択 **します**。

    :::image type="content" source="images/cf30438b5512ac89af1d11cbf35219a6.png" alt-text="構成設定の addsav" lightbox="images/cf30438b5512ac89af1d11cbf35219a6.png":::

    :::image type="content" source="images/6f093e42856753a3955cab7ee14f12d9.png" alt-text="構成設定の通知" lightbox="images/6f093e42856753a3955cab7ee14f12d9.png":::

16. [**完了**] を選択します。 新しい **構成プロファイル** が表示されます。

    ![構成設定構成プロファイル イメージの画像。](images/dd55405106da0dfc2f50f8d4525b01c8.png)
    :::image type="content" source="images/dd55405106da0dfc2f50f8d4525b01c8.png" alt-text="構成プロファイルの設定" lightbox="images/dd55405106da0dfc2f50f8d4525b01c8.png":::

## <a name="step-4-configure-notifications-settings"></a>手順 4: 通知設定を構成する

これらの手順は、macOS 10.15 (Catalina) 以降に適用されます。

1. Jamf Pro ダッシュボードで、[**コンピューター**]、[**構成プロファイル**] の順に選択します。

2. [ **新規]** をクリックし、[ **オプション**] に次の詳細を入力します。

    - タブ **の全般**:
        - **名前**: MDATP MDAV 通知設定
        - **説明**: macOS 10.15 (Catalina) 以降
        - **カテゴリ**: なし *(既定)*
        - **配布方法**: 自動インストール *(既定)*
        - **レベル**: コンピューター レベル *(既定)*

        :::image type="content" source="images/c9820a5ff84aaf21635c04a23a97ca93.png" alt-text="新しい macOS 構成プロファイル ページ" lightbox="images/c9820a5ff84aaf21635c04a23a97ca93.png":::

    - タブ **通知** をクリックし、[ **追加]** をクリックして、次の値を入力します。
        - **バンドル ID**: `com.microsoft.wdav.tray`
        - **重要なアラート**: **[無効]** をクリックする
        - **通知**: **[有効にする**] をクリックします
        - **バナー アラートの種類**: **[含める** ] と [ **一時**] を選択 *します (既定)*
        - **ロック画面の通知**: **[非表示**] をクリックする
        - **通知センターの通知**: [**表示**] をクリックする
        - **バッジ アプリ アイコン**: [**表示**] をクリックする

        :::image type="content" source="images/7f9138053dbcbf928e5182ee7b295ebe.png" alt-text="構成設定 mdatpmdav 通知トレイ" lightbox="images/7f9138053dbcbf928e5182ee7b295ebe.png":::

    - タブ **通知**、もう 1 回 **追加** をクリックし、下にスクロールして **[新しい通知] 設定**
        - **バンドル ID**: `com.microsoft.autoupdate.fba`
        - 上記と同じ値に残りの設定を構成する

        :::image type="content" source="images/4bac6ce277aedfb4a674f2d9fcb2599a.png" alt-text="構成設定 mdatpmdav 通知 mau" lightbox="images/4bac6ce277aedfb4a674f2d9fcb2599a.png":::

        これで、通知構成を持つ 2 つの "テーブル" が用意されています。1 つは **バンドル ID の場合は com.microsoft.wdav.tray** で、もう 1 つは **バンドル ID の場合は com.microsoft.autoupdate.fba** です。 要件に従ってアラート設定を構成できますが、バンドル ID は前に説明したものとまったく同じにする必要があり、**Include** スイッチは **通知** 用 **にオン** にする必要があります。

3. [ **スコープ** ] タブを選択し、[ **追加**] を選択します。

   :::image type="content" source="images/441aa2ecd36abadcdd8aed03556080b5.png" alt-text="構成設定の値を追加できるページ" lightbox="images/441aa2ecd36abadcdd8aed03556080b5.png":::

4. **Contoso のマシン グループを選択します**。

5. [ **追加]** を選択し、[保存] を選択 **します**。

   :::image type="content" source="images/09a275e321268e5e3ac0c0865d3e2db5.png" alt-text="構成設定 contoso コンピューター グループの値を保存できるページ" lightbox="images/09a275e321268e5e3ac0c0865d3e2db5.png":::

   :::image type="content" source="images/4d2d1d4ee13d3f840f425924c3df0d51.png" alt-text="構成設定の完了通知を表示するページ" lightbox="images/4d2d1d4ee13d3f840f425924c3df0d51.png":::

6. [**完了**] を選択します。 新しい **構成プロファイル** が表示されます。

   :::image type="content" source="images/633ad26b8bf24ec683c98b2feb884bdf.png" alt-text="完了した構成設定" lightbox="images/633ad26b8bf24ec683c98b2feb884bdf.png":::

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>手順 5: Microsoft AutoUpdate (MAU) を構成する

1. 次のMicrosoft Defender for Endpoint構成設定を使用します。

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

2. 名前を付けて `MDATP_MDAV_MAU_settings.plist`保存します。

3. Jamf Pro ダッシュボードで、[**全般**] を選択します。

   :::image type="content" source="images/eaba2a23dd34f73bf59e826217ba6f15.png" alt-text="構成設定" lightbox="images/eaba2a23dd34f73bf59e826217ba6f15.png":::

4. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV MAU の設定
    - 説明: mDATP for macOS の Microsoft AutoUpdate 設定
    - カテゴリ: なし (既定)
    - 配布方法: 自動的にインストールする(既定)
    - レベル: コンピューター レベル(既定値)

5. **[アプリケーション & カスタム 設定**] で [構成] を選択 **します**。

   :::image type="content" source="images/1f72e9c15eaafcabf1504397e99be311.png" alt-text="構成設定アプリケーションとカスタム設定" lightbox="images/1f72e9c15eaafcabf1504397e99be311.png":::

6. **アップロード ファイル (PLIST ファイル)を** 選択します。

7. **[基本設定ドメイン]** に「: `com.microsoft.autoupdate2`」と入力し、**PLIST ファイルアップロード** 選択します。

   :::image type="content" source="images/1213872db5833aa8be535da57653219f.png" alt-text="構成設定の基本設定ドメイン" lightbox="images/1213872db5833aa8be535da57653219f.png":::
    

8. [ **ファイルの選択] を選択します**。

   :::image type="content" source="images/335aff58950ce62d1dabc289ecdce9ed.png" alt-text="構成設定に関するファイルを選択するプロンプト" lightbox="images/335aff58950ce62d1dabc289ecdce9ed.png":::

9. **MDATP_MDAV_MAU_settings.plist** を選択します。

   :::image type="content" source="images/a26bd4967cd54bb113a2c8d32894c3de.png" alt-text="mdatpmdavmau の設定" lightbox="images/a26bd4967cd54bb113a2c8d32894c3de.png":::

10. [**アップロード**] を選択します。
    :::image type="content" source="images/4239ca0528efb0734e4ca0b490bfb22d.png" alt-text="構成設定に関するファイルのアップロード" lightbox="images/4239ca0528efb0734e4ca0b490bfb22d.png":::

    :::image type="content" source="images/4ec20e72c8aed9a4c16912e01692436a.png" alt-text="構成設定に関するファイルのアップロード オプションを表示するページ" lightbox="images/4ec20e72c8aed9a4c16912e01692436a.png":::

11. **[保存]** を選択します。

    :::image type="content" source="images/253274b33e74f3f5b8d475cf8692ce4e.png" alt-text="構成設定に関するファイルの保存オプションを表示するページ" lightbox="images/253274b33e74f3f5b8d475cf8692ce4e.png":::

12. [ **スコープ** ] タブを選択します。

    :::image type="content" source="images/10ab98358b2d602f3f67618735fa82fb.png" alt-text="構成設定の [スコープ] タブ" lightbox="images/10ab98358b2d602f3f67618735fa82fb.png":::

13. **[追加]** を選択します。

    :::image type="content" source="images/56e6f6259b9ce3c1706ed8d666ae4947.png" alt-text="デプロイ ターゲットを追加するオプション" lightbox="images/56e6f6259b9ce3c1706ed8d666ae4947.png":::

    :::image type="content" source="images/38c67ee1905c4747c3b26c8eba57726b.png" alt-text="構成設定に値を追加するページ" lightbox="images/38c67ee1905c4747c3b26c8eba57726b.png":::

    :::image type="content" source="images/321ba245f14743c1d5d51c15e99deecc.png" alt-text="構成設定に値を追加できるページ" lightbox="images/321ba245f14743c1d5d51c15e99deecc.png":::

14. [**完了**] を選択します。

    :::image type="content" source="images/ba44cdb77e4781aa8b940fb83e3c21f7.png" alt-text="構成設定に関する完了通知" lightbox="images/ba44cdb77e4781aa8b940fb83e3c21f7.png":::

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>手順 6: Microsoft Defender for Endpointへのフル ディスク アクセスを許可する

1. Jamf Pro ダッシュボードで、[**構成プロファイル**] を選択します。

   :::image type="content" source="images/264493cd01e62c7085659d6fdc26dc91.png" alt-text="設定を構成するプロファイル" lightbox="images/264493cd01e62c7085659d6fdc26dc91.png":::

2. [ **+ 新規**] を選択します。

3. 次の詳細を入力します。

    **全般**
    - 名前: MDATP MDAV - EDRと AV へのフル ディスク アクセスを許可する
    - 説明: macOS Catalina 以降では、新しいプライバシー設定ポリシー コントロール
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    :::image type="content" source="images/ba3d40399e1a6d09214ecbb2b341923f.png" alt-text="一般的な構成設定" lightbox="images/ba3d40399e1a6d09214ecbb2b341923f.png":::
    

4. [ **プライバシー設定ポリシー制御の構成] で** [構成] を選択 **します**。

   :::image type="content" source="images/715ae7ec8d6a262c489f94d14e1e51bb.png" alt-text="構成のプライバシー ポリシー制御" lightbox="images/715ae7ec8d6a262c489f94d14e1e51bb.png":::

5. [ **プライバシー設定ポリシー制御] で**、次の詳細を入力します。

    - 識別子： `com.microsoft.wdav`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

    :::image type="content" source="images/22cb439de958101c0a12f3038f905b27.png" alt-text="構成設定のプライバシー設定ポリシー制御の詳細" lightbox="images/22cb439de958101c0a12f3038f905b27.png":::

6. **[+ 追加]** を選択します。

   :::image type="content" source="images/bd93e78b74c2660a0541af4690dd9485.png" alt-text="構成設定で、システム ポリシーのすべてのファイルを追加するオプション" lightbox="images/bd93e78b74c2660a0541af4690dd9485.png":::

    - アプリまたはサービスの下: **SystemPolicyAllFiles** に設定する

    - [アクセス] の下: **[許可**] に設定します

7. **[保存] を選択します** (右下の名前ではありません)。

   :::image type="content" source="images/6de50b4a897408ddc6ded56a09c09fe2.png" alt-text="構成設定の保存操作" lightbox="images/6de50b4a897408ddc6ded56a09c09fe2.png":::

8. **[App Access**] の`+`横にある記号をクリックして、新しいエントリを追加します。

   :::image type="content" source="images/tcc-add-entry.png" alt-text="構成設定に関連する保存操作" lightbox="images/tcc-add-entry.png":::

9. 次の詳細を入力します。

    - 識別子： `com.microsoft.wdav.epsext`
    - 識別子の種類: バンドル ID
    - コード要件: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. **[+ 追加]** を選択します。

    :::image type="content" source="images/tcc-epsext-entry.png" alt-text="構成設定 tcc epsext エントリ" lightbox="images/tcc-epsext-entry.png":::

    - アプリまたはサービスの下: **SystemPolicyAllFiles** に設定する

    - [アクセス] の下: **[許可**] に設定します

11. **[保存] を選択します** (右下の名前ではありません)。

    :::image type="content" source="images/tcc-epsext-entry2.png" alt-text="構成設定 tcc epsext のもう 1 つのインスタンス" lightbox="images/tcc-epsext-entry2.png":::

12. [ **スコープ** ] タブを選択します。

    :::image type="content" source="images/2c49b16cd112729b3719724f581e6882.png" alt-text="構成設定のスコープを示すページ" lightbox="images/2c49b16cd112729b3719724f581e6882.png":::

13. **[+ 追加]** を選択します。

    :::image type="content" source="images/57cef926d1b9260fb74a5f460cee887a.png" alt-text="構成設定を示すページ" lightbox="images/57cef926d1b9260fb74a5f460cee887a.png":::

14. [グループ **名**] で **[コンピューター グループ**>を選択> **Contoso の MachineGroup** を選択します。

    :::image type="content" source="images/368d35b3d6179af92ffdbfd93b226b69.png" alt-text="構成設定 contoso コンピューター グループ" lightbox="images/368d35b3d6179af92ffdbfd93b226b69.png":::

15. **[追加]** を選択します。

16. **[保存]** を選択します。

17. [**完了**] を選択します。

    :::image type="content" source="images/809cef630281b64b8f07f20913b0039b.png" alt-text="構成設定 contoso machine-group" lightbox="images/809cef630281b64b8f07f20913b0039b.png":::

    :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="構成設定の図" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

または、「Jamf を使用したカスタム構成プロファイルのデプロイ」で説明されているように[、fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) をダウンロード[して JAMF 構成プロファイルにアップロードPro|方法 2: 構成プロファイルを Jamf Proにアップロード](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)します。

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>手順 7: Microsoft Defender for Endpointのカーネル拡張機能を承認する

> [!CAUTION]
> Apple シリコン (M1) デバイスでは、KEXT はサポートされていません。 これらのデバイスでは、KEXT ポリシーで構成される構成プロファイルのインストールが失敗します。

1. **構成プロファイル** で、[ **+ 新規**] を選択します。

   :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="ソーシャル メディア投稿の説明が自動的に生成される" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

2. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV カーネル拡張機能
    - 説明: MDATP カーネル拡張機能 (kext)
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    :::image type="content" source="images/24e290f5fc309932cf41f3a280d22c14.png" alt-text="構成設定 mdatpmdav カーネル" lightbox="images/24e290f5fc309932cf41f3a280d22c14.png":::

3. [ **承認済みカーネル拡張機能の構成]** で [構成] を選択 **します**。

   :::image type="content" source="images/30be88b63abc5e8dde11b73f1b1ade6a.png" alt-text="構成設定が承認されたカーネル拡張機能を表示するページ" lightbox="images/30be88b63abc5e8dde11b73f1b1ade6a.png":::

4. [ **承認済みカーネル拡張機能]** で、次の詳細を入力します。

    - 表示名: Microsoft Corp.
    - チーム ID: UBF8T346G9

    :::image type="content" source="images/39cf120d3ac3652292d8d1b6d057bd60.png" alt-text="[承認済みカーネル拡張機能] ウィンドウ" lightbox="images/39cf120d3ac3652292d8d1b6d057bd60.png":::

5. [ **スコープ** ] タブを選択します。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="構成の [スコープ] タブ" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

6. **[+ 追加]** を選択します。

7. [**グループ名**] で **[コンピューター グループ**>を選択> **Contoso のコンピューター グループ** を選択します。

8. **[+ 追加]** を選択します。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="構成設定の追加値を定義するページ" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

9. **[保存]** を選択します。

   :::image type="content" source="images/0add8019b85a453b47fa5c402c72761b.png" alt-text="MDATP MDAV カーネル拡張機能" lightbox="images/0add8019b85a453b47fa5c402c72761b.png":::

10. [**完了**] を選択します。

    :::image type="content" source="images/1c9bd3f68db20b80193dac18f33c22d0.png" alt-text="構成プロファイルの詳細ページ" lightbox="images/1c9bd3f68db20b80193dac18f33c22d0.png":::

または、「Jamf を使用したカスタム構成プロファイルのデプロイ」で説明されているように[、kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) をダウンロード[して JAMF 構成プロファイルにアップロードPro|方法 2: 構成プロファイルを Jamf Proにアップロード](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)します。

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>手順 8: Microsoft Defender for Endpointのシステム拡張機能を承認する

1. **構成プロファイル** で、[ **+ 新規**] を選択します。

   :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="自動生成されたソーシャル メディア投稿の説明" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

2. 次の詳細を入力します。

    **全般**

    - 名前: MDATP MDAV システム拡張機能
    - 説明: MDATP システム拡張機能
    - カテゴリ: なし
    - 配布方法: 自動的にインストールする
    - レベル: コンピューター レベル

    :::image type="content" source="images/sysext-new-profile.png" alt-text="構成設定 sysext 新しいプロファイル" lightbox="images/sysext-new-profile.png":::

3. **[システム拡張機能]** で [構成] を選択 **します**。

   :::image type="content" source="images/sysext-configure.png" alt-text="システム拡張機能の [構成] オプションが表示されたウィンドウ" lightbox="images/sysext-configure.png":::

4. **[システム拡張機能]** に、次の詳細を入力します。

   - 表示名: Microsoft Corp. システム拡張機能
   - システム拡張機能の種類: 許可されるシステム拡張機能
   - チーム識別子: UBF8T346G9
   - 許可されるシステム拡張機能:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    :::image type="content" source="images/sysext-configure2.png" alt-text="MDATP MDAV システム拡張機能ウィンドウ" lightbox="images/sysext-configure2.png":::

5. [ **スコープ** ] タブを選択します。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="[ターゲット コンピューター] 選択ウィンドウ" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

6. **[+ 追加]** を選択します。

7. [**グループ名**] で **[コンピューター グループ**>を選択> **Contoso のコンピューター グループ** を選択します。

8. **[+ 追加]** を選択します。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="[新しい macOS 構成プロファイル] ウィンドウ" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

9. **[保存]** を選択します。

   :::image type="content" source="images/sysext-scope.png" alt-text="MDATP MDAV システム拡張機能に関するオプションの表示" lightbox="images/sysext-scope.png":::

10. [**完了**] を選択します。

    :::image type="content" source="images/sysext-final.png" alt-text="構成設定 sysext - final" lightbox="images/sysext-final.png":::

## <a name="step-9-configure-network-extension"></a>手順 9: ネットワーク拡張機能を構成する

エンドポイントの検出と応答機能の一環として、macOS のMicrosoft Defender for Endpointはソケット トラフィックを検査し、この情報をMicrosoft 365 Defender ポータルに報告します。 次のポリシーを使用すると、ネットワーク拡張機能でこの機能を実行できます。

これらの手順は、macOS 10.15 (Catalina) 以降に適用されます。

1. Jamf Pro ダッシュボードで、[**コンピューター**]、[**構成プロファイル**] の順に選択します。

2. [ **新規]** をクリックし、[ **オプション**] に次の詳細を入力します。

    - タブ **の全般**:
        - **名前**: Microsoft Defender ネットワーク拡張機能
        - **説明**: macOS 10.15 (Catalina) 以降
        - **カテゴリ**: なし *(既定)*
        - **配布方法**: 自動インストール *(既定)*
        - **レベル**: コンピューター レベル *(既定)*

    - タブ **コンテンツ フィルター**:
        - **フィルター名**: Microsoft Defender コンテンツ フィルター
        - **識別子**: `com.microsoft.wdav`
        - **[サービス アドレス**]、[**組織]**、[**ユーザー名]**、[**パスワード]**、[**証明書**] は空白のままにします (**[含める**] が選択 *されていません*)
        - **フィルターの順序**: インスペクター
        - **ソケット フィルター**: `com.microsoft.wdav.netext`
        - **ソケット フィルター指定要件**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - **[ネットワーク フィルター]** フィールドは空白のままにします (**[含める**] は選択 *されていません*)

        上記で指定した **識別子**、 **ソケット フィルター** 、 **ソケット フィルター指定要件** の正確な値に注意してください。

        :::image type="content" source="images/netext-create-profile.png" alt-text="mdatpmdav 構成設定" lightbox="images/netext-create-profile.png":::

3. [ **スコープ** ] タブを選択します。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="[構成設定] の [sco] タブ" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

4. **[+ 追加]** を選択します。

5. [**グループ名**] で **[コンピューター グループ**>を選択> **Contoso のコンピューター グループ** を選択します。

6. **[+ 追加]** を選択します。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="構成設定の adim" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

7. **[保存]** を選択します。

   :::image type="content" source="images/netext-scope.png" alt-text="[コンテンツ フィルター] ウィンドウ" lightbox="images/netext-scope.png":::

8. [**完了**] を選択します。

   :::image type="content" source="images/netext-final.png" alt-text="構成設定 netext - final" lightbox="images/netext-final.png":::

または、「Jamf Pro|を使用したカスタム構成プロファイルのデプロイ」で説明されているように、[netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) をダウンロード[して JAMF 構成プロファイルにアップロードすることもできます。方法 2: 構成プロファイルを Jamf Proにアップロード](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)します。

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>手順 10: macOS でMicrosoft Defender for Endpointでスキャンをスケジュールする

[macOS でMicrosoft Defender for Endpointを使用してスキャンをスケジュールするに関する手順に](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)従います。

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>手順 11: macOS にMicrosoft Defender for Endpointをデプロイする

1. 保存した場所に移動します `wdav.pkg`。

   :::image type="content" source="images/8dde76b5463047423f8637c86b05c29d.png" alt-text="エクスプローラーの wdav パッケージ" lightbox="images/8dde76b5463047423f8637c86b05c29d.png":::

2. 名前を変更します `wdav_MDM_Contoso_200329.pkg`。

   :::image type="content" source="images/fb2220fed3a530f4b3ef36f600da0c27.png" alt-text="エクスプローラー 1 wdavmdm パッケージ" lightbox="images/fb2220fed3a530f4b3ef36f600da0c27.png":::

3. Jamf Pro ダッシュボードを開きます。

   :::image type="content" source="images/990742cd9a15ca9fdd37c9f695d1b9f4.png" alt-text="jamfpro の構成設定" lightbox="images/990742cd9a15ca9fdd37c9f695d1b9f4.png":::

4. コンピューターを選択し、上部にある歯車アイコンをクリックして、[ **コンピューターの管理**] を選択します。

   :::image type="content" source="images/b6d671b2f18b89d96c1c8e2ea1991242.png" alt-text="構成設定 - コンピューター管理" lightbox="images/b6d671b2f18b89d96c1c8e2ea1991242.png":::

5. **[パッケージ**] で 、[**+ 新規**] を選択します。
   :::image type="content" source="images/57aa4d21e2ccc65466bf284701d4e961.png" alt-text="自動生成されたパッケージの鳥の説明" lightbox="images/57aa4d21e2ccc65466bf284701d4e961.png":::

6. **[新しいパッケージ]** で、次の詳細を入力します。

    **[全般] タブ**
    - 表示名: 今は空白のままにしておきます。 pkg を選択するとリセットされるためです。
    - カテゴリ: なし (既定)
    - ファイル名: ファイルの選択

    :::image type="content" source="images/21de3658bf58b1b767a17358a3f06341.png" alt-text="構成設定の [全般] タブ" lightbox="images/21de3658bf58b1b767a17358a3f06341.png":::

    ファイルを開き、そのファイルを `wdav.pkg` ポイントするか、 を指定します `wdav_MDM_Contoso_200329.pkg`。

    :::image type="content" source="images/1aa5aaa0a387f4e16ce55b66facc77d1.png" alt-text="自動生成されたパッケージの説明を表示するコンピューター画面" lightbox="images/1aa5aaa0a387f4e16ce55b66facc77d1.png":::

7. [**開く**]を選択します。 **表示名** を **Microsoft Defender Advanced Threat Protection と Microsoft Defender ウイルス対策** に設定します。

    **マニフェスト ファイル** は必要ありません。 Microsoft Defender for Endpointはマニフェスト ファイルなしで機能します。

    **[オプション] タブ**: 既定値をそのまま使用します。

    **[制限事項] タブ**: 既定値のままにします。

    :::image type="content" source="images/56dac54634d13b2d3948ab50e8d3ef21.png" alt-text="構成設定の [制限] タブ" lightbox="images/56dac54634d13b2d3948ab50e8d3ef21.png":::

8. **[保存]** を選択します。 パッケージは Jamf Proにアップロードされます。

   :::image type="content" source="images/33f1ecdc7d4872555418bbc3efe4b7a3.png" alt-text="構成設定に関連するパッケージの構成設定パックのアップロード プロセス" lightbox="images/33f1ecdc7d4872555418bbc3efe4b7a3.png":::

   パッケージがデプロイに使用できるようになるまでに数分かかる場合があります。

   :::image type="content" source="images/1626d138e6309c6e87bfaab64f5ccf7b.png" alt-text="構成設定用にパッケージをアップロードするインスタンス" lightbox="images/1626d138e6309c6e87bfaab64f5ccf7b.png":::

9. **[ポリシー**] ページに移動します。

   :::image type="content" source="images/f878f8efa5ebc92d069f4b8f79f62c7f.png" alt-text="構成設定ポリシー" lightbox="images/f878f8efa5ebc92d069f4b8f79f62c7f.png":::

10. **[+ 新規]** を選択して新しいポリシーを作成します。

    :::image type="content" source="images/847b70e54ed04787e415f5180414b310.png" alt-text="構成設定の新しいポリシー" lightbox="images/847b70e54ed04787e415f5180414b310.png":::


11. 一 **般に** 、次の詳細を入力します。

    - 表示名: MDATP Onboarding Contoso 200329 v100.86.92 以降

      :::image type="content" source="images/625ba6d19e8597f05e4907298a454d28.png" alt-text="構成設定 - MDATP オンボード" lightbox="images/625ba6d19e8597f05e4907298a454d28.png":::

12. [ **定期的なチェックイン**] を選択します。

    :::image type="content" source="images/68bdbc5754dfc80aa1a024dde0fce7b0.png" alt-text="構成設定の定期的なチェックイン" lightbox="images/68bdbc5754dfc80aa1a024dde0fce7b0.png":::

13. **[保存]** を選択します。

14. [ **パッケージ] > [構成] を選択します**。

    :::image type="content" source="images/8fb4cc03721e1efb4a15867d5241ebfb.png" alt-text="パッケージを構成するオプション" lightbox="images/8fb4cc03721e1efb4a15867d5241ebfb.png":::

15. **Microsoft Defender Advanced Threat Protection とMicrosoft Defender ウイルス対策** の横にある **[追加]** ボタンを選択します。

    :::image type="content" source="images/526b83fbdbb31265b3d0c1e5fbbdc33a.png" alt-text="MDATP MDA に設定を追加するオプション" lightbox="images/526b83fbdbb31265b3d0c1e5fbbdc33a.png":::

16. **[保存]** を選択します。

    :::image type="content" source="images/9d6e5386e652e00715ff348af72671c6.png" alt-text="構成設定の保存オプション" lightbox="images/9d6e5386e652e00715ff348af72671c6.png":::

17. [ **スコープ** ] タブを選択します。

    :::image type="content" source="images/8d80fe378a31143db9be0bacf7ddc5a3.png" alt-text="構成設定に関連する [スコープ] タブ" lightbox="images/8d80fe378a31143db9be0bacf7ddc5a3.png":::

18. ターゲット コンピューターを選択します。

    :::image type="content" source="images/6eda18a64a660fa149575454e54e7156.png" alt-text="コンピューター グループを追加するオプション" lightbox="images/6eda18a64a660fa149575454e54e7156.png":::

    **スコープ**

    **[追加]** を選択します。

    :::image type="content" source="images/1c08d097829863778d562c10c5f92b67.png" alt-text="構成設定 - ad1" lightbox="images/1c08d097829863778d562c10c5f92b67.png":::

    :::image type="content" source="images/216253cbfb6ae738b9f13496b9c799fd.png" alt-text="構成設定 - ad2" lightbox="images/216253cbfb6ae738b9f13496b9c799fd.png":::

    **セルフ・サービス**

    :::image type="content" source="images/c9f85bba3e96d627fe00fc5a8363b83a.png" alt-text="構成設定の [セルフサービス] タブ" lightbox="images/c9f85bba3e96d627fe00fc5a8363b83a.png":::

19. [**完了**] を選択します。

    :::image type="content" source="images/99679a7835b0d27d0a222bc3fdaf7f3b.png" alt-text="Contoso のオンボード状態 (完了オプションあり)" lightbox="images/99679a7835b0d27d0a222bc3fdaf7f3b.png":::

    :::image type="content" source="images/632aaab79ae18d0d2b8e0c16b6ba39e2.png" alt-text="[ポリシー] ページ" lightbox="images/632aaab79ae18d0d2b8e0c16b6ba39e2.png":::
