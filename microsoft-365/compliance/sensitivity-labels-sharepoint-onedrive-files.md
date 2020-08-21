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
description: 管理者は、SharePoint および OneDrive で Word、Excel、PowerPoint ファイルに対する機密ラベルのサポートを有効にできます。
ms.openlocfilehash: d049cdd61d2155267f4e55c612885929e27adaaa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845723"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする前に、Web 上の[sensitivity labels](sensitivity-labels.md)機密ラベルOffice適用することはできません。 リボンに [機密 **] ボタンが表示され、** 適用されているラベル名がステータス バーに表示されません。 また、デスクトップ アプリを使用してファイルにラベルを付けて SharePoint または OneDrive に保存した場合、ラベルが暗号化されていると、サービスはこれらのファイルのコンテンツを処理できません。 共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能は、このような状況では動作しません。

SharePoint および OneDrive でファイルの機密ラベルOffice有効にする場合、これらの機能はすべて有効になります。 ユーザーに秘密度ラベルを表示するだけでなく、クラウド ベースのキーによる暗号化 (および二重キーの暗号化を使用しない) を含む機密ラベルが適用されている新しいファイルおよび [変更された](double-key-encryption.md)ファイルを表示する

- Word、Excel、PowerPoint ファイルに対しては、SharePoint がラベルを認識し、暗号化されたファイルのコンテンツを処理できるようになりました。

