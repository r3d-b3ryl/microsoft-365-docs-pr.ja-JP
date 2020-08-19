---
title: レコード管理
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365 のレコード管理を使用すると、保持スケジュールをファイル計画に適用し、保持、レコード宣言、廃棄を管理することができます。
ms.openlocfilehash: c2ff344d22286fcd865aa08344389dad6334d48d
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778325"
---
# <a name="learn-about-records-management"></a>レコード管理の詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

すべての種類の組織では、企業データ全体にわたって規制、法務およびビジネスに不可欠なレコードを管理するためにレコード管理ソリューションが必要です。 Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、保持する必要がなくなった、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。

Microsoft 365 のレコード管理ソリューションをサポートするには、次の機能を使用します。

- **コンテンツをレコードとして分類する**。 コンテンツを[レコード](#records)としてマークする保持ラベルを作成および構成します。レコードは、ユーザーが適用することも、機密情報、キーワード、またはコンテンツ タイプを識別することにより自動的に適用することもできます。

- **ファイル計画を使用して、保持期間に関する要件を移行して管理します**。 [ファイル計画](file-plan-manager.md)を使用して、既存の保持プランを Microsoft 365 に持ち込んだり、新しいプランを構築して管理機能を強化したりすることができます。

- **保持ラベルを使用して、保持と削除の設定を構成します**。 保持期間を使用して[保持ラベル](retention.md#retention-labels)を構成したり、最終更新日や作成日などのさまざまな要因に基づきアクションを構成したりします。

- [イベントベースの保持](event-driven-retention.md)を使って、**イベントが発生したときに、別の保持期間を開始する**。

- [処理確認](disposition.md#disposition-reviews)、[レコードの削除](disposition.md#disposition-of-records)の証明を使用して**廃棄を確認および検証します**。

- [[エクスポート] オプション](disposition.md#filter-and-export-the-views)を使用して、**廃棄されたすべてのアイテムに関する情報をエクスポートします**。

- [適切なアクセス権を取得する](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に**特定のアクセス許可**を設定します。

これらの機能を使用すると、組織の保持スケジュールと要件をレコード管理ソリューションに反映させ、保持、レコード宣言、廃棄を管理して、コンテンツのライフサイクル全体をサポートすることができます。

オンライン ドキュメントの他にも、レコード管理に関する[ウェビナーの録音](https://aka.ms/MIPC/Video-RecordsManagementWebinar)を聴いたり、[よく寄せられる質問を含む付属のスライド](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)をダウンロードしたりすることもできます。

## <a name="records"></a>レコード

コンテンツがレコードとしてマークされているときには:

- [アクションが許可またはブロックされている](#compare-restrictions-for-what-actions-are-allowed-or-blocked) という観点から、アイテムに制限がかけられています。

- アイテムに関する追加のアクティビティが記録されます。

- アイテムが保持期間の終了時に削除された時点で、廃棄の証明を取得します。

[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。 それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。

保持ラベルを使用してコンテンツをレコードとして宣言することで、Microsoft 365 環境全体で単一かつ一貫したレコード管理戦略を実装することができます。

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>許可またはブロックするアクションの制限を比較する

次の表を使用して、標準の保持ラベルを適用した結果、コンテンツに適用される制限事項、およびコンテンツをレコードとしてマークする保持ラベルを特定します。 

標準の保持ラベルには、保持の設定とアクションが含まれていますが、コンテンツをレコードとしてマークしません。

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

詳細については、「[レコード管理の概要](get-started-with-records-management.md)」を参照してください。

コンテンツをレコードとしてマークするには、[[保持ラベルを使用してレコードを宣言する](declare-records.md)] を参照してください。
