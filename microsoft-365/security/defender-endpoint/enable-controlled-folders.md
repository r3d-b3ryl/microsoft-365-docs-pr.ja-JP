---
title: フォルダー アクセスの制御を有効にする
keywords: フォルダー アクセスの制御、Windows 10、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、有効化、オン、使用
description: フォルダー アクセスの制御を有効にすることで重要なファイルを保護する方法について説明します。
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218762"
---
# <a name="enable-controlled-folder-access"></a>フォルダー アクセスの制御を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[フォルダー アクセスの制御により](controlled-folders.md) 、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。 フォルダー アクセスの制御は、Windows 10 および Windows Server 2019 に含まれています。

次の方法を使用して、フォルダーアクセスの制御を有効にできます。

* [Windows セキュリティ アプリ](#windows-security-app)
* [Microsoft Intune](#intune)
* [モバイル デバイス管理 (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [グループ ポリシー](#group-policy)
* [PowerShell](#powershell)

[監査モード](evaluate-controlled-folder-access.md) を使用すると、デバイスの通常の使用に影響を与えることなく、機能の動作をテスト (およびイベントの確認) を行えます。

ローカル管理者リストのマージを無効にするグループ ポリシー設定は、フォルダー アクセスの制御設定を上書きします。 また、フォルダー アクセスの制御によってローカル管理者が設定した保護フォルダーと許可されたアプリも上書きされます。 これらのポリシーには、次のものが含まれます。

* Microsoft Defender ウイルス対策 **リストのローカル管理者のマージ動作を構成する**
* System Center Endpoint Protection **ユーザーによる除外と上書きの追加を許可する**

ローカル リストのマージを無効にする方法の詳細については、「ユーザーが Microsoft Defender AV ポリシー設定をローカルで変更するを防止または許可する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)。

## <a name="windows-security-app"></a>Windows セキュリティ アプリ

1. タスク バーでシールド アイコンを選択して、Windows セキュリティ アプリを開きます。 スタート メニューで Defender を検索 **することもできます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護] **を選択します**。

3. [フォルダー アクセスの制御] **のスイッチを [オン]** に **設定します**。

> [!NOTE]
> グループ ポリシー、PowerShell、または MDM CSP でフォルダー アクセスの制御が構成されている場合、デバイスの再起動後に Windows セキュリティ アプリで状態が変更されます。
> これらのツールを使用して機能が **監査** モードに設定されている場合、Windows セキュリティ アプリは状態を [オフ] と表示 **します**。
> ユーザー プロファイル データを保護する場合は、ユーザー プロファイルを既定の Windows インストール ドライブに保存することをお勧めします。

## <a name="intune"></a>Intune

1. Azure ポータルにサインイン [し、Intune](https://portal.azure.com) を開きます。

2. [デバイス構成 **プロファイル]**  >  **[プロファイルの**  >  **作成] に移動します**。

3. プロファイルに名前を付け **、[Windows 10** 以降] と [エンドポイント保護] **を選択します**。 <br/> ![エンドポイント保護プロファイルの作成](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. 「Configure **Windows Defender**  >  **Exploit Guard**  >  **管理フォルダー アクセス を有効にする」に**  >  **移動します**。

5. 保護されたフォルダーにアクセスできる各アプリケーションへのパスと、保護が必要な追加のフォルダーへのパスを入力します。 **[追加]** を選択します。<br/> ![Intune でフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard はアプリケーションでサポートされますが、フォルダーではサポートされません。 サブフォルダーは保護されません。 許可されたアプリは、再起動するまでイベントをトリガーし続ける。

6. **[OK] を選択** して、開いている各ブレードを保存し、[作成]**を選択します**。

7. プロファイルの割り **当てを選択し**、[すべてのデバイス] の [すべての **ユーザー&割り当** てる] 、および [保存] を **選択します**。

## <a name="mobile-device-management-mdm"></a>モバイル デバイス管理 (MDM)

アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 構成サービス プロバイダー (CSP) を使用します。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Microsoft Endpoint Configuration Manager で、[アセットとコンプライアンス エンドポイント保護] に移動 **し**、[Exploit  >    >  **Guard Windows Defenderに移動します**。

2. [ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。

3. 名前と説明を入力し、[フォルダー **アクセスの制御**] を選択し、[次へ] を **選択します**。

4. 変更をブロックまたは監査するか、他のアプリを許可するか、他のフォルダーを追加するか選択し、[次へ] を **選択します**。
   > [!NOTE]
   > Wilcard はアプリケーションでサポートされますが、フォルダーではサポートされません。 サブフォルダーは保護されません。 許可されたアプリは、再起動するまでイベントをトリガーし続ける。

5. 設定を確認し、[次へ] **を選択** してポリシーを作成します。

6. ポリシーが作成された後、閉 **じます**。

## <a name="group-policy"></a>グループ ポリシー

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを Microsoft Defender ウイルス対策> Exploit Guard > Windows Defender管理> **Windows コンポーネントに展開します**。

4. [フォルダー アクセスの構成 **] 設定** をダブルクリックし、オプションを [有効] に **設定します**。 [オプション] セクションで、次のいずれかのオプションを指定する必要があります。
    * **有効** - 悪意のあるアプリや疑わしいアプリでは、保護されたフォルダー内のファイルを変更することはできません。 Windows イベント ログに通知が表示されます。
    * **無効 (既定)** - フォルダー アクセスの制御機能が機能しません。 すべてのアプリは、保護されたフォルダー内のファイルを変更できます。
    * **監査モード** - 悪意のあるアプリや疑わしいアプリが保護されたフォルダー内のファイルに変更を加えた場合、変更が許可されます。 ただし、Windows イベント ログに記録され、組織への影響を評価できます。
    * **[ディスクの変更をブロックする** ] - 信頼されていないアプリがディスク セクターに書き込む試みは、Windows イベント ログに記録されます。 これらのログは、Microsoft  > Windows > > Windows Defender > ID 1123 >で確認できます。
    * **ディスクの変更** の監査のみ - 保護されたディスク セクターへの書き込みのみを Windows イベント ログに記録します ([アプリケーションとサービス ログ] の  >  **[Microsoft** Windows Windows Defender  >    >    >  **運用**  >  **ID 1124]** の下)。 保護されたフォルダー内のファイルを変更または削除しようとすると、記録されません。

      ![グループ ポリシー オプションのスクリーンショット [有効] と [監査モード] がドロップダウンで選択されている](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> 管理されたフォルダー アクセスを完全に有効にするには、[グループ ポリシー] オプションを [有効] に設定し、[オプション] ドロップダウン メニューの [ブロック] を選択する必要があります。

## <a name="powershell"></a>PowerShell

1. [ **スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

代わりにを指定することで、監査モードで機能 `AuditMode` を有効にできます `Enabled` 。

機能 `Disabled` をオフにする場合に使用します。

## <a name="see-also"></a>関連項目

* [フォルダー アクセスを制御して重要なフォルダーを保護する](controlled-folders.md)
* [フォルダー アクセスの制御をカスタマイズする](customize-controlled-folders.md)
* [エンドポイントに対する Microsoft Defender の評価](evaluate-mde.md)
