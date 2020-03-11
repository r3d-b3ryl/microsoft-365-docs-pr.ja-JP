---
title: Office アプリで秘密度ラベルを使用する
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
description: ユーザーがデスクトップ用の Office アプリ、モバイル用 Office アプリ、web 用 Office アプリの機密ラベルを操作する方法について説明します。 機密ラベルをサポートしているアプリを確認します。
ms.openlocfilehash: 41d4231b163d85b55ed0cd68ffb551f67d30827a
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583154"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Office アプリで秘密度ラベルを使用する

Microsoft 365 コンプライアンスセンターまたは同等のラベル付けセンターから機密ラベルが[公開](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)されている場合は、作成または編集時にデータを分類して保護するために、ユーザーが Office アプリに表示され始めます。

この記事の情報を使用して、Office アプリの機密ラベルを正常に管理するのに役立ちます。 たとえば、組み込みのラベルをサポートするために必要な最小限のバージョンのアプリを特定し、Azure Information Protection のユニファイドラベルクライアントと他のアプリやサービスとの互換性について理解します。

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>秘密度ラベルのサブスクリプションとライセンスの要件

ユーザーには、少なくとも次のライセンスのいずれかが割り当てられている必要があります。

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)またはそれ以上

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software)またはそれ以上

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/)以上

Office 組み込みのラベル付けクライアントは、Office のサブスクリプションエディションの機密ラベルをサポートしています。 このラベル付けクライアントは、office 2016 または Office 2019 などのスタンドアロンエディションの Office をサポートしていません。 これらのエディションの Windows コンピューターで機密ラベルを使用するには、Azure Information Protection のユニファイドラベルクライアントをインストールします。

自動または推奨される秘密度のラベル付けを使用するには、ユーザーが次のいずれかのライセンスを持っている必要があります。

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)以降

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software)以上

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>アプリでの機密ラベル機能のサポート

各機能について、次の表に、組み込みのラベル付けを使用して機密ラベルをサポートするために、そのアプリに必要な最小バージョンを示します。 または、ラベル機能がパブリックプレビューであるか、今後のリリースのレビューの下にある場合。

