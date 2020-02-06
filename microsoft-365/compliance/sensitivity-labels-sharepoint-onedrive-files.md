---
title: SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルの機密ラベルサポートを有効にすることができます。
ms.openlocfilehash: 97d46c7fce851e420c33763260c88e948718840f
ms.sourcegitcommit: 0f09f54f43924d1fcd2fdcfcbf04c53519b92a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2020
ms.locfileid: "41784684"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)

このプレビューの前に、SharePoint および OneDrive に格納されている Office ファイルへの暗号化を含む機密ラベルを適用すると、サービスはこれらのファイルのコンテンツを処理できませんでした。 このような状況では、共同編集、電子情報開示、データ損失防止、検索、Delve、その他のコラボレーション機能は使用できません。 次のプレビューでは、クラウドベースのキーで暗号化が適用されている場合に、次の機能が有効になります。

- SharePoint は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。 SharePoint では、各ラベルに対応する設定も適用されます。

- SharePoint または OneDrive からファイルをダウンロードすると、機密ラベルがファイルと共に移動し、設定が適用されたままになります。

- Office ファイルに機密ラベルを適用し、機密ラベルが適用されている (ラベルのアクセス許可が許可されている場合) ファイルを開いて編集するには、Word、Excel、および PowerPoint の web バージョンを使用します。 Word on the web では、ドキュメントを編集するときに自動ラベル付けを使用することもできます。

- Office 365 eDiscovery は、機密ラベルが適用されているファイル内のフルテキスト検索をサポートします。 データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。

- 機密ラベルの監視に使用できる3つの新しい監査イベントがあります。
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

> [!NOTE]
> クラウドベースのキーで暗号化が適用されておらず、オンプレミスキーであっても、"自分のキーを保持する" と呼ばれるキー管理トポロジ (HYOK) では、SharePoint の動作はこのプレビューでは変更されません。 

また、Microsoft Teams、Office 365 グループ、および SharePoint サイトに機密ラベルを適用できるようになりました。 この個別のプレビューの詳細については、「 [Microsoft Teams、Office 365 グループ、および SharePoint サイト (パブリックプレビュー) を使用して機密ラベルを使用する](sensitivity-labels-teams-groups-sites.md)」を参照してください。

いつでもこのプレビューの選択を解除することができます。

次のビデオ (オーディオはない) を見て、これらの新機能をご確認ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>Requirements

これらの機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。 現在 Azure Information Protection のラベルがある場合は、それらを機密ラベルに移行してから、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。 手順については、「 [Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)」を参照してください。

このプレビューでは、Windows で OneDrive 同期アプリのバージョン19.002.0121.0008 以降、バージョン19.002.0107.0008 以降の Mac を使用します。 これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。 詳細については、 [OneDrive リリースノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。 このプレビューを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- このプレビューを有効にすると、OneDrive Sync フォルダー内のファイルのラベルを変更したユーザーは、ファイルに加えた他の変更を保存できない場合があります。  [白い十字アイコンのエラー](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示された赤い円が表示され、新しい変更内容を別のコピーとして保存するように求められます。  ユーザーによって開始されたラベルの変更に加えて、管理者が、既にユーザーの同期クライアントにダウンロードしたファイルに適用されている発行済みラベルの設定を変更した場合にも、同じ現象が発生することがあります。
    
    これらのシナリオの作業を失わないようにするには、次のいずれかの操作を行います。
    - ラベルを適用するには、Office アプリの web 版を使用します。
    - ラベルを適用した後、ファイルを閉じてから、他の変更を行うためにファイルを開きます。

- SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに新しいラベルが自動的に適用されることはありません。 代わりに、このプレビューを有効にした後で機能を使用できるようにするには、次のタスクを完了します。
    
    1. Azure Information Protection ラベルを機密ラベルに移行し、Microsoft 365 コンプライアンスセンター (または同等のラベル付き管理センター) から公開していることを確認してください。
    
    2. ファイルをダウンロードし、それらを SharePoint にアップロードします。

- 暗号化を適用したラベルが暗号化に使用する次のいずれかの構成を持っている場合、SharePoint は暗号化されたファイルを処理できません。
    - **ユーザーがラベルを適用するときにアクセス許可を割り当てる** **、Word、PowerPoint、および Excel に**ユーザーがアクセス許可を指定できるようにする
    - **コンテンツへのユーザーアクセスの有効期限**が、 **Never**以外の値に設定されています。

- ユーザーに編集権限を付与する暗号化されたドキュメントの場合、Office アプリの web 版ではコピーをブロックすることはできません。

- Azure Information Protection ドキュメント追跡サイトはサポートされていません。

- Office デスクトップアプリとモバイルアプリは共同編集をサポートしていません。 代わりに、これらのアプリは引き続き、排他編集モードでファイルを開きます。

- ラベルに暗号化が含まれている場合、Microsoft Cloud App Security は SharePoint のファイルのラベル情報を読み取ることができません。

- ラベル付きドキュメントが SharePoint にアップロードされ、そのラベルがサービスプリンシパル名のアカウントを使用して暗号化されている場合、そのドキュメントは web 上の Office では開くことができません。 シナリオの例としては、Microsoft Cloud App Security と、電子メールで Teams に送信されるファイルがあります。

- 次の方法で暗号化されたドキュメントは、web 上の Office で開くことができません。
    - オンプレミスキー ("自分のキーを保持する" または HYOK) を使用する暗号化
    - ラベルとは独立して適用された暗号化。たとえば、Rights Management protection テンプレートを直接適用します。

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>プレビュー用の SharePoint Online 管理シェルの準備

プレビューを有効にする前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。 最新バージョンが既にある場合は、プレビューを有効にすることができます。

1. 以前のバージョンの SharePoint Online Management Shell を PowerShell ギャラリーからインストールした場合は、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。 不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。


6. ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Microsoft PowerShell を使用してプレビューを有効にする (オプトイン)

プレビューを有効にするには、Set-spotenant コマンドレットを使用します。

1. Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

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

1. Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

2. 次のコマンドを実行します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
