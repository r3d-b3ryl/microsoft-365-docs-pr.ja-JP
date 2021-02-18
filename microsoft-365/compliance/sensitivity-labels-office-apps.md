---
title: Office アプリで秘密度ラベルを管理する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: デスクトップ、モバイル、および Web 用アプリで Officeラベルを管理するための IT 管理者向け情報。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d7fd75aaa1b6f54222252c3e8379aaed2c4c223
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290812"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Office アプリで秘密度ラベルを管理する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft 365 コンプライアンス センターまたは同等のラベル付けセンターから公開したラベルは、ユーザーがデータの作成または編集時に分類および保護するために Office アプリに表示され始める。 [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)

この記事の情報を使用して、新しいアプリでラベルのOfficeしてください。 たとえば、組み込みのラベル付けをサポートするために必要なアプリの最小バージョンを特定し、Azure Information Protection 統合ラベル付けクライアントとのやり取りや、他のアプリやサービスとの互換性について理解します。

## <a name="labeling-client-for-desktop-apps"></a>デスクトップ アプリのラベル付けクライアント

Windows および Mac 用のデスクトップ Officeに組み込みの区別ラベルを使用するには、サブスクリプション エディションの Office。 このラベル付けクライアントは、Office 2016 や Office 2019 などのスタンドアロン エディションOfficeサポートされていません。

