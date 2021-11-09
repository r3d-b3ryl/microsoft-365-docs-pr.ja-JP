---
title: 制御されたフォルダー アクセスを有効にする
keywords: フォルダー アクセスの制御, Windows 10, Windows 11, Windows Defender, ランサムウェア, 保護, ファイル, フォルダー, 有効化, オンにする, 使用
description: フォルダー アクセスの制御を有効にすることで重要なファイルを保護する方法について説明します。
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 6f18bfdc4e8dd4701831ed169684db110a54e154
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882143"
---
# <a name="enable-controlled-folder-access"></a>制御されたフォルダー アクセスを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[フォルダー アクセスの制御により](controlled-folders.md) 、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。 フォルダー アクセスの制御は、サーバー 2019 Windows 10、Windows 11、および Windowsに含まれます。 フォルダー アクセスの制御は、Windows Server [2012R2 および 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)の最新の統合ソリューションの一部として含まれています。

次の方法を使用して、フォルダーアクセスの制御を有効にできます。

- [Windows セキュリティアプリ *](#windows-security-app)
- [Microsoft エンドポイント マネージャー](#endpoint-manager)
- [モバイル デバイス管理 (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [グループ ポリシー](#group-policy)
- [PowerShell](#powershell)

[監査モード](evaluate-controlled-folder-access.md) を使用すると、デバイスの通常の使用に影響を与えることなく、機能の動作をテスト (およびイベントの確認) を行えます。

ローカル管理者リストのマージを無効にするグループ ポリシー設定は、フォルダー アクセスの制御設定を上書きします。 また、フォルダー アクセスの制御によってローカル管理者が設定した保護フォルダーと許可されたアプリも上書きされます。 これらのポリシーには、次のものが含まれます。

- Microsoft Defender ウイルス対策 **リストのローカル管理者のマージ動作を構成する**
- System Center Endpoint Protection **ユーザーによる除外と上書きの追加を許可する**

ローカル リストのマージを無効にする方法の詳細については、「ユーザーが Microsoft Defender AV ポリシー設定をローカルで変更するを防止または許可する」 [を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)。

## <a name="windows-security-app"></a>Windows セキュリティアプリ

1. タスク バー Windows セキュリティシールド アイコンを選択して、アプリを開きます。 スタート メニューで Defender を検索 **することもできます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護] **を選択します**。

3. [フォルダー アクセスの制御] **のスイッチを [オン]** に **設定します**。

> [!NOTE]
> *このメソッドは、サーバー 2012R2 Windows 2016 では使用できません。
> 
> グループ ポリシー、PowerShell、または MDM CSP を使用してフォルダー アクセスの制御が構成されている場合、デバイスの再起動後に Windows セキュリティ アプリで状態が変更されます。
> これらのツールを使用して機能が **監査** モードに設定されている場合、アプリWindows セキュリティ状態が [オフ] と表示 **されます**。
> ユーザー プロファイル データを保護する場合は、ユーザー プロファイルをインストール ドライブの既定のWindowsすることをお勧めします。

## <a name="endpoint-manager"></a>エンドポイント マネージャー

1. [エンドポイント セキュリティ][を開](https://endpoint.microsoft.com)エンドポイント マネージャーに **サインインします**。

2. [攻撃表面 **の縮小ポリシー] に** \> **移動します**。

3. [**プラットフォーム] を** 選択 **し、[Windows 10] 以降を** 選択し、プロファイル攻撃表面縮小ルール [作成]**を** \> **選択します**。

4. ポリシーに名前を付け、説明を追加します。 **[次へ]** を選択します。

5. 下までスクロールし、[フォルダー保護を有効にする] ドロップダウンを選択し、[有効にする] を **選択します**。

6. [ **保護する必要がある追加のフォルダーの一覧] を選択し** 、保護する必要があるフォルダーを追加します。

7. [ **保護されたフォルダーにアクセスできる** アプリの一覧] を選択し、保護されたフォルダーにアクセスできるアプリを追加します。

8. [ **攻撃表面の縮小** ルールからファイルとパスを除外する] を選択し、攻撃表面の縮小ルールから除外する必要があるファイルとパスを追加します。

9. プロファイルの割り **当てを選択し**、[すべてのデバイス] で [すべてのユーザー&割り当てる] **を選択し、[** 保存] を **選択します**。

10. [次 **へ]** を選択して、開いている各ブレードを保存し、[作成] **を選択します**。

    > [!NOTE]
    > ワイルドカードはアプリケーションでサポートされますが、フォルダーではサポートされません。 サブフォルダーは保護されません。 許可されたアプリは、再起動するまでイベントをトリガーし続ける。

## <a name="mobile-device-management-mdm"></a>モバイル デバイス管理 (MDM)

アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) 構成サービス プロバイダー (CSP) を使用します。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. この **Microsoft Endpoint Configuration Manager、Exploit** Guard の [アセットと \> **コンプライアンス] Endpoint Protection Windows Defender** \> **移動します**。

2. [ホーム **エクスプ** \> **ロイト ガード ポリシーの作成] を選択します**。

3. 名前と説明を入力し、[フォルダー **アクセスの制御**] を選択し、[次へ] を **選択します**。

4. 変更をブロックまたは監査するか、他のアプリを許可するか、他のフォルダーを追加するか選択し、[次へ] を **選択します**。

   > [!NOTE]
   > ワイルドカードはアプリケーションでサポートされますが、フォルダーではサポートされません。 サブフォルダーは保護されません。 許可されたアプリは、再起動するまでイベントをトリガーし続ける。

5. 設定を確認し、[次へ] **を選択** してポリシーを作成します。

6. ポリシーが作成された後、閉 **じます**。

## <a name="group-policy"></a>グループ ポリシー

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して **、Exploit Guard Windowsアクセス> Microsoft Defender ウイルス対策 > Windows Defender管理>コンポーネントを表示します**。

4. [フォルダー アクセスの構成 **] 設定** をダブルクリックし、オプションを [有効] に **設定します**。 [オプション] セクションで、次のいずれかのオプションを指定する必要があります。
   - **有効** - 悪意のあるアプリや疑わしいアプリでは、保護されたフォルダー内のファイルを変更することはできません。 通知は、イベント ログWindowsされます。
   - **無効 (既定)** - フォルダー アクセスの制御機能が機能しません。 すべてのアプリは、保護されたフォルダー内のファイルを変更できます。
   - **監査モード** - 悪意のあるアプリや疑わしいアプリが保護されたフォルダー内のファイルに変更を加えた場合、変更が許可されます。 ただし、組織への影響を評価Windowsイベント ログに記録されます。
   - **[ディスクの変更** をブロックする] - 信頼されていないアプリがディスク セクターに書き込む試みは、Windowsログに記録されます。 これらのログは、運用 **ID** \> \> \> \> \> 1123 Windows Windows Defenderで確認できます。
   - ディスク **の** 変更の監査のみ - 保護されたディスク セクターへの書き込みのみを Windows イベント ログに記録します([アプリケーションとサービス ログ Microsoft Windows Windows Defender \>  \>  \>  \> **運用** \> **ID 1124]** の下)。 保護されたフォルダー内のファイルを変更または削除しようとすると、記録されません。

      ![グループ ポリシー オプション [有効] および [監査モード] がドロップダウンで選択されているスクリーンショットです。](../../media/cfa-gp-enable.png)

> [!IMPORTANT]
> 管理されたフォルダー アクセスを完全に有効にするには、[グループ ポリシー] オプションを [有効] に設定し、[オプション] ドロップダウン メニューの [ブロック] を選択する必要があります。

## <a name="powershell"></a>PowerShell

1. **[powershell]** と入力スタート メニュー **右クリックし**、[管理者Windows PowerShell **実行] を選択します**。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

代わりにを指定することで、監査モードで機能 `AuditMode` を有効にできます `Enabled` 。

機能 `Disabled` をオフにする場合に使用します。

## <a name="see-also"></a>関連項目

- [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
- [制御されたフォルダー アクセスをカスタマイズする](customize-controlled-folders.md)
- [Microsoft Defender for Endpoint の評価](evaluate-mde.md)
