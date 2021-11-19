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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 正確なデータ一致ベースの機密情報の種類の作成を開始します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 469cc7262ff1eef92d9a03e04070dc353e12b445
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110501"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類の使用を開始する

完全なデータ一致 (EDM) ベースの機密情報の種類 (SIT) を作成して使用するには、複数フェーズのプロセスを使用します。 これらは、データ損失防止ポリシー、電子情報開示、および特定のコンテンツ ガバナンス タスクで使用できます。この記事では、ワークフローの概要と各フェーズの手順へのリンクについて説明します。

## <a name="before-you-begin"></a>はじめに

以下の記事の概念と用語について理解してください。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online の管理者である必要があります。 DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

完全な [ライセンス情報については、データ損失防止サービス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) の説明を参照してください。

## <a name="portal-links-for-your-subscription"></a>サブスクリプションのポータルリンク

|ポータル|世界中の GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 Defender ポータル|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft 365 コンプライアンス センター|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>ワークフローの概要

![完全なデータ一致ワークフロー フェーズ](..\media\swimlane_edm_process.png)


|フェーズ|前提条件|
|---|---|
|[フェーズ 1: 完全なデータ一致ベースの機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- 機密データへの読み取りアクセス|
|[フェーズ 2: 完全なデータ一致ベースの機密情報の種類のスキーマを作成する](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- 機密情報の種類ウィザードへのアクセスは、Microsoft 365 管理センター </br>- コンプライアンス[PowerShell Microsoft 365 管理センター経由&アクセス](/powershell/exchange/connect-to-scc-powershell) |
|[フェーズ 3: 機密情報の種類に一致する正確なデータの機密情報ソース テーブルのハッシュとアップロード](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- カスタムのセキュリティ グループとユーザー アカウント </br>- **1 つのコンピューターからの** ハッシュとアップロード : インターネットに直接アクセスできるコンピューターへのローカル管理者アクセスと、EDM クライアントエージェントアップロードします。 </br>- **個別の** コンピューターからのハッシュとアップロード: 直接インターネット アクセスを持つコンピューターへのローカル管理者アクセスと、EDM アップロード エージェントをホストして、セキュリティで保護されたコンピューターへのアップロードとローカル管理者アクセスをホストし、EDM アップロード エージェントをホストして機密情報ソース テーブルをハッシュする </br>- 機密情報ソース テーブル ファイルへの読み取りアクセス </br> スキーマ ファイル |
|[フェーズ 4: 機密情報の種類/ルール パッケージと完全一致するデータを作成する](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- コンプライアンス センター Microsoft 365アクセス |
|[機密情報の種類と完全に一致するデータをテストする](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - コンプライアンス センター Microsoft 365アクセス

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
