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
description: 管理者は、SharePoint および OneDrive で Word、Excel、PowerPoint ファイルの区別ラベルのサポートを有効にできます。
ms.openlocfilehash: b4981e8f2fda88f9ba078b29e70d572b7bcc7ce2
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150491"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

SharePoint および OneDrive Officeファイルの区別ラベルを有効にして、ユーザーが Web[](sensitivity-labels.md)上の Officeに適用できます。 この機能を有効にすると、リボンに **[Sensitivity]** ボタンが表示され、ラベルを適用し、ステータス バーに適用されているラベル名を確認できます。 

この機能を有効にすると、SharePoint と OneDrive は、暗号化されたファイルの内容を、区別ラベルを使用して処理できます。 ラベルは、Web 用の Office または Office デスクトップ アプリで適用し、SharePoint と OneDrive にアップロードまたは保存できます。 この機能を有効にするまで、これらのサービスは暗号化されたファイルを処理できないので、共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能は、これらのファイルでは機能しません。

SharePoint および OneDrive で Office ファイルの区別ラベルを有効にした後、クラウドベースのキーによる暗号化を適用する (二重キー暗号化を使用しない) 新しいファイルと変更[](double-key-encryption.md)されたファイルに対して、次の手順を実行します。

- Word、Excel、PowerPoint ファイルの場合、SharePoint と OneDrive はラベルを認識し、暗号化されたファイルの内容を処理できます。