Windows コンピューターでこれらのスタンドアロン エディションの Office と一緒に区別ラベルを使用するには [、Azure Information Protection 統合ラベル付けクライアントをインストールします](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>アプリでの区別ラベル機能のサポート

各機能について、次の表に、組み込みのラベル付Office使用して、区別ラベルをサポートするために必要な最小のバージョンを示します。 または、ラベル機能がパブリック プレビューの場合、または今後のリリースでレビュー中である場合。 今後の [リリースの詳細については、Microsoft 365](https://aka.ms/MIPC/Roadmap) ロードマップを使用してください。

新しいバージョンの Officeアプリは、更新プログラム チャネルごとに異なる時間に利用できます。 関心のある新しいラベル付け機能をテストできるよう更新プログラム チャネルを構成する方法など、詳細については [、「Microsoft 365 アプリ](https://docs.microsoft.com/DeployOffice/overview-update-channels)の更新プログラム チャネルの概要」を参照してください。 プライベート プレビューの新機能は表に含まれていませんが [、Microsoft Information Protection](https://aka.ms/mip-preview)プライベート プレビュー プログラムに組織を指名することで、これらのプレビューに参加できる場合があります。

> [!NOTE]
> アプリの更新プログラム チャネルのOfficeが最近変更されました。 たとえば、月次チャネルは現在のチャネルで、Insider Officeはベータ チャネルです。 詳細については [、「Microsoft 365 アプリのチャネルを更新する変更」を参照してください](https://docs.microsoft.com/deployoffice/update-channels-changes)。

Office iOS および Android Officeの場合: Office [アプリにOfficeされます](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)。

追加の機能は、Windows コンピューターでのみ実行される Azure Information Protection 統合ラベル付けクライアントをインストールする場合に使用できます。 これらの詳細については、「Windows コンピューターの [ラベル付けクライアントを比較する」を参照してください](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel、PowerPoint の感度ラベル機能

各機能に必要なOfficeの最小バージョンを示す数値を示します。

|機能                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手動でラベルを適用、変更、または削除する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上          | 16.21+     | 2.21以上 | 16.0.11231以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上          | 16.21+     | 2.21以上 | 16.0.11231以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[ラベルを変更する理由を要求する](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上          | 16.21+     | 2.21以上 | 16.0.11231以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[カスタム ヘルプ ページへのヘルプ リンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上          | 16.21+     | 2.21以上 | 16.0.11231以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[コンテンツをマークする](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910以上          | 16.21+     | 2.21以上 | 16.0.11231以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[変数を使用した動的なマーキング](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | レビュー中 |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上          | 16.21+     | 2.21以上 | 16.0.11231以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | レビュー中   | レビュー中         | レビュー中                                                        |
|[データ分類の使用を開始し](data-classification-overview.md) 、管理者向けデータを送信する                      | 2011+ | 16.43+ | プレビュー: [現在のチャネル (プレビュー)](https://office.com/insider) | プレビュー: [現在のチャネル (プレビュー)](https://office.com/insider) | はい <sup>\*</sup>                                                        |
|[ユーザーに電子メールとドキュメントへのラベルの適用を要求する](#require-users-to-apply-a-label-to-their-email-and-documents)   | プレビュー: [現在のチャネル (プレビュー)](https://office.com/insider)             | プレビュー: [現在のチャネル (プレビュー)](https://office.com/insider)         | レビュー中   | ロール アウト: 16.0.13628+ | レビュー中                                            
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | 2009+                                  | ロール アウト: 16.44+ | レビュー中 | レビュー中 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|ラベル [付きおよび](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 暗号化 [されたドキュメントの](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) 自動保存と共同編集をサポートする | レビュー中 | レビュー中 | レビュー中 | レビュー中 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**脚注:**

<sup>\*</sup> 現時点では、ラベルを削除したり分類レベルを下げる理由テキストは含めなかった

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook の感度ラベル機能

各機能に必要なOfficeの最小バージョンを示す数値を示します。

|機能                                                                                                        |Outlook for Windows |Outlook for Mac |Outlook on iOS |Outlook on Android |Outlook on the web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手動でラベルを適用、変更、または削除する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[ラベルを変更する理由を要求する](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[カスタム ヘルプ ページへのヘルプ リンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[コンテンツをマークする](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[変数を使用した動的なマーキング](#dynamic-markings-with-variables)                                              | レビュー中                     | レビュー中                 | レビュー中         | レビュー中           | レビュー中               |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910以上                     | 16.21+                 | 4.7.1+         | 4.0.39+           | はい               |
|[ユーザーに電子メールとドキュメントへのラベルの適用を要求する](#require-users-to-apply-a-label-to-their-email-and-documents)   | プレビュー:[現在のチャネル (プレビュー)](https://office.com/insider)                        | 16.43+                     | レビュー中            | レビュー中                | はい                |
|[データ分類の使用を開始し](data-classification-overview.md) 、管理者向けデータを送信する                      | 2011+ | レビュー中 | レビュー中           | レビュー中               | レビュー中 |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+                    | レビュー中           | レビュー中               | はい |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Officeのラベル付けクライアントおよび他のラベル付けソリューション

組Officeラベル付けクライアントは、次の管理センターから、感度ラベルと感度ラベル ポリシー設定をダウンロードします。

- Microsoft 365 コンプライアンス センター
- Microsoft 365 セキュリティ センター
- Office 365 セキュリティ/コンプライアンス センター

Office 組み込みのラベル付けクライアントを使用するには、リストされている管理センターの[](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)1 つおよびサポートされているバージョンの Office から 1 つ以上のラベル ポリシーをユーザーに公開[する必要があります](#support-for-sensitivity-label-capabilities-in-apps)。

これらの両方の条件が満たされているが、組み込みのラベル付けクライアントOfficeオフにする必要がある場合は、次のグループ ポリシー設定を使用します。

1. ユーザーの **構成/管理用テンプレート/Microsoft Office 2016/[セキュリティの設定] に移動します**。

2. [Office で **[Sensitivity]** 機能を使用して、Officeラベルを **適用および表示するには 0 に設定します**。 
 
この設定は、グループ ポリシーを使用するか、クラウド ポリシー Office [使用して展開します](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。 この設定は、アプリが再起動Office有効になります。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Officeのラベル付けクライアントと Azure Information Protection クライアント

Azure Information Protection[クライアントの](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)1 つ (統合ラベル付[](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)けクライアントまたは従来のクライアント) が既定でインストールされている場合、組み込みのラベル付けクライアントは Office アプリでオフになります。 

Office アプリの Azure Information Protection クライアントではなく、組み込みのラベル付けを使用するには、前のセクションの手順を使用しますが、グループポリシー設定 Office の [感度] 機能を使用して、区別ラベルを適用および表示するには **1** に設定します。 

または、Azure Information Protection Officeを無効または **削除します**。 この方法は、1 台のコンピューターとアドホック テストに適しています。 手順については、次のプログラムでアドインを表示、管理 [、インストールOfficeしてください](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)。 

このアドインを無効にするかOfficeすると、Azure Information Protection クライアントがインストールされたままなので、引き続きアプリの外部にあるファイルにラベルを付Officeできます。 たとえば、エクスプローラーまたは PowerShell を使用します。

Azure Information Protection クライアントと Office 組み込みのラベル付けクライアントでサポートされている機能の詳細については、「Azure Information Protection」のドキュメントの [「Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) コンピューターで使用するラベル付けクライアントを選択する」を参照してください。

## <a name="office-file-types-supported"></a>Officeされるファイルの種類

word、Excel、PowerPoint ファイルに組み込みのラベル付けがある Office アプリでは、Open XML 形式 (.docx や .xlsx など) がサポートされますが、Microsoft Office 97-2003 形式 (.doc や .xls など)、Open Document Format (.odt や .ods など)、その他の形式はサポートされていません。 組み込みのラベル付けでファイルの種類がサポートされていない場合、アプリの [区別] Officeできません。

Azure Information Protection 統合ラベル付けクライアントは、Open XML 形式と Microsoft Office 97-2003 形式の両方をサポートします。 詳細については、Azure [Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 統合ラベル付けクライアントでサポートされているファイルの種類を、そのクライアントの管理者ガイドで参照してください。

その他のラベル付けソリューションについては、そのドキュメントでサポートされているファイルの種類を確認してください。

## <a name="protection-templates-and-sensitivity-labels"></a>保護テンプレートと感度ラベル

Office 365 Message Encryption 用に定義した保護テンプレートなど、管理者が定義した保護テンプレートは、組み込みのラベル付けを使用している場合、Office アプリでは表示されません。 [](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) この簡素化されたエクスペリエンスは、暗号化が有効になっている区別ラベルに同じ設定が含まれているため、保護テンプレートを選択する必要がないことを反映しています。

既存の保護テンプレートをラベルに変換する必要がある場合は、Azure portal と次の手順を使用します。テンプレートをラベルに [変換するには](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Information Rights Management (IRM) オプションと感度ラベル

暗号化を適用するために構成した区別ラベルは、ユーザーが独自の暗号化設定を指定する複雑さを取り除きます。 多くのOfficeでは、これらの個々の暗号化設定は、Information Rights Management (IRM) オプションを使用してユーザーが手動で構成できます。 たとえば、Windows アプリの場合:

- ドキュメントの場合:**ファイル**  >  **情報保護**  >  **ドキュメント**  >  **制限アクセス**
- 電子メールの場合: [オプション]**タブの**[暗号化>  
  
ユーザーは、最初にドキュメントまたは電子メールにラベルを付け始め、ラベル構成設定を独自の暗号化設定でいつでも上書きできます。 例:

- ユーザーがドキュメントに **[機密] # [すべての従業員** ] ラベルを適用し、このラベルは組織内のすべてのユーザーに暗号化設定を適用するように構成されます。 次に、このユーザーは IRM 設定を手動で構成して、組織外のユーザーへのアクセスを制限します。 最後の結果は、「Confidential \ All **Employees」** というラベルが付いて暗号化されたドキュメントですが、組織内のユーザーは期待通り開くことができません。

- ユーザーが電子メールに **[機密] # [** 受信者のみ] ラベルを適用し、この電子メールは [転送しない] の暗号化設定 **を適用するように構成されています**。 次に、このユーザーは、電子メールが制限を受け付けなく IRM 設定を手動で構成します。 最後の結果として、"Confidential **\ Recipients Only"** ラベルがあるにもかかわらず、受信者がメールを転送できます。

- ユーザーがドキュメントに [全般 **]** ラベルを適用し、このラベルは暗号化を適用するように構成されていません。 次に、このユーザーは IRM 設定を手動で構成して、ドキュメントへのアクセスを制限します。 最後の結果は、[全般] というラベルが付いたドキュメントですが、暗号化も適用され、一部のユーザーが期待した通り開くことができません。

ドキュメントまたは電子メールに既にラベルが付けされている場合、コンテンツが暗号化されていない場合、または使用権限がエクスポートまたはフル コントロールである場合、[](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)ユーザーはこれらの操作を実行できます。 

わかりやすいレポートを作成してラベルエクスペリエンスの一貫性を高めるために、ユーザーがドキュメントを保護するためにラベルのみを適用するための適切なラベルとガイダンスを提供します。 例:

- ユーザーが独自のアクセス許可を割り当てる必要がある例外の場合は、ユーザーが自分のアクセス許可を割り当て [可能なラベルを提供します](encryption-sensitivity-labels.md#let-users-assign-permissions)。 

- 暗号化を適用するラベルを選択した後、ユーザーが手動で暗号化を削除する代わりに、ユーザーが同じ分類のラベルを必要とするが、暗号化は必要ない場合は、サブラベルの代替手段を提供します。 次に例を示します。
    - **Confidential \ All Employees**
    - **Confidential \ Anyone (暗号化なし)**

> [!NOTE]
> ユーザーが SharePoint または OneDrive に保存されているラベル付きドキュメントから暗号化を手動で削除し [、SharePoint](sensitivity-labels-sharepoint-onedrive-files.md)と OneDrive の Office ファイルに対する感度ラベルを有効にした場合、次回ドキュメントにアクセスまたはダウンロードすると、ラベルの暗号化が自動的に復元されます。 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>ファイル、電子メール、および添付ファイルに対して感度ラベルを適用する

ユーザーは、ドキュメントまたは電子メールごとに一度に 1 つのラベルを適用できます。

添付ファイルを含む電子メール メッセージにラベルを付け、電子メール メッセージに適用するラベルが暗号化を適用し、添付ファイルが Office ドキュメントでまだ暗号化されていない場合にのみ、添付ファイルはラベルを継承します。 継承されたラベルは暗号化を適用するために、添付ファイルは新しく暗号化されます。

電子メール メッセージに適用されたラベルが暗号化を適用しない場合、または添付ファイルが既に暗号化されている場合、添付ファイルは電子メール メッセージからラベルを継承しません。

ラベルの継承の例。「 **機密** 」というラベルが暗号化を適用し、「 **全般** 」というラベルは暗号化を適用しません。

- ユーザーが新しい電子メール メッセージを作成し、このメッセージに **[機密** ] ラベルを適用します。 その後、ラベル付けも暗号化もされていない Word 文書を追加します。 継承の結果、ドキュメントは新しく 「機密」というラベルが付けされ、そのラベルから暗号化が適用されます。

- ユーザーが新しい電子メール メッセージを作成し、このメッセージに **[機密** ] ラベルを適用します。 次に、[全般] というラベルの付いた **Word** 文書が追加され、このファイルは暗号化されません。 継承の結果、ドキュメントは 「機密」として再ラベル付けされ、そのラベルから暗号化が適用されます。

## <a name="sensitivity-label-compatibility"></a>ラベルの互換性

**RMS** 対応アプリの場合: RMS 対応のアプリケーションで、ラベル付き暗号化されたドキュメント [](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)または電子メールを開き、そのアプリケーションが区別ラベルをサポートしない場合でも、アプリは暗号化と権利管理を適用します。

**Azure Information Protection** クライアントを使用すると、Azure Information Protection クライアントを使用して、Office の組み込みのラベル付けクライアントを使用して、ドキュメントやメールに適用する、その他の方法で、ドキュメントやメールに適用する区別ラベルを表示および変更できます。

**他のバージョンの** Office : 承認されたユーザーは、ラベル付きドキュメントやメールを他のバージョンのドキュメントやメール で開Office。 ただし、ラベルの表示または変更は、サポートされているバージョンまたは Azure Information Protection Office使用する場合のみ可能です。 サポートされているOfficeバージョンについては、前のセクションで [説明します](#support-for-sensitivity-label-capabilities-in-apps)。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>SharePoint および OneDrive ファイルのサポートが、区別ラベルで保護されている

SharePoint または OneDrive のドキュメントに対して Office on the web で Office 組み込みのラベル付けクライアントを使用するには [、SharePoint](sensitivity-labels-sharepoint-onedrive-files.md)と OneDrive の Office ファイルの区別ラベルを有効にしてください。

## <a name="support-for-external-users-and-labeled-content"></a>外部ユーザーとラベル付きコンテンツのサポート

ドキュメントまたは電子メールにラベルを付けすると、ラベルはテナントとラベル GUID を含むメタデータとして保存されます。 ラベル付きドキュメントまたは電子メールが、Office アプリで開いて、そのユーザーが同じテナントに属している場合にのみ、このメタデータが読み取り専用になります。ラベルはアプリに表示されます。 たとえば、Word、PowerPoint、Excel の組み込みのラベル付けでは、ラベル名がステータス バーに表示されます。 

つまり、異なるラベル名を使用する別の組織とドキュメントを共有する場合、各組織はドキュメントに適用された独自のラベルを適用して表示できます。 ただし、適用されたラベルの次の要素は、組織外のユーザーに表示されます。

- コンテンツのマーキング。 ラベルがヘッダー、フッター、透かしを適用すると、これらはコンテンツに直接追加され、誰かが変更または削除するまで表示されたままになります。

- 暗号化を適用したラベルの基になる保護テンプレートの名前と説明。 この情報は、ドキュメントを開く権限を持つユーザーとそのドキュメントの使用権限に関する情報を提供するために、ドキュメントの上部にあるメッセージ バーに表示されます。

### <a name="sharing-encrypted-documents-with-external-users"></a>暗号化されたドキュメントを外部ユーザーと共有する

自分の組織内のユーザーへのアクセスを制限する以外に、Azure Active Directory のアカウントを持つ他のユーザーにアクセスを拡張できます。 ただし、組織で条件付きアクセス ポリシーを使用している場合[](#conditional-access-policies)は、次のセクションで追加の考慮事項を参照してください。

すべてのOfficeアプリケーションおよび他の [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 対応アプリケーションは、ユーザーが正常に認証された後、暗号化されたドキュメントを開く可能性があります。 

外部ユーザーが Azure Active Directory にアカウントを持たない場合は、テナントのゲスト アカウントを使用して認証できます。 これらのゲスト アカウントは、SharePoint と OneDrive の Office ファイルに対する感度ラベルを有効にした場合に [、SharePoint](sensitivity-labels-sharepoint-onedrive-files.md)または OneDrive の共有ドキュメントにアクセスするためにも使用できます。

- 1 つのオプションは、これらのゲスト アカウントを自分で作成する方法です。 これらのユーザーが既に使用している任意の電子メール アドレスを指定できます。 たとえば、Gmail アドレスなどです。
    
    このオプションの利点は、暗号化設定で電子メール アドレスを指定することで、特定のユーザーへのアクセスと権限を制限できるという方法です。 欠点は、アカウントの作成とラベル構成との連携に対する管理オーバーヘッドです。

- もう 1 つのオプションは、SharePoint と OneDrive を [Azure AD B2B (プレビュー)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) と統合して、ユーザーがリンクを共有するときにゲスト アカウントが自動的に作成される方法です。
    
    このオプションの利点は、アカウントが自動的に作成され、ラベルの構成が簡単になるため、管理オーバーヘッドが最小限に抑えられます。 このシナリオでは、電子メール アドレスを事前[](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users)に知らないため、暗号化オプション [認証されたユーザーを追加する] を選択する必要があります。 欠点は、この設定では、特定のユーザーに対するアクセス権と使用権を制限できない点です。

外部ユーザーは、Windows と Microsoft 365 Apps (以前の[Office 365](https://docs.microsoft.com/deployoffice/name-change)アプリ) または Office 2019 のスタンドアロン エディションを使用するときに、Microsoft アカウントを使用して暗号化されたドキュメントを開くすることもできます。 他のプラットフォームで最近サポートされた Microsoft アカウントは、macOS (Microsoft 365 Apps バージョン 16.42 以上)、Android (バージョン 16.0.13029+)、iOS (バージョン 2.42 以上) で暗号化されたドキュメントを開く機能もサポートされています。 たとえば、組織内のユーザーが暗号化されたドキュメントを組織外のユーザーと共有し、暗号化設定では外部ユーザーの Gmail メール アドレスを指定します。 この外部ユーザーは、Gmail のメール アドレスを使用する独自の Microsoft アカウントを作成できます。 次に、このアカウントでサインインした後、ドキュメントを開き、指定された使用制限に従ってドキュメントを編集できます。 このシナリオのチュートリアルの例については、「保護されたドキュメントを開いて [編集する」を参照してください](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)。

> [!NOTE]
> Microsoft アカウントのメール アドレスは、暗号化設定へのアクセスを制限するために指定されたメール アドレスと一致している必要があります。

Microsoft アカウントを持つユーザーが暗号化されたドキュメントをこの方法で開くと、同じ名前のゲスト アカウントが存在しない場合、テナントのゲスト アカウントが自動的に作成されます。 ゲスト アカウントが存在する場合は、サポートされているデスクトップアプリとモバイル Office アプリから暗号化されたドキュメントを開くだけでなく、web 上の Office を使用して SharePoint と OneDrive でドキュメントを開く際に使用できます。

ただし、レプリケーションの待機時間が理由で、このシナリオでは自動ゲスト アカウントが直ちに作成されるわけではありません。 ラベルの暗号化設定の一部として個人の電子メール アドレスを指定する場合は、Azure Active Directory で対応するゲスト アカウントを作成することをお勧めします。 次に、これらのユーザーに、組織から暗号化されたドキュメントを開くのにこのアカウントを使用する必要があるという情報を知らせたとします。

> [!TIP]
> 外部ユーザーがサポートされている Office クライアント アプリを使用すると確信できないので、(特定のユーザーの) ゲスト アカウントを作成した後、または SharePoint と OneDrive を [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (認証済みユーザー用) と統合した後で SharePoint と OneDrive からのリンクを共有する方が、外部ユーザーとの安全な共同作業をサポートするための信頼性の高い方法です。

### <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

組織で Azure [Active Directory 条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシーを実装している場合は、それらのポリシーの構成を確認します。 ポリシーに Azure Information Protection が含まれる場合、そのポリシーが外部ユーザーにまで拡張されている場合、外部ユーザーが自分のテナントに Azure AD アカウントを持っている場合でも、それらの外部ユーザーはテナントにゲスト アカウントを持っている必要があります。

このゲスト アカウントがない場合、暗号化されたドキュメントを開いてエラー メッセージを表示することはできません。 メッセージ テキストは、自分のアカウントをテナントの外部ユーザーとして追加する必要があるという通知を表示し、このシナリオでサインアウトして、別の **Azure Active Directory** ユーザー アカウントでもう一度サインインする不適切な指示を示す場合があります。

ラベルで暗号化されたドキュメントを開く必要がある外部ユーザーのテナントでゲスト アカウントを作成して構成できない場合は、条件付きアクセス ポリシーから Azure Information Protection を削除するか、ポリシーから外部ユーザーを除外する必要があります。

条件付きアクセスと Azure Information Protection (区別ラベルで使用される暗号化サービス) の詳細については、よく寄せられる質問を参照してください。条件付きアクセスで利用可能なクラウド アプリとして[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)が一覧表示されているのは、どのように機能しますか?

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>アプリOffice、コンテンツのマーキングと暗号化を適用する場合

Officeでは、使用するアプリに応じて、コンテンツのマーキングと機度ラベルによる暗号化の適用方法が異なります。

| アプリ | コンテンツのマーケティング | 暗号化 |
| --- | --- | --- |
| すべてのプラットフォームの Word、Excel、PowerPoint | 直ちに | 直ちに |
| Outlook for PC と Outlook for Mac | Exchange Online が電子メールを送信した後 | 直ちに |
| Outlook on the web、iOS、および Android | Exchange Online が電子メールを送信した後 | Exchange Online が電子メールを送信した後 |
|

アプリの外部にあるファイルにOffice適用するソリューションでは、ファイルにラベル付けメタデータを適用します。 このシナリオでは、ラベルの構成からのコンテンツ マーキングはファイルに挿入されませんが、暗号化が適用されます。 

これらのファイルを Office デスクトップ アプリで開いた場合、コンテンツマーキングは Azure Information Protection 統合ラベル付けクライアントによって自動的に適用されます。 デスクトップ、モバイル、または Web アプリに組み込みのラベル付けを使用する場合、コンテンツ マーキングは自動的には適用されません。

アプリの外部に感度ラベルを適用するシナリオにはOfficeがあります。

- Azure Information Protection 統合ラベル付けクライアントからのスキャナー、エクスプローラー、PowerShell 

- SharePoint と OneDrive の自動ラベル付けポリシー

- Power BI からラベル付きおよび暗号化されたデータをエクスポートする

- Microsoft Cloud App Security

このようなシナリオでは、Office アプリを使用して、ラベル付けの組み込みのユーザーは、現在のラベルを一時的に削除または置き換え、元のラベルを再適用することで、ラベルのコンテンツ マーキングを適用できます。

### <a name="dynamic-markings-with-variables"></a>変数を使用した動的なマーキング

> [!IMPORTANT]
> 現時点では、すべてのプラットフォーム上のすべてのアプリが、ヘッダー、フッター、透かしに指定できる動的コンテンツ マーキングをサポートしているのではありません。 この機能をサポートしないアプリでは、ラベル構成で指定された元のテキストとして、変数を解決するのではなく、マーキングを適用します。
> 
> Azure Information Protection 統合ラベル付けクライアントは、動的マーキングをサポートします。 組み込みのラベル付けOffice、このページの「 [機能](#support-for-sensitivity-label-capabilities-in-apps) 」セクションの表を参照してください。

コンテンツ マーキングの機度ラベルを構成する場合は、ヘッダー、フッター、透かしのテキスト文字列で次の変数を使用できます。

| 変数 | 説明 | ラベルが適用された場合の例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 適用されたラベルのラベル表示名| **全般**|
| `${Item.Name}` | ラベルが付けられているコンテンツのファイル名または電子メールの件名 | **Sales.docx** |
| `${Item.Location}` | ラベルが付けられているドキュメントのパスとファイル名、またはラベルが付けられているメールの電子メールの件名 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | ラベルを適用するユーザーの表示名| **Richard Richarde** |
| `${User.PrincipalName}` | Azure ADラベルを適用するユーザーのユーザー プリンシパル名 (UPN) | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | ラベルを適用するユーザーのローカル タイム ゾーンで、コンテンツにラベルが付いた日時 | **8/10/2020 13:30** |

> [!NOTE]
> これらの変数の構文では、大文字と小文字が区別されます。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Word、Excel、PowerPoint、Outlook で異なる視覚的なマーキングを設定する

追加の変数として、テキスト文字列の "If.App" 変数ステートメントを使用して Office アプリケーションの種類ごとに視覚的なマーキングを構成し、Word、Excel、PowerPoint、または Outlookの値を使用してアプリケーションの種類を識別できます。  これらの値を省略することもできます。これは、同じ If.App ステートメントで複数の値を指定する場合に必要です。

> [!NOTE]
> 完成度を高めるには、Outlook の手順が含まれていますが、現在は Azure Information Protection 統合ラベル付けクライアントでのみサポートされています。

次の構文を使用してください。

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

他の動的な視覚的なマーキングと同様に、構文では大文字と小文字が区別されます。

例:

- **Word 文書のヘッダー テキストのみを設定します。**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Word 文書のヘッダーでのみ、ラベルは "This Word document is sensitive" というヘッダー テキストを適用します。 他のアプリケーションにヘッダー テキストOfficeされません。

- **Word、Excel、Outlook のフッター テキストと PowerPoint 用の異なるフッター テキストを設定します。**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    Word、Excel、および Outlook では、ラベルはフッター テキスト "This content is confidential" を適用します。 PowerPoint では、ラベルはフッター テキスト "This presentation is confidential" を適用します。

- **Word と PowerPoint の特定の透かしテキストを設定し、Word、Excel、PowerPoint の透かしテキストを設定します。**

    `${If.App.WP}This content is ${If.End}Confidential`

    Word および PowerPoint では、ラベルは透かしテキスト "This content is Confidential" を適用します。 Excel では、ラベルは透かしテキスト "Confidential" を適用します。 Outlook では、視覚的なマーキングとしての透かしは Outlook でサポートされていないので、ラベルには透かしテキストは適用されません。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>ユーザーに電子メールとドキュメントへのラベルの適用を要求する

> [!IMPORTANT]
> 必須のラベル付けとも呼ばれるすべてのプラットフォーム上のすべてのアプリで、現在、ユーザーが自分の電子メールとドキュメントにラベルを適用する必要があるというポリシー設定 **をサポートしているのではありません**。
> 
> [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)統合ラベル付けクライアントは、必須のラベル付けと、Office アプリに組み込まれるラベル付けを[](#support-for-sensitivity-label-capabilities-in-apps)サポートしています。このページの機能に関するセクションの表をご覧ください。

このポリシー設定が選択されている場合、ポリシーが割り当てられているユーザーは、次のシナリオで、感度ラベルを選択して適用する必要があります。

- Azure Information Protection 統合ラベル付けクライアントの場合:
    - 文書 (Word、Excel、PowerPoint): ラベルのない文書を保存するか、ユーザーが文書を閉じるとき。
    - メール (Outlook): ユーザーがラベルのないメッセージを送信した時点。

- アプリに組み込Officeの場合:
    - ドキュメント ((Word、Excel、PowerPoint) の場合: ラベルのないドキュメントを開く、または保存する場合。
    - メール (Outlook): ユーザーがラベルのない電子メール メッセージを送信した時点。

組み込みのラベル付けの追加情報:

- ラベルのないドキュメントを開く際に、ユーザーに対してラベルの追加を求めるメッセージが表示された場合は、ラベルを追加するか、ドキュメントを読み取り専用モードで開くことを選択できます。

- 必須のラベル付けが有効な場合、ユーザーはドキュメントから区別ラベルを削除できませんが、既存のラベルを変更できます。

この設定を使用する場合のガイダンスについては、ポリシー設定に関する情報を [参照してください](sensitivity-labels.md#what-label-policies-can-do)。

## <a name="end-user-documentation"></a>エンド ユーザーのドキュメント

- [Office 内の文書やメールに機密ラベルを適用する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office ファイルに機密ラベルを適用した場合の既知の問題](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
