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
ms.localizationpriority: high
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: デスクトップ、モバイル、および Web 用の Office アプリで秘密度ラベルを管理するための IT 管理者向けの情報。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 18153facee37f52ea0bcc5baa5e5193f63e06360
ms.sourcegitcommit: 9a4b0bc6a3ba076ecc392260efe7d2e1b655cde8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67419953"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Office アプリで秘密度ラベルを管理する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

Microsoft Purview コンプライアンス ポータルから秘密度ラベルを[公開](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)すると、Office アプリに表示され始め、ユーザーはデータの作成または編集時にデータを分類および保護できます。

この記事の情報を使用して、Office アプリの秘密度ラベルを正常に管理するのに役立ててください。たとえば、組み込みのラベル付けに固有の機能をサポートするために必要なアプリの最小バージョン、これらの機能の追加の構成情報を特定し、Azure Information Protection 統合ラベル付けクライアントやその他のアプリやサービスとの相互作用を理解します。

## <a name="labeling-client-for-desktop-apps"></a>デスクトップ アプリのラベル付けクライアント

Windows および Mac 用の Office デスクトップ アプリに組み込まれている秘密度ラベルを使用するには、Office のサブスクリプション エディションを使用する必要があります。 このラベル付けクライアントは、スタンドアロン エディションの Office ("永続ライセンス版 Office"とも呼ばれます) をサポートしていません。

Windows コンピューター専用の Office のサブスクリプション バージョンの Microsoft 365 Apps for enterprise にアップグレードできない場合は、[Azure Information Protection (AIP) 統合ラベル付けクライアント](/azure/information-protection/rms-client/aip-clientv2)を使用できます。 ただし、このクライアントは[メンテナンス モード](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-aip-unified-labeling-client-maintenance-mode-and/ba-p/3043613)になるため、必要な場合を除き、Office アプリに AIP アドインを使用することはお勧めしません。 詳細については、「[Office アプリの AIP アドインに対して MIP 組み込みラベル付けを選択する理由](sensitivity-labels-aip.md)」を参照してください。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>アプリでの秘密度ラベル機能のサポート

次の表に、Office アプリに組み込まれている秘密度ラベルの特定の機能を導入した Office の最小バージョンを示します。 または、ラベル機能が公開プレビュー中または将来のリリースのためにレビュー中の場合。 将来のリリースで計画されている新機能に関する詳細に[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label)を使用します。

Office アプリの新しいバージョンは、さまざまな更新チャネルでさまざまな時間に利用できるようになります。 Windows の場合、半期エンタープライズ チャネルよりも最新チャネルや月次エンタープライズ チャネルである場合に早期に取得できます。 最小バージョン番号も、ある更新チャネルと次の更新のものとで異なる場合があります。 詳細については、「[Microsoft 365 Apps 用更新プログラム チャネルの概要](/deployoffice/overview-update-channels)」および「[Microsoft 365 Apps の更新履歴](/officeupdates/update-history-microsoft365-apps-by-date)」を参照してください。

