---
title: 厳密なデータ一致の機密情報の種類のワークフローの新しいエクスペリエンスを作成する
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
description: 新しいエクスペリエンスを使用して、厳密なデータ一致ベースの機密情報の種類の作成を開始します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47fa9bd604f5a905ce46dad2ef0b2177c86cfdec
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360694"
---
# <a name="create-exact-data-match-sensitive-information-type-workflow-new-experience"></a>厳密なデータ一致の機密情報の種類のワークフローの新しいエクスペリエンスを作成する

完全なデータ一致 (EDM) ベースの機密情報の種類 (SIT) を作成して使用できるようにするのは、多フェーズ プロセスです。 Microsoft Purview データ損失防止ポリシー、電子情報開示、特定のコンテンツ ガバナンス タスクで使用できます。この記事では、ワークフローの概要と各フェーズの手順へのリンクについて説明します。

## <a name="applies-to"></a>適用対象

- 新しいエクスペリエンス

クラシック エクスペリエンスを使用して EDM SIT を作成する場合は、「 [EDM SIT クラシック エクスペリエンスを作成する](sit-create-edm-sit-classic-ux-workflow.md)」を参照してください。

## <a name="before-you-begin"></a>はじめに

次の内容を確認してください。

- [EDM ベースの SIT について学習する](sit-learn-about-exact-data-match-based-sits.md)
- [厳密なデータ一致に基づく機密情報の種類の概要の概要を開始する](sit-get-started-exact-data-match-based-sits-overview.md)

## <a name="the-work-flow-at-a-glance"></a>ワークフローの概要


|フェーズ|前提条件|
|---|---|
|[フェーズ 1: 厳密なデータ一致ベースの機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- 機密データへの読み取りアクセス|
|[フェーズ 2:サンプル ファイルを作成する](sit-create-edm-sit-unified-ux-sample-file.md)|- 列ヘッダーと、各列で探すデータの形式を把握します。
|[フェーズ 3: EDM SIT を作成する](sit-create-edm-sit-unified-ux-schema-rule-package.md)|- **Microsoft Purview コンプライアンス ポータル** > **のデータ分類** > **の完全なデータ一致** へのアクセス |
|[フェーズ 4: 機密情報の種類に一致する厳密なデータの機密情報ソース テーブルをハッシュしてアップロードする](sit-get-started-exact-data-match-hash-upload.md)|- カスタムのセキュリティ グループとユーザー アカウント </br>- **1 台のコンピューターからのハッシュとアップロード**: インターネットに直接アクセスできるコンピューターへのローカル管理者アクセスと、EDM アップロード エージェントのホスト </br>- **個別のコンピューターからのハッシュとアップロード**: ローカル管理者が直接インターネット にアクセスできるコンピューターにアクセスし、EDM アップロード エージェントをホストし、セキュリティで保護されたコンピューターへのアップロードとローカル管理者アクセスをホストして、機密情報ソース テーブルをハッシュする EDM アップロード エージェントをホストする </br>- 機密情報ソース テーブル ファイルへの読み取りアクセス|
|[フェーズ 5: 厳密なデータ一致の機密情報の種類をテストする](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Microsoft Purview コンプライアンス ポータルへのアクセス

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)


## <a name="next-step"></a>次のステップ

- **新しいエクスペリエンスの場合**: [正確なデータ一致ベースの機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
