---
title: 制御されたフォルダー アクセスをカスタマイズする
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
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d8db481c06df22592897389656601be2dc9ab0c4
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53657305"
---
# <a name="customize-controlled-folder-access"></a>制御されたフォルダー アクセスをカスタマイズする

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

フォルダー アクセスの制御により、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。 フォルダー アクセスの制御は、サーバー 2019 WindowsクライアントでWindows 10されます。 この記事では、フォルダー アクセスの制御機能をカスタマイズする方法について説明し、次のセクションを示します。

- [追加のフォルダーを保護する](#protect-additional-folders)
- [保護されたフォルダーへのアクセスを許可する必要がありますアプリを追加する](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する](#allow-signed-executable-files-to-access-protected-folders)
- [通知をカスタマイズする](#customize-the-notification)

> [!IMPORTANT]
> フォルダー アクセスの制御により、悪意のあるアクティビティが検出されたアプリが監視されます。 場合によっては、正当なアプリがファイルに変更を加えるのをブロックされる場合があります。 フォルダー アクセスの制御が組織の生産性に影響を与える場合は、監査モード[](audit-windows-defender.md)でこの機能を実行して、その影響を完全に評価することもできます。

## <a name="protect-additional-folders"></a>追加のフォルダーを保護する

フォルダー アクセスの制御は、ドキュメント、ピクチャ、ムービーなどのフォルダーを含む、多くのシステムフォルダーと既定の場所 **に適用されます**。 保護する他のフォルダーを追加できますが、既定の一覧で既定のフォルダーを削除することはできません。

他のフォルダーを制御されたフォルダー アクセスに追加すると、既定の Windows ライブラリにファイルを保存しない場合や、ライブラリの既定の場所を変更した場合に役立ちます。

ネットワーク共有とマップされたドライブを指定することもできます。 環境変数とワイルドカードがサポートされています。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

保護されたフォルダーを追加および削除するには、Windows セキュリティ アプリ、グループ ポリシー、PowerShell コマンドレット、またはモバイル デバイス管理構成サービス プロバイダーを使用できます。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>アプリを使用Windows セキュリティフォルダーを保護する

1. タスク バー Windows セキュリティシールド アイコンを選択するか、タスク バーでセキュリティを検索して、アプリを開スタート メニュー。

2. [ **ウイルス対策&保護] を** 選択し、[ランサムウェア保護] セクション **まで下にスクロール** します。

3. [ランサムウェア **保護の管理] を** 選択して **、[ランサムウェア保護] ウィンドウを開** きます。

4. [フォルダー アクセス **の制御] セクションで** 、[保護された **フォルダー] を選択します**。

5. [ユーザー **アクセス制御** ] プロンプト **で [はい] を選択** します。 [ **保護されたフォルダー] ウィンドウ** が表示されます。

6. [ **保護されたフォルダーの追加] を選択** し、プロンプトに従ってフォルダーを追加します。

### <a name="use-group-policy-to-protect-additional-folders"></a>グループ ポリシーを使用して追加のフォルダーを保護する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)を開きます。 

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー **管理エディターで、[****コンピューター構成ポリシー**]  >  **[管理**  >  **用テンプレート] に移動します**。

4. ツリーを展開して **、Exploit** Guard Windowsフォルダー アクセスMicrosoft Defender ウイルス対策Windows Defender  >    >  **コンポーネント**  >  **を展開します**。 <br/>**注**: 以前のバージョンの Windowsでは、以前のバージョン **Windows Defender ウイルス対策表示される** 場合 **Microsoft Defender ウイルス対策。**

5. [構成済みの **保護されたフォルダー] を** ダブルクリックし、オプションを [有効] に **設定します**。 [ **表示] を** 選択し、保護する各フォルダーを指定します。

6. 通常と同じ方法でグループ ポリシー オブジェクトを展開します。

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell を使用して追加のフォルダーを保護する

1. **[PowerShell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**

2. 次の PowerShell コマンドレットを入力し、フォルダーのパス (など) `<the folder to be protected>` に置き換えてください `"c:\apps\"` 。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 保護するフォルダーごとに手順 2 を繰り返します。 保護されているフォルダーは、アプリ内にWindows セキュリティされます。

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="コマンドレットが表示された PowerShell ウィンドウ":::

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します `Set-MpPreference` 。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM CSP を使用して追加のフォルダーを保護する

アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 構成サービス プロバイダー (CSP) を使用します。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>特定のアプリが管理フォルダーに変更を加えるのを許可する

特定のアプリが常に安全と見なされる場合を指定し、保護されたフォルダー内のファイルへの書き込みアクセス権を与えることもできます。 アプリを許可すると、特定のアプリが、管理されたフォルダー アクセス機能によってブロックされている場合に便利です。

> [!IMPORTANT]
> 既定では、Windowsリストに対してフレンドリーと見なされるアプリが追加されます。 自動的に追加されるこのようなアプリは、アプリに表示される一覧や、Windows セキュリティ PowerShell コマンドレットを使用して記録されません。 ほとんどのアプリを追加する必要はない必要があります。 アプリがブロックされている場合にのみアプリを追加し、信頼度を確認できます。

アプリを追加する場合は、アプリの場所を指定する必要があります。 その場所のアプリだけが、保護されたフォルダーへのアクセスを許可されます。 (同じ名前の) アプリが別の場所にある場合、アプリは許可リストに追加されません。フォルダー アクセスの制御によってブロックされる場合があります。

許可されているアプリケーションまたはサービスは、開始後にのみ、制御フォルダーへの書き込みアクセス権を持つ。 たとえば、更新サービスは、イベントが停止して再起動されるまで、イベントが許可された後も引き続きトリガーされます。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>特定のアプリWindows Defenderセキュリティ アプリを使用する

1. [セキュリティ] Windows セキュリティスタート メニューを検索して、アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護の管理] **を選択します**。

3. [フォルダー アクセス **の制御] セクションで** 、[フォルダー アクセス **の制御によるアプリの許可] を選択します。**

4. [ **許可されたアプリを追加する] を選択** し、プロンプトに従ってアプリを追加します。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="許可されたアプリ ボタンを追加する":::

### <a name="use-group-policy-to-allow-specific-apps"></a>グループ ポリシーを使用して特定のアプリを許可する

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して **、Exploit** Guard Windowsフォルダー アクセスMicrosoft Defender ウイルス対策Windows Defender  >    >  **コンポーネント**  >  **を展開します**。

4. [許可されたアプリケーションの **構成] 設定をダブルクリック** し、オプションを [有効] に **設定します**。 [表示 **] を** 選択し、各アプリを入力します。

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell を使用して特定のアプリを許可する

1. **[PowerShell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**
2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    たとえば *、C:\apps* フォルダーtest.exe実行可能ファイルを追加するには、コマンドレットは次のようになります。

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   引き続き使用 `Add-MpPreference -ControlledFolderAccessAllowedApplications` して、リストにアプリを追加します。 このコマンドレットを使用して追加されたアプリは、アプリのWindows セキュリティされます。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="アプリを許可する PowerShell コマンドレット":::

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM CSP を使用して特定のアプリを許可する

アプリが保護されたフォルダーを変更するには [、./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 構成サービス プロバイダー (CSP) を使用します。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>署名された実行可能ファイルに保護されたフォルダーへのアクセスを許可する

Microsoft Defender for Endpoint 証明書とファイル インジケーターを使用すると、署名された実行可能ファイルが保護されたフォルダーにアクセスできます。 実装の詳細については、「証明書に [基づいてインジケーターを作成する」を参照してください](indicator-certificates.md)。

> [!Note]
> これは、Powershell を含むスクリプト エンジンには適用されません。

## <a name="customize-the-notification"></a>通知をカスタマイズする

ルールがトリガーされ、アプリまたはファイルをブロックするときに通知をカスタマイズする方法の詳細については、「Configure alert [notification in Microsoft Defender for Endpoint」を参照してください](configure-email-notifications.md)。

## <a name="see-also"></a>関連項目

- [フォルダーへのアクセス制御で重要なフォルダーを保護する](controlled-folders.md)
- [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