プライベート プレビューにある新機能は表に含まれていませんが、組織を [Microsoft Information Protection プライベート プレビュー プログラム](https://aka.ms/mip-preview)に指定することで、これらのプレビューに参加できる場合があります。

Office for iOS および Office for Android: 秘密度ラベルは [Office アプリ](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)に組み込まれています。

> [!TIP]
> テーブル内の最小バージョンと、使用しているバージョンとを比較するときは、先行するゼロを省略するリリース バージョンの一般的な方法を覚えておいてください。
> 
> たとえば、お使いのバージョン 4.2128.0 であり、4.7.1 以降が最小バージョンであることを確認します。 比較しやすいように言うと、4.7.1 (先頭のゼロなし) は (4 **7000**.1 ではなく) 4 **0007**.1 と読んでください。 4.2128.0 のバージョンが 4.0007.1 より大きいため、お使いのバージョンがサポートされています。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel、および PowerPoint での秘密度ラベル機能

記載されている番号は、各機能に必要な Office アプリケーションの最小バージョンです。 

> [!NOTE]
> Windows と半期エンタープライズ チャネルの場合、最小サポート バージョン番号がまだリリースされていない可能性があります。[詳細情報](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)
 
|機能 |Windows |Mac |iOS |Android |Web |
|-----------|-------:|----|----|--------|----|
|[ラベルを手動で適用、変更、または削除する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[多言語サポート](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)| 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | レビュー中 |
|新しいドキュメントに[既定の ラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|既存のドキュメントに[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do) | プレビュー: [現在のチャネル (プレビュー)](https://office.com/insider) にロールアウト) | プレビュー: [現在のチャネル (プレビュー)](https://office.com/insider) にロールアウト | レビュー中 | レビュー中 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[ラベル変更の正当な理由を要求する](sensitivity-labels.md#what-label-policies-can-do)                     | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上  <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[カスタム ヘルプ ページへのリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[コンテンツをマークする](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[変数を使用した動的マーキング](#dynamic-markings-with-variables)                                              | 現在のチャネル: 2010 以上 <br /><br> 月次エンタープライズ チャネル: 2010 以上 <br /><br> 半期エンタープライズ チャネル: 2102 以上 | 16.42 以上     | 2.42 以上 | 16.0.13328 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上     | 2.21 以上 | 16.0.11231 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[ユーザーにアクセス許可の割り当てを許可する: <br /> - ユーザーにカスタム アクセス許可の入力を求める (ユーザーとグループ)](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |現在のチャネル: 2004 以上 <br /><br> 月次エンタープライズ チャネル: 2004 以上 <br /><br> 半期エンタープライズ チャネル: 2008 以上 | 16.35 以上   | レビュー中   | レビュー中         | レビュー中                                                        |
|[ユーザーにアクセス許可の割り当てを許可する: <br /> - ユーザーにカスタム アクセス許可 (ユーザー、グループ、および組織) を求める](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |プレビュー: [ベータ チャネル](https://office.com/insider)へのロールアウト  | レビュー中   | レビュー中   | レビュー中         | レビュー中                                                        |
|[ラベル関連のユーザー アクティビティを監査する](#auditing-labeling-activities)                      | 現在のチャネル: 2011 以上 <br /><br> 月次エンタープライズ チャネル: 2011 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.43 以上 | 2.46 以上 | 16.0.13628 以上 | はい |
|[ユーザーがメールとドキュメントにラベルを適用することを必須にする](#require-users-to-apply-a-label-to-their-email-and-documents)   | 現在のチャネル: 2101 以上 <br /><br> 月次エンタープライズ チャネル: 2101 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.45 以上         | 2.47 以上 | 16.0.13628 以上 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[秘密度ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md) <br /> - 機密情報の種類の使用                    | 現在のチャネル: 2009 以上 <br /><br> 月次エンタープライズ チャネル: 2009 以上 <br /><br> 半期エンタープライズ チャネル: 2102 以上 | 16.44 以上  | レビュー中 | レビュー中 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[秘密度ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md) <br /> - トレーニング可能な分類子の使用                    | 現在のチャネル: 2105 以上 <br /><br> 月次エンタープライズ チャネル: 2105 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.49+ | レビュー中 | レビュー中 | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|ラベル付きおよび暗号化されたドキュメントの[共同編集と自動保存をサポート](sensitivity-labels-coauthoring.md) | 現在のチャネル: 2107 以上 <br /><br> 月次エンタープライズ チャネル: 2107 以上 <br /><br> 半期エンタープライズ チャネル: 2202 以上 |  16.51 以上 | 2.58+ | 16.0.14931+  | [はい - オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[PDF サポート](#pdf-support)| プレビュー: [最新チャネル (プレビュー版)](https://office.com/insider) |  レビュー中 | レビュー中 | レビュー中 | レビュー中 |

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook での秘密度ラベル機能

記載されている番号は、各機能に必要な Office アプリケーションの最小バージョンです。 

> [!NOTE]
> Windows と半期エンタープライズ チャネルの場合、最小サポート バージョン番号がまだリリースされていない可能性があります。[詳細情報](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)

|機能 |Outlook for Windows |Outlook for Mac |Outlook on iOS |Outlook on Android |Outlook on the web |
|-----------|-------------------:|----------------|---------------|-------------------|-------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[多言語サポート](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)| 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上 | 4.7.1 以上 | 4.0.39 以上 | はい |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[ラベル変更の正当な理由を要求する](sensitivity-labels.md#what-label-policies-can-do)                     | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[カスタム ヘルプ ページへのリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[コンテンツをマークする](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[変数を使用した動的マーキング](#dynamic-markings-with-variables)                                              | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[ユーザーに権限の割り当てをさせる: <br /> - 転送不可](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 現在のチャネル: 1910 以上 <br /><br> 月次エンタープライズ チャネル: 1910 以上 <br /><br> 半期エンタープライズ チャネル: 2002 以上 | 16.21 以上                 | 4.7.1 以上         | 4.0.39 以上           | はい               |
|[ユーザーに権限の割り当てをさせる: <br /> - 暗号化のみ](encryption-sensitivity-labels.md#let-users-assign-permissions)  | 現在のチャネル: 2011 以上 <br /><br> 月次エンタープライズ チャネル: 2011 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.48 以上 <sup>\*</sup> | 4.2112.0 以上  | 4.2112.0 以上 | はい |
|[ユーザーがメールとドキュメントにラベルを適用することを必須にする](#require-users-to-apply-a-label-to-their-email-and-documents)   | 現在のチャネル: 2101 以上 <br /><br> 月次エンタープライズ チャネル: 2101 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.43 以上 <sup>\*</sup>                    | 4.2111 以上            | 4.2111 以上                | はい                |
|[ラベル関連のユーザー アクティビティを監査する](#auditing-labeling-activities) | 現在のチャネル: 2011 以上 <br /><br> 月次エンタープライズ チャネル: 2011 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.51 以上 <sup>\*</sup> | 4.2126 以上 | 4.2126 以上 | はい |
|[秘密度ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md) <br /> - 機密情報の種類の使用                    | 現在のチャネル: 2009 以上 <br /><br> 月次エンタープライズ チャネル: 2009 以上 <br /><br> 半期エンタープライズ チャネル: 2102 以上 | 16.44 以上 <sup>\*</sup>                    | レビュー中           | レビュー中               | はい |
|[秘密度ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md) <br /> - トレーニング可能な分類子の使用                    | 現在のチャネル: 2105 以上 <br /><br> 月次エンタープライズ チャネル: 2105 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.49+ | レビュー中           | レビュー中               | はい |
|[既定ラベルと必須ラベルのさまざまな設定](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | 現在のチャネル: 2105 以上 <br /><br> 月次エンタープライズ チャネル: 2105 以上 <br /><br> 半期エンタープライズ チャネル: 2108 以上 | 16.43 以上 <sup>\*</sup>                   | 4.2111 以上           | 4.2111 以上               | はい |
|[PDF サポート](#pdf-support) | プレビュー: [ベータ チャネル](https://office.com/insider)へのロールアウト|  レビュー中 | レビュー中 | レビュー中 | レビュー中 |
|[S/MIME 保護を適用する](#configure-a-label-to-apply-smime-protection-in-outlook)                    | レビュー中 | ロールアウト: 16.61 以上 <sup>\*</sup>                   | ロールアウト: 4.2226 以上 | ロールアウト: 4.2203 以上 | レビュー中 |

**脚注:**

<sup>\*</sup> [新しい Outlook for Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439) が必要です

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 組み込みのラベル付けクライアントと Azure Information Protection クライアント

ユーザーが [Azure Information Protection (API) クライアント](/azure/information-protection/rms-client/aip-clientv2)を Windows コンピューターにインストールしている場合、既定では、組み込みのラベル付けクライアントは[サポートする Windows Office アプリ](#labeling-client-for-desktop-apps)でオフになっています。 組み込みラベルは、AIP クライアントで使用される Office アドインを使用しないため、安定性とパフォーマンスの向上という利点があります。 また、高度な分類子などの最新の機能もサポートしています。 

> [!NOTE]
> Office更新チャネルでサポートされている最小バージョンを確認しているにもかかわらず、Windows コンピューターで必要なラベル付け機能が表示されない場合は、[AIP アドインを無効にする](sensitivity-labels-aip.md#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps)必要がある可能性があります。

AIP クライアントを使用したラベル付けのサポート、および Office アプリでこのクライアントを無効にする方法の詳細については、「[Office アプリの AIP アドインに対して MIP 組み込みラベル付けを選択する理由](sensitivity-labels-aip.md)」を参照してください。

## <a name="if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows"></a>Windows 上の Office アプリで組み込みのラベル付けを無効にする必要がある場合

Office 組み込みのラベル付けクライアントは、Microsoft Purview コンプライアンス ポータルから秘密度ラベルと秘密度ラベル ポリシー設定をダウンロードします。

Office 組み込みのラベル付けクライアントを使用するには、Microsoft Purview コンプライアンス ポータルと[サポートされているバージョンの Office](#support-for-sensitivity-label-capabilities-in-apps) からユーザーに 1 つ以上の[ラベル ポリシーを公開](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。

これらの条件の両方が満たされているが、Windows Office アプリの組み込みのラベル付けクライアントをオフにする必要がある場合は、次のグループ ポリシー設定を使用します:

1. **ユーザーの構成/管理用テンプレート/Microsoft Office 2016/セキュリティ設定** に移動します。

2. **[Office の秘密度機能を使用して、秘密度ラベルを適用および表示する]** を **0** に設定します。

後でこの構成を元に戻す必要がある場合は、値を **1** に変更 します。 また、リボンに **[秘密度]** ボタンが期待どおりに表示されない場合は、この値を 1 に変更する必要がある場合もあります。 たとえば、前の管理者がこのラベル付け設定をオフにしたとします。
 
グループ ポリシーを使用するか、[Office クラウド ポリシー サービス](/DeployOffice/overview-office-cloud-policy-service)を使用して、この設定を展開します。 この設定は、Office アプリが再起動したときに有効になります。 

この設定は Windows Office アプリに固有であるため、秘密度ラベル (Power BI など) や他のプラットフォーム (macOS、モバイル デバイス、Office for the web など) をサポートする Windows 上の他のアプリには影響しません。 一部またはすべてのユーザーにすべてのアプリ (すべてのプラットフォーム) で秘密度ラベルを表示して使用したくない場合は、それらのユーザーに秘密度ラベル ポリシーを割り当てないでください。

## <a name="office-file-types-supported"></a>サポートされる Office ファイルの種類

Word、Excel、および PowerPoint ファイルに組み込みのラベル付けをする Office アプリは、Open XML 形式 (.docx や .xlsx など) をサポートしていますが、Microsoft Office 97-2003 形式 (.doc や .xls など)、Open Document 形式 (.odt や .ods など)、またはその他の形式はサポートしていません。ファイルの種類が組み込みのラベル付けでサポートされていない場合、Office アプリでは **[秘密度]** ボタンを使用できません。

Azure Information Protection 統合ラベル付けクライアントは、Open XML 形式と Microsoft Office 97-2003 形式の両方をサポートしています。 詳細については、クライアントの管理ガイドの「[Azure Information Protection 統合ラベル付けクライアントでサポートされるファイルの種類](/azure/information-protection/rms-client/clientv2-admin-guide-file-types)」を参照してください。

その他のラベル付けソリューションについては、サポートされるファイルの種類のドキュメントを確認してください。

## <a name="protection-templates-and-sensitivity-labels"></a>保護テンプレートと秘密度ラベル

組み込みのラベル付けを使用している場合、Office 365 Message Encryption に定義したものなど、管理者が定義した[保護テンプレート](/azure/information-protection/configure-policy-templates)は Office アプリに表示されません。 この簡素化されたエクスペリエンスにより、保護テンプレートを選択する必要はありません。暗号化が有効になっている秘密度ラベルに同じ設定が含まれているためです。

*EncryptionTemplateId* パラメーターを指定して [New-Label](/powershell/module/exchange/new-label) コマンドレットを使用すると、既存のテンプレートを秘密度ラベルに変換できます。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Information Rights Management (IRM) オプションと秘密度ラベル

暗号化を適用するために構成する秘密度ラベルは、ユーザーから複雑さを取り除き、独自の暗号化設定を指定します。 多くの Office アプリでは、これらの個々の暗号化設定は、ユーザーが Information Rights Management (IRM) オプションを使用して手動で構成できます。 たとえば、Windows アプリの場合:

- ドキュメントの場合: **[ファイル]** > **[情報]** > **[ドキュメントの保護]** > **[アクセスの制限]**
- メールの場合: **[オプション]** タブ > **[暗号化]** から 
  
ユーザーが最初にドキュメントまたはメールにラベルを付けるとき、ユーザーはいつでも独自の暗号化設定でラベル構成設定を上書きできます。例えば、以下のような場合があります。

- ユーザーが **社外秘 \ すべての従業員** ラベルをドキュメントに適用し、このラベルは組織内のすべてのユーザーに暗号化設定を適用するように構成されています。 次に、このユーザーは IRM 設定を手動で構成して、組織外のユーザーへのアクセスを制限します。 最終結果は、**社外秘 \ すべての従業員** というラベルが付けられ、暗号化されたドキュメントですが、組織内のユーザーは期待どおりに開くことができません。

- ユーザーが **社外秘 \ 受信者のみ** ラベルをメールに適用し、このメールは **転送不可** の暗号化設定を適用するように構成されています。 Outlook アプリでは、このユーザーが手動で暗号化のみの IRM 設定を選択します。 最終的に、**社外秘 \ 受信者のみ** ラベルが付いていても、暗号化が保持される間は受信者はメールを転送できます。
    
    例外として、Outlook on the web の場合、現在選択されているラベルが暗号化を適用する場合、ユーザーは **[暗号化]** メニューのオプションを選択できません。

- ユーザーが **全般** ラベルをドキュメントに適用しますが、このラベルは暗号化を適用するように構成されていません。 次に、このユーザーは IRM 設定を手動で構成して、ドキュメントへのアクセスを制限します。 最終結果は、**全般** というラベルの付いたドキュメントですが、暗号化も適用されるため、一部のユーザーは期待どおりに開くことができません。

ドキュメントまたはメールにすでにラベルが付けられている場合、コンテンツがまだ暗号化されていないか、「エクスポート」または「フル コントロール」の[使用権限](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)があるなら、ユーザーはこれらのアクションのいずれかを実行できます。 

意味のあるレポートでより一貫性のあるラベル エクスペリエンスを実現するには、ドキュメントとメールを保護するためにラベルを適用するように、ユーザーに適切なラベルとガイダンスを提供します。以下のような例があります。

- ユーザーが独自のアクセス許可を割り当てる必要がある例外的なケースでは、[ユーザーが独自のアクセス許可を割り当てることができる](encryption-sensitivity-labels.md#let-users-assign-permissions)以下のようなラベルを提供します。 

- ユーザーが暗号化を適用するラベルを選んだ後に手動で暗号化を削除する代わりに、ユーザーが同じ分類の暗号化なしのラベルを必要とする場合は、以下のようなサブラベルの代替手段を提供します。
    - **社外秘 \ すべての従業員**
    - **社外秘 \ すべてのユーザー (暗号化なし)**

- 以下のように IRM 設定を無効化してユーザーが選択しないようにすることを検討します。
    - Outlook for Windows: 
        - レジストリ キー`DWORD:00000001` *DisableDNF* および *DisableEO* `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM` より
        - グループ ポリシー設定では、**[暗号化] ボタン向けに既定の暗号化オプションを構成する** は構成されないことを確認してください。
    - Outlook for Mac: 
        - キー *DisableEncryptOnly* および *DisableDoNotForward* セキュリティ設定は、[Outlook for Mac 向けの環境設定の設定](/DeployOffice/mac/preferences-outlook)で文書化されます
    - Outlook on the web: 
        - パラメーター *SimplifiedClientAccessDoNotForwardDisabled* および *SimplifiedClientAccessEncryptOnlyDisabled* は、[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) 向けに文書化されます
    - iOS および Android 用の Outlook: これらのアプリでは、ユーザーがラベルなしの暗号化を適用することをサポートされていないため、すべて無効です。

> [!NOTE]
> ユーザーが SharePoint または OneDrive に保存されているラベル付きドキュメントから暗号化を手動で削除し、[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にした](sensitivity-labels-sharepoint-onedrive-files.md)場合、ラベルの暗号化は、次にドキュメントがアクセスまたはダウンロードされたときに、自動的に復元します。 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>ファイル、メール、および添付ファイルに秘密度ラベルを適用する

ユーザーは、ドキュメントまたはメールごとに一度に 1 つだけラベルを適用することができます。

添付ファイルのあるメール メッセージにラベルを付ける場合、メール メッセージに適用するラベルが暗号化を適用し、添付ファイルがまだ暗号化されていない Office ドキュメントである場合にのみ、添付ファイルはラベルを継承します。継承されたラベルは暗号化を適用するため、添付ファイルは新たに暗号化されます。

メール メッセージに適用されたラベルが暗号化を適用していない場合、または添付ファイルがすでに暗号化されている場合、添付ファイルはメール メッセージからラベルを継承しません。

ラベルの継承の例。ラベル **社外秘** は暗号化を適用し、ラベル **全般** は暗号化を適用しません。

- ユーザーが新しいメール メッセージを作成し、このメッセージに **社外秘** のラベルを適用します。 次に、ラベル付けも暗号化もされていない Word 文書を追加します。 継承の結果、ドキュメントには新たに **社外秘** のラベルが付けられ、そのラベルから暗号化が適用されるようになりました。

- ユーザーが新しいメール メッセージを作成し、このメッセージに **社外秘** のラベルを適用します。 次に、**全般** というラベルの付いた Word 文書を追加しますが、このファイルは暗号化されていません。 継承の結果、ドキュメントには **社外秘** として再度ラベルが付けられ、そのラベルから暗号化が適用されるようになりました。

## <a name="sensitivity-label-compatibility"></a>秘密度ラベルの互換性

**RMS 対応アプリの場合**: 秘密度ラベルをサポートしていない [RMS 対応アプリケーション](/azure/information-protection/requirements-applications#rms-enlightened-applications)で、ラベル付きで暗号化されたドキュメントまたはメールを開いた場合でも、アプリは暗号化とアクセス権管理を実施します。

**Azure Information Protection クライアントの場合**: Azure Information Protection クライアントを使用して、Office 組み込みのラベル付けクライアントでドキュメントやメールに適用する秘密度ラベルを表示および変更できます。その逆も可能です。

**他のバージョンの Office の場合**: 許可されたユーザーは、他のバージョンの Office でラベル付きのドキュメントやメールを開くことができます。 ただし、サポートされている Office バージョン、または Azure Information Protection クライアントを使用してのみ、ラベルを表示または変更できます。 サポートされている Office アプリのバージョンは、[前のセクション](#support-for-sensitivity-label-capabilities-in-apps)に記載されています。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>秘密度ラベルで保護された SharePoint および OneDrive ファイルのサポート

SharePoint または OneDrive のドキュメントに対して Office on the web で Office 組み込みのラベル付けクライアントを使用するには、[SharePoint および OneDrive の Office ファイルに秘密度ラベルが有効になっている](sensitivity-labels-sharepoint-onedrive-files.md)ことを確認してください。

## <a name="support-for-external-users-and-labeled-content"></a>外部ユーザーとラベル付きコンテンツのサポート

ドキュメントまたはメールにラベルを付けると、ラベルはテナントとラベル GUID を含むメタデータとして保存されます。 秘密度ラベルをサポートする Office アプリでラベル付きのドキュメントまたはメールを開くと、このメタデータが読み取られ、ユーザーが同じテナントに属している場合にのみ、ラベルがアプリに表示されます。 たとえば、Word、PowerPoint、Excel の組み込みのラベル付けの場合、ラベル名はステータス バーに表示されます。 

つまり、異なるラベル名を使用する別の組織とドキュメントを共有する場合、各組織はドキュメントに適用された独自のラベルを適用して確認できます。 ただし、適用されたラベルの次の要素は、組織外のユーザーに表示されます。

- コンテンツのマーキング。ラベルがヘッダー、フッター、または透かしを適用すると、これらはコンテンツに直接追加され、誰かが変更または削除するまで表示されたままになります。

- 暗号化を適用したラベルの基になる保護テンプレートの名前と説明。 この情報は、ドキュメントの上部にあるメッセージ バーに表示され、ドキュメントを開く権限のあるユーザーと、そのドキュメントの使用権に関する情報を提供します。

### <a name="sharing-encrypted-documents-with-external-users"></a>暗号化されたドキュメントを外部ユーザーと共有する

自分の組織内のユーザーへのアクセスを制限できますが、Azure Active Directory (Azure AD) にアカウントを持つ他のユーザーにアクセスを拡張することもできます。 既定では、これらの外部ユーザーは追加の構成なしで認証されます。 ただし、Azure AD [外部 ID のクロステナント アクセス設定](/azure/active-directory/external-identities/cross-tenant-access-overview) と [条件付き](/azure/active-directory/conditional-access/overview)アクセスには、追加の構成が必要になる場合があります。 

外部ユーザーが Azure AD にアカウントを持っていない場合は、テナント内のゲスト アカウントを使用して認証できます。 これらのゲスト アカウントは、SharePoint および OneDrive で [Office ファイルの秘密度ラベルを有効にしている場合に、SharePoint または OneDrive の共有ドキュメントに](sensitivity-labels-sharepoint-onedrive-files.md)アクセスするためにも使用できます。

オプションの Azure AD 機能と認証要件にゲスト アカウントを使用する方法の詳細については、 [暗号化コンテンツの Azure AD 構成に関するページを](encryption-azure-ad-configuration.md)参照してください。

すべての Office アプリおよびその他の [RMS 対応アプリケーション](/azure/information-protection/requirements-applications#rms-enlightened-applications)は、ユーザーが正常に認証された後、暗号化されたドキュメントを開くことができます。 

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office アプリがコンテンツ マーキングと暗号化を適用した場合

Office アプリは、使用するアプリに応じて、秘密度ラベルを使用したコンテンツ マーキングと暗号化を異なる方法で適用します。

| アプリ | コンテンツのマーケティング | 暗号化 |
| --- | --- | --- |
| すべてのプラットフォームの Word、Excel、PowerPoint | 直ちに | 直ちに |
| Outlook for PC と Outlook for Mac | Exchange Online がメールを送信した後 | 直ちに |
| Outlook on the web、iOS、および Android | Exchange Online がメールを送信した後 | Exchange Online がメールを送信した後 |
|

Office アプリの外部のファイルに秘密度ラベルを適用するソリューションは、ファイルにラベル付けメタデータを適用します。 このシナリオでは、ラベルの構成からコンテンツ マーキングはファイルに挿入されませんが、暗号化が適用されます。 

これらのファイルを Office デスクトップ アプリで開くと、ファイルが最初に保存されたときに、Azure Information Protection 統合ラベル付けクライアントによってコンテンツのマーキングが自動的に適用されます。 デスクトップ、モバイル、または Web アプリに組み込みのラベル付けを使用する場合、コンテンツ マーキングは自動的に適用されません。

Office アプリの外部に秘密度ラベルを適用することを含むシナリオは次のとおりです。

- Azure Information Protection 統合ラベル付けクライアントのスキャナー、エクスプローラー、および PowerShell 

- SharePoint と OneDrive の自動ラベル付けポリシー

- Power BI からエクスポートされた、ラベル付けおよび暗号化されたデータ

- Microsoft Defender for Cloud Apps

これらのシナリオでは、Office アプリを使用して、組み込みのラベル付けを持つユーザーは、現在のラベルを一時的に削除または置換してから元のラベルを再適用することで、ラベルのコンテンツ マーキングを適用できます。

### <a name="dynamic-markings-with-variables"></a>変数を使用した動的マーキング

> [!IMPORTANT]
> ご使用の Office アプリがこの機能をサポートしていない場合、変数を解決するのではなく、ラベル構成で指定された元のテキストとしてマーキングを適用します。
> 
> Azure Information Protection 統合ラベル付けクライアントは、動的マーキングをサポートしています。Office に組み込まれているラベル付けについては、サポートされている最小バージョンについて、このページの[機能](#support-for-sensitivity-label-capabilities-in-apps)セクションの表を参照してください。

コンテンツ マーキングの秘密度ラベルを構成する場合、ヘッダー、フッター、または透かしのテキスト文字列で次の変数を使用できます。

| 変数 | 説明 | ラベルが適用された場合の例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 適用されたラベルのラベル表示名 | **全般**|
| `${Item.Name}` | ラベル付けされたコンテンツのファイル名またはメールの件名 | **Sales.docx** |
| `${Item.Location}` | ラベル付けされたドキュメントのパスとファイル名、またはラベル付けされたメールの件名 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | ラベルを適用するユーザーの表示名 | **Richard Simone** |
| `${User.PrincipalName}` | ラベルを適用するユーザーの Azure AD ユーザー プリンシパル名 (UPN) | **rsimone\@contoso.com** |
| `${Event.DateTime}` | コンテンツにラベル付けされる日時、Microsoft 365 アプリでラベルを適用するユーザーのローカル タイム ゾーン、または Office Online および自動ラベル付けポリシーの UTC (協定世界時) | **2020 年 8 月 10 日午後 1:30** |

> [!NOTE]
> これらの変数の構文では大文字と小文字が区別されます。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Word、Excel、PowerPoint、および Outlook にさまざまな視覚的マーキングを設定する

追加の変数として、テキスト文字列で "If.App" 変数ステートメントを使用して Office アプリケーションの種類ごとに視覚的マーキングを構成し、**Word**、**Excel**、**PowerPoint**、または **Outlook** の値を使用してアプリケーションの種類を識別できます。 これらの値を短縮することもできます。これは、同じ If.App ステートメントで複数を指定する場合に必要です。

次の構文を使用してください。

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

他の動的な視覚的マーキングと同様に、構文では大文字と小文字が区別され、各アプリケーション タイプ (WEPO) の略語が含まれます。

例:

- **Word 文書のみのヘッダー テキストを設定します。**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Word 文書ヘッダーのみで、ラベルに「この Word 文書は機密です」というヘッダー テキストを適用します。 ヘッダー テキストは他の Office アプリケーションには適用されません。

- **Word、Excel、および Outlook のフッター テキストと、PowerPoint の別のフッター テキストを設定します。**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    Word、Excel、および Outlook では、ラベルに「このコンテンツは社外秘です」というフッター テキストを適用します。 PowerPoint では、ラベルに「このプレゼンテーションは社外秘です」というフッター テキストを適用します。

- **Word と PowerPoint に特定の透かしテキストを設定してから、Word、Excel、PowerPoint に透かしテキストを設定します。**

    `${If.App.WP}This content is ${If.End}Confidential`

    Word および PowerPoint では、ラベルに「このコンテンツは社外秘です」という透かしテキストを適用します。 Excel では、ラベルに「社外秘」という透かしテキストを適用します。 Outlook では、視覚的マーキングとしての透かしは Outlook でサポートされていないため、ラベルに透かしテキストを適用しません。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>ユーザーがメールとドキュメントにラベルを適用することを必須にする

> [!IMPORTANT]
> 
> [Azure Information Protection 統合ラベル付けクライアント](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)は、必須ラベリングとも呼ばれるこの構成をサポートします。Office アプリに組み込まれているラベル付けについては、このページの[機能](#support-for-sensitivity-label-capabilities-in-apps)セクションの表で最小バージョンを参照してください。
>
> メールではなくドキュメントに必須ラベルを使用するには、Outlook 固有のオプションを構成する方法を説明する次のセクションの手順を参照してください。
> 
> Power BI の必須のラベル付けを使用するには、「[Power BI の必須のラベル付けポリシー](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy)」を参照してください。

このポリシー設定 [**ユーザーに電子メールとドキュメントへのラベルの適用を要求する**] を選択した場合、ポリシーを割り当てられたユーザーは、次のシナリオで秘密度ラベルを選択して適用する必要があります。

- Azure Information Protection 統合ラベル付けクライアントの場合:
    - ドキュメント (Word、Excel、PowerPoint) の場合: ラベル付けされていないドキュメントが保存されたとき、またはユーザーがドキュメントを閉じたとき。
    - メール (Outlook) の場合: ユーザーがラベル付けされていないメッセージを送信するとき。

- Office アプリに組み込まれているラベル付けの場合:
    - ドキュメント (Word、Excel、PowerPoint) の場合: ラベル付けされていないドキュメントを開いたり保存したりしたとき。
    - メール (Outlook) の場合: ユーザーがラベル付けされていないメール メッセージを送信するとき。

組み込みのラベル付けに関する追加情報:

- ラベル付けされていないドキュメントを開いたために秘密度ラベルを追加するように求められた場合、ユーザーはラベルを追加するか、ドキュメントを読み取り専用モードで開くことを選択できます。

- 必須のラベル付けが有効になっている場合、ユーザーはドキュメントから秘密度ラベルを削除することはできませんが、既存のラベルを変更することはできます。

- 必須のラベル付けが有効になっている場合、ドキュメントにラベルが付けられているか暗号化されていると、PDF に印刷オプションは使用できなくなります。 詳細については、このページの「[PDF サポート](#pdf-support)」セクションを参照してください。

この設定をいつ使用するかについては、[ポリシー設定](sensitivity-labels.md#what-label-policies-can-do)に関する情報を参照してください。

> [!NOTE]
> 必須のラベル付けに加えて、ドキュメントやメールに既定のラベル ポリシー設定を使用する場合: 
>
> 既定のラベルは、必須のラベル付けよりも常に優先されます。 ただし、ドキュメントの場合、Azure Information Protection 統合ラベル付けクライアントでは、既定のラベルがすべてのラベルなしドキュメントに適用されます。一方、組み込みのラベル付けでは、既定のラベルは新しいドキュメントには適用されますが、ラベルのない既存のドキュメントには適用されません。 この動作の違いにより、ユーザーが既定のラベル設定で必須のラベル付けを使用する場合、Azure Information Protection の統合ラベル付けクライアント使用時よりも、組み込みのラベル付け使用時のほうが、秘密度ラベルの適用を求めるメッセージがより頻繁に表示されることになります。
> 
> 今すぐロールアウト: 組み込みラベル付けを使用し、既存のドキュメント用に既定のラベルをサポートする Office アプリ。 詳細については、Word、Excel、および PowerPoint の[機能表](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)を参照してください。

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>既定ラベルと必須ラベルの Outlook 固有のオプション

組み込みのラベル付けの場合は、このページの [Outlook の機能テーブル](#sensitivity-label-capabilities-in-outlook)と、**既定ラベルと必須ラベル付けのさまざまな設定** の行を使用して、これらの機能をサポートする Outlook の最小バージョンを特定します。Azure Information Protection 統合ラベル付けクライアントのすべてのバージョンは、これらの Outlook 固有のオプションをサポートします。

Outlook アプリが、ドキュメントの既定のラベル設定と異なる既定のラベル設定をサポートしている場合は、以下のようになります。

- Microsoft Purview コンプライアンス ポータルのラベル ポリシー構成の **[メールに既定のラベルを適用する]** ページでは、ラベルなしのすべてのメールに適用される秘密度ラベルを選択するか、既定のラベルをなしにするかを指定できます。 この設定は、構成の以前の **[ドキュメント向けポリシー設定]** ページの **[既定でドキュメントにこのラベルを適用する**] 設定とは独立しています。

Outlook アプリが、ドキュメント向けの既定のラベル設定と異なる既定のラベル設定をサポートしていない場合: Outlook は、ラベル ポリシー ウィザードの **[ドキュメント向けポリシー設定]** ページで **[既定でドキュメントにこのラベルを適用する]** に指定した値を常に使用します。

Outlook アプリが、必須のラベル付けをオフすることをサポートする場合は、以下のようになります。

- **[ポリシー設定]** ページの Microsoft Purview コンプライアンス ポータルのラベル ポリシー構成で、**[メールまたはドキュメントにラベルを適用するユーザーを要求する]** を選択します。 次に **[次へ]** > 、**[次へ]** の順に選択し、**[メールへのラベルの適用をユーザーに要求する]** チェックボックスをオフにします。 ドキュメントに加えて、メールにもラベル付けを必須にすることを適用する場合は、チェックボックスをオンにしたままにしておきます。

Outlook アプリが必須のラベル付けをオフにすることをサポートしていない場合。ポリシー設定で **Require users to apply a label to their email or documents** を選択した場合、Outlookはラベルのない電子メールに対して常にユーザーにラベルの選択を促すようになります。

> [!NOTE]
> [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) コマンドレットまたは [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy) コマンドレットを使用して、PowerShell の詳細設定 **OutlookDefaultLabel** および **DisableMandatoryInOutlook** を設定している場合は、このコマンドレットを使用してください。
> 
> これらの PowerShell 設定で選択した値は、Microsoft Purview コンプライアンス ポータルのラベル ポリシー構成に反映され、これらの設定をサポートする Outlook アプリで自動的に機能します。 その他の PowerShell の詳細設定は、Azure Information Protection 統合ラベル付けクライアントでのみサポートされたままです。

## <a name="configure-a-label-to-apply-smime-protection-in-outlook"></a>Outlook で S/MIME 保護を適用するようにラベルを構成する

> [!NOTE]
> この機能は現在、組み込みのラベル付けのためにロールアウトされています。 このページの Outlook の [機能テーブル](#sensitivity-label-capabilities-in-outlook) と行 [ **S/MIME 保護の適用**] を使用して、この機能をサポートする Outlook の最小バージョンを特定します。
> 
> S/MIME 保護を適用するようにラベルを構成しても、Outlook アプリではまだサポートされていない場合、ラベルは Outlook に表示され、適用できますが、S/MIME 設定は無視されます。 Exchange 自動ラベル付けポリシーに対してこのラベルを選択することはできません。

この構成は、Microsoft Purview コンプライアンス センターでは使用できません。 [Office 365 セキュリティ/コンプライアンス センター PowerShell ](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) に接続した後、 [Set-Label](/powershell/module/exchange/set-label) または [New-Label](/powershell/module/exchange/new-label) cmd で PowerShell の詳細設定を使用する必要があります。

これらの設定は、作業中の [ S/MIME 展開](/microsoft-365/security/office-365-security/s-mime-for-message-signing-and-encryption) があり、[ Azure Information ProtectionからのRights Management 暗号化を使用する既定の保護](encryption-sensitivity-labels.md)ではなく、電子メールにラベルでこの保護方法を自動的に適用する場合にのみ使用します。 結果として得られる保護は、ユーザーが Outlook から S/MIME オプションを手動で選択した場合と同じです。

|構成  |詳細設定のキー/値 |
|---------|---------|
|**S/MIME デジタル署名** | SMimeSign="True" |
|**S/MIME 暗号化** | SMimeEncrypt="True"|

これらの設定に対して構成するラベルは、コンプライアンス ポータルで暗号化用に構成する必要はありません。 ただし、その場合、S/MIME 保護は Outlook でのみRights Management暗号化を置き換えます。 他のアプリの場合、ラベルは Microsoft Purview コンプライアンス ポータルで指定された暗号化設定を適用します。

秘密度ラベル GUID が **8faca7b8-8d20-48a3-8ea2-0f96310a848e** である PowerShell コマンドの例:

```PowerShell
Set-Label -Identity "8faca7b8-8d20-48a3-8ea2-0f96310a848e" -AdvancedSettings @{SMimeSign="True"}

Set-Label -Identity "8faca7b8-8d20-48a3-8ea2-0f96310a848e" -AdvancedSettings @{SMimeEncrypt="True"}
```

PowerShell の詳細設定の指定に関する詳細については、「[PowerShell の詳細設定の指定に関するヒント](create-sensitivity-labels.md#powershell-tips-for-specifying-the-advanced-settings)」を参照してください。

## <a name="pdf-support"></a>PDF サポート

組み込みのラベル付けについては、このページの[機能](#support-for-sensitivity-label-capabilities-in-apps)セクションの表を使用して、サポートされている最小バージョンを特定してください。 Azure Information Protection 統合ラベル付けクライアントは、Office アプリでは PDF をサポートしていません。

Word、Excel、および PowerPoint は、Office ドキュメントを PDF ドキュメントに変換するための次の方法をサポートしています。

- [ファイル] > [名前を付けて保存] > [PDF] 
- [ファイル] > [エクスポート] > [PDF]
- [共有] > [コピーを送信] > [PDF]

このアクションは、[ファイル アクティビティとページ アクティビティ](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)監査グループの **名前変更されたファイル** 監査イベントでログに記録されます。 コンプライアンス ポータルの監査検索結果に、この監査イベントの詳細が [**アクティビティ**] フィールドの **SensitivityLabeledFileRenamed** と表示されます。

PDF が作成されると、コンテンツのマーキングと暗号化を含むラベルが継承されます。 暗号化された PDF は、Windows または Mac の Microsoft Edge で開くことができます。 詳細および代替リーダーについては、「[保護された PDF をサポートする PDF リーダー](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)」を参照してください。

Outlook では、現在、ラベル付きメッセージから暗号化を継承する PDF 添付ファイルはサポートされていません。 ただし、Outlook では、次に説明するように、ユーザーが PDF に印刷できないように警告またはブロックする機能がサポートされるようになりました。

PDF シナリオはサポートされていません:

- PDF に印刷する
    
    ユーザーがこのオプションを選択すると、ドキュメントまたはメールがラベルの保護と暗号化 (適用されている場合) を失うことを警告され、続行するには確認する必要があります。 秘密度ラベル ポリシーでラベルを削除するか、その分類を下げる理由が必要な場合は、このプロンプトが表示されます。
    
    このオプションは秘密度ラベルを削除するため、必須のラベルを使用している場合、ユーザーはこのオプションを使用できません。 この構成は、ユーザーがメールとドキュメントにラベルを適用することを要求する秘密度ラベル ポリシー設定を参照します。

- PDF/A 形式と暗号化
    
     長期アーカイブ用に設計されたこの PDF 形式は、ラベルが暗号化を適用する場合はサポートされず、ユーザーが Office ドキュメントを PDF に変換できなくなります。 構成情報については、「 [ISO 19005-1 への PDF 準拠を強制する (PDF/A)](https://admx.help/?Category=Office2016&Policy=office16.Office.Microsoft.Policies.Windows::L_EnforcePDFcompliancewithISO190051PDFA) 」に関するグループ ポリシードキュメントを参照してください。
    
- パスワード保護と暗号化
    
    ドキュメントのラベルが暗号化を適用する場合、オプション **[ファイル]** > **[情報]** > **[ドキュメントの保護]** > **[パスワードで暗号化]** はサポートされません。 このシナリオでは、ユーザーは [パスワードで暗号化] オプションを使用できなくなります。

この機能の詳細については、「[Office アプリで作成された PDF に秘密度ラベルを適用する](https://insider.office.com/blog/apply-sensitivity-labels-to-pdfs-created-with-office-apps)」の発表を参照してください。

## <a name="auditing-labeling-activities"></a>ラベル付けアクティビティの監査

秘密度ラベル アクティビティによって生成される監査イベントの詳細については、[「Microsoft Purview コンプライアンス ポータルの監査ログを検索する」](search-the-audit-log-in-security-and-compliance.md)の「[秘密度ラベル アクティビティ](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)」セクションを参照してください。

この監査情報は [コンテンツ エクスプローラー](data-classification-content-explorer.md) と [アクティビティ エクスプローラー](data-classification-activity-explorer.md) で視覚的に表され、秘密度ラベルの使用方法と、ラベル付けされたコンテンツの場所を理解するのに役立ちます。 

また、[監査ログ レコードをエクスポートして構成](export-view-audit-log-records.md)するときに、選択したセキュリティ情報およびイベント管理 (SIEM) ソフトウェアを使用してカスタム レポート作成することもできます。大規模なレポート ソリューションについては、「[Office 365 マネージメント アクティビティ API リファレンス」](/office/office-365-management-api/office-365-management-activity-api-reference)を参照してください。

> [!TIP]
> カスタム レポートを作成するには、次のブログ記事を参照してください:
> - [O365 マネージメント API による Microsoft Purview 監査ログ アクティビティ - パート 1](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957171)
> - [O365 マネージメント API による Microsoft Purview 監査ログ アクティビティ - パート 2](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957297)

## <a name="end-user-documentation"></a>エンド ユーザー向けのドキュメント

- [Office 内のファイルやメールに秘密度ラベルを適用する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office の秘密度ラベルに関する既知の問題](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [機密度ラベルの自動適用または推奨に関する既知の問題](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
