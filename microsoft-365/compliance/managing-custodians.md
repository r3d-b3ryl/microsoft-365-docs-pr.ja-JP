---
title: 電子情報開示でのカストディアンの操作 (プレミアム)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 電子情報開示 (プレミアム) でカストディアン管理ツールを使用して訴訟のデータを管理する方法について説明します。
ms.openlocfilehash: 360e66c3244b614624b6817f7fe95d9204c34bef
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096658"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-ediscovery-premium"></a>電子情報開示 (プレミアム) で保管担当者と非保管データ ソースを操作する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

組織が法的調査に対応する場合、潜在的に関連するコンテンツの特定、保持、収集に関するワークフローは、関連するデータのカストディアンである組織内のユーザーに基づきます。 電子情報開示では、これらの個人は *データカストディアン* (または単なる *カストディアン*) と呼ばれ、"ドキュメントまたは電子ファイルの管理制御を持つユーザー" として定義されます。 たとえば、電子メールメッセージのカストディアンは、関連メッセージを含むメールボックスの所有者でもあります。

さらに、メールボックスやサイト内に、保管担当者に関連付けられていないが、ケースに関連するコンテンツが存在する可能性があります。 ケースカストディアンが管理制御を持たないが、関連するデータの所有者である可能性があるコンテンツの場所は、 *非管理データ ソース* と呼ばれます。

電子情報開示 (プレミアム) の場合、法務チームは組織内の個人をカストディアンとして追加し、Exchange メールボックス、OneDrive アカウント、SharePoint サイト、Teams サイトなどの管理データ ソースを特定して保持できます。 また、非親権データ ソースを識別して保持することもできます。 組織は、電子情報開示 (プレミアム) の組み込みの保管担当者とデータ ソース管理ツールを使用して、不注意 (または意図的な) 削除から電子的に保存された情報をセキュリティで保護できます。 これにより、手動で訴訟ホールド プロセスを実行する必要がある時間とエラーが発生しやすいプロセスを排除できます。

カストディアンの操作の詳細については、次の記事を参照してください。

- [ケースにカストディアンを追加する](add-custodians-to-case.md)

- [カストディアンをケースに一括追加する](bulk-add-custodians.md)

- [ケース内のカストディアンを管理する](manage-new-custodians.md)

- [カストディアンのアクティビティを表示する](view-custodian-activity.md)

- [非カストディアンのデータ ソースをケースに追加する](non-custodial-data-sources.md)
