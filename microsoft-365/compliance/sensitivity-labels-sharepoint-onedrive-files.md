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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、Word、Excel、および PowerPoint ファイルのSharePointラベルのOneDrive。
ms.openlocfilehash: e95b4287fba3994c1e2a3515a038af4f36970202
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151040"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

SharePoint および OneDrive で[](sensitivity-labels-office-apps.md#office-file-types-supported)サポートされている Office ファイルに対して組み込みのラベル付けを有効にし、ユーザー[](sensitivity-labels.md)が Office for the web で感度ラベルを適用Office for the web。 この機能を有効にすると、リボンに [感度] ボタンが表示され、ラベルを適用し、ステータス バーに適用されたラベル名が表示されます。

また、この機能を有効にすると、SharePoint および OneDrive は、暗号化された Office ファイルの内容を、感度ラベルを使用して処理できます。 ラベルは、Office for the webまたはデスクトップ アプリOfficeに適用し、SharePointおよびOneDrive。 この機能を有効にするまで、これらのサービスは暗号化されたファイルを処理できないので、共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能は、これらのファイルでは機能しません。

SharePoint および OneDrive の Office ファイルの感度ラベルを有効にした後、クラウドベースのキーで暗号化を適用する (およびダブル キー暗号化を使用しない) 感度ラベルを持つ新しいファイルと変更[](double-key-encryption.md)されたファイルに対して次の手順を実行します。

- Word、Excel、PowerPoint、SharePointおよび OneDriveはラベルを認識し、暗号化されたファイルの内容を処理できます。

- ユーザーがこれらのファイルを SharePoint または OneDrive からダウンロードまたはアクセスすると、ラベルからの感度ラベルと暗号化設定が適用され、保存されている場所はどこでもファイルに残ります。 ラベルのみを使用してドキュメントを保護するためのユーザー ガイダンスを提供してください。 詳細については [、「Information Rights Management (IRM) オプションと感度ラベル」を参照してください](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- ユーザーがラベル付きファイルと暗号化されたファイルを SharePointまたは OneDriveにアップロードする場合、それらのファイルに対する表示権限が少なくとも必要です。 たとえば、外部のファイルを開SharePoint。 この最小使用権がない場合、アップロードは成功しますが、サービスはラベルを認識し、ファイルの内容を処理できない。

- 暗号化Office for the web付けるExcel、PowerPointを使用して、Officeファイルを開いて編集します。 暗号化で割り当てられたアクセス許可が適用されます。 これらのドキュメントには [自動ラベル付](apply-sensitivity-label-automatically.md) けも使用できます。

- 外部ユーザーは、ゲスト アカウントを使用して暗号化でラベル付けされたドキュメントにアクセスできます。 詳細については、「外部ユーザーと [ラベル付きコンテンツのサポート」を参照してください](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。

- Office 365は、これらのファイルのフルテキスト検索をサポートし、データ損失防止 (DLP) ポリシーは、これらのファイル内のコンテンツをサポートします。

> [!NOTE]
> オンプレミスのキー (キー管理トポロジは、"自分のキーを保持する" または HYOK と呼ばれることが多い) または [ダブル](double-key-encryption.md)キー暗号化を使用して暗号化が適用されている場合、ファイルの内容を処理するサービスの動作は変わりません。 したがって、これらのファイルでは、共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能は機能しません。
>
> また、SharePointおよびOneDriveの動作は、単一の Azure ベースのキーを使用して暗号化でラベル付けされたこれらの場所の既存のファイルでも変更されません。 SharePoint および OneDrive の Office ファイルの感度ラベルを有効にした後で、これらのファイルを新しい機能の恩恵を受けるには、ファイルを再度ダウンロードしてアップロードするか、編集する必要があります。

SharePoint および OneDrive の Office ファイルの感度ラベルを有効にした後、SharePoint および OneDrive[](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)のドキュメントに適用される感度ラベルを監視するために、次の 3 つの新しい監査イベントを使用できます。

- **ファイルに適用された機密ラベル**
- **ファイルに適用された機密ラベルの変更**
- **ファイルから削除された機密ラベル**

次のビデオ (音声なし) を見て、新しい機能の動作を確認します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

常に、Office および SharePoint ( OneDrive[)](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)の Office ファイルの感度ラベルを無効にすることもできます。

SharePoint Information Rights Management (IRM) を使用して SharePoint でドキュメントを現在保護している場合は、このページの SharePoint Information [Rights Management (IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels)と感度ラベルセクションを確認してください。

## <a name="requirements"></a>要件

これらの新機能は、感度ラベル [でのみ機能](sensitivity-labels.md) します。 現在 Azure Information Protection ラベルがある場合は、アップロードする新しいファイルに対してこれらの機能を有効にできるよう、最初にラベルを感度ラベルに移行します。 手順については、、「[Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](/azure/information-protection/configure-policy-migrate-labels)」を参照してください。

Windows では OneDrive 同期 アプリ バージョン 19.002.0121.0008 以降、Mac ではバージョン 19.002.0107.0008 以降を使用します。 これらのバージョンはどちらも 2019 年 1 月 28 日にリリースされ、現在すべてのリングにリリースされています。 詳細については、「リリース ノート[」OneDrive参照してください](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 SharePoint および OneDrive の Office ファイルの感度ラベルを有効にした後、以前のバージョンの同期アプリを実行するユーザーに更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- SharePoint および OneDrive は、これらのファイルに PowerQuery データ、カスタム アドインによって保存されたデータ、またはカバー ページ プロパティ、コンテンツ タイプ スキーマ、カスタム ドキュメント情報パネル、カスタム XSN などのカスタム XML パーツが含まれている場合、Office デスクトップ アプリからラベル付けおよび暗号化された一部のファイルを処理できません。 この制限は、アップロード時にドキュメント [ID](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) が追加されたファイルにも適用されます。

    これらのファイルに対して、後で Office on the web で開くことができるよう、暗号化なしのラベルを適用するか、デスクトップ アプリでファイルを開くようユーザーに指示します。 ラベル付けされ、暗号化されているファイルは、Office on the web影響を受け取らない。

- SharePointおよびOneDriveは、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに対して、感度ラベルを自動的に適用しない。 代わりに、Office ファイルの感度ラベルを有効にした後SharePoint機能をOneDrive、次のタスクを実行します。

    1. Azure Information [Protection ラベルを](/azure/information-protection/configure-policy-migrate-labels)感度ラベルに移行し、そのラベル[](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)をセキュリティ ポリシーから公開Microsoft 365 コンプライアンス センター。
    2. ラベル付きファイルをダウンロードし、そのファイルを元の場所にアップロードSharePointまたはOneDrive。

- SharePointおよびOneDrive暗号化を適用したラベルに暗号化用の次の構成がある場合、暗号化されたファイルを[処理できない](encryption-sensitivity-labels.md#configure-encryption-settings)。
  - **ラベルを適用する場合にユーザーがアクセス許可を割り当てられ**、**Word、PowerPoint、Excel でユーザーにアクセス許可を指定するように求める** のチェックボックスが選択されています。 この設定は、"ユーザー定義のアクセス許可" と呼ばれる場合があります。
  - **コンテンツへのユーザー アクセスは有効期限が切れています** は、**[使用しない]** 以外の値が設定されています。
  - **二重キー暗号化** が選択されています。

    これらの暗号化構成を持つラベルの場合、ラベルはユーザーに表示Office for the web。 さらに、これらの暗号化設定が既にあるラベル付きドキュメントでは、新しい機能を使用できません。 たとえば、これらのドキュメントは、更新された場合でも検索結果に返されません。

- パフォーマンス上の理由から、SharePoint にドキュメントをアップロードまたは保存し、ファイルのラベルが暗号化を適用しない場合、ドキュメント ライブラリの **[Sensitivity]** 列にラベル名が表示されるのに時間がかかる場合があります。 この列のラベル名に依存するスクリプトまたはオートメーションを使用する場合は、この遅延を考慮してください。

- [SharePoint](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de)でチェックアウト中にドキュメントにラベルが付いている場合、ドキュメント ライブラリの[感度] 列には、SharePoint でドキュメントがチェックインされ、次に開くまでラベル名は表示されません。

- ラベル付きおよび暗号化されたドキュメントが、サービス プリンシパル名を使用するアプリまたはサービスによって SharePoint または OneDrive からダウンロードされ、異なる暗号化設定を適用するラベルで再度アップロードされると、アップロードは失敗します。 たとえば、ファイルMicrosoft Cloud App Security機密ラベルを [機密] から [高機密]に、または [機密情報] から [全般]**に** 変更する場合 **があります**。
    
    「ラベル付きドキュメントの暗号化の削除」セクションで説明したように、アプリまたはサービスが [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) コマンドレットを最初に実行しても、アップロードは [失敗](#remove-encryption-for-a-labeled-document) しません。 または、アップロードの前に、元のファイルが削除されたか、ファイル名が変更されます。

- ユーザーは、次の [名前を付けて保存] シナリオで暗号化されたドキュメントを開くのに遅延が発生する可能性があります。 Office のデスクトップ バージョンを使用すると、暗号化を適用する感度ラベルを持つドキュメントに対して [名前を付けて保存] を選択します。 ユーザーは、SharePointまたはOneDriveを選択し、そのドキュメントをすぐに開Office for the web。 サービスが引き続き暗号化を処理している場合、ユーザーはデスクトップ アプリでドキュメントを開く必要があるというメッセージを表示します。 数分後にもう一度やり直す場合は、ドキュメントが正常に開Office for the web。

- 暗号化されたドキュメントの場合、印刷はサポートされていません。

- ユーザーに編集アクセス許可を付与する暗号化されたドキュメントの場合、コピーは Web バージョンのアプリでブロックOfficeできません。

- 既定では、Officeアプリとモバイル アプリは、暗号化でラベル付けされたファイルの共同編集をサポートしません。 これらのアプリは、ラベル付きファイルと暗号化されたファイルを排他的編集モードで引き続き開きます。
    
    > [!NOTE]
    > 共同編集は、Windows macOS でサポートされています。 詳細については、「感度ラベルで暗号化されたファイルの共同編集を有効 [にする」を参照してください](sensitivity-labels-coauthoring.md)。

- ユーザーの同期クライアントにダウンロードされたファイルに既に適用されている発行済みのラベルの設定を管理者が変更した場合、ユーザーはファイルに加えた変更を OneDrive Sync フォルダーに保存できない可能性があります。 このシナリオは、暗号化でラベル付けされたファイル、およびラベルの変更が暗号化を適用するラベルに暗号化を適用しなかったラベルからの場合にも適用されます。 ユーザーには、 [白い十字](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)アイコン エラーが表示された赤い円が表示され、新しい変更を別のコピーとして保存する必要があります。 代わりに、ファイルを閉じて再度開くか、ファイルを使用Office for the web。

- ユーザーは、Office for the web を使用する代わりに、Word、Excel、または PowerPoint のデスクトップ アプリとモバイル アプリを使用するときに、オフラインまたはスリープ モードに入った後に問題を保存できます。 これらのユーザーは、Office アプリ セッションを再開して変更を保存しようとするときに、元のファイルを保存する代わりにコピーを保存するオプションを指定したアップロードエラー メッセージが表示されます。

- 次の方法で暗号化されたドキュメントは、次の方法で開Office for the web。
  - オンプレミスのキーを使用する暗号化 ("独自のキーを保持する" または HYOK)
  - ダブル キー暗号化を使用して適用 [された暗号化](double-key-encryption.md)
  - たとえば、Rights Management 保護テンプレートを直接適用することによって、ラベルから個別に適用された暗号化。

- 他の言語 [用に構成されたラベル](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) はサポートされていません。元の言語のみを表示します。

- 暗号化されたドキュメントでは、画面キャプチャを防止できません。 詳細については、「Can [Rights Management prevent screen captures」を参照してください。](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- SharePoint または OneDrive のドキュメントに適用されているラベルを削除した場合、該当するラベル ポリシーからラベルを削除する代わりに、ダウンロードしたドキュメントにはラベルや暗号化は適用されません。 一方、ラベル付きドキュメントが SharePoint または OneDrive の外部に保存されている場合、ラベルが削除された場合、ドキュメントは暗号化されたままです。 テスト フェーズ中にラベルを削除する場合があるが、実稼働環境でラベルを削除する場合は非常にまれです。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>ユーザーとユーザーに対してSharePointラベルOneDriveする方法 (オプトイン)

新しい機能を有効にするには、新しい機能Microsoft 365 コンプライアンス センター PowerShell を使用します。 SharePoint および OneDrive のすべてのテナント レベルの構成変更と同様に、変更を有効にするのに約 15 分かかります。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>コンプライアンス センターを使用して、感度ラベルのサポートを有効にする

このオプションは、SharePoint および OneDrive の感度ラベルを有効にする最も簡単な方法ですが、テナントのグローバル管理者としてサインインする必要があります。

1. グローバル管理者 [としてMicrosoft 365 コンプライアンス センターサインイン](https://compliance.microsoft.com/)し、[ソリューション情報保護]  >  **に移動します。**

    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。

2. オンライン ファイル内のコンテンツを処理する機能を有効にするメッセージが表示された場合は、[今すぐOfficeをオンにする]**を選択します**。

    ![[今すぐ有効にする] ボタンをオンにして、オンラインの感度ラベルOfficeします。](../media/sensitivity-labels-turn-on-banner.png)

    コマンドはすぐに実行され、ページが次に更新されると、メッセージまたはボタンが表示されなくなりました。

> [!NOTE]
> 複数地域をMicrosoft 365場合は、PowerShell を使用して、すべての地域の場所でこれらの機能を有効にする必要があります。 詳細については、次のセクションを参照してください。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell を使用して、感度ラベルのサポートを有効にする

コンプライアンス センターを使用する代わりに、オンライン PowerShell の[Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant)コマンドレットを使用して、SharePointを有効にできます。

複数地域Microsoft 365場合は、PowerShell を使用して、すべての地域の場所に対してこのサポートを有効にする必要があります。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>オンライン管理シェルSharePoint準備する

powerShell コマンドを実行して SharePoint および OneDrive の Office ファイルの感度ラベルを有効にする前に、SharePoint Online Management Shell バージョン 16.0.19418.12000 以降を実行してください。 最新バージョンが既にある場合は、次の手順に[](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)進み、PowerShell コマンドを実行できます。

1. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロード センターから以前のバージョンの SharePoint Online 管理シェルをインストールしている場合は、[プログラムの追加と削除] に移動し、SharePoint Online 管理シェルをアンインストールできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 32 ビット バージョンを実行する場合は、64 ビット バージョンの Windows または x86 ファイルを実行する場合は、x64 ファイルをダウンロードします。 分からない場合は、「実行中のオペレーティング システムWindows[バージョン」を参照してください。](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. ファイルをダウンロードしたら、ファイルを実行し、セットアップ ウィザードの手順に従います。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell コマンドを実行して、感度ラベルのサポートを有効にする

新しい機能を有効にするには [、EnableAIPIntegration パラメーターで Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) コマンドレット *を使用* します。

1. グローバル管理者または管理者特権を持つ仕事または学校SharePointを使用して、Microsoft 365に接続SharePoint。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

    > [!NOTE]
    > 複数地域Microsoft 365場合は[、Connect-SPOService](/powershell/module/sharepoint-online/connect-sposervice)で -Url パラメーターを使用し、地域の場所の 1 つの SharePoint Online Administration Center サイト URL を指定します。

2. 次のコマンドを実行し **、Y キーを押して** 確認します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. [Microsoft 365: 残りの地理的位置ごとに手順 1 と 2 を繰り返します。

## <a name="publishing-and-changing-sensitivity-labels"></a>感度ラベルの発行と変更

SharePoint と OneDrive で感度ラベルを使用する場合は、新しい感度ラベルを発行したり、既存の感度ラベルを更新したりするときに、レプリケーション時間を許可する必要があります。 これは、暗号化を適用する新しいラベルで特に重要です。

たとえば、暗号化を適用する新しい感度ラベルを作成して発行すると、ユーザーのデスクトップ アプリにすばやく表示されます。 ユーザーは、このラベルをドキュメントに適用し、ドキュメントまたはドキュメントSharePointアップロードOneDrive。 サービスのラベル レプリケーションが完了しない場合、アップロード時に新しい機能はドキュメントに適用されません。 その結果、ドキュメントは検索または電子情報開示で返され、ドキュメントを電子情報開示で開くOffice for the web。

次の変更は、1 時間以内にレプリケートされます。新しいおよび削除された感度ラベルと、ポリシー内のラベルを含む感度ラベル ポリシー設定。

次の変更は、24 時間以内にレプリケートされます。既存のラベルの感度ラベル設定の変更。

レプリケーションの遅延は新しい感度ラベルの場合は 1 時間だけなので、この例ではシナリオを実行する可能性は低いと考えられます。 ただし、安全対策として、最初に数人のテスト ユーザーに新しいラベルを発行し、1 時間待ち、SharePoint と OneDrive でラベルの動作を確認することをお勧めします。 最後の手順として、既存のラベル ポリシーにユーザーを追加するか、標準ユーザーの既存のラベル ポリシーにラベルを追加して、より多くのユーザーがラベルを使用できます。 標準ユーザーにラベルが表示された時点で、ラベルは既にユーザーとSharePoint同期OneDrive。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePointInformation Rights Management (IRM) と感度ラベル

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md)は、ファイルのダウンロード時に暗号化と制限を適用して、リストおよびライブラリ レベルのファイルを保護する古いテクノロジです。 この古い保護テクノロジは、権限のないユーザーがファイルを開く際にファイルが外部にある間に開かSharePoint。

それに対して、感度ラベルは、暗号化に加えて視覚的なマーキング (ヘッダー、フッター、透かし) の保護設定を提供します。 暗号化設定は、ユーザーがコンテンツに[](/azure/information-protection/configure-usage-rights)対して実行できる操作を制限する使用権限の全範囲をサポートし、多くのシナリオで同じ感度ラベル[がサポートされています](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)。 ワークロードとアプリ間で一貫した設定で同じ保護方法を使用すると、一貫した保護戦略が実現します。

ただし、両方の保護ソリューションを一緒に使用できます。動作は次のとおりです。

- 暗号化を適用する感度ラベル付きファイルをアップロードすると、SharePoint はこれらのファイルのコンテンツを処理できないので、これらのファイルの共同編集、電子情報開示、DLP、および検索はサポートされません。

- ファイルにラベルを付Office for the web、ラベルの暗号化設定が適用されます。 これらのファイルでは、共同編集、電子情報開示、DLP、および検索がサポートされています。

- Office for the web を使用してラベル付けされたファイルをダウンロードすると、ラベルは保持され、IRM 制限設定ではなく、ラベルからの暗号化設定が適用されます。

- 暗号化されていないOfficeまたは PDF ファイルをダウンロードすると、IRM 設定が適用されます。

- 追加の IRM ライブラリ設定 (IRM をサポートしないドキュメントをユーザーがアップロードできないなど) を有効にした場合、これらの設定が適用されます。

この動作により、ラベル付けされていない場合でも、Officeおよび PDF ファイルがダウンロードされた場合、すべてのファイルと PDF ファイルが不正アクセスから保護されます。 ただし、アップロードされたラベル付きファイルは、新しい機能の恩恵を受け取るわけではありません。


## <a name="search-for-documents-by-sensitivity-label"></a>感度ラベルでドキュメントを検索する

管理プロパティ **InformationProtectionLabelId** を使用して、特定のSharePointまたはOneDriveにあるドキュメントを検索します。 次の構文を使用します。 `InformationProtectionLabelId:<GUID>`

たとえば、"Confidential" というラベルが付いたドキュメントを検索し、そのラベルに "8faca7b8-8d20-48a3-8ea2-0f96310a848e" という GUID を入力します。

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

検索では、圧縮ファイル内のラベル付きドキュメント (ファイルファイルなど) が.zipされません。

感度ラベルの GUID を取得するには [、Get-Label コマンドレットを使用](/powershell/module/exchange/get-label) します。

1. まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

    たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。

2. 次に、次のコマンドを実行します。

    ```powershell
    Get-Label |ft Name, Guid
    ```

管理プロパティの使用の詳細については、「Manage [the search schema in SharePoint」 を参照してください](/sharepoint/manage-search-schema)。

## <a name="remove-encryption-for-a-labeled-document"></a>ラベル付きドキュメントの暗号化を削除する

管理者が管理者が、SharePointに保存されているドキュメントから暗号化を削除する必要がある場合は、まれにSharePoint。 そのドキュメントに割り[](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)当てられているエクスポートまたはフル コントロールの権限管理の使用権を持つユーザーは、Azure Rights Management サービスによって Azure Information Protection から適用された暗号化を削除できます。 たとえば、これらの使用権限を持つユーザーは、暗号化を適用するラベルを暗号化なしのラベルに置き換える可能性があります。 スーパー [ユーザーは、](/azure/information-protection/configure-super-users) ファイルをダウンロードし、暗号化なしでローカル コピーを保存できます。

代わりに、グローバル管理者または[SharePoint](/sharepoint/sharepoint-admin-role)管理者は[Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile)コマンドレットを実行して、感度ラベルと暗号化の両方を削除できます。 このコマンドレットは、管理者がサイトまたはファイルへのアクセス許可を持っていなくても、Azure Rights Management サービスが利用できない場合でも実行されます。

次に例を示します。

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

要件:

- SharePointオンライン管理シェル バージョン 16.0.20616.12000 以降。

- 暗号化は、管理者が定義した暗号化設定 ([アクセス許可の割り当て] ラベル設定) を持つ感度ラベル [によって](encryption-sensitivity-labels.md#assign-permissions-now) 適用されています。 [このコマンドレットでは](encryption-sensitivity-labels.md#double-key-encryption) 、ダブル キー暗号化はサポートされていません。

ファイルから削除された秘密度ラベルの監査[](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)イベントに位置合わせテキストが追加され、復号化アクションは Azure Information Protection の保護使用状況ログにも[記録されます](/azure/information-protection/log-analyze-usage)。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>ユーザーとユーザーに対してSharePointラベルOneDriveする方法 (オプトアウト)

これらの新機能を無効にすると、SharePoint と OneDrive の感度ラベルを有効にした後にアップロードしたファイルは、ラベル設定が引き続き適用されるので、ラベルによって引き続き保護されます。 これらの新機能を無効にした後で、新しいファイルに感度ラベルを適用すると、フルテキスト検索、電子情報開示、および共同編集は機能しなくなりました。

これらの新機能を無効にするには、PowerShell を使用する必要があります。 SharePoint Online 管理シェルと [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant)コマンドレットを使用して [、「PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels)を使用して感度ラベルのサポートを有効にする」セクションで説明されているのと同じ *EnableAIPIntegration* パラメーターを指定します。 ただし、今回はパラメーター値を false に設定し **、Y キーを** 押して確認します。

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

複数地域をMicrosoft 365場合は、各地域の場所に対してこのコマンドを実行する必要があります。

## <a name="next-steps"></a>次の手順

SharePoint および OneDrive の Office ファイルの感度ラベルを有効にした後、自動ラベル付けポリシーを使用してこれらのファイルに自動的にラベルを付ける方法を検討してください。 詳細については、「コンテンツに感度 [ラベルを自動的に適用する」を参照してください](apply-sensitivity-label-automatically.md)。

ラベル付けおよび暗号化されたドキュメントを組織外の人々と共有する必要がありますか?  「[暗号化されたドキュメントを外部ユーザーと共有する](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)」を参照してください。