新しいバージョンのアプリは、異なる更新プログラムチャネルに対してさまざまなタイミングで利用可能になります。 必要な新しいラベル機能をテストできるように更新プログラムチャネルを構成する方法などの詳細については、「 [365 Office の更新プログラムチャネルの概要 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)」を参照してください。 プライベートプレビューの新機能は表に含まれていませんが、 [Microsoft Information Protection のプライベートプレビュープログラム](https://aka.ms/mip-preview)を使用するように組織を nominating すれば、これらのプレビューに参加できます。

Windows コンピューター上でのみ実行される Azure Information Protection のユニファイドラベルクライアントをインストールすると、追加機能を利用できるようになります。 詳細については、「 [Windows コンピューターのラベルクライアントを比較する](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)」を参照してください。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel、PowerPoint の機密ラベル機能

|機能                                                                                                        |Windows デスクトップ |Mac デスクトップ |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | レビュー                                                        |
|[ラベルを変更する場合は、根拠を設定する必要があります。](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[カスタムヘルプページへのヘルプリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[コンテンツをマークする](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | プレビュー:[月次チャネル (対象指定)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#monthly-channel-for-office-365-proplus)            | プレビュー: [Office Insider](https://office.com/insider)        | レビュー   | レビュー         | レビュー                                                        |
|[ラベル分析を使用](label-analytics.md)してラベルの使用を表示し、管理者向けにデータを送信する                      | レビュー            | レビュー        | レビュー   | レビュー         | レビュー                                                        |
|[ユーザーが電子メールとドキュメントにラベルを適用することを必須にする](sensitivity-labels.md#what-label-policies-can-do)   | レビュー            | レビュー        | レビュー   | レビュー         | レビュー                                                        |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | プレビュー: [Office Insider](https://office.com/insider)                                  | レビュー | レビュー | レビュー | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|ラベル付きおよび保護されたドキュメントでの[自動保存](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)と[共同編集](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4)をサポートする | レビュー | レビュー | レビュー | レビュー | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook の機密ラベル機能

|機能                                                                                                        |Windows デスクトップ上の Outlook |Outlook on Mac デスクトップ  |Outlook on iOS |Outlook on Android |Outlook on the web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[ラベルを変更する場合は、根拠を設定する必要があります。](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[カスタムヘルプページへのヘルプリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[コンテンツをマークする](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 必要               |
|[ラベル分析を使用](label-analytics.md)してラベルの使用を表示し、管理者向けにデータを送信する                      | レビュー                       | レビュー                    | レビュー           | レビュー               | レビュー               |
|[ユーザーが電子メールとドキュメントにラベルを適用することを必須にする](sensitivity-labels.md#what-label-policies-can-do)   | レビュー                       | レビュー                    | レビュー           | レビュー               | レビュー               |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | プレビュー: [Office Insider](https://office.com/insider)へのロールアウト                       | レビュー                    | レビュー           | レビュー               | 必要 |
|

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 組み込みのラベルクライアントと Azure Information Protection クライアント

Office 組み込みのラベルクライアントは、次の管理センターから、機密ラベルと機密ラベルポリシー設定をダウンロードします。

- Microsoft 365 コンプライアンス センター
- Microsoft 365 セキュリティ センター
- Office 365 セキュリティ/コンプライアンス センター

Office の組み込みラベルクライアントを使用するには、リストされた管理センターの1つからユーザーに対して発行された1つ以上の[ラベルポリシー](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)が必要です。

ただし、ユーザーが ([ユニファイドラベルクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)または[クラシッククライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)) インストールされている Azure Information Protection クライアントの1つである場合、既定では、組み込みのラベルクライアントは Office アプリで無効になっています。 Office アプリ用の Azure Information Protection クライアントではなく、組み込みのラベルを使用するには、Azure Information Protection 用の Office アドインを無効にするかアンインストールします。

1. 次のオプションのいずれかを実行します。
    
    - **複数のコンピューターの場合:**[ **Office の秘密度機能を使用して、機密ラベルを適用して表示する**] グループポリシー設定を構成します。 [**ユーザーの構成]/[管理用テンプレート]/[Microsoft Office 2016/セキュリティ設定**] の下にあるこの設定を見つけます。 この設定は、グループポリシーまたは[Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)を使用して展開します。
    
    - **1 台のコンピューターの場合:** 1台のコンピューターで Azure Information Protection アドインを[完全に無効](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)にしたり、削除したりする方法については、「Office プログラムでアドインを表示、管理、およびインストールする」を参照してください。

2. すべての Office アプリケーションを再起動します。

この Office アドインを無効にするかアンインストールすると、Office アプリの外部でファイルに引き続きラベルを付けることができるように、Azure Information Protection クライアントがインストールされたままになります。 たとえば、ファイルエクスプローラーや PowerShell を使用します。

Azure Information Protection クライアントおよび Office 組み込みのラベルクライアントによってサポートされる機能については、「Azure Information Protection のドキュメントで[Windows コンピューターに使用するラベル付けクライアントを選択する](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)」を参照してください。

## <a name="protection-templates-and-sensitivity-labels"></a>保護テンプレートと機密ラベル

Office 365 メッセージの暗号化に対して定義するような管理者定義の[保護テンプレート](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)は、組み込みのラベル付けを使用している場合、office アプリでは表示されません。 この単純化された操作性は、暗号化が有効になっている機密ラベルに同じ設定が含まれるため、保護テンプレートを選択する必要がないことを反映しています。

既存の保護テンプレートをラベルに変換する必要がある場合は、Azure ポータルと、次の手順を使用します。[テンプレートをラベルに変換するに](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)は、次の手順を実行します。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Information Rights Management (IRM) のオプションと機密ラベル

暗号化を適用するように構成した機密ラベルユーザーが独自の暗号化設定を指定するために、複雑さを排除します。 多くの Office アプリでは、Information Rights Management (IRM) のオプションを使用して、ユーザーがこれらの個々の暗号化設定を手動で構成することができます。 たとえば、Windows アプリの場合は次のようになります。

- ドキュメントの場合:**ファイル** > **情報** > **保護ドキュメント** > に**よるアクセスの制限**
- 電子メールの場合: [**オプション**] タブから [**暗号化**] を > 
  
ユーザーが最初にドキュメントまたは電子メールにラベルを付けると、独自の暗号化設定を使用して、ラベルの構成設定をいつでも変更できます。 以下に例を示します。

- ユーザーが**機密 \ All Employees**ラベルをドキュメントに適用します。このラベルは、組織内のすべてのユーザーの暗号化設定を適用するように構成されています。 このユーザーは、組織外のユーザーへのアクセスを制限するように IRM 設定を手動で構成します。 最終的には、"**社外秘**" というラベルが付けられた文書が作成されますが、組織内のユーザーは意図したとおりに開くことができません。

- ユーザーが [**社外秘**] のラベルを電子メールに適用し、この電子メールは、[**転送不可**] の暗号化設定を適用するように設定されています。 このユーザーは、電子メールが無制限になるように IRM 設定を手動で構成します。 最終的には、電子メールが送信者によって転送されることがありますが、**機密 \ 受信者のみ**のラベルがある場合があります。

- ユーザーがドキュメントに **[全般**] ラベルを適用します。このラベルは、暗号化を適用するように構成されていません。 このユーザーは、ドキュメントへのアクセスを制限するように IRM 設定を手動で構成します。 最終的には、 **[General** ] というラベルの付いたドキュメントが生成されますが、暗号化も適用されるため、一部のユーザーは意図したとおりに開くことができません。

ドキュメントまたは電子メールに既にラベルが付けられている場合、ユーザーはこれらの操作を実行できます。コンテンツが暗号化されていない場合、または[利用状況](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)のエクスポートまたはフルコントロールがある場合です。 

有用なレポートで一貫したラベルを使用するには、ユーザーが排他的にラベルを適用するための適切なラベルとガイダンスを提供します。 以下に例を示します。

- ユーザーが自分のアクセス許可を割り当てる必要がある例外の場合は、[ユーザーが自分のアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)ためのラベルを提供します。 

- 暗号化を適用するラベルを選択した後、ユーザーが手動で暗号化を削除するのではなく、ユーザーが同じ分類のラベルを必要とするが暗号化を必要としない場合は、sublabel の代替手段を提供します。 次に例を示します。
    - **社外秘すべての従業員**
    - **機密情報 (すべての暗号化なし)**

> [!NOTE]
> ユーザーが SharePoint または OneDrive に格納されているラベル付きドキュメントから手動で暗号化を削除し、 [sharepoint と onedrive で Office ファイルの機密ラベルを有効に](sensitivity-labels-sharepoint-onedrive-files.md)している場合は、次回ドキュメントにアクセスまたはダウンロードしたときに、ラベルの暗号化が自動的に復元されます。 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>ファイル、電子メール、および添付ファイルに機密ラベルを適用する

ユーザーは、ドキュメントまたは電子メールごとに、一度に1つのラベルだけを適用できます。

添付ファイルが含まれている電子メールメッセージにラベルを付けると、添付ファイルはラベルを継承しません。1つの例外があります。

- 添付ファイルは、暗号化を適用しないラベル付きの Office ドキュメントで、電子メールメッセージに適用するラベルは暗号化を適用します。 この場合、メールで送信された Office ドキュメントは、その電子メールのラベルを暗号化設定で継承します。

無視しない場合は: 

- 添付ファイルにラベルがある場合は、元のラベルが適用されたままになります。
- 添付ファイルがラベルなしで暗号化されている場合、暗号化は保持されますが、ラベルは付けられません。
- 添付ファイルにラベルが付いていない場合は、ラベルが付いていないままになります。

## <a name="sensitivity-label-compatibility"></a>機密ラベルの互換性

**Rms-なりアプリ**の場合: 機密ラベルをサポートしていない[rms なりアプリケーション](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)で、ラベル付きの暗号化されたドキュメントまたは電子メールを開くと、そのアプリは暗号化と権限の管理を引き続き適用します。

**Azure Information protection クライアントを使用**すると、ドキュメントやメールに適用する機密ラベルを、Azure information protection クライアントを使用して Office 組み込みのラベルクライアントを使用して表示および変更できます。また、その他の方法もあります。

**他のバージョンの office**の場合: 承認されたユーザーは、他のバージョンの office でラベル付きドキュメントとメールを開くことができます。 ただし、サポートされている Office バージョンまたは Azure Information Protection クライアントを使用してのみ、ラベルを表示または変更できます。 サポートされている Office アプリのバージョンは、[前のセクション](#support-for-sensitivity-label-capabilities-in-apps)に一覧表示されています。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>機密ラベルで保護された SharePoint および OneDrive ファイルのサポート

OneDrive for business または SharePoint Online のドキュメントに対して web 上の office に office の組み込みラベルクライアントを使用するには、[プレビュー] をオンにして、 [sharepoint および onedrive で office ファイルの機密ラベルを有効](sensitivity-labels-sharepoint-onedrive-files.md)にしていることを確認してください。

## <a name="when-office-365-applies-content-marking-and-encryption"></a>Office 365 がコンテンツマーキングと暗号化を適用する場合

Office 365 では、使用しているアプリによって、機密ラベル付きのコンテンツマーキングと暗号化が異なる方法で適用されます。

| アプリ | コンテンツのマーケティング | 暗号化 |
| --- | --- | --- |
| すべてのプラットフォームの Word、Excel、PowerPoint | 直ちに | 直ちに |
| Outlook for PC と Outlook for Mac | Exchange Online が電子メールを送信した後 | 直ちに |
| Outlook on the web、iOS、および Android | Exchange Online が電子メールを送信した後 | Exchange Online が電子メールを送信した後 |
|

## <a name="end-user-documentation"></a>エンドユーザードキュメント

- [Office 内の文書やメールに機密ラベルを適用する](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office ファイルに機密ラベルを適用した場合の既知の問題](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
