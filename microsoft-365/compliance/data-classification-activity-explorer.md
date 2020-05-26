---
title: アクティビティ エクスプローラーの使用を開始する
f1.keywords:
- NOCSH
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
description: アクティビティ エクスプローラーでは、ラベル付きコンテンツを取り扱うユーザーの操作の確認およびフィルター処理を行い、データ分類機能の機能性を完全なものにします。
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327843"
---
# <a name="get-started-with-activity-explorer"></a>アクティビティ エクスプローラーの使用を開始する

データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。 アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。 アクティビティ エクスプローラーでは、履歴ビューを提供します。

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](../media/data-classification-activity-explorer-1.png)

使用可能なフィルターは 30 種類以上あり、以下がその一例です。

- 日付の範囲
- アクティビティの種類
- 場所
- ユーザー
- 機密ラベル
- 保持ラベル
- ファイル パス
- DLP ポリシー


## <a name="prerequisites"></a>前提条件

データ分類にアクセスし、データ分類を使用するすべてのアカウントには、以下のサブスクリプションのいずれかからライセンスが割り当てられている必要があります。

- Microsoft 365 (E5)
- Office 365 (E5)
- 高度なコンプライアンス (E5) アドオン
- 高度な脅威インテリジェンス (E5) アドオン

### <a name="permissions"></a>アクセス許可

 [アクティビティ エクスプローラー] タブにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。

**Microsoft 365 の役割グループ**

- 全体管理者
- コンプライアンス管理者
- セキュリティ管理者
- コンプライアンス データ管理者

## <a name="activity-type"></a>アクティビティの種類

Microsoft 365 は、SharePoint Online、OneDrive 全体で以下のようなアクティビティの種類を監視し、レポートします。

- ラベルの適用
- ラベルの変更 (アップグレード、ダウングレード、または削除)
- 自動ラベル付けのシミュレーション

機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。 そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。

> [!NOTE]
> アクティビティ エクスプローラーは現在、Exchange Online の保持アクティビティを監視していません。

## <a name="see-also"></a>関連項目
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](labels.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [アイテム保持ポリシーの概要](retention-policies.md)
