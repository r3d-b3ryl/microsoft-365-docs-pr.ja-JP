---
title: 制御されたフォルダー アクセスをカスタマイズする
description: フォルダー アクセスを制御して保護する必要がある他のフォルダーを追加するか、重要なファイルへの変更を誤ってブロックしているアプリを許可します。
keywords: フォルダー アクセスの制御, Windows 10, Windows 11, Windows Defender, ランサムウェア, 保護, ファイル, フォルダー, カスタマイズ, フォルダーの追加, アプリの追加, 許可, 実行可能ファイルの追加
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.date: ''
ms.openlocfilehash: b9af738d4b1f59705132a84239d06dc762447417
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683759"
---
# <a name="customize-controlled-folder-access"></a>制御されたフォルダー アクセスをカスタマイズする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

フォルダー アクセスの制御により、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。 フォルダー アクセスの制御は、Windows Server 2019、Windows Server 2022、Windows 10、Windows 11 クライアントでサポートされます。 この記事では、フォルダー アクセスの制御機能をカスタマイズする方法について説明し、次のセクションを示します。

- [追加のフォルダーを保護する](#protect-additional-folders)
- [保護されたフォルダーへのアクセスを許可する必要がありますアプリを追加する](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する](#allow-signed-executable-files-to-access-protected-folders)
- [通知をカスタマイズする](#customize-the-notification)

> [!IMPORTANT]
> フォルダー アクセスの制御により、悪意のあるアクティビティが検出されたアプリが監視されます。 場合によっては、正当なアプリがファイルに変更を加えるのをブロックされる場合があります。 フォルダー アクセスの制御が組織の生産性に影響を与える場合は、監査モードで[](audit-windows-defender.md)この機能を実行して、その影響を完全に評価することもできます。

## <a name="protect-additional-folders"></a>追加のフォルダーを保護する

フォルダー アクセスの制御は、ドキュメント、ピクチャ、ムービーなどのフォルダーを含む、多くのシステム フォルダーと既定の場所に **適用されます**。 保護する他のフォルダーを追加できますが、既定の一覧で既定のフォルダーを削除することはできません。

フォルダー アクセスの制御に他のフォルダーを追加すると、既定の Windows ライブラリにファイルを保存しない場合や、ライブラリの既定の場所を変更した場合に役立ちます。

ネットワーク共有とマップされたドライブを指定することもできます。 環境変数とワイルドカードがサポートされています。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用 [する」を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

保護されたフォルダーを追加Windows セキュリティ削除するには、アプリ、グループ ポリシー、PowerShell コマンドレット、またはモバイル デバイス管理構成サービス プロバイダーを使用できます。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>アプリを使用Windows セキュリティフォルダーを保護する

1. タスク バー Windows セキュリティシールド アイコンを選択するか、タスク バーでセキュリティを検索して、アプリを開スタート メニュー。

2. [ **ウイルス対策&を選択** し、[ランサムウェアの保護] セクション **まで下にスクロール** します。

3. [ランサムウェア **保護の管理] を** 選択して **、[ランサムウェア保護] ウィンドウを開** きます。

4. [フォルダー アクセス **の制御] セクションで** 、[保護 **されたフォルダー] を選択します**。

5. [ユーザー **アクセス制御** ] プロンプト **で [はい] を選択** します。 [ **保護されたフォルダー] ウィンドウ** が表示されます。

6. [ **保護されたフォルダーの追加] を選択** し、プロンプトに従ってフォルダーを追加します。

### <a name="use-group-policy-to-protect-additional-folders"></a>グループ ポリシーを使用して追加のフォルダーを保護する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)を開きます。 

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. グループ ポリシー **管理エディターで、[** コンピューター構成\>ポリシー] **[管理用** \> **テンプレート] に移動します**。

4. ツリーを展開して **、Exploit Guard WindowsアクセスMicrosoft Defender ウイルス対策** \>  \> Windows Defender **コンポーネント** \> **を表示します**。 <br/>**注**: 以前のバージョンの Windowsの場合は、**Windows Defender ウイルス対策の代** わりに **Microsoft Defender ウイルス対策。**

5. [構成済みの **保護されたフォルダー] をダブルクリック** し、オプションを [有効] に **設定します**。 [ **表示] を** 選択し、保護する各フォルダーを指定します。

6. 通常と同じ方法でグループ ポリシー オブジェクトを展開します。

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell を使用して追加のフォルダーを保護する

1. [**PowerShell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**

2. 次の PowerShell コマンドレットを入力し、 `<the folder to be protected>` フォルダーのパス (など) に置き換えてください `"c:\apps\"`。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 保護するフォルダーごとに手順 2 を繰り返します。 保護されているフォルダーは、アプリ内にWindows セキュリティされます。

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="コマンドレットが表示された PowerShell ウィンドウ。":::

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します `Set-MpPreference`。 コマンドレットを使用 `Set-MpPreference` すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM CSP を使用して追加のフォルダーを保護する

アプリが保護されたフォルダーに変更を加えるのを許可するには、. [/Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 構成サービス プロバイダー (CSP) を使用します。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>特定のアプリが管理フォルダーに変更を加えるのを許可する

特定のアプリが常に安全と見なされる場合を指定し、保護されたフォルダー内のファイルへの書き込みアクセス権を与えることもできます。 アプリを許可すると、特定のアプリが、管理されたフォルダー アクセス機能によってブロックされている場合に便利です。

> [!IMPORTANT]
> 既定では、Windowsリストに対してフレンドリーと見なされるアプリが追加されます。 自動的に追加されるこのようなアプリは、アプリに表示される一覧や、Windows セキュリティ PowerShell コマンドレットを使用して記録されません。 ほとんどのアプリを追加する必要はない必要があります。 アプリがブロックされている場合にのみアプリを追加し、信頼度を確認できます。

アプリを追加する場合は、アプリの場所を指定する必要があります。 その場所のアプリだけが、保護されたフォルダーへのアクセスを許可されます。 (同じ名前の) アプリが別の場所にある場合、アプリは許可リストに追加されません。フォルダー アクセスの制御によってブロックされる場合があります。

許可されているアプリケーションまたはサービスは、開始後にのみ、制御フォルダーへの書き込みアクセス権を持つ。 たとえば、更新サービスは、イベントが停止して再起動されるまで、イベントが許可された後も引き続きトリガーされます。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>特定のアプリWindows Defenderを許可するには、セキュリティ アプリを使用する

1. [セキュリティ] Windows セキュリティスタート メニューを検索して、アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護の管理] **を選択します**。

3. [フォルダー アクセス **の制御] セクションで** 、[フォルダー アクセス **の制御によるアプリの許可] を選択します。**

4. [ **許可されたアプリを追加する] を選択** し、プロンプトに従ってアプリを追加します。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="許可されたアプリ ボタンを追加します。":::

### <a name="use-group-policy-to-allow-specific-apps"></a>グループ ポリシーを使用して特定のアプリを許可する

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して **、Exploit Guard WindowsアクセスMicrosoft Defender ウイルス対策** \>  \> Windows Defender **コンポーネント** \> **を表示します**。

4. [許可されたアプリケーションの **構成] 設定をダブルクリック** し、オプションを [有効] に **設定します**。 [表示 **] を** 選択し、各アプリを入力します。

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell を使用して特定のアプリを許可する

1. [**PowerShell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**
2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    たとえば、C *:\apps* フォルダー ** test.exe実行可能ファイルを追加するには、コマンドレットは次のようになります。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   引き続き使用 `Add-MpPreference -ControlledFolderAccessAllowedApplications` して、リストにアプリを追加します。 このコマンドレットを使用して追加されたアプリは、アプリのWindows セキュリティされます。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="アプリを許可する PowerShell コマンドレット。":::

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを使用 `Set-MpPreference` すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM CSP を使用して特定のアプリを許可する

アプリが保護されたフォルダーを変更するには、. [/Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 構成サービス プロバイダー (CSP) を使用します。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する

Microsoft Defender for Endpoint 証明書とファイル インジケーターを使用すると、署名された実行可能ファイルが保護されたフォルダーにアクセスできます。 実装の詳細については、「証明書に [基づいてインジケーターを作成する」を参照してください](indicator-certificates.md)。

> [!Note]
> これは、Powershell を含むスクリプト エンジンには適用されません。

## <a name="customize-the-notification"></a>通知をカスタマイズする

ルールがトリガーされ、アプリまたはファイルをブロックするときに通知をカスタマイズする方法の詳細については、「Configure alert [notifications in Microsoft Defender for Endpoint」を参照してください](configure-email-notifications.md)。

## <a name="see-also"></a>関連項目

- [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
- [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
