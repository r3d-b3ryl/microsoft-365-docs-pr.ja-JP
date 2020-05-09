---
title: SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする
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
ms.openlocfilehash: bb35d4ed287e87ba17780c0e7106b837beb9666a
ms.sourcegitcommit: 758263ad484e00f5a561a47c8c22d5787af7671e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44170916"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にする前に、web 上の Office に[機密ラベル](sensitivity-labels.md)を適用することはできません。 リボンに [**秘密度**] ボタン、またはステータスバーに適用されるラベル名が表示されません。 さらに、デスクトップアプリを使用してファイルにラベルを付け、それらを SharePoint または OneDrive に保存する場合、ラベルが暗号化を適用した場合、サービスはこれらのファイルのコンテンツを処理できません。 共同編集、電子情報開示、データ損失防止、検索、およびその他の共同作業機能は、これらの状況では機能しません。

SharePoint および OneDrive で Office ファイルの機密ラベルを有効にする場合、これらすべての機能が有効になります。 機密ラベルをユーザーに表示することに加えて、クラウドベースのキーを使用した暗号化を含む、新しいファイルと変更されたファイルについては、次のようにします。

- Sharepoint は、sharepoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。ファイルが SharePoint に格納されている間は、ファイルの内容を処理できるように、Azure Information Protection からの暗号化が削除されます。 SharePoint に保存されているドキュメントを保護する方法については、「 [OneDrive for business および Sharepoint Online のデータ暗号化](data-encryption-in-odb-and-spo.md)」を参照してください。

- このファイルを SharePoint または OneDrive からダウンロードするか、またはそのファイルにアクセスすると、ラベルからの暗号化設定がファイルに再適用され、これらの設定はファイルが保存されているすべての場所に適用されたままになります。 この動作により、ドキュメントを保護するためにラベルのみを使用するようにユーザーガイダンスが提供されます。 詳細については、「 [Information Rights Management (IRM) のオプション」および「機密ラベル](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)」を参照してください。

- アップロード時に SharePoint がファイルから暗号化を削除するには、ラベル付きおよび暗号化されたファイルをアップロードするユーザーは、少なくともファイルを表示するための使用権限を持っている必要があります。 ユーザーが SharePoint の外部でファイルを開くことができない場合、SharePoint はファイルから暗号化を削除しません。

- Web 上の Office (Word、Excel、PowerPoint) を使用して、暗号化を適用する機密ラベルが設定された Office ファイルを開いて編集します。 暗号化によって割り当てられたアクセス許可が適用されます。 Word on the web では、これらの文書を編集するときに自動ラベルを使用することもできます。

- Office 365 電子情報開示では、これらのファイルのフルテキスト検索がサポートされています。 データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。

> [!NOTE]
> 暗号化がクラウドベースのキーではなく、オンプレミスキーで適用されていない場合、キー管理トポロジ (HYOK) と呼ばれることもありますが、ファイルコンテンツを処理するための SharePoint の動作は変わりません。
>
> Sharepoint の動作は、SharePoint の既存のラベル付きファイルと暗号化されたファイルに対しても変わりません。 これらのファイルが新しい機能を利用できるようにするには、コマンドを実行して SharePoint と OneDrive の機密ラベルを有効にした後、それらのファイルをダウンロードしてアップロードするか、または編集する必要があります。 たとえば、それらは検索と電子情報開示の結果として返されます。

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にした後、次の3つの新しい[監査イベント](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)を使用して、Sharepoint と onedrive のドキュメントに適用される機密ラベルを監視できます。
- **ファイルに適用された機密ラベル**
- **ファイルに適用された機密ラベルの変更**
- **ファイルから削除された機密ラベル**

次のビデオ (オーディオなし) を見て、新しい機能を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

