---
title: Office アプリの機密ラベル
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 12/09/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: ユーザーがデスクトップ用の Office アプリ、モバイル用 Office アプリ、web 用 Office アプリの機密ラベルを操作する方法について説明します。 機密ラベルをサポートしているアプリを確認します。
ms.openlocfilehash: a904f1adde6ea8df6d7225ed368f77790b21161a
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802850"
---
# <a name="sensitivity-labels-in-office-apps"></a>Office アプリの機密ラベル

この記事の内容

- メール、ファイル、および添付ファイルに機密ラベルを適用する前の環境の要件。
- 各 Office アプリでサポートされている機密ラベル機能。
- Office アプリで動作する他の Microsoft セキュリティおよびコンプライアンステクノロジとの機密ラベルを結合すると、どうなりますか。
- 組織内のユーザーが、Windows 用の Office アプリと web 用の Office アプリを使用する際に、機密ラベルをどのように使用できるようにします。
- 組織内のユーザーに機密ラベルを使用して開始する場所。

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>秘密度ラベルのサブスクリプションとライセンスの要件

ユーザーには、少なくとも次のライセンスのいずれかが割り当てられている必要があります。

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)またはそれ以上

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software)またはそれ以上

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/)以上

Office 組み込みのラベル付けクライアントは、Office のサブスクリプション版で機密ラベルをサポートします。 クライアントは、Office 2016 または Office 2019 などのスタンドアロンバージョンをサポートしていません。

自動または推奨される秘密度のラベル付けを使用するには、ユーザーが次のいずれかのライセンスを持っている必要があります。

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)以降

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software)以上

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)以降

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel、PowerPoint での機密ラベル機能のサポート

各機能について、次の表に、そのアプリに必要な最小バージョンを示します。 これは、そのプラットフォームではその機能を使用できないことを意味します。

|機能                                                                                                        |Windows デスクトップ |Mac デスクトップ |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | TBD                                                        |
|[ラベルを変更する場合は、根拠を設定する必要があります。](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[カスタムヘルプページへのヘルプリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[コンテンツをマークする](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|[ラベル分析を使用](label-analytics.md)してラベルの使用を表示し、管理者向けにデータを送信する                      | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|
  [ユーザーがメールとドキュメントにラベルを適用することを必須にする](sensitivity-labels.md#what-label-policies-can-do)   | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | プレビュー: [Office Insider](https://office.com/insider)へのロールアウト                                  | TBD | TBD | TBD | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|ラベル付きおよび保護されたドキュメントでの[自動保存](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)と[共同編集](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4)をサポートする | TBD | TBD | TBD | TBD | [プレビュー](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Outlook での機密ラベル機能のサポート

各機能について、次の表に、そのアプリに必要な最小バージョンを示します。 これは、そのプラットフォームではその機能を使用できないことを意味します。

|機能                                                                                                        |Windows デスクトップ上の Outlook |Outlook on Mac デスクトップ  |Outlook on iOS |Outlook on Android |Outlook on the web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[ラベルを変更する場合は、根拠を設定する必要があります。](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[カスタムヘルプページへのヘルプリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[コンテンツをマークする](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910以上                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | はい               |
|[ラベル分析を使用](label-analytics.md)してラベルの使用を表示し、管理者向けにデータを送信する                      | TBD                       | TBD                    | TBD           | TBD               | TBD               |
|
  [ユーザーがメールとドキュメントにラベルを適用することを必須にする](sensitivity-labels.md#what-label-policies-can-do)   | TBD                       | TBD                    | TBD           | TBD               | TBD               |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | TBD                       | TBD                    | TBD           | TBD               | プレビュー:[対象指定リリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)へのロールアウト |
|

## <a name="about-the-office-built-in-labeling-client"></a>Office の組み込みラベルクライアントについて

Office 組み込みのラベルクライアントは、次の管理センターからラベルとポリシー設定をダウンロードします。

- Office 365 セキュリティ/コンプライアンス センター

- Microsoft 365 セキュリティ センター

- Microsoft 365 コンプライアンス センター

Office の組み込みラベルクライアントを使用するには、リストされた管理センターの1つからユーザーに対して発行された1つ以上の[ラベルポリシー](sensitivity-labels.md#what-label-policies-can-do)が必要です。

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

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>ファイル、電子メール、および添付ファイルに機密ラベルを適用する

ユーザーは、ドキュメントまたは電子メールごとに、一度に1つのラベルだけを適用できます。

添付ファイルを含む電子メールメッセージにラベルを付けると、添付ファイルはラベルを継承しません。 添付ファイルにラベルが付けられている場合は、ラベルを個別に適用したままにします。 添付ファイルにラベルが付いていない場合、添付ファイルはラベルなしで保持されます。 ただし、メールのラベルが保護されている場合、その保護は Office の添付ファイルに適用されます。

## <a name="sensitivity-label-compatibility"></a>機密ラベルの互換性

**なりアプリを使用**します。 機密ラベルをサポートしていない[なりアプリケーション](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)で、ラベル付きの_暗号化さ_れたドキュメントまたは電子メールを開くと、アプリは依然として暗号化と権限の管理を適用します。

**Azure Information Protection クライアントを使用**します。 Azure Information Protection クライアントを使用して Office 組み込みのラベル付けクライアントを使用して、ドキュメントや電子メールに適用する機密ラベルを表示および変更することができます。

**他のバージョンの Office で使用**します。 承認されたユーザーは、他のバージョンの Office でラベル付きドキュメントとメールを開くことができます。 ただし、サポートされている Office バージョンまたは Azure Information Protection クライアントでのみ、ラベルを表示または変更できます。 サポートされている Office アプリのバージョンは、この記事の表に記載されています。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>機密ラベルで保護された SharePoint および OneDrive ファイルのサポート

Web 上の office に Office の組み込みラベルクライアントを使用するには、ドキュメントを OneDrive for Business または SharePoint Online のインスタンスに配置し、 [sharepoint および OneDrive で office ファイルの機密ラベルを有効](sensitivity-labels-sharepoint-onedrive-files.md)にする必要があります。

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Office 365 がコンテンツにマークと暗号化を適用する場合

Office 365 は、使用するアプリケーションによって、機密ラベル付きのコンテンツマークまたは暗号化を適用します。

| アプリケーション | コンテンツのマーケティング | 暗号化 |
| --- | --- | --- |
| すべてのプラットフォームの Word、Excel、PowerPoint | 直ちに | 直ちに |
| Outlook for PC と Outlook for Mac | Exchange Online が電子メールを送信した後 | 直ちに |
| Outlook on the web、iOS、および Android | Exchange Online が電子メールを送信した後 | Exchange Online が電子メールを送信した後 |
|

## <a name="more-resources"></a>その他のリソース

[Azure Information Protection での分類とラベル付けについてよく寄せられる質問](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Office 内のドキュメントとメールに機密ラベルを適用する](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
