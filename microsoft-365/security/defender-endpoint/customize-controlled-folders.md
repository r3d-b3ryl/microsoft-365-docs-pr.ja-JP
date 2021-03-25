---
title: フォルダー アクセスの制御をカスタマイズする
description: フォルダー アクセスを制御して保護する必要がある他のフォルダーを追加するか、重要なファイルへの変更を誤ってブロックしているアプリを許可します。
keywords: フォルダー アクセスの制御、Windows 10、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、カスタマイズ、フォルダーの追加、アプリの追加、許可、実行可能ファイルの追加
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199915"
---
# <a name="customize-controlled-folder-access"></a>フォルダー アクセスの制御をカスタマイズする

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


フォルダー アクセスの制御により、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。 フォルダー アクセスの制御は、Windows Server 2019 および Windows 10 クライアントでサポートされます。

この記事では、フォルダー アクセスの制御機能をカスタマイズする方法について説明し、次のセクションを示します。

- [追加のフォルダーを保護する](#protect-additional-folders)
- [保護されたフォルダーへのアクセスを許可する必要がありますアプリを追加する](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する](#allow-signed-executable-files-to-access-protected-folders)
- [通知をカスタマイズする](#customize-the-notification)

> [!IMPORTANT]
> フォルダー アクセスの制御により、悪意のあるアクティビティが検出されたアプリが監視されます。 場合によっては、正当なアプリがファイルに変更を加えるのをブロックされる場合があります。 フォルダー アクセスの制御が組織の生産性に影響を与える場合は、監査モード[](audit-windows-defender.md)でこの機能を実行して、その影響を完全に評価することもできます。

## <a name="protect-additional-folders"></a>追加のフォルダーを保護する

フォルダー アクセスの制御は、ドキュメント、ピクチャ、ムービーなどのフォルダーを含む、多くのシステムフォルダーと既定の場所 **に適用されます**。 保護するフォルダーを追加できますが、既定の一覧で既定のフォルダーを削除することはできません。

フォルダー アクセスの制御に他のフォルダーを追加すると、既定の Windows ライブラリにファイルを保存しない場合や、ライブラリの既定の場所を変更した場合に役立ちます。

ネットワーク共有とマップされたドライブを指定することもできます。 環境変数とワイルドカードがサポートされています。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。

Windows セキュリティ アプリ、グループ ポリシー、PowerShell コマンドレット、またはモバイル デバイス管理構成サービス プロバイダーを使用して、追加の保護されたフォルダーを追加および削除できます。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Windows セキュリティ アプリを使用して追加のフォルダーを保護する

1. タスク バーでシールド アイコンを選択するか、スタート メニューの [セキュリティ] を検索して、Windows セキュリティ アプリを開 **きます**。

2. [ **ウイルス対策&保護] を** 選択し、[ランサムウェア保護] セクション **まで下にスクロール** します。

3. [ランサムウェア **保護の管理] を** 選択して **、[ランサムウェア保護] ウィンドウを開** きます。

4. [フォルダー アクセス **の制御] セクションで** 、[保護された **フォルダー] を選択します**。

5. [ユーザー **アクセス制御** ] プロンプト **で [はい] を選択** します。 [ **保護されたフォルダー] ウィンドウ** が表示されます。

4. [ **保護されたフォルダーの追加] を選択** し、プロンプトに従ってフォルダーを追加します。

### <a name="use-group-policy-to-protect-additional-folders"></a>グループ ポリシーを使用して追加のフォルダーを保護する

1. グループ ポリシー管理コンピューターで、グループ [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを Windows コンポーネント **の Microsoft** Defender Antivirus  >  **Windows Defender**  >  **に** 展開  >  **します**。

4. [構成済みの **保護されたフォルダー] をダブルクリック** し、オプションを [有効] に **設定します**。 [表示 **] を** 選択し、各フォルダーを入力します。

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell を使用して追加のフォルダーを保護する

1. [**スタート] メニューに「PowerShell」** と入力し、[管理者として実行 **Windows PowerShellを右****クリックし、[管理者として実行] を選択します。**

2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 保護するフォルダーを追加するまで、手順 2 を繰り返します。 追加されたフォルダーは、Windows セキュリティ アプリに表示されます。

   ![上記のコマンドレットが入力された PowerShell ウィンドウのスクリーンショット](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM CSP を使用して追加のフォルダーを保護する

アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 構成サービス プロバイダー (CSP) を使用します。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>特定のアプリが管理フォルダーに変更を加えるのを許可する

特定のアプリが常に安全と見なされる場合を指定し、保護されたフォルダー内のファイルへの書き込みアクセス権を与えることもできます。 アプリを許可すると、特定のアプリが、管理されたフォルダー アクセス機能によってブロックされている場合に便利です。

> [!IMPORTANT]
> 既定では、Windows は許可されたリストに対して使い分け可能と見なされるアプリを追加します。 自動的に追加されるアプリは、Windows セキュリティ アプリに表示される一覧や、関連付けられた PowerShell コマンドレットを使用して記録されません。 ほとんどのアプリを追加する必要はない必要があります。 アプリがブロックされている場合にのみアプリを追加し、信頼度を確認できます。

アプリを追加する場合は、アプリの場所を指定する必要があります。 その場所のアプリだけが、保護されたフォルダーへのアクセスを許可されます。 (同じ名前の) アプリが別の場所にある場合、アプリは許可リストに追加されません。フォルダー アクセスの制御によってブロックされる場合があります。

許可されているアプリケーションまたはサービスは、開始後にのみ、制御フォルダーへの書き込みアクセス権を持つ。 たとえば、更新サービスは、イベントが停止して再起動されるまで、イベントが許可された後も引き続きトリガーされます。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>特定のアプリWindows Defenderを許可するには、セキュリティ アプリを使用する

1. [セキュリティ] のスタート メニューを検索して、Windows セキュリティ アプリを **開きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護の管理] **を選択します**。

3. [フォルダー アクセス **の制御] セクションで** 、[フォルダー アクセス **の制御によるアプリの許可] を選択します。**

4. [ **許可されたアプリを追加する] を選択** し、プロンプトに従ってアプリを追加します。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="許可されたアプリ ボタンを追加する":::

### <a name="use-group-policy-to-allow-specific-apps"></a>グループ ポリシーを使用して特定のアプリを許可する

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを Windows コンポーネント **の Microsoft** Defender Antivirus  >  **Windows Defender**  >  **に** 展開  >  **します**。

4. [許可されたアプリケーションの **構成] 設定をダブルクリック** し、オプションを [有効] に **設定します**。 [表示 **] を** 選択し、各アプリを入力します。

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell を使用して特定のアプリを許可する

1. [**スタート] メニューに「PowerShell」** と入力し、[管理者として実行 **Windows PowerShellを右****クリックし、[管理者として実行] を選択します。**
2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    たとえば *、C:\apps* フォルダーtest.exe実行可能ファイルを追加するには、コマンドレットは次のようになります。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   引き続き使用 `Add-MpPreference -ControlledFolderAccessAllowedApplications` して、リストにアプリを追加します。 このコマンドレットを使用して追加されたアプリは、Windows セキュリティ アプリに表示されます。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="アプリを許可する PowerShell コマンドレット":::

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM CSP を使用して特定のアプリを許可する

アプリが保護されたフォルダーを変更するには [、./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 構成サービス プロバイダー (CSP) を使用します。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する

Microsoft Defender for Endpoint 証明書とファイル インジケーターを使用すると、署名された実行可能ファイルが保護されたフォルダーにアクセスできます。 実装の詳細については、「証明書に [基づいてインジケーターを作成する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)。

> [!Note]
> これは、Powershell を含むスクリプト エンジンには適用されません。

## <a name="customize-the-notification"></a>通知をカスタマイズする

ルールがトリガーされ、アプリまたはファイルをブロックするときに通知をカスタマイズする方法の詳細については、「Configure alert [notification in Microsoft Defender for Endpoint」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)。

## <a name="see-also"></a>関連項目

- [フォルダー アクセスを制御して重要なフォルダーを保護する](controlled-folders.md)
- [フォルダー アクセスの制御を有効にする](enable-controlled-folders.md)
- [攻撃表面の縮小ルールを評価する](evaluate-attack-surface-reduction.md)
