---
title: データ分類プレビューのリリース ノート (プレビュー)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: データ分類パブリック プレビューのリリース ノート。
ms.openlocfilehash: 1beae92089833327cedf6090690530d9e5457a37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076364"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>データ分類パブリック プレビューのリリース ノート (プレビュー)

このパブリック プレビューでは、ポリシーを作成する *前に* 機密コンテンツとラベル付きコンテンツのスキャンを開始する新しい機能が導入されています。 これは **ゼロ変更管理** と呼ばれます。 これにより、すべての保持ラベルおよび機密ラベルが環境に与える影響を確認でき、保護ポリシーおよびガバナンス ポリシーのニーズの評価を開始できます。

このパブリック プレビューで最高の体験ができるように、これらのリリース ノートを確認してください。 現在と一般提供 (GA) の間のこれらのポイントに対処する作業を行います。

## <a name="permissions-for-accessing-content-explorer"></a>コンテンツ エクスプローラーにアクセスするためのアクセス許可

コンテンツ エクスプローラーへのアクセスは、スキャンしたファイルのコンテンツを読み取ることができるため、厳しく制限されています。 コンテンツ エクスプローラーにアクセスするには、**コンテンツ エクスプローラーのリスト ビューアー** および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループのメンバーシップが必要です。 既定では、コンテンツ エクスプローラーにアクセスできるアカウントはありません。 「[データ分類コンテンツ エクスプローラー (プレビュー)](data-classification-content-explorer.md#permissions)」を参照してください。 グローバル管理者、コンプライアンス管理者、またはデータ管理者は、必要な **コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループのメンバーシップを割り当てることができます。

> [!TIP]
> ロール ベースのアクセス制御 (RBAC) が世界中に展開されている間、**コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループがアクセス許可のページに表示されない場合があります。 アクセス許可のページに表示されない場合は、カスタム役割グループを作成し、`data classification list viewer` ロールまたは `data classification content viewer` ロールをカスタム役割グループに割り当てる必要があります。

## <a name="exchange-mailbox-count"></a>Exchange メールボックス数

Exchange メールボックスに移動すると、小さなツール ヒントが表示されます。 これは、機密情報の種類、機密ラベル、および保持ラベルに表示される集計数が、メールボックス内にあるアイテムの数と正確に一致しない場合があることを示すためです。 これは、集計された数が計算されている間に、フォルダへのドリルダウンが分類されたコンテンツのライブ ビューをフェッチするためです。

## <a name="seeing-guids-instead-of-label-names"></a>ラベル名の代わりに GUID を表示する

プライベート プレビューのお客様の場合、コンテンツが既にスタンプされたラベルの移行またはラベルを削除するとコンテンツ エクスプローラーおよびアクティビティ エクスプローラーでラベル名の代わりに 32 ビット GUID に解決されるインスタンスが表示されます。 

## <a name="rendering-of-encrypted-documents"></a>暗号化されたドキュメントのレンダリング

暗号化された SharePoint、Exchange、および OneDrive ファイルは、コンテンツ エクスプローラーにレンダリングされません。 これは、コンテンツ エクスプローラーでファイル コンテンツを表示する必要性とコンテンツを暗号化しておく必要性とのバランスを必要とする、慎重を期する問題です。 **コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループによってアクセス許可が付与されると、ファイルのリスト ビュー、ファイルのメタデータ、および Web クライアント経由でコンテンツにアクセスするために使用できるリンクが表示されます。

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 検索の保持ラベル名でサポートされている文字

SharePoint検索では、`-` または `_` を含む保持ラベル名はサポートされていません。 たとえば、`Label-MIP` や `Label_MIP` はサポートされていません。 SharePoint 検索は、機密ラベル名および機密情報の種類の名前に含まれるこれらの文字はサポートします。

## <a name="see-also"></a>関連項目

- [データ分類の使用を開始する (プレビュー)](data-classification-overview.md)
- [ラベル アクティビティを表示する (プレビュー)](data-classification-activity-explorer.md)
- [ラベル付きコンテンツの表示 (プレビュー)](data-classification-content-explorer.md)
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](labels.md)
- [機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)

