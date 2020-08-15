---
title: レコードについての詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 365 でのレコード管理ソリューションの実装に役立つレコードについて説明します。
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685443"
---
# <a name="learn-about-records"></a>レコードについての詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft 365 でレコードを管理することで、組織は企業のポリシー、法的および規制上の義務を順守し、リスクや法的責任を軽減することもできます。

コンテンツがレコードとしてマークされているときには:

- [アクションが許可またはブロックされている](#compare-restrictions-for-what-actions-are-allowed-or-blocked) という観点から、アイテムに制限がかけられています。

- アイテムに関する追加のアクティビティが記録されます。

- アイテムが保持期間の終了時に削除された時点で、廃棄の証明を取得します。

[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。 それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。

保持ラベルを使用してコンテンツをレコードとして宣言することで、Microsoft 365 環境全体で単一かつ一貫したレコード管理戦略を実装することができます。

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>許可またはブロックするアクションの制限を比較する

次の表を使用して、標準の保持ラベルを適用した結果、コンテンツに適用される制限事項、およびコンテンツをレコードとしてマークする保持ラベルを特定します。 

標準的な保持ラベルには、コンテンツをレコードとしてマークすることなくデータを保持する構成があります。

>[!NOTE] 
> 完全性を期すために、テーブルにはロックされたレコードの列とロック解除されたレコードの列が含まれています。これは、SharePoint と OneDrive には適用できますが、Exchange には適用されません。 レコードをロックまたはロック解除する機能は、Exchange アイテムでサポートされていない [レコード バージョン管理](record-versioning.md) を使用します。 そのため、レコードとしてマークされているすべての Exchange アイテムについて、[**レコード - ロック済み**] 列に動作がマップされ、[**レコード - ロック解除**] は関連がありません。


|アクション| 保持ラベル |レコード - ロック済み| レコード - ロック解除|
|:-----|:-----|:-----|:-----|:-----|
|コンテンツを編集する|可 | **ブロック済み** | 可|
|名前の変更など、プロパティを編集する|可 |可 | 可|
|削除|許可 <sup>1</sup> |**ブロック済み** | **ブロック済み**|
|コピー|可 |可 | 可|
|コンテナー内の移動 <sup>2</sup>|可 |可 | 可|
|コンテナー間の移動 <sup>2</sup>|可 |ロック解除されていない場合は許可 | 可|
|開く/読み取り|可 |可 | 可|
|ラベルを変更する|可 |許可-コンテナー管理のみ | 許可-コンテナー管理のみ|
|ラベルを削除する|可 |許可-コンテナー管理のみ | 許可-コンテナー管理のみ|

脚注:

<sup>1</sup> セキュリティ保護された場所にコピーを保持することによって、OneDrive と Exchange ではサポートされますが、SharePoint ではブロックされます。

ユーザーが SharePoint のラベル付きドキュメントを削除しようとしたときに表示されるメッセージは、次のとおりです。

![SharePoint の「アイテムが削除されませんでした」というメッセージ](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> コンテナーには、SharePoint ドキュメント ライブラリと Exchange メールボックスが含まれます。

## <a name="next-steps"></a>次の手順

レコード管理に使用する保持ラベルをまだ作成していない場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。

コンテンツをレコードとしてマークするには、[[保持ラベルを使用してレコードを宣言する](declare-records.md)] を参照してください。
