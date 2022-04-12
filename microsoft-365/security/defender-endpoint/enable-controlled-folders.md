---
title: 制御されたフォルダー アクセスを有効にする
keywords: フォルダー アクセスの制御、Windows 10、Windows 11、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、有効化、オン、使用
description: フォルダー アクセスの制御を有効にして、重要なファイルを保護する方法について説明します
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: 4854ca235790cc8400f3f5a962e4bff203f86f98
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788130"
---
# <a name="enable-controlled-folder-access"></a>制御されたフォルダー アクセスを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[フォルダー アクセスの制御は](controlled-folders.md) 、ランサムウェアなどの悪意のあるアプリや脅威から貴重なデータを保護するのに役立ちます。 フォルダー アクセスの制御は、Windows 10、Windows 11、Windows Server 2019 に含まれています。 フォルダー アクセスの制御は[、Windows Server 2012R2 と 2016 の統合ソリューション](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)の一部としても含まれています。

次のいずれかの方法を使用して、フォルダー アクセスの制御を有効にすることができます。

- [Windows セキュリティ アプリ *](#windows-security-app)
- [Microsoft エンドポイント マネージャー](#endpoint-manager)
- [モバイル デバイス管理 (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [グループ ポリシー](#group-policy)
- [PowerShell](#powershell)

[監査モード](evaluate-controlled-folder-access.md) を使用すると、デバイスの通常の使用に影響を与えずに、機能がどのように機能するかをテスト (およびイベントの確認) できます。

ローカル管理者リストのマージを無効にするグループ ポリシー設定は、制御されたフォルダー アクセス設定よりも優先されます。 また、保護されたフォルダーと、フォルダー アクセスの制御によってローカル管理者によって設定された許可されたアプリもオーバーライドされます。 これらのポリシーには、次のものが含まれます。

- Microsoft Defender ウイルス対策 **リストのローカル管理者マージ動作を構成する**
- System Center Endpoint Protection **ユーザーによる除外とオーバーライドの追加を許可する**

ローカル リストのマージを無効にする方法の詳細については、「 [ユーザーが Microsoft Defender AV ポリシー設定をローカルで変更できないようにするか許可する](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)」を参照してください。

## <a name="windows-security-app"></a>Windows セキュリティ アプリを開きます。

1. タスク バーのシールド アイコンを選択して、Windows セキュリティ アプリを開きます。 スタート メニューで **Windows セキュリティ** を検索することもできます。

2. **[ウイルス&脅威の防止**] タイル (または左側のメニュー バーのシールド アイコン) を選択し、**ランサムウェア保護** を選択します。

3. **フォルダー アクセスの制御** のスイッチを **[オン]** に設定します。

> [!NOTE]
> *このメソッドは、Windows Server 2012R2 または 2016 では使用できません。
> 
> グループ ポリシー、PowerShell、または MDM CSP でフォルダー アクセスの制御が構成されている場合、デバイスの再起動後、Windows セキュリティ アプリで状態が変化します。
> これらのツールのいずれかで機能が **監査モード** に設定されている場合、Windows セキュリティ アプリは状態を **[オフ]** と表示します。
> ユーザー プロファイル データを保護する場合は、ユーザー プロファイルを既定のインストール ドライブにWindowsすることをお勧めします。

## <a name="endpoint-manager"></a>エンドポイント マネージャー

1. [エンドポイント マネージャー](https://endpoint.microsoft.com)にサインインし、**Endpoint Security を開きます**。

2. **[攻撃面の縮小**\>ポリシー] に移動 **します**。

3. **[プラットフォーム**] を選択 **し、Windows 10以降** を選択し、プロファイル [**攻撃表面縮小ルール**\>の **作成**] を選択します。

4. ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。

5. 下にスクロールし、[ **フォルダー保護を有効にする** ] ドロップダウンを選択して、[ **有効]** を選択します。

6. [ **保護する必要がある追加フォルダーの一覧** ] を選択し、保護する必要があるフォルダーを追加します。

7. [ **保護されたフォルダーにアクセスできるアプリの一覧** ] を選択し、保護されたフォルダーにアクセスできるアプリを追加します。

8. [ **攻撃対象の縮小ルールからファイルとパスを除外** する] を選択し、攻撃対象の縮小ルールから除外する必要があるファイルとパスを追加します。

9. プロファイルの **割り当てを** 選択し、[ **すべてのユーザー] & [すべてのデバイス**] に割り当て、[保存] を選択 **します**。

10. **[次へ**] を選択して開いている各ブレードを保存し、[**作成**] を選択します。

    > [!NOTE]
    > ワイルドカードはアプリケーションではサポートされますが、フォルダーではサポートされません。 サブフォルダーは保護されません。 許可されたアプリは、再起動されるまで引き続きイベントをトリガーします。

## <a name="mobile-device-management-mdm"></a>モバイル デバイス管理 (MDM)

[./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) 構成サービス プロバイダー (CSP) を使用して、アプリが保護されたフォルダーを変更できるようにします。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Microsoft Endpoint Configuration Managerで、**資産とコンプライアンス** \> **Endpoint Protection Windows Defender** \> **Exploit Guard** に移動します。

2. **[ホーム** \> **エクスプロイト ガード ポリシーの作成**] を選択します。

3. 名前と説明を入力し、[ **フォルダー アクセスの制御**] を選択して、[ **次へ**] を選択します。

4. 変更をブロックするか監査するか、他のアプリを許可するか、他のフォルダーを追加するかを選択し、[ **次へ**] を選択します。

   > [!NOTE]
   > ワイルドカードはアプリケーションではサポートされていますが、フォルダーではサポートされません。 サブフォルダーは保護されません。 許可されたアプリは、再起動されるまで引き続きイベントをトリガーします。

5. 設定を確認し、[ **次へ** ] を選択してポリシーを作成します。

6. ポリシーが作成されたら、 **閉じます**。

## <a name="group-policy"></a>グループ ポリシー

1. グループ ポリシー管理デバイスで、[グループ ポリシー管理コンソール](https://technet.microsoft.com/library/cc731212.aspx)を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して **、Exploit Guard >フォルダー アクセスの制御> Microsoft Defender ウイルス対策 > Windows DefenderコンポーネントをWindowsします**。

4. [ **フォルダー アクセス制御の構成]** 設定をダブルクリックし、オプションを **[有効]** に設定します。 [オプション] セクションで、次のいずれかのオプションを指定する必要があります。
   - **有効 -** 悪意のあるアプリと疑わしいアプリは、保護されたフォルダー内のファイルに変更を加えることはできません。 Windows イベント ログに通知が提供されます。
   - **無効 (既定値)** - フォルダー アクセスの制御機能は機能しません。 すべてのアプリは、保護されたフォルダー内のファイルに変更を加えることができます。
   - **監査モード** - 悪意のあるアプリまたは疑わしいアプリが保護されたフォルダー内のファイルに変更を加えようとした場合、変更が許可されます。 ただし、組織への影響を評価できるWindows イベント ログに記録されます。
   - **[ブロック ディスクの変更のみ**] - 信頼されていないアプリがディスク セクターに書き込もうとすると、イベント ログWindows記録されます。 これらのログは、Microsoft \> Windows Windows Defender \> \>運用 \> ID 1123 の **アプリケーションログとサービス ログ**\>にあります。
   - **監査ディスク変更のみ** - 保護されたディスク セクターへの書き込みの試行のみがWindowsイベント ログに記録されます (**[アプリケーションとサービス ログ** \> **] Microsoft** \> **Windows Windows Defender** \>  \> **[運用** \> **ID 1124**] の下)。 保護されたフォルダー内のファイルの変更または削除の試行は記録されません。

    :::image type="content" source="../../media/cfa-gp-enable.png" alt-text="グループ ポリシー オプション [有効] と [監査モード] が選択されている" lightbox="../../media/cfa-gp-enable.png":::

> [!IMPORTANT]
> フォルダー アクセスの制御を完全に有効にするには、グループ ポリシー オプションを **[有効]** に設定し、オプションのドロップダウン メニューで **[ブロック**] を選択する必要があります。

## <a name="powershell"></a>PowerShell

1. スタート メニューに **「powershell**」と入力し、**Windows PowerShell** 右クリックして [**管理者として実行**] を選択します。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

の代わりに`Enabled`指定することで、監査モードで機能を`AuditMode`有効にすることができます。

機能をオフにするために使用 `Disabled` します。

## <a name="see-also"></a>関連項目

- [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
- [制御されたフォルダー アクセスをカスタマイズする](customize-controlled-folders.md)
- [Microsoft Defender for Endpoint の評価](evaluate-mde.md)
