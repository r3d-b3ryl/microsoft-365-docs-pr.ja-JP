---
title: 完全なデータ一致に基づく機密情報の種類の使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 厳密なデータ一致ベースの機密情報の種類を作成する概要。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 592a4c7342af9ffe5c18d0d25b99b12cd1b3e212
ms.sourcegitcommit: f723ebbc56db8013598a88b0d7f13214d9d3eb10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2022
ms.locfileid: "65294671"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類の使用を開始する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

完全なデータ一致 (EDM) ベースの機密情報の種類 (SIT) を作成して使用できるようにするのは、多フェーズ プロセスです。 Microsoft Purview データ損失防止ポリシー、電子情報開示、特定のコンテンツ ガバナンス タスクで使用できます。この記事では、ワークフローの概要と各フェーズの手順へのリンクについて説明します。

## <a name="before-you-begin"></a>開始する前に

これらの記事の概念と用語について理解します。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="supported-regions"></a>サポートされる地域

正確なデータ一致は、次のリージョンで使用できます。

- アジア太平洋
- オーストラリア
- ブラジル
- カナダ
- ヨーロッパ
- フランス
- ドイツ
- インド
- 日本
- 韓国
- ノルウェー
- 南アフリカ
- スイス
- アラブ首長国連邦
- 英国
- 米国
- US DoD
- 米国GCC
- US GCCH

テナントが保存データをホストしているリージョンを確認するには、「Microsoft 365[顧客データの保存場所](../enterprise/o365-data-locations.md)」の手順に従って、同じ記事のデータ センターの都市の場所を参照します。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online の管理者である必要があります。 DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

完全なライセンス情報については、 [データ損失防止サービスの説明](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) を参照してください

## <a name="portal-links-for-your-subscription"></a>サブスクリプションのポータルリンク

|ポータル|世界中の GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 Defender ポータル|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft Purview コンプライアンス ポータル|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>ワークフローの概要

![正確なデータ一致ワークフロー フェーズ](..\media\swimlane_edm_process.png)


|フェーズ|前提条件|
|---|---|
|[フェーズ 1: 厳密なデータ一致ベースの機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- 機密データへの読み取りアクセス|
|[フェーズ 2: 厳密なデータ一致ベースの機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- Microsoft 365 管理センターの機密情報の種類ウィザードへのアクセス </br>- [セキュリティ & コンプライアンス PowerShell を使用してMicrosoft 365 管理センター](/powershell/exchange/connect-to-scc-powershell)にアクセスする |
|[フェーズ 3: 厳密なデータ一致の機密情報の種類の機密情報ソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- カスタムのセキュリティ グループとユーザー アカウント </br>- **1 台のコンピューターからのハッシュとアップロード**: インターネットに直接アクセスできるコンピューターへのローカル管理者アクセスと、EDM アップロード エージェントのホスト </br>- **個別のコンピューターからのハッシュとアップロード**: 直接インターネット にアクセスできるコンピューターへのローカル管理者アクセスと、EDM アップロード エージェントをホストして、機密情報ソース テーブルをハッシュするために EDM アップロード エージェントをホストするセキュリティで保護されたコンピューターへのローカル管理者アクセス </br>- 機密情報ソース テーブル ファイルへの読み取りアクセス </br> スキーマ ファイル |
|[フェーズ 4: 厳密なデータ一致の機密情報の種類/規則パッケージを作成する](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- Microsoft Purview コンプライアンス ポータルへのアクセス |
|[機密情報の種類と完全に一致するデータをテストする](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Microsoft Purview コンプライアンス ポータルへのアクセス

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
