---
title: SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルの機密ラベルサポートを有効にすることができます。
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802830"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)

以前は、SharePoint および OneDrive に格納された Office ファイルへの暗号化を含む機密ラベルを適用すると、サービスはこれらのファイルのコンテンツを処理できませんでした。 このような状況では、共同編集、電子情報開示、データ損失防止、検索、Delve、その他のコラボレーション機能は使用できません。 このプレビューでは、次の機能を有効にします。

- SharePoint は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。 SharePoint では、各ラベルに対応する設定も適用されます。

- SharePoint または OneDrive からファイルをダウンロードすると、機密ラベルがファイルと共に移動し、設定が適用されたままになります。

- Office ファイルに機密ラベルを適用し、機密ラベルが適用されている (ラベルのアクセス許可が許可されている場合) ファイルを開いて編集するには、Word、Excel、および PowerPoint の web バージョンを使用します。 Word on the web では、ドキュメントを編集するときに自動ラベル付けを使用することもできます。

- Office 365 eDiscovery は、機密ラベルが適用されているファイル内のフルテキスト検索をサポートします。 データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。

- 機密ラベルの監視に使用できる3つの新しい監査イベントがあります。
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

また、Microsoft Teams、Office 365 グループ、および SharePoint サイトに機密ラベルを適用できるようになりました。 [詳細情報](sensitivity-labels-teams-groups-sites.md) を参照してください。

必要に応じて、いつでもプレビューの表示を中止することができます。

## <a name="requirements"></a>要件

これらの機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。 Azure Information Protection ラベルを使用した場合は、それらを機密ラベルに変換して、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。 [方法について説明します。](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

このプレビューでは、Windows とバージョン19.002.0107.0008 以降の Mac の OneDrive 同期アプリバージョン19.002.0121.0008 を使用します。 これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。 [OneDrive リリースノートを参照してください](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 このプレビューを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- このプレビューを有効にすると、Office デスクトップまたはモバイルアプリを使用してファイルにラベルを適用するユーザーは、ファイルに加えた他の変更を保存できない場合があります。 代わりに、アプリはユーザーにローカルの変更を保存するか、破棄するかを確認します。 作業が失われるのを防ぐには、次のいずれかの操作を行います。

  - ラベルを適用するには、Office アプリの web 版を使用します。

  - ラベルを適用した後でファイルを閉じてから、他の変更を行うためにファイルを再度開いてください。

- SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに新しいラベルが自動的に適用されることはありません。 代わりに、このプレビューを有効にした後で機能を使用できるようにするには、次のタスクを完了します。

  - Azure Information Protection ラベルを機密ラベルに変換します。

  - ファイルをダウンロードし、それらを SharePoint にアップロードします。

- SharePoint では、カスタムアクセス許可と、有効期限のあるラベルを処理することはできません。

- ユーザーが編集アクセス許可を持っている場合、Office アプリの web 版では、ラベルのコピーポリシー設定に関係なくコピーが許可されます。

- RMS の失効、追跡、およびレポートはサポートされていません。

- Office デスクトップアプリとモバイルアプリは共同編集をサポートしていません。 代わりに、これらのアプリは引き続き、排他編集モードでファイルを開きます。

- ラベルに暗号化が含まれている場合、Microsoft Cloud App Security は SharePoint のファイルのラベル情報を読み取ることができません。

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>プレビュー用の SharePoint Online 管理シェルの準備

プレビューを有効にする前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。 最新バージョンが既にある場合は、プレビューを有効にすることができます。

1. 以前のバージョンの SharePoint Online Management Shell を PowerShell ギャラリーからインストールした場合は、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。

3. Web ブラウザーで、ダウンロードセンターページに移動して、[最新の SharePoint Online 管理シェルをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=255251)します。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. X64 ファイルと x86 .msi ファイルのどちらかを選択します。 64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。 不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。


6. ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Microsoft PowerShell を使用してプレビューを有効にする (オプトイン)

プレビューを有効にするには、Set-spotenant コマンドレットを使用します。

1. Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint のオンライン管理シェルを使うにあたって](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

2. 次のコマンドを実行します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>機密ラベルを作成または変更した後のロールアウトをスケジュールする

Microsoft 365 コンプライアンスセンターで機密ラベルを作成または変更した後、それを段階的に公開します。 完全に同期されていないラベルを発行した場合、ユーザーがファイルにラベルを適用してそれらを SharePoint にアップロードすると、ファイルを web 版の Office アプリで開くことができなくなります。 検索と電子情報開示もファイルに対して機能しません。

次の手順を実行することをお勧めします。

1. 新しいまたは変更された機密ラベルを1人または2人のユーザーにのみ発行します。

2. 最初の発行の後、少なくとも24時間待機します。 ラベルが完全に同期していることを確認します。

3. ラベルを広く公開します。

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Microsoft PowerShell を使用してプレビューを無効にする (オプトアウト)

このプレビューを無効にすると、プレビュー時にアップロードしたファイルはラベルで保護されたままになります。 対応する設定は引き続き適用されます。 プレビューを無効にした後、新しいファイルにラベルを適用すると、フルテキスト検索、電子情報開示、および共同編集は機能しなくなります。

プレビューを無効にするには、Set-spotenant コマンドレットを使用します。

1. Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint のオンライン管理シェルを使うにあたって](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

2. 次のコマンドを実行します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