- SharePoint または OneDrive からこれらのファイルをダウンロードしたりアクセスしたりすると、ラベルから機密ラベルと暗号化設定が適用され、ファイルが格納される場所にかかわらなく残されます。 ラベルのみを使用してドキュメントを保護するためのユーザー ガイダンスを提供する。 詳細については [、「Information Rights Management (IRM) オプションと機密ラベル」を参照してください](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- ユーザーがラベル付きおよび暗号化されたファイルを SharePoint にアップロードするときに、それらのファイルの表示権限以上が必要です。 たとえば、SharePoint の外部でファイルを開くことができます。 この最小利用権を持っていない場合は、アップロードは成功しますが、SharePoint でラベルが認識されず、ファイルのコンテンツを処理できません。

- Web Office (Word、Excel、PowerPoint) を使用して、暗号化を適用する機密ラベルを持つOffice ファイルを開いて編集します。 暗号化に割り当てられたアクセス許可が適用されます。 Word on the web では、ドキュメントの編集時に自動ラベル付けを使用することもできます。

- 外部ユーザーは、ゲスト アカウントを使用して、暗号化でラベルが付けられているドキュメントにアクセスできます。 詳細については、「外部ユーザー [のサポート」および「ラベル付きコンテンツ」を参照してください](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。

- Office 365 電子情報開示では、これらのファイルのフルテキスト検索およびデータ損失防止 (DLP) ポリシーは、これらのファイルのコンテンツをサポートします。

> [!NOTE]
> オンプレミス キー ("Hold Your Own Key" または "HYOK" と呼ばれるキー管理トポロジ) または Double Key Encryption を使用して暗号化が [適用されている場合](double-key-encryption.md)、ファイル コンテンツを処理する SharePoint の動作は変化しない。
>
> また、SharePoint の動作では、単一の Azure ベースのキーを使用した暗号化でラベルが付けられている、SharePoint 内の既存のファイルは変更されません。 SharePoint および OneDrive で Office ファイルの機密ラベルを有効にした後、これらのファイルが新しい機能を活用するには、ファイルをダウンロードして再びアップロードするか、編集する必要があります。 たとえば、検索と電子情報開示の結果で結果が返されます。

SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にすると、SharePoint[audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)および OneDrive のドキュメントに適用される機密ラベルを監視するために新しい 3 つの新しい監査イベントを使用できます。

- **ファイルに適用された機密ラベル**
- **ファイルに適用された機密ラベルの変更**
- **ファイルから削除された機密ラベル**

以下のビデオ (オーディオなし) を視し、新しい機能の動作をご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

SharePoint および OneDrive のデータ ファイルの機密ラベルを[無効にする](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) (いつでもオ Officeプトアウト) できます。

SharePoint Information Rights Management (IRM) を使用して SharePoint のドキュメントを現在保護している場合は、このページの [SharePoint Information Rights Management (IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) と機密ラベル セクションを確認してください。

## <a name="requirements"></a>Requirements

これらの新しい [機能は機密ラベルでのみ動作](sensitivity-labels.md) します。 現在 Azure Information Protection ラベルがある場合は、まずラベルを機密ラベルに移行して、アップロードする新しいファイルに対してこれらの機能を有効にできるようにします。 手順については [、「Azure Information Protection ラベルを統合された機密ラベルに移行する方法」を参照してください。](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Windows 版 OneDrive 同期アプリのバージョン 19.002.0121.0008 以降、Mac ではバージョン 19.002.0107.0008 以降を使用します。 これらのバージョンはどちらも 2019 年 1 月 28 日にリリースされ、現在はすべてのリングにリリースされています。 詳細については [、OneDrive のリリース ノートを参照してください](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 SharePoint および OneDrive で Office ファイルの機密ラベルを有効にした後、古いバージョンの同期アプリを実行したユーザーに対して、そのファイルの更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- SharePoint では、Azure Information Protection ラベルを使用して既に暗号化した既存のファイルには機密ラベルが自動的に適用されません。 代わりに、SharePoint および OneDrive で機密ラベルを SharePoint および OneDrive で機密機密ラベルを Office有効にした後に機能する機能を確認するには、以下のタスクを完了します。

    1. Azure Information [Protection ラベルを機密ラベル](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)に移行し、Microsoft 365 コンプライアンス[published them](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)センターまたは同等のラベル付け管理センターから公開したことを確認します。

    2. ファイルをダウンロードしてから SharePoint にアップロードします。

- 暗号化を適用したラベルには、暗号化の次のいずれかの構成がある場合、SharePoint は暗号化 [ファイルを処理することができません](encryption-sensitivity-labels.md#configure-encryption-settings)。

  - **ユーザーが Word、PowerPoint、Excel の** チェックボックスを適用するときに、アクセス許可を割り **当てることができます。ユーザーは、アクセス許可を指定するように求めるダイアログ** を表示します。 この設定は、"ユーザー定義のアクセス許可" と呼ばれることがあります。
  - **コンテンツへのユーザー アクセスの有効期限は** 、[Never] 以外の値 **に設定されます**。
  - **二重キーの暗号化** が選択されています。

  これらの暗号化構成のいずれかのラベルの場合、ラベルは Web 上のユーザーにはOffice表示されません。 また、新しい機能は、既にこれらの暗号化設定があるラベル付きのドキュメントでは使用できません。 たとえば、これらのドキュメントは、更新された場合でも検索結果に返されません。

- ユーザーに編集アクセス許可を付与する暗号化されたドキュメントの場合、アプリの Web バージョンでコピーOfficeできません。

- Azure Information Protection のドキュメント追跡サイトはサポートされていません。

- Office アプリとモバイル アプリでは、暗号化のラベルが付けられているファイルの共同編集機能はサポートされません。 これらのアプリは、排他的な編集モードで、ラベル付きのファイルと暗号化されたファイルを継続的に開きます。

- 管理者が、ユーザーの同期クライアントにダウンロードされているファイルに既に適用されている公開されたラベルの設定を変更すると、ユーザーが OneDrive 同期フォルダーでファイルに加た変更内容を保存できない場合があります。 このシナリオは、暗号化のラベルが付けられているファイルに適用されます。また、ラベルが変更された場合は、暗号化を適用しているラベルにラベルが変更された場合にも適用されます。 クロス アイコン エラー [が発生した赤](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)い円がユーザーに表示され、新しい変更内容を別のコピーとして保存するようにユーザーに勧めるメッセージが表示されます。 代わりに、ファイルを閉じてから開くか、Web 上Office開くことができます。

- ラベル付きのドキュメントが SharePoint にアップロードされ、アカウントを使用してサービス プリンシパル名のラベルを使用して暗号化が適用された場合、Web 上の web Officeドキュメントは開くことができません。 シナリオの例としては、Microsoft Cloud App Security と Teams に電子メールで送信されるファイルがあります。

- ユーザーがオフラインまたはスリープ モードで Office for the web を使用する代わりに、デスクトップとモバイル アプリを使用して、Word、Excel、PowerPoint の場合に問題の保存に関する問題が発生する可能性があります。 これらのユーザーは、Office アプリ セッションを再開して変更を保存しようとすると、元のファイルを保存するのではなく、コピーを保存するオプションと共にアップロード エラー メッセージが表示されます。

- 次の方法で暗号化されているドキュメントは、Web 上の web Office開くことができません。

  - オンプレミスのキーを使う ("自分のキーを保持する" (HYOK) を使用する暗号化
  - 二重キーの暗号化を使用して [適用された暗号化](double-key-encryption.md)
  - Rights Management 保護テンプレートを直接適用するなどによって、ラベルとは別に適用された暗号化。

- SharePoint 内のドキュメントに適用されているラベルを削除した場合は、該当するラベル ポリシーからラベルを削除するのではなく、ダウンロード時のドキュメントにはラベルが付けられるか、暗号化されません。 これに対し、ラベルが付けされたドキュメントが SharePoint の外部に保存されている場合、ラベルを削除した場合でも、ドキュメントは暗号化されたままになります。 テスト段階でラベルを削除しても、運用環境のラベルを削除することは非常にかな点に注意してください。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint および OneDrive の機密ラベルを有効にする方法 (オプトイン)

新しい機能を有効にするには、Microsoft 365 コンプライアンス センターまたは PowerShell を使用します。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>コンプライアンス センターを使用して機密ラベルのサポートを有効にする

このオプションは、SharePoint および OneDrive の機密ラベルを有効にする最も簡単な方法です。

組織のグローバル管理者には、秘密度ラベルのすべての側面を作成および管理するための完全な権限があります。 グローバル管理者としてサインインしていない場合は、「[機密ラベルの作成と管理に必要なアクセス許可](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)」を参照してください。

1. [Microsoft 365 コンプライアンス センターにサインインし、ソリューション](https://compliance.microsoft.com/)情報**保護に**  >  **移動します。**

    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。

2. オンライン ファイルのコンテンツを処理する機能を有効にするメッセージが表示された場合はOffice[現在 **有効にする] を選択します**。

    ![[現在] ボタンをオンにして、データ センターの機密ラベルOfficeします](../media/sensitivity-labels-turn-on-banner.png)

    コマンドはすぐに実行され、次にページが更新されると、メッセージまたはボタンは表示されなけません。

> [!NOTE]
> Microsoft 365 Multi-Geo がある場合は、PowerShell を使用して、すべての地理的位置でこれらの機能を有効にする必要があります。 詳細については、次のセクションを参照してください。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell を使用して機密ラベルのサポートを有効にする

コンプライアンス センターを使用する代わりとして、SharePoint Online PowerShell の [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) コマンドレットを使用して機密ラベルのサポートを有効にできます。

Microsoft 365 Multi-Geo がある場合は、PowerShell を使用してすべての地域に対してこのサポートを有効にする必要があります。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 管理シェルを準備する

PowerShell コマンドを実行して SharePoint および OneDrive で Office ファイルの機密ラベルを有効にする前に、SharePoint Online 管理シェル バージョン 16.0.19418.12000 以降を実行している必要があります。 既に最新バージョンをお持持いの場合は、次の手順に [進んで](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) PowerShell コマンドを実行できます。

1. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロード センターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[プログラムの追加と削除] **に移動して** 、SharePoint Online 管理シェルをアンインストールすることもできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 Windows の 64 ビット版を実行している場合は x64 ファイルを、32 ビット版を実行している場合は x86 ファイルをダウンロードします。 確認がわからない場合は、 [実行している Windows オペレーティング システムのバージョンを確認しますか?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. ファイルをダウンロードした後、そのファイルを実行し、セットアップ ウィザードの手順に従います。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell コマンドを実行して機密ラベルのサポートを有効にする

新機能を有効にするには、次に示す*EnableAIPIntegration*パラメーターを指定して[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを使用します。

1. Microsoft 365 のグローバル管理者または SharePoint 管理者権限を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

    注: Microsoft 365 Multi-Geo を使用している場合 [、Connect-SPOService で](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)-Url パラメーターを使用し、お使いの地理的な場所の SharePoint Online 管理センター サイトの URL を指定します。

2. 次のコマンドを実行し **、Y** キーを押して確認します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```

3. Microsoft 365 Multi-Geo: 残りのジオ位置情報ごとに手順 1. ~ 2. を繰り返します。

## <a name="publishing-and-changing-sensitivity-labels"></a>機密ラベルの発行と変更

SharePoint および OneDrive で機密ラベルを使用する場合、新しい機密ラベルを公開するとき、または既存の機密ラベルを更新する場合は、レプリケーション時間を考慮する必要があります。 暗号化を適用する新しいラベルにはこの点が特に重要です。

たとえば、暗号化を適用する新しい機密ラベルを作成して発行すると、そのラベルはユーザーのデスクトップ アプリに非常にすばやく表示されます。 ユーザーはこのラベルをドキュメントに適用してから、SharePoint または OneDrive にアップロードします。 サービスのラベル レプリケーションが完了しなけたけでは、アップロード時に新しい機能はそのドキュメントに適用されません。 結果として、ドキュメントは検索で返されないので、web 用の Web の Web でドキュメントをOffice開くことができません。

- 変更内容は 1 時間以内にレプリケートされます。新しい機密ラベルおよび削除された機密ラベル ポリシーの設定には、ポリシーに含まれるラベルが含まれます。

- 24 時間以内にレプリケートされる変更は、既存のラベルの機密ラベルの設定に変更されます。

新しい機密ラベルではレプリケーションの遅延が 1 時間しかないため、例ではシナリオを実行する可能性は大きくなくなるはと考えられます。 ただし、安全な方法として、最初に少数のテスト ユーザーに新しいラベルを発行し、1 時間待ってから 1 時間待ってから SharePoint と OneDrive 上でラベルの動作を検証する方法をお勧めします。 最後の手順として、既存のラベル ポリシーにさらに多くのユーザーを追加してより多くのユーザーがラベルを利用できるようにするか、標準ユーザーの既存のラベル ポリシーにラベルを追加します。 標準ユーザーが表示した時に、既に SharePoint と OneDrive に同期されています。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) と機密ラベル

[SharePoint Information Rights Management (IRM) は](set-up-irm-in-sp-admin-center.md) 、ファイルのダウンロード時に暗号化と制限が適用され、リストおよびライブラリ レベルでファイルを保護する旧テクノロジです。 この古い保護テクノロジは、承認されていないユーザーが SharePoint 外のファイルを開くことがないように意ニされている機能です。

それに対し、機密ラベルでは暗号化だけでなく、視覚的なマーリング (ヘッダー、フッター、ウトエルト) の保護設定も提供されます。 暗号化設定は、コンテンツに対してユーザーが行 [う操作](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) を制限するために、すべての使用権をサポートし、さまざまなシナリオで同じ機密 [ラベルがサポートされます](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)。 ワークロードとアプリ間で設定が一貫したもので同じ保護方法を使用すると、一貫した保護戦略を実行できます。

ただし、保護ソリューションと動作の両方を組み合わせ、実行できます。

- 暗号化を適用する機密度ラベルを含むファイルをアップロードすると、SharePoint はこのファイルを処理しなく、共同編集、電子情報開示、DLP、および検索はこのファイルに対して機能しません。

- Web 上のファイルを使用してOfficeラベルを付けると、ラベルの暗号化設定が適用されます。 これらのファイルに対しては、共同編集、電子情報開示、DLP、および検索がサポートされます。

- Office on the web を使用してラベルが付けされたファイルをダウンロードすると、ラベルは保持され、IRM の制限設定ではなく、ラベルからの暗号化設定が適用されます。

- 暗号化ラベルの付Officeのファイルまたは PDF ファイルをダウンロードすると、IRM 設定が適用されます。

- IRM ライブラリの追加の設定 (IRM をサポートしないドキュメントのアップロードをユーザーが防止する) を有効にした場合、これらの設定が適用されます。

この動作により、ラベルが付けされていない場合でも、すべての Office ファイルと PDF ファイルがダウンロードされた場合に、不正アクセスから保護されます。 ただし、ラベルが付けされたファイルは、新しい機能のメリットはありません。

## <a name="search-for-documents-by-sensitivity-label"></a>機密ラベル別のドキュメントを検索する

管理プロパティ **InformationProtectionLabelId を使用** して、SharePoint または OneDrive で特定の機密ラベルが付いています。 次の構文を使用してください。 `InformationProtectionLabelId:<GUID>`

たとえば、"機密" というラベルが付き、このラベルの GUID が "8faca7b8-8d20-48a3-8ea2-0f96310a848e" のドキュメントを検索するには、検索ボックスに次のように入力します。

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

機密ラベルの GUID を取得するには、Get-Label コマンドレット [を使用](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) します。

1. まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

    たとえば、管理者として実行している PowerShell セッションで、全体管理者アカウントでサインインします。

2. 次に、次のコマンドを実行します。

    ```powershell
    Get-Label |ft Name, Guid
    ```

管理プロパティの使用方法については [、「SharePoint で検索スキーマを管理する」を参照してください](https://docs.microsoft.com/sharepoint/manage-search-schema)。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint および OneDrive の機密ラベルを無効にする方法 (オプトアウト)

これらの新機能を無効にした場合、SharePoint と OneDrive の機密ラベルを有効にした後もアップロードしたファイルはラベルの設定が引き続き適用されるので、ラベルで引き続き保護されます。 これらの新機能を無効にした後に、新しいファイルに機密ラベルを適用すると、フルテキスト検索、電子情報開示、共同編集が動作しななけなれます。

これらの新機能を無効にするには、PowerShell を使用する必要があります。 SharePoint Online 管理シェルと[Set-SPOTenant コマンドレットを使用](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)して[、PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels)を使用して機密ラベルセクションのサポートを有効にする方法と同じ*EnableAIPIntegration*パラメーターを指定します。 ただし、パラメーター値を false に設定し **、Y** キーを押して確認します。

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Microsoft 365 Multi-Geo がある場合は、それぞれの地理的位置に対してこのコマンドを実行する必要があります。

## <a name="next-steps"></a>次の手順

SharePoint および OneDrive でファイルの機密Officeを有効にした後で、自動ラベル付けポリシーを使用してこれらのファイルに自動的にラベルを付けを行うことを検討してください。 詳細については、「機密 [ラベルをコンテンツに自動的に適用する」を参照してください](apply-sensitivity-label-automatically.md)。
