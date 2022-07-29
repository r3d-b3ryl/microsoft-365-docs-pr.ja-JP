---
title: Office ファイルの秘密度ラベルを有効にする
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、SharePoint と OneDrive で Word、Excel、および PowerPoint ファイルの秘密度ラベルのサポートを有効にすることができます。
ms.openlocfilehash: b995d1b97676eb3251c33069ed20f9ce382a61bb
ms.sourcegitcommit: 57c2f5ba74e238543d6fd724ed79527547bd0780
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67069671"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

SharePoint と OneDrive で[サポートされている Office ファイル](sensitivity-labels-office-apps.md#office-file-types-supported)の組み込みのラベル付けを有効にして、ユーザーがOffice for the webで[機密ラベル](sensitivity-labels.md)を適用できるようにします。 この機能が有効になっていると、ユーザーはリボンの **[秘密度** ] ボタンを表示してラベルを適用し、適用されたラベル名をステータス バーに表示します。

また、この機能を有効にすると、SharePoint と OneDrive は、秘密度ラベルを使用して暗号化された Office ファイルの内容を処理できるようになります。 ラベルは、Office for the web、または Office デスクトップ アプリで適用し、SharePoint と OneDrive にアップロードまたは保存できます。 この機能を有効にするまで、これらのサービスは暗号化されたファイルを処理できません。つまり、共同編集、電子情報開示、Microsoft Purview データ損失防止、検索、およびその他の共同作業機能は、これらのファイルでは機能しません。

SharePoint と OneDrive で Office ファイルの秘密度ラベルを有効にした後、クラウドベースのキーを使用して暗号化を適用する秘密度ラベルを持つ新しいファイルと変更されたファイルに対して 、 [二重キー暗号化](double-key-encryption.md)を使用しません。

- Word、Excel、および PowerPoint ファイルの場合、SharePoint と OneDrive はラベルを認識し、暗号化されたファイルの内容を処理できるようになりました。

- ユーザーが SharePoint または OneDrive からこれらのファイルをダウンロードまたはアクセスすると、秘密度ラベルとラベルからの暗号化設定が適用され、保存されている場所に関係なくファイルに残ります。 ドキュメントを保護するためにラベルのみを使用するためのユーザー ガイダンスを提供してください。 詳細については、「 [Information Rights Management (IRM) オプションと秘密度ラベル](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)」を参照してください。

- ユーザーがラベル付きファイルと暗号化されたファイルを SharePoint または OneDrive にアップロードするときは、少なくともそれらのファイルに対する表示権限が必要です。 たとえば、SharePoint の外部でファイルを開くことができます。 この最小使用権がない場合、アップロードは成功しますが、サービスはラベルを認識せず、ファイルの内容を処理できません。

- Office for the web (Word、Excel、PowerPoint) を使用して、暗号化を適用する秘密度ラベルを持つ Office ファイルを開いて編集します。 暗号化で割り当てられたアクセス許可が適用されます。 また、これらのドキュメント [に対して自動ラベル付けを](apply-sensitivity-label-automatically.md) 使用することもできます。

- 外部ユーザーは、ゲスト アカウントを使用して暗号化でラベル付けされたドキュメントにアクセスできます。 詳細については、「 [外部ユーザーとラベル付きコンテンツのサポート](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)」を参照してください。

- Office 365電子情報開示では、これらのファイルのフルテキスト検索がサポートされ、データ損失防止 (DLP) ポリシーではこれらのファイル内のコンテンツがサポートされます。

> [!NOTE]
> 暗号化がオンプレミス のキー (多くの場合は "自分のキーを保持する" または HYOK と呼ばれるキー管理トポロジ) で適用されている場合、または [ダブル キー暗号化](double-key-encryption.md)を使用しても、ファイルの内容を処理するためのサービス動作は変更されません。 そのため、これらのファイルでは、共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能は機能しません。
>
> SharePoint と OneDrive の動作は、単一の Azure ベースのキーを使用して暗号化でラベル付けされているこれらの場所の既存のファイルについても変更されません。 SharePoint と OneDrive で Office ファイルの秘密度ラベルを有効にした後に、これらのファイルが新機能の恩恵を受けるためには、ファイルをダウンロードして再度アップロードするか、編集する必要があります。

SharePoint と OneDrive で Office ファイルの秘密度ラベルを有効にすると、SharePoint と OneDrive のドキュメントに適用される秘密度ラベルを監視するために、次の 3 つの新しい [監査イベント](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) を使用できます。

- **ファイルに適用された機密ラベル**
- **ファイルに適用された機密ラベルの変更**
- **ファイルから削除された機密ラベル**

次のビデオ (オーディオなし) を見て、新しい機能の動作を確認します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

SharePoint および OneDrive ([オプトアウト](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) の Office ファイルの秘密度ラベルはいつでも無効にできます。

SharePoint Information Rights Management (IRM) を使用して SharePoint でドキュメントを現在保護している場合は、このページの [SharePoint Information Rights Management (IRM) と秘密度ラベル](#sharepoint-information-rights-management-irm-and-sensitivity-labels) のセクションを確認してください。

## <a name="requirements"></a>要件

これらの新機能は、 [秘密度ラベル](sensitivity-labels.md) でのみ機能します。 現在 Azure Information Protection ラベルがある場合は、最初に機密ラベルに移行して、アップロードする新しいファイルに対してこれらの機能を有効にします。 手順については、、「[Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](/azure/information-protection/configure-policy-migrate-labels)」を参照してください。

Windows では OneDrive 同期 アプリ バージョン 19.002.0121.0008 以降、Mac ではバージョン 19.002.0107.0008 以降を使用します。 これらのバージョンはどちらも 2019 年 1 月 28 日にリリースされ、現在すべてのリングにリリースされています。 詳細については、 [OneDrive のリリース ノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。 SharePoint と OneDrive で Office ファイルの秘密度ラベルを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- SharePoint と OneDrive は、PowerQuery データ、カスタム アドインによって格納されたデータ、または Cover Page プロパティ、コンテンツ タイプ スキーマ、カスタム ドキュメント情報パネル、カスタム XSN などのカスタム XML パーツが含まれている場合、Office デスクトップ アプリからラベル付けされ、暗号化された一部のファイルを処理できません。 この制限は、 [文献目録](https://support.microsoft.com/en-us/office/create-a-bibliography-citations-and-references-17686589-4824-4940-9c69-342c289fa2a5)を含むファイルや、ドキュメント [ID が](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) アップロードされたときに追加されたファイルにも適用されます。

    これらのファイルの場合は、後でOffice on the webで開くことができるように暗号化なしでラベルを適用するか、デスクトップ アプリでファイルを開くようユーザーに指示します。 Office on the web内でのみラベル付けおよび暗号化されたファイルは影響を受けられません。

- SharePoint と OneDrive は、Azure Information Protection ラベルを使用して既に暗号化した既存のファイルに秘密度ラベルを自動的に適用しません。 代わりに、SharePoint と OneDrive で Office ファイルの秘密度ラベルを有効にした後で機能を機能させるには、次のタスクを実行します。

    1. [Azure Information Protection ラベルを](/azure/information-protection/configure-policy-migrate-labels)秘密度ラベルに移行し、Microsoft Purview コンプライアンス ポータルから[発行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)していることを確認します。
    2. ラベル付きファイルをダウンロードし、SharePoint または OneDrive の元の場所にアップロードします。

- 暗号化を適用したラベルに暗号化用の次の構成のいずれかが含まれている場合、SharePoint と OneDrive は [暗号化](encryption-sensitivity-labels.md#configure-encryption-settings)されたファイルを処理できません。
  - **ラベルを適用する場合にユーザーがアクセス許可を割り当てられ**、**Word、PowerPoint、Excel でユーザーにアクセス許可を指定するように求める** のチェックボックスが選択されています。 この設定は、"ユーザー定義のアクセス許可" と呼ばれることもあります。
  - **コンテンツへのユーザー アクセスは有効期限が切れています** は、**[使用しない]** 以外の値が設定されています。
  - **二重キー暗号化** が選択されています。

    これらの暗号化構成のいずれかを持つラベルの場合、ラベルはOffice for the webのユーザーには表示されません。 さらに、これらの暗号化設定が既にあるラベル付きドキュメントでは、新しい機能を使用できません。 たとえば、これらのドキュメントは、更新されても検索結果に返されません。

- パフォーマンス上の理由から、ドキュメントを SharePoint にアップロードまたは保存してもファイルのラベルに暗号化が適用されない場合、ドキュメント ライブラリの **[秘密度** ] 列にラベル名が表示されるまでに時間がかかる場合があります。 この列のラベル名に依存するスクリプトまたはオートメーションを使用する場合は、この遅延を考慮してください。

- [SharePoint でチェックアウト](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de)中にドキュメントにラベルが付けられている場合、ドキュメントがチェックインされ、次に SharePoint で開かれるまで、ドキュメント ライブラリの **[秘密度**] 列にラベル名は表示されません。

- ラベル付けされた暗号化されたドキュメントが、サービス プリンシパル名を使用するアプリまたはサービスによって SharePoint または OneDrive からダウンロードされ、異なる暗号化設定を適用するラベルで再度アップロードされた場合、アップロードは失敗します。 シナリオの例として、ファイルの秘密度ラベルを **機密から高機密** に、または **機密** から **一般** に **変更するMicrosoft Defender for Cloud Apps** があります。

    [ラベル付きドキュメントの暗号化の削除](#remove-encryption-for-a-labeled-document)セクションで説明されているように、アプリまたはサービスが [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) コマンドレットを最初に実行した場合、アップロードは失敗しません。 または、アップロード前に元のファイルが削除されるか、ファイル名が変更されます。

- ユーザーは、次の [名前を付けて保存] シナリオで暗号化されたドキュメントを開く際に遅延が発生する可能性があります。デスクトップ バージョンの Office を使用すると、暗号化を適用する秘密度ラベルを持つドキュメントに対して [名前を付けて保存] を選択します。 ユーザーはその場所に SharePoint または OneDrive を選択し、すぐにOffice for the webでそのドキュメントを開こうとします。 サービスが暗号化をまだ処理している場合は、デスクトップ アプリでドキュメントを開く必要があるというメッセージがユーザーに表示されます。 数分後にもう一度やり直すと、Office for the webでドキュメントが正常に開きます。

- 暗号化されたドキュメントの場合、印刷はOffice for the webではサポートされていません。

- Office for the webで暗号化されたドキュメントの場合、クリップボードと画面キャプチャへのコピーは防止されません。 詳細については、「[Rights Management で画面キャプチャを防止できますか?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)」を参照してください。

- 既定では、Office デスクトップ アプリとモバイル アプリは、暗号化でラベル付けされたファイルの共同編集をサポートしていません。 これらのアプリは、ラベル付けされた暗号化されたファイルを排他的編集モードで引き続き開きます。

    > [!NOTE]
    > 共同編集は、Windows と macOS、および iOS と Android のプレビューでサポートされるようになりました。 詳細については、「 [秘密度ラベルで暗号化されたファイルの共同編集を有効にする](sensitivity-labels-coauthoring.md)」を参照してください。

- 管理者が、ユーザーの同期クライアントにダウンロードされたファイルに既に適用されている発行済みラベルの設定を変更した場合、ユーザーはそのファイルに加えた変更を OneDrive Sync フォルダーに保存できない可能性があります。 このシナリオは、暗号化でラベル付けされたファイル、およびラベルの変更が暗号化を適用するラベルに暗号化を適用しなかったラベルからの場合にも適用されます。 ユーザーには [白い十字アイコン エラーが表示された赤い円](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示され、新しい変更を別のコピーとして保存するように求められます。 代わりに、ファイルを閉じて再度開くか、Office for the webを使用できます。

- ユーザーは、Office for the webを使用する代わりに、Word、Excel、または PowerPoint 用のデスクトップ アプリとモバイル アプリを使用する場合に、オフラインまたはスリープ モードになった後に保存の問題が発生する可能性があります。 これらのユーザーの場合、Office アプリ セッションを再開して変更を保存しようとすると、元のファイルを保存する代わりにコピーを保存するオプションを含むアップロードエラー メッセージが表示されます。

- 次の方法で暗号化されたドキュメントは、Office for the webで開くできません。
  - オンプレミス キーを使用する暗号化 ("自分のキーを保持する" または HYOK)
  - [ダブル キー](double-key-encryption.md)暗号化を使用して適用された暗号化
  - ラベルとは別に適用された暗号化 。たとえば、Rights Management 保護テンプレートを直接適用します。

- [他の言語](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)用に構成されたラベルはサポートされておらず、元の言語のみが表示されます。

- SharePoint または OneDrive のドキュメントに適用されているラベルを削除した場合、該当するラベル ポリシーからラベルを削除する代わりに、ダウンロード時にドキュメントにラベル付けや暗号化は行われません。 これに対して、ラベル付けされたドキュメントが SharePoint または OneDrive の外部に保存されている場合、ラベルが削除された場合、ドキュメントは暗号化されたままになります。 テスト フェーズ中にラベルを削除する可能性がありますが、運用環境でラベルを削除することは非常にまれであることに注意してください。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint と OneDrive の秘密度ラベルを有効にする方法 (オプトイン)

新しい機能を有効にするには、Microsoft Purview コンプライアンス ポータルを使用するか、PowerShell を使用します。 手順については、次のセクションを参照してください。

SharePoint と OneDrive のすべてのテナント レベルの構成変更と同様に、変更が有効になるまでに約 15 分かかります。

### <a name="use-the-microsoft-purview-compliance-portal-to-enable-support-for-sensitivity-labels"></a>Microsoft Purview コンプライアンス ポータルを使用して秘密度ラベルのサポートを有効にする

このオプションは、SharePoint と OneDrive の秘密度ラベルを有効にする最も簡単な方法ですが、テナントのグローバル管理者としてサインインする必要があります。

1. グローバル管理者として [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインし、**ソリューション** > **情報保護** > **ラベル** に移動します

2. Office オンライン ファイルでコンテンツを処理する機能を有効にするメッセージが表示された場合は、[ **今すぐ有効にする**] を選択します。

    ![Office Online の秘密度ラベルを有効にするには、[今すぐ有効にする] ボタンをオンにします。](../media/sensitivity-labels-turn-on-banner.png)

    コマンドはすぐに実行され、ページが次に更新されると、メッセージまたはボタンは表示されなくなります。

> [!NOTE]
> Microsoft 365 Multi-Geo をお持ちのお客様は、PowerShell を使用して、すべての地域の場所でこれらの機能を有効にする必要があります。 詳細については、次のセクションを参照してください。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell を使用して秘密度ラベルのサポートを有効にする

Microsoft Purview コンプライアンス ポータルを使用する代わりに、SharePoint Online PowerShell の [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) コマンドレットを使用して、秘密度ラベルのサポートを有効にすることができます。

Microsoft 365 Multi-Geo を使用している場合は、PowerShell を使用して、すべての地域の場所でこのサポートを有効にする必要があります。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 管理シェルを準備する

PowerShell コマンドを実行して SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする前に、SharePoint Online Management Shell バージョン 16.0.19418.12000 以降を実行していることを確認します。 最新バージョンが既にある場合は、 [次の手順](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) に進んで PowerShell コマンドを実行できます。

1. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロード センターから以前のバージョンの SharePoint Online Management Shell をインストールした場合は、 **プログラムの追加または削除** に移動し、SharePoint Online 管理シェルをアンインストールすることもできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 64 ビット バージョンの Windows を実行する場合は x64 ファイルをダウンロードし、32 ビット バージョンを実行する場合は x86 ファイルをダウンロードします。 わからない場合は、「[実行している Windows オペレーティング システムのバージョン](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。

6. ファイルをダウンロードしたら、ファイルを実行し、セットアップ ウィザードの手順に従います。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell コマンドを実行して秘密度ラベルのサポートを有効にする

新しい機能を有効にするには、*EnableAIPIntegration* パラメーターで [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) コマンドレットを使用します。

1. Microsoft 365 でグローバル管理者または SharePoint 管理者特権を持つ職場または学校アカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

    > [!NOTE]
    > Microsoft 365 Multi-Geo がある場合は、 [Connect-SPOService](/powershell/module/sharepoint-online/connect-sposervice) で -Url パラメーターを使用し、いずれかの地理的場所に SharePoint Online 管理センター サイトの URL を指定します。

2. 次のコマンドを実行し、 **Y** キーを押して確認します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Microsoft 365 Multi-Geo の場合:残りの地域の場所ごとに手順 1 と 2 を繰り返します。

## <a name="publishing-and-changing-sensitivity-labels"></a>秘密度ラベルの発行と変更

SharePoint と OneDrive で秘密度ラベルを使用する場合は、新しい秘密度ラベルを発行したり、既存の秘密度ラベルを更新したりするときに、レプリケーション時間を確保する必要があることに注意してください。 これは、暗号化を適用する新しいラベルに特に重要です。

たとえば、暗号化を適用する新しい秘密度ラベルを作成して発行すると、ユーザーのデスクトップ アプリにすばやく表示されます。 ユーザーはこのラベルをドキュメントに適用し、SharePoint または OneDrive にアップロードします。 ラベルレプリケーションがサービスに対して完了していない場合、アップロード時にそのドキュメントに新しい機能は適用されません。 その結果、ドキュメントは検索または電子情報開示で返されないため、ドキュメントをOffice for the webで開く必要があります。

ラベルのタイミングの詳細については、「[新しいラベルと変更が反映されるタイミング](create-sensitivity-labels.md#when-to-expect-new-labels-and-changes-to-take-effect)」を参照してください。

セーフガードとして、最初に少数のテスト ユーザーだけに新しいラベルを発行し、少なくとも 1 時間待ってから、SharePoint と OneDrive でラベルの動作を確認することをお勧めします。 少なくとも 1 日待ってから、既存のラベル ポリシーにユーザーを追加するか、標準ユーザーの既存のラベル ポリシーにラベルを追加して、ラベルをより多くのユーザーが利用できるようにします。 標準ユーザーにラベルが表示される時点で、SharePoint と OneDrive に既に同期されています。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) ラベルと秘密度ラベル

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) は、ファイルのダウンロード時に暗号化と制限を適用することで、リストレベルとライブラリ レベルでファイルを保護するための古いテクノロジです。 この古い保護テクノロジは、承認されていないユーザーが SharePoint の外部にいる間にファイルを開くのを防ぐために設計されています。

これに対して、秘密度ラベルは、暗号化に加えて視覚的なマーキング (ヘッダー、フッター、透かし) の保護設定を提供します。 暗号化設定では、ユーザーがコンテンツに対して実行できる操作を制限するための [使用権限](/azure/information-protection/configure-usage-rights) の全範囲がサポートされており、 [多くのシナリオ](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)で同じ秘密度ラベルがサポートされています。 同じ保護方法をワークロードとアプリ間で一貫した設定で使用すると、一貫性のある保護戦略が実現します。

ただし、両方の保護ソリューションを一緒に使用できます。動作は次のとおりです。

- 暗号化を適用する秘密度ラベルを持つファイルをアップロードする場合、SharePoint はこれらのファイルのコンテンツを処理できないため、これらのファイルの共同編集、電子情報開示、DLP、検索はサポートされません。

- Office for the webを使用してファイルにラベルを付ける場合、ラベルからのすべての暗号化設定が適用されます。 これらのファイルでは、共同編集、電子情報開示、DLP、検索がサポートされています。

- Office for the webを使用してラベル付けされたファイルをダウンロードすると、ラベルは保持され、ラベルからの暗号化設定は IRM 制限設定ではなく適用されます。

- 秘密度ラベルで暗号化されていない Office または PDF ファイルをダウンロードすると、IRM 設定が適用されます。

- IRM をサポートしていないドキュメントをユーザーがアップロードできないようにする追加の IRM ライブラリ設定のいずれかを有効にした場合、これらの設定が適用されます。

この動作により、すべての Office ファイルと PDF ファイルは、ラベルが付いていない場合でも、ダウンロードされた場合に不正アクセスから保護されます。 ただし、アップロードされたラベル付きファイルは、新しい機能の恩恵を受けることはありません。

## <a name="search-for-documents-by-sensitivity-label"></a>機密ラベルでドキュメントを検索する

管理プロパティ **InformationProtectionLabelId** を使用して、特定の秘密度ラベルを持つ SharePoint または OneDrive 内のすべてのドキュメントを検索します。 次の構文を使用します。 `InformationProtectionLabelId:<GUID>`

たとえば、"Confidential" としてラベル付けされたすべてのドキュメントを検索し、そのラベルに "8faca7b8-8d20-48a3-8ea2-0f96310a848e" の GUID を持つすべてのドキュメントを検索するには、検索ボックスに次のように入力します。

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

検索では、.zip ファイルなどの圧縮ファイルにラベル付きのドキュメントが見つかりません。

秘密度ラベルの GUID を取得するには、 [Get-Label](/powershell/module/exchange/get-label) コマンドレットを使用します。

1. まず、[Office 365 セキュリティ&コンプライアンス PowerShell に接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

    たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。

2. 次に、次のコマンドを実行します。

    ```powershell
    Get-Label |ft Name, Guid
    ```

管理プロパティの使用の詳細については、「 [SharePoint での検索スキーマの管理](/sharepoint/manage-search-schema)」を参照してください。

## <a name="remove-encryption-for-a-labeled-document"></a>ラベル付きドキュメントの暗号化を削除する

SharePoint 管理者が SharePoint に格納されているドキュメントから暗号化を削除する必要がある場合は、まれに発生することがあります。 そのドキュメントに対して、エクスポートまたはフル コントロールの [Rights Management 使用権](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)が割り当てられているすべてのユーザーは、Azure Rights Management サービスによって適用された暗号化を Azure Information Protectionから削除できます。 たとえば、これらの使用権限のいずれかを持つユーザーは、暗号化を適用するラベルを暗号化のないラベルに置き換えることができます。 [スーパー ユーザー](/azure/information-protection/configure-super-users)は、ファイルをダウンロードし、暗号化なしでローカル コピーを保存することもできます。

代わりに、グローバル管理者または [SharePoint 管理者](/sharepoint/sharepoint-admin-role) は [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) コマンドレットを実行できます。これにより、秘密度ラベルと暗号化の両方が削除されます。 このコマンドレットは、管理者がサイトまたはファイルに対するアクセス許可を持っていない場合や、Azure Rights Management サービスが利用できない場合でも実行されます。

以下に例を示します。

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

要件:

- SharePoint Online Management Shell バージョン 16.0.20616.12000 以降。

- 暗号化は、管理者が定義した暗号化設定を持つ秘密度ラベルによって適用されています ( [[今すぐアクセス許可を割り当てる](encryption-sensitivity-labels.md#assign-permissions-now) ] ラベル設定)。 このコマンドレットでは[、ダブル キー暗号化](encryption-sensitivity-labels.md#double-key-encryption)はサポートされていません。

正当な理由テキストは、**ファイルから機密ラベルを削除** した [監査イベント](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)に追加され、復号化アクションも [Azure Information Protectionの保護使用状況ログ](/azure/information-protection/log-analyze-usage)に記録されます。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint と OneDrive の秘密度ラベルを無効にする方法 (オプトアウト)

これらの新機能を無効にした場合、SharePoint と OneDrive の秘密度ラベルを有効にした後にアップロードしたファイルは、ラベル設定が引き続き適用されるため、引き続きラベルによって保護されます。 これらの新機能を無効にした後で新しいファイルに秘密度ラベルを適用すると、フルテキスト検索、電子情報開示、共同編集は機能しなくなります。

これらの新機能を無効にするには、PowerShell を使用する必要があります。 SharePoint Online 管理シェルと [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) コマンドレットを使用して、「[PowerShell を使用して秘密度ラベルのサポートを有効にする](#use-powershell-to-enable-support-for-sensitivity-labels)」セクションで説明されているのと同じ *EnableAIPIntegration* パラメーターを指定します。 ただし、今回はパラメーター値を false に設定し、 **Y** キーを押して確認します。

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Microsoft 365 Multi-Geo がある場合は、それぞれの地域の場所に対してこのコマンドを実行する必要があります。

## <a name="next-steps"></a>次の手順

SharePoint と OneDrive で Office ファイルの秘密度ラベルを有効にした後は、次のいずれかのラベル付け方法または両方のラベル付け方法を使用してファイルに自動的にラベルを付ける方法を検討してください。

- SharePoint の新規ファイルと編集済みファイルに対して、ドキュメント ライブラリに既定の秘密度ラベルを適用します。 詳細については、「 [SharePoint ドキュメント ライブラリの既定の秘密度ラベルを構成する](sensitivity-labels-sharepoint-default-label.md)」を参照してください。
- SharePoint と OneDrive のファイルのコンテンツ検査を使用する自動ラベル付けポリシー。 詳細については、「[秘密度ラベルを自動でコンテンツに適用する](apply-sensitivity-label-automatically.md)」を参照してください。

ラベル付けおよび暗号化されたドキュメントを組織外の人々と共有する必要がありますか?  「[暗号化されたドキュメントを外部ユーザーと共有する](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)」を参照してください。