SharePoint および OneDrive では、Office ファイルの機密ラベルを無効にするかどうかをいつでも選択できます ([オプトアウト)](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 。

## <a name="requirements"></a>要件

これらの新機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。 現在 Azure Information Protection のラベルがある場合は、それらを機密ラベルに移行してから、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。 手順については、「 [Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)」を参照してください。

OneDrive sync app バージョン19.002.0121.0008 以降、またはバージョン19.002.0107.0008 以降の Mac を使用します。 これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。 詳細については、 [OneDrive リリースノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。 SharePoint と OneDrive で Office ファイルの機密ラベルを有効にした後、古いバージョンの同期アプリを実行しているユーザーには、更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに機密ラベルが自動的に適用されることはありません。 代わりに、SharePoint および OneDrive で Office ファイルの機密ラベルを有効にした後に機能を使用できるようにするには、次のタスクを完了します。
    
    1. [Azure Information Protection ラベル](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)を機密ラベルに移行し、Microsoft 365 コンプライアンスセンター (または同等のラベル付き管理センター) から[公開](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)していることを確認してください。
    
    2. ファイルをダウンロードしてから、それらを SharePoint にアップロードします。

- 暗号化を適用したラベルが[暗号化に使用](encryption-sensitivity-labels.md#configure-encryption-settings)する次のいずれかの構成を持っている場合、SharePoint は暗号化されたファイルを処理できません。
    - ユーザーがラベルと Word、PowerPoint、Excel のチェックボックスを**適用するときにアクセス許可を割り当てること**ができるようにし **、[アクセス許可を指定するようユーザーに要求する]** を選択します。 この設定は、"ユーザー定義の権限" と呼ばれることがあります。
    - **コンテンツへのユーザーアクセスの有効期限**が、 **Never**以外の値に設定されています。
    
    これらの暗号化構成のいずれかを使用したラベルの場合、web 上の Office のユーザーにはラベルが表示されません。 また、これらの暗号化設定を既に持っているラベル付きドキュメントでは、新しい機能を使用できません。 たとえば、これらのドキュメントは、更新された場合でも、検索結果では返されません。

- ユーザーに編集権限を付与する暗号化されたドキュメントの場合、Office アプリの web 版ではコピーをブロックすることはできません。

- Azure Information Protection ドキュメント追跡サイトはサポートされていません。

- Office デスクトップアプリとモバイルアプリは、暗号化によってラベルが付けられたファイルの共同編集をサポートしていません。 これらのアプリは、ラベル付きで暗号化されたファイルを排他編集モードで引き続き開きます。

- ユーザーの同期クライアントにダウンロードしたファイルに既に適用されている発行済みのラベルの設定が管理者によって変更された場合、ユーザーが OneDrive Sync フォルダーのファイルに加えた変更を保存できないことがあります。 このシナリオは、暗号化のラベルが付けられたファイルに適用されます。また、暗号化を適用したラベルに暗号化が適用されなかったラベルからラベルが変更された場合にも適用されます。 [白い十字アイコンのエラー](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示された赤い円が表示され、新しい変更内容を別のコピーとして保存するように求められます。 代わりに、ファイルを閉じて開き直すことができます。また、web 上の Office を使用することもできます。

- ラベル付きのドキュメントが SharePoint にアップロードされ、そのラベルがサービスプリンシパル名のアカウントを使用して暗号化されている場合、そのドキュメントを web 上の Office で開くことはできません。 シナリオの例としては、Microsoft Cloud App Security と、電子メールで Teams に送信されるファイルがあります。

- ユーザーは、web 用の Office を使用する代わりに、オフラインまたはスリープモードに移行した後に、Word、Excel、または PowerPoint 用のデスクトップおよびモバイルアプリを使用して、保存の問題を発生させることができます。 これらのユーザーは、Office アプリセッションを再開して変更を保存しようとすると、元のファイルを保存するのではなく、コピーを保存するためのオプションを含むアップロードエラーメッセージが表示されます。 

- 次の方法で暗号化されたドキュメントは、web 上の Office で開くことができません。
    - オンプレミスキー ("自分のキーを保持する" または HYOK) を使用する暗号化
    - ラベルとは独立して適用された暗号化。たとえば、Rights Management protection テンプレートを直接適用します。

- SharePoint でドキュメントに適用されているラベルを削除する場合、該当するラベルポリシーからラベルを削除するのではなく、ダウンロードしたドキュメントがラベル付けまたは暗号化されないようにします。 比較すると、ラベル付きドキュメントが SharePoint の外部に保存されている場合、ラベルが削除されてもドキュメントは暗号化されたままになります。 テストフェーズではラベルを削除することもできますが、運用環境でラベルを削除するのは非常にまれです。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint および OneDrive の機密ラベルを有効にする方法 (オプトイン)

新しい機能は、Microsoft 365 コンプライアンスセンターまたは PowerShell を使用して有効にすることができます。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>コンプライアンスセンターを使用して機密ラベルのサポートを有効にする

このオプションは、SharePoint と OneDrive の機密ラベルを有効にする最も簡単な方法です。

組織のグローバル管理者には、秘密度ラベルのすべての側面を作成および管理するための完全な権限があります。 グローバル管理者としてサインインしていない場合は、「[機密ラベルの作成と管理に必要なアクセス許可](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)」を参照してください。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)にサインインし、[**ソリューション** > **情報保護**] に移動します。
    
    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。 

2. Office online ファイルのコンテンツを処理する機能を有効にするメッセージが表示された場合は、[**今すぐ有効**にする] を選択します。
    
    ![[今すぐ開始] ボタンをオンにして、Office Online の機密ラベルを有効にする](../media/sensitivity-labels-turn-on-banner.png)
    
    コマンドはすぐに実行され、ページが次に更新されるときに、メッセージまたはボタンが表示されなくなります。 

> [!NOTE]
> 複数地域の Office 365 を使用している場合は、PowerShell を使用して、すべての地域の場所に対してこれらの機能を有効にする必要があります。 詳細については、次のセクションを参照してください。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell を使用して機密ラベルのサポートを有効にする

コンプライアンスセンターを使用する代わりに、SharePoint Online PowerShell から[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを使用して、機密ラベルのサポートを有効にすることができます。 

複数地域の Office 365 がある場合は、PowerShell を使用して、すべての地域の場所でこのサポートを有効にする必要があります。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 管理シェルの準備

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にするために PowerShell コマンドを実行する前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。 最新バージョンが既にインストールされている場合は、[次の手順](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)に進んで PowerShell コマンドを実行できます。

1. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。 不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。

6. ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell コマンドを実行して機密ラベルのサポートを有効にする

新機能を有効にするには、 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを*EnableAIPIntegration*パラメーターと共に使用します。

1. Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。
    
    注: Office 365 複数地域を使用している場合は、-Url パラメーターと[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)を使用して、地理的な場所の1つに対して SharePoint Online 管理センターサイトの Url を指定します。

2. 次のコマンドを実行し、 **Y**キーを押して確認します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. Office 365 の複数地域: 残りの各地域の場所について、手順1と2を繰り返します。

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>機密ラベルを作成または変更した後のロールアウトをスケジュールする

Microsoft 365 コンプライアンスセンターで機密ラベルを作成または変更した後、それを段階的に公開します。 完全に同期されていないラベルを発行した場合、ユーザーがファイルにラベルを適用してそれらを SharePoint にアップロードすると、ファイルを web 版の Office アプリで開くことができなくなります。 検索と電子情報開示もファイルに対して機能しません。

次の手順を実行することをお勧めします。

1. 新しいまたは変更された機密ラベルを1人または2人のユーザーにのみ発行します。

2. 最初の発行の後、少なくとも24時間待機します。 ラベルが完全に同期していることを確認します。

3. ラベルを広く公開します。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint と OneDrive の機密ラベルを無効にする方法 (オプトアウト)

これらの新機能を無効にした場合、SharePoint と OneDrive の機密ラベルを有効にした後にアップロードしたファイルは、ラベル設定が引き続き適用されるため、ラベルによって保護されます。 これらの新機能を無効にした後、機密ラベルを新しいファイルに適用すると、フルテキスト検索、電子情報開示、共同編集は機能しなくなります。

これらの新機能を無効にするには、PowerShell を使用する必要があります。 SharePoint Online 管理シェルと[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを使用して、「PowerShell を使用して[機密ラベルのサポートを有効にする](#use-powershell-to-enable-support-for-sensitivity-labels)」の説明に従って、同じ*EnableAIPIntegration*パラメーターを指定します。 しかし、今回はパラメーター値を false に設定し、 **Y**キーを押して確認します。

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

複数地域の Office 365 を使用している場合は、各地域の場所に対してこのコマンドを実行する必要があります。

## <a name="next-steps"></a>次の手順

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にした後、自動ラベル付けポリシーを使用して、これらのファイルに自動的にラベル付けすることを検討してください。 詳細については、「[コンテンツに機密ラベルを自動的に適用する](apply-sensitivity-label-automatically.md)」を参照してください。