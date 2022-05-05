---
title: 制御されたフォルダー アクセスをカスタマイズする
description: フォルダー アクセスの制御によって保護する必要がある他のフォルダーを追加するか、重要なファイルへの変更を誤ってブロックしているアプリを許可します。
keywords: フォルダー アクセスの制御、Windows 10、Windows 11、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、カスタマイズ、フォルダーの追加、アプリの追加、許可、実行可能ファイルの追加
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
ms.openlocfilehash: ba9102f96ea08bf33f72a260779b4b37d6a6f0f4
ms.sourcegitcommit: b3f5fe84a319741583954ef8ff2ec9ec6da69bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217378"
---
# <a name="customize-controlled-folder-access"></a>制御されたフォルダー アクセスをカスタマイズする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

フォルダー アクセスの制御は、ランサムウェアなどの悪意のあるアプリや脅威から貴重なデータを保護するのに役立ちます。 フォルダー アクセスの制御は、Windows Server 2019、Windows Server 2022、Windows 10、Windows 11 クライアントでサポートされています。 この記事では、制御されたフォルダー アクセス機能をカスタマイズする方法について説明し、次のセクションを含みます。

- [追加のフォルダーを保護する](#protect-additional-folders)
- [保護されたフォルダーへのアクセスを許可する必要があるアプリを追加する](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する](#allow-signed-executable-files-to-access-protected-folders)
- [通知をカスタマイズする](#customize-the-notification)

> [!IMPORTANT]
> フォルダー アクセスを制御すると、悪意があると検出されたアクティビティについてアプリが監視されます。 正当なアプリがファイルに変更を加えるのをブロックされる場合があります。 フォルダー アクセスの制御が組織の生産性に影響する場合は、この機能を [監査モード](audit-windows-defender.md) で実行して影響を完全に評価することを検討してください。

## <a name="protect-additional-folders"></a>追加のフォルダーを保護する

フォルダー アクセスの制御は、 **ドキュメント**、 **画像**、ムービーなどのフォルダーを含む、多くのシステム フォルダーと既定の場所に適用 **されます**。 保護する他のフォルダーは追加できますが、既定の一覧で既定のフォルダーを削除することはできません。

既定のWindows ライブラリにファイルを格納しない場合や、ライブラリの既定の場所を変更した場合に、フォルダー アクセスの制御に他のフォルダーを追加すると便利です。

ネットワーク共有とマップされたドライブを指定することもできます。 環境変数とワイルドカードがサポートされています。 ワイルドカードの使用の詳細については、「 [ファイル名とフォルダーパスまたは拡張子の除外リストでワイルドカードを使用](configure-extension-file-exclusions-microsoft-defender-antivirus.md)する」を参照してください。

Windows セキュリティ アプリ、グループ ポリシー、PowerShell コマンドレット、モバイル デバイス管理構成サービス プロバイダーを使用して、保護されたフォルダーを追加および削除できます。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Windows セキュリティ アプリを使用して追加のフォルダーを保護する

1. タスク バーでシールド アイコンを選択するか、スタート メニューで *セキュリティ* を検索して、Windows セキュリティ アプリを開きます。

2. [ **ウイルス&脅威の防止**] を選択し、[ **ランサムウェアの保護** ] セクションまで下にスクロールします。

3. [ **ランサムウェア保護の管理** ] を選択して、[ **ランサムウェアの保護** ] ウィンドウを開きます。

4. [ **フォルダー アクセスの制御** ] セクションで、[ **保護されたフォルダー**] を選択します。

5. **ユーザー Access Control** プロンプトで **[はい**] を選択します。 [ **保護されたフォルダー] ウィンドウが** 表示されます。

6. [ **保護されたフォルダーの追加]** を選択し、プロンプトに従ってフォルダーを追加します。

### <a name="use-group-policy-to-protect-additional-folders"></a>グループ ポリシーを使用して追加のフォルダーを保護する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)を開きます。 

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

3. **グループ ポリシー管理エディター** で、**コンピューター構成** \> **ポリシー** \> **管理テンプレート** に移動します。

4. ツリーを展開して、**Exploit Guard** \> **によって制御されたフォルダー へのアクセス****Windows Defender Microsoft Defender ウイルス対策** \> **コンポーネント**\>をWindowsします。 <br/>**注**: 以前のバージョンのWindowsでは、**Microsoft Defender ウイルス対策ではなくWindows Defender ウイルス対策** が表示される場合 **があります。**

5. **[構成済みの保護フォルダー**] をダブルクリックし、オプションを **[有効]** に設定します。 [ **表示]** を選択し、保護する各フォルダーを指定します。

6. 通常どおり、グループ ポリシー オブジェクトをデプロイします。

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell を使用して追加のフォルダーを保護する

1. スタート メニューに **「PowerShell**」と入力し、**Windows PowerShell** 右クリックして **[管理者として実行**] を選択します

2. 次の PowerShell コマンドレットを入力し `<the folder to be protected>` 、フォルダーのパス (次のように `"c:\apps\"`) に置き換えます。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 保護するフォルダーごとに手順 2 を繰り返します。 保護されているフォルダーは、Windows セキュリティ アプリに表示されます。

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="コマンドレットが表示された PowerShell ウィンドウ" lightbox="images/cfa-allow-folder-ps.png":::

> [!IMPORTANT]
> リストにアプリを追加または追加する場合に使用 `Add-MpPreference` します。アプリは追加しません `Set-MpPreference`。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM CSP を使用して追加のフォルダーを保護する

[./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 構成サービス プロバイダー (CSP) を使用して、アプリが保護されたフォルダーを変更できるようにします。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>特定のアプリが制御されたフォルダーに変更を加えることを許可する

特定のアプリが常に安全であると見なされ、保護されたフォルダー内のファイルへの書き込みアクセス権を付与するかどうかを指定できます。 アプリの許可は、特定のアプリがフォルダー アクセスの制御機能によってブロックされている場合に便利です。

> [!IMPORTANT]
> 既定では、Windowsは許可されたリストに対してフレンドリと見なされるアプリを追加します。 自動的に追加されるこのようなアプリは、Windows セキュリティ アプリに表示される一覧や、関連付けられた PowerShell コマンドレットを使用して記録されません。 ほとんどのアプリを追加する必要はありません。 アプリがブロックされ、その信頼性を確認できる場合にのみ、アプリを追加します。

アプリを追加するときは、アプリの場所を指定する必要があります。 その場所にあるアプリのみが、保護されたフォルダーへのアクセスを許可されます。 アプリ (同じ名前) が別の場所にある場合、アプリは許可リストに追加されず、フォルダー アクセスの制御によってブロックされる可能性があります。

許可されたアプリケーションまたはサービスは、制御されたフォルダーの開始後にのみ書き込みアクセス権を持ちます。 たとえば、更新サービスは、停止して再起動するまで、許可された後も引き続きイベントをトリガーします。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Windows Defender セキュリティ アプリを使用して特定のアプリを許可する

1. [**セキュリティ**] の [スタート] メニューを検索して、Windows セキュリティ アプリを開きます。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[**ランサムウェア保護の管理**] を選択します。

3. [**フォルダー アクセスの制御**] セクションで、[**フォルダー アクセスの制御によるアプリの許可**] を選択します。

4. [ **許可されたアプリの追加]** を選択し、プロンプトに従ってアプリを追加します。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="[許可されたアプリの追加] ボタン" lightbox="images/cfa-allow-app.png":::

### <a name="use-group-policy-to-allow-specific-apps"></a>グループ ポリシーを使用して特定のアプリを許可する

1. グループ ポリシー管理デバイスで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して、**Exploit Guard** \> **によって制御されたフォルダー へのアクセス****Windows Defender Microsoft Defender ウイルス対策** \> **コンポーネント**\>をWindowsします。

4. [ **許可されるアプリケーションの構成]** 設定をダブルクリックし、オプションを **[有効]** に設定します。 [ **表示** ] を選択し、各アプリを入力します。

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell を使用して特定のアプリを許可する

1. スタート メニューに **「PowerShell**」と入力し、**Windows PowerShell** 右クリックして **[管理者として実行**] を選択します
2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    たとえば、フォルダー *C:\apps* にある実行可能 *ファイルtest.exe* を追加するには、コマンドレットは次のようになります。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   引き続き使用 `Add-MpPreference -ControlledFolderAccessAllowedApplications` して、リストにアプリを追加します。 このコマンドレットを使用して追加されたアプリは、Windows セキュリティ アプリに表示されます。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="アプリケーションを許可する PowerShell コマンドレット" lightbox="images/cfa-allow-app-ps.png":::

> [!IMPORTANT]
> リストにアプリを追加または追加するために使用 `Add-MpPreference` します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM CSP を使用して特定のアプリを許可する

[./Vendor/MSFT/Policy/Config/Defender/ControlledFolderAccessAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 構成サービス プロバイダー (CSP) を使用して、アプリが保護されたフォルダーに変更を加えるようにします。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する

Microsoft Defender for Endpoint証明書インジケーターとファイル インジケーターを使用すると、署名された実行可能ファイルから保護されたフォルダーにアクセスできます。 実装の詳細については、「 [証明書に基づくインジケーターの作成](indicator-certificates.md)」を参照してください。

> [!Note]
> これは、Powershell を含むスクリプト エンジンには適用されません。

## <a name="customize-the-notification"></a>通知をカスタマイズする

ルールがトリガーされ、アプリまたはファイルがブロックされたときに通知をカスタマイズする方法の詳細については、「[Microsoft Defender for Endpointでアラート通知を構成する」を](configure-email-notifications.md)参照してください。

## <a name="see-also"></a>関連項目

- [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
- [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