- ユーザーが SharePoint または OneDrive からこれらのファイルをダウンロードまたはアクセスすると、ラベルの区別ラベルと暗号化設定が適用され、ファイルが保存されている場所に置き換わります。 ラベルのみを使用してドキュメントを保護するためのユーザー ガイダンスを提供してください。 詳細については [、「Information Rights Management (IRM) のオプションと感度ラベル」を参照してください](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- ラベル付きおよび暗号化されたファイルを SharePoint または OneDrive にアップロードする場合は、少なくともこれらのファイルに対する表示権限が必要です。 たとえば、SharePoint の外部でファイルを開く場合があります。 この最小限の使用権を持たなかった場合、アップロードは成功しますが、サービスはラベルを認識し、ファイルの内容を処理できない。

- Web Office (Word、Excel、PowerPoint) を使用して、暗号化を適用するOffice付けファイルを開いて編集します。 暗号化で割り当てられたアクセス許可が適用されます。 これらのドキュメントに [対して自動ラベル付](apply-sensitivity-label-automatically.md) けも使用できます。

- 外部ユーザーは、ゲスト アカウントを使用して暗号化のラベルが付いたドキュメントにアクセスできます。 詳細については、「外部ユーザー [とラベル付きコンテンツのサポート」を参照してください](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。 

- Office 365 電子情報開示は、これらのファイルのフルテキスト検索をサポートし、データ損失防止 (DLP) ポリシーは、これらのファイル内のコンテンツをサポートします。

> [!NOTE]
> オンプレミスキー (キー管理トポロジは"自分のキーを保持する" または HYOK と呼ばれることが多い) を使用して暗号化が適用されている場合、または [Double Key Encryption](double-key-encryption.md)を使用した場合、ファイルの内容を処理するサービスの動作は変わりません。 そのため、これらのファイルでは、共同編集、電子情報開示、データ損失防止、検索、その他の共同作業機能は機能しません。
>
> SharePoint と OneDrive の動作も、単一の Azure ベースのキーを使用した暗号化のラベルが付いたこれらの場所の既存のファイルでは変更されません。 SharePoint と OneDrive で Office ファイルの区別ラベルを有効にした後でこれらのファイルが新しい機能を活用するには、ファイルを再びダウンロードしてアップロードするか、編集する必要があります。

SharePoint および OneDrive で Office ファイルの区別ラベルを有効にした後[](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)、SharePoint および OneDrive のドキュメントに適用される区別ラベルを監視するために、次の 3 つの新しい監査イベントを使用できます。
- **ファイルに適用された機密ラベル**
- **ファイルに適用された機密ラベルの変更**
- **ファイルから削除された機密ラベル**

次のビデオ (音声なし) を見て、新しい機能の動作を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

SharePoint および OneDrive のファイルのOffice[ラベルを無効](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)にする (オプトアウト) オプションはいつでも選択できます。

現在、SharePoint Information Rights Management (IRM) を使用して SharePoint のドキュメントを保護している場合は、このページで [SharePoint Information Rights Management (IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) と感度ラベルのセクションを確認してください。 

## <a name="requirements"></a>要件

これらの新しい機能は、区別ラベル [でのみ機能](sensitivity-labels.md) します。 現在 Azure Information Protection ラベルがある場合は、まず、アップロードする新しいファイルに対してこれらの機能を有効にできるよう、ラベルを区別ラベルに移行します。 手順については、「Azure Information Protection ラベルを [統合された区別ラベルに移行する方法」を参照してください](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)。

Windows では OneDrive 同期アプリ バージョン 19.002.0121.0008 以降、Mac ではバージョン 19.002.0107.0008 以降を使用します。 これらのバージョンはいずれも 2019 年 1 月 28 日にリリースされ、現在すべてのリングにリリースされています。 詳細については [、OneDrive のリリース ノートを参照してください](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 SharePoint および OneDrive の Office ファイルの区別ラベルを有効にした後、古いバージョンの同期アプリを実行するユーザーは、更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- SharePoint と OneDrive では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに、自動的に区別ラベルが適用されません。 代わりに、SharePoint と OneDrive でファイルのOfficeラベルを有効にした後に機能を機能するには、次のタスクを実行します。
    
    1. Azure Information [Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)ラベルを感度ラベルに移行し、Microsoft [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 365 コンプライアンス センターまたは同等のラベル付け管理センターから発行済みである必要があります。
    
    2. ファイルをダウンロードし、SharePoint にアップロードします。

- 暗号化を適用したラベルに暗号化用の次のいずれかの構成がある場合、SharePoint と OneDrive は暗号化されたファイル [を処理できない](encryption-sensitivity-labels.md#configure-encryption-settings)。
    - **ユーザーがラベルと** チェック ボックスを適用するときに **、Word、PowerPoint、および Excel** でアクセス許可を割り当て、ユーザーにアクセス許可の指定を求めるメッセージが選択されます。 この設定は、"ユーザー定義のアクセス許可" と呼ばれる場合があります。
    - **コンテンツへのユーザー アクセスの有効期限は** 、Never 以外の値に **設定されます**。
    - **[二重キー暗号化** ] が選択されています。
    
    これらの暗号化構成のラベルの場合、ラベルは Web 上のユーザーにOfficeされません。 さらに、これらの暗号化設定が既にあるラベル付きドキュメントでは、新しい機能を使用できません。 たとえば、これらのドキュメントは更新された場合でも、検索結果に返されません。

- ユーザーに編集アクセス許可を付与する暗号化されたドキュメントの場合、web バージョンの Office アプリでコピーをブロックすることはできません。

- Azure Information Protection ドキュメント追跡サイトはサポートされていません。

- Officeアプリとモバイル アプリでは、暗号化のラベルが付いたファイルの共同編集はサポートされていません。 これらのアプリは、排他的編集モードで、ラベル付きファイルと暗号化されたファイルを引き続き開きます。

- 管理者が、ユーザーの同期クライアントにダウンロードされたファイルに既に適用されている発行済みのラベルの設定を変更した場合、ユーザーはファイルに加えた変更を OneDrive Sync フォルダーに保存できない可能性があります。 このシナリオは、暗号化でラベル付けされたファイルに適用されます。また、ラベルの変更が、暗号化を適用するラベルに暗号化を適用していないラベルからの場合にも適用されます。 ユーザーには、白 [い十字](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)アイコンのエラーが表示された赤い円が表示され、新しい変更を別のコピーとして保存する必要があります。 代わりに、ファイルを閉じて再度開くか、web Officeを使用できます。

- ラベル付きドキュメントが SharePoint または OneDrive にアップロードされ、サービス プリンシパル名のアカウントを使用して暗号化が適用されたラベルは、web 上の Office で開くことができません。 シナリオの例としては、Microsoft Cloud App Security や、Teams に電子メールで送信されるファイルがあります。

- ユーザーは、Web 用の Office を使用する代わりに、Word、Excel、または PowerPoint 用のデスクトップ アプリとモバイル アプリを使用する場合に、オフラインまたはスリープ モードに入った後に問題を解決できます。 これらのユーザーの場合、Office アプリ セッションを再開して変更の保存を試みた場合、元のファイルを保存する代わりにコピーを保存するオプションを含むアップロード エラー メッセージが表示されます。 

- 次の方法で暗号化されたドキュメントは、web 上Office開くことができません。
    - オンプレミスキーを使用する暗号化 ("自分のキーを保持する" または HYOK)
    - 二重キー暗号化を使用して [適用された暗号化](double-key-encryption.md)
    - ラベルとは別に適用された暗号化 。たとえば、Rights Management 保護テンプレートを直接適用します。

- 他の言語 [用に構成されたラベル](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) はサポートされていないので、元の言語のみを表示します。

- 暗号化されたドキュメントでは、画面キャプチャを防止できません。 詳細については [、「Can Rights Management による画面キャプチャの防止」を参照してください。](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- 該当するラベル ポリシーからラベルを削除するのではなく、SharePoint または OneDrive のドキュメントに適用されているラベルを削除した場合、ダウンロード時のドキュメントはラベル付けも暗号化もされません。 一方、ラベル付きドキュメントが SharePoint または OneDrive の外部に保存されている場合、ラベルが削除された場合でもドキュメントは暗号化されたままです。 テスト フェーズ中にラベルを削除する可能性は高い点に注意してください。ただし、実稼働環境でラベルを削除する場合は非常にまれです。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint と OneDrive の区別ラベルを有効にする方法 (オプトイン)

Microsoft 365 コンプライアンス センターを使用するか、PowerShell を使用して、新しい機能を有効にできます。 SharePoint と OneDrive のすべてのテナント レベルの構成の変更と同様に、変更が有効にするのに約 15 分かかります。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>コンプライアンス センターを使用して、区別ラベルのサポートを有効にする

このオプションは、SharePoint と OneDrive の区別ラベルを有効にする最も簡単な方法ですが、テナントの全体管理者としてサインインする必要があります。

1. グローバル管理者として [Microsoft 365 コンプライアンス](https://compliance.microsoft.com/)センターにサインインし、[ソリューション情報の保護 **] に**  >  **移動します。**
    
    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。 

2. オンライン ファイル内のコンテンツを処理する機能を有効にするメッセージOffice、[今すぐ有効にする] を **選択します**。
    
    ![[今すぐ有効にする] ボタンをオンにして、Office Online のOfficeする](../media/sensitivity-labels-turn-on-banner.png)
    
    コマンドはすぐに実行され、ページが次に更新されると、メッセージまたはボタンが表示されなくなりました。

> [!NOTE]
> Microsoft 365 Multi-Geo を使用している場合は、PowerShell を使用して、すべての地域の場所でこれらの機能を有効にする必要があります。 詳細については、次のセクションを参照してください。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell を使用して、区別ラベルのサポートを有効にする

コンプライアンス センターを使用する代わりに、SharePoint Online PowerShell から [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) コマンドレットを使用して、感度ラベルのサポートを有効にできます。 

Microsoft 365 Multi-Geo を使用している場合は、PowerShell を使用して、すべての地域の場所に対してこのサポートを有効にする必要があります。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 管理シェルを準備する

PowerShell コマンドを実行して SharePoint および OneDrive の Office ファイルの感度ラベルを有効にする前に、SharePoint Online 管理シェル バージョン 16.0.19418.12000 以降を実行してください。 既に最新バージョンを使用している場合は、次の[](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)手順に進み、PowerShell コマンドを実行できます。

1. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロード センターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[プログラムの追加と削除] に移動して SharePoint Online 管理シェルをアンインストールできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 64 ビット バージョンの Windows を実行する場合は x64 ファイルをダウンロードし、32 ビット バージョンを実行する場合は x86 ファイルをダウンロードします。 分からない場合は、実行している Windows オペレーティング [システムのバージョンを確認してください。](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. ファイルをダウンロードしたら、ファイルを実行し、セットアップ ウィザードの手順に従います。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell コマンドを実行して、区別ラベルのサポートを有効にする

新しい機能を有効にするには [、Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) コマンドレットを *EnableAIPIntegration パラメーター* と一緒に使用します。

1. Microsoft 365 の全体管理者または SharePoint 管理者特権を持つ、仕事または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。
    
    注: Microsoft 365 Multi-Geo を使用している場合は、-Url パラメーターを [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice)と一緒に使用し、地域の場所の 1 つについて SharePoint Online 管理センター サイトの URL を指定します。

2. 次のコマンドを実行し **、Y キーを押** して確認します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Microsoft 365 Multi-Geo の場合: 残りの地域の場所ごとに手順 1 と 2 を繰り返します。

## <a name="publishing-and-changing-sensitivity-labels"></a>ラベルの公開と変更

SharePoint と OneDrive で感度ラベルを使用する場合は、新しい感度ラベルを発行したり、既存の区別ラベルを更新したりするときに、レプリケーション時間を許可する必要がある点に念頭に置きます。 これは、暗号化を適用する新しいラベルで特に重要です。

たとえば、暗号化を適用する新しい区別ラベルを作成して発行すると、ユーザーのデスクトップ アプリにすばやく表示されます。 ユーザーは、このラベルをドキュメントに適用し、SharePoint または OneDrive にアップロードします。 ラベルのレプリケーションがサービスに対して完了しない場合、アップロード時に新しい機能はドキュメントに適用されません。 その結果、ドキュメントは検索または電子情報開示で返されません。また、ドキュメントを Web 用の Officeで開く必要があります。  

次の変更は、1 時間以内にレプリケートされます。新規および削除された区別ラベル、およびポリシーに含まれるラベルを含む、ラベルのポリシー設定。

次の変更は、24 時間以内にレプリケートされます。既存のラベルの区別ラベル設定に対する変更。

新しい区別ラベルのレプリケーション遅延は 1 時間だけなので、この例のシナリオに出る可能性は低いと考えられます。 ただし、保護策として、最初に数名のテスト ユーザーに新しいラベルを発行し、1 時間待ち、SharePoint と OneDrive でラベルの動作を確認することをお勧めします。 最後の手順として、既存のラベル ポリシーにユーザーを追加するか、標準ユーザーの既存のラベル ポリシーにラベルを追加して、ラベルをより多くのユーザーが使用できます。 標準ユーザーにラベルが表示された時点で、そのラベルは既に SharePoint と OneDrive に同期されています。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) および感度ラベル

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) は、ファイルのダウンロード時に暗号化と制限を適用することで、リストレベルおよびライブラリ レベルでファイルを保護する古いテクノロジです。 この古い保護テクノロジは、承認されていないユーザーが SharePoint の外部でファイルを開くのを防ぐことを目的として設計されています。

一方、機応性ラベルは、暗号化に加えて視覚的なマーキング (ヘッダー、フッター、透かし) の保護設定を提供します。 暗号化設定は、ユーザーがコンテンツに[](https://docs.microsoft.com/azure/information-protection/configure-usage-rights)対して実行できる操作を制限する使用権限の範囲全体をサポートし、多くのシナリオで同じ感度ラベル[がサポートされています](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)。 ワークロードとアプリ間で一貫した設定で同じ保護方法を使用すると、一貫した保護戦略が実現されます。

ただし、両方の保護ソリューションを一緒に使用できます。動作は次のとおりです。 

- 暗号化を適用する区別ラベルを持つファイルをアップロードすると、SharePoint はこれらのファイルのコンテンツを処理できないので、これらのファイルの共同編集、電子情報開示、DLP、および検索はサポートされません。

- web 上のファイルを使用してOfficeすると、ラベルの暗号化設定が適用されます。 これらのファイルでは、共同編集、電子情報開示、DLP、および検索がサポートされています。

- Office on the web を使用してラベル付けされたファイルをダウンロードすると、ラベルは保持され、IRM 制限設定ではなくラベルの暗号化設定が適用されます。

- 暗号化されていないOfficeファイルまたは PDF ファイルをダウンロードすると、IRM 設定が適用されます。

- 追加の IRM ライブラリ設定 (IRM をサポートしないドキュメントをユーザーがアップロードできないなど) を有効にした場合は、これらの設定が適用されます。

この動作を使用すると、ラベルが付けなくても、すべての Office ファイルと PDF ファイルがダウンロードされた場合、承認されていないアクセスから保護されます。 ただし、アップロードされたラベル付きファイルは、新しい機能を利用できません。


## <a name="search-for-documents-by-sensitivity-label"></a>ドキュメントを区別ラベルで検索する    

管理プロパティ **InformationProtectionLabelId** を使用して、特定の感度ラベルを持つ SharePoint または OneDrive 内のすべてのドキュメントを検索します。 次の構文を使用します。 `InformationProtectionLabelId:<GUID>`

たとえば、"Confidential" というラベルが付いた、そのラベルの GUID が "8faca7b8-8d20-48a3-8ea2-0f96310a848e" であるすべてのドキュメントを検索するには、検索ボックスに次のように入力します。

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

感度ラベルの GUID を取得するには [、Get-Label コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/get-label) します。  

1. まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
   
    たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。    

2. 次に、次のコマンドを実行します。  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

管理プロパティの使用の詳細については [、「SharePoint で検索スキーマを管理する」を参照してください](https://docs.microsoft.com/sharepoint/manage-search-schema)。

## <a name="remove-encryption-for-a-labeled-document"></a>ラベル付きドキュメントの暗号化を削除する

SharePoint 管理者が SharePoint に保存されているドキュメントから暗号化を削除する必要がある場合はまれです。 そのドキュメントに対して [Rights Management](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) の使用権 (エクスポートまたはフル コントロール) が割り当てられているユーザーは、Azure Information Protection から Azure Rights Management サービスによって適用された暗号化を削除できます。 たとえば、これらの使用権のいずれかを持つユーザーは、暗号化を適用するラベルを暗号化なしのラベルに置き換える場合があります。 または、スーパー ユーザー [は、](https://docs.microsoft.com/azure/information-protection/configure-super-users) 暗号化を使用せずにファイルをダウンロードしてローカル コピーを保存できます。

代わりに、全体管理者または [SharePoint](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) 管理者は [Unlock-SPOSensitivityLabelEncryptedFile](https://docs.microsoft.com/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) コマンドレットを実行して、区別ラベルと暗号化の両方を削除できます。 このコマンドレットは、管理者がサイトまたはファイルに対するアクセス許可を持たなかったり、Azure Rights Management サービスが利用できない場合でも実行されます。 

例:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

要件:

- SharePoint Online 管理シェル バージョン 16.0.20616.12000 以降。

- 暗号化は、管理者が定義した暗号化設定 ([アクセス許可の割り当て] ラベル設定) を持つ、区別 [ラベルによって](encryption-sensitivity-labels.md#assign-permissions-now) 適用されています。 [このコマンドレットでは](encryption-sensitivity-labels.md#double-key-encryption) 、二重キー暗号化はサポートされていません。

理由テキストは、ファイルから削除された秘密[](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)度ラベルの監査イベントに追加され、復号化アクションは Azure Information Protection の保護利用状況ログにも[記録されます](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint と OneDrive の区別ラベルを無効にする方法 (オプトアウト)

これらの新機能を無効にした場合、SharePoint と OneDrive の区別ラベルを有効にした後にアップロードしたファイルは、ラベルの設定が引き続き適用されるので、ラベルによって引き続き保護されます。 新しい機能を無効にした後で新しいファイルに区別ラベルを適用すると、フルテキスト検索、電子情報開示、共同編集は機能しなくなりました。

これらの新機能を無効にするには、PowerShell を使用する必要があります。 SharePoint Online 管理シェルと [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant)コマンドレットを使用して [、「PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels)を使用して感度ラベルのサポートを有効にする」セクションで説明されているのと同じ *EnableAIPIntegration* パラメーターを指定します。 ただし、今回はパラメーター値を false に設定し **、Y キーを** 押して次の確認を行います。

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Microsoft 365 Multi-Geo を使用している場合は、各地域の場所に対してこのコマンドを実行する必要があります。

## <a name="next-steps"></a>次の手順

SharePoint と OneDrive で Office ファイルの区別ラベルを有効にした後、自動ラベル付けポリシーを使用してこれらのファイルに自動的にラベルを付ける方法を検討してください。 詳細については、「コンテンツに自動的 [に感度ラベルを適用する」を参照してください](apply-sensitivity-label-automatically.md)。

ラベル付けおよび暗号化されたドキュメントを組織外の人々と共有する必要がありますか?  「[暗号化されたドキュメントを外部ユーザーと共有する](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)」を参照してください。
