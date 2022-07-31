---
title: Microsoft 365 Defender のインシデントに優先順位を付け、管理し、調査し、対応する方法
description: Microsoft 365 Defenderでトリガーされるアラートを管理する手順。 サブスクリプション全体で自動的に調査と対応 (AIR) を検出し、脅威の影響と範囲を決定し、情報を 1 つのインシデントに結合します。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 18127cd732c0e2e1392a9c62e221dadfbd123246
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994297"
---
# <a name="prioritize-manage-investigate--respond-to-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defenderでのインシデントへの対応&優先順位付け、管理、調査

アラートがMicrosoft 365 Defenderにトリガーされると、自動調査と対応 (AIR) がトリガーされ、組織のサブスクリプション全体を捜索し、脅威の影響と範囲を決定し、管理者が複数のインシデントを管理する必要がないように情報を 1 つのインシデントに照合します。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365 プラン 2 以降
- 十分なアクセス許可 (セキュリティ リーダー、セキュリティ操作、またはセキュリティ管理者、および [検索ロールと消去](../permissions-microsoft-365-security-center.md) ロール)

## <a name="prioritize--manage-incidents"></a>インシデントを管理&優先順位を付ける

セキュリティ ポータルの [インシデント] ページ https://security.microsoft.com/incidentsに移動します。

インシデント ページが読み込まれると、フィルターを適用したり、列をクリックして優先順位を付けてアクションを並べ替えたり、フィルターキーを押してデータ ソース、タグ、状態などのフィルターを適用したりできます。

インシデントの優先順位付けされた一覧が作成されました。そこから、[インシデントの管理] ボタンを使用して、名前の変更、割り当て、分類、タグ付け、状態の変更、またはコメントの追加を選択できます。

フィルターを使用して、Microsoft Defender for Office アイテムが含まれていることを確認します。

特定のアラートを探している場合は、インシデント検索機能 (*名前または ID の検索*) を使用するか、特定のアラートでアラート キューのフィルター処理を使用することを検討してください。

## <a name="investigate--respond-to-incidents"></a>インシデントへの対応&調査する

インシデント キューに優先順位を付けたら、調査するインシデントをクリックしてインシデントの概要ページを読み込みます。 *MITRE ATT&CK 手法* などの有用な情報が観察され、*攻撃のタイムラインが* 表示されます。

インシデント ページの上部にあるタブを使用すると、影響を受けるユーザー、メールボックス、エンドポイント、et cetera などの詳細を調べることができます。

[ *証拠と応答]* タブには、調査によって元のアラートに関連するアイテムが表示されます。

証拠と応答内で *保留中のアクション* として表示されるすべての項目は、管理者からの承認を待機しています。  *[すべての証拠*] ビューの修復状態列で並べ替え、エンティティまたはクラスターをクリックしてポップアップ メニューを読み込み、必要に応じてアクションを承認することをお勧めします。

関連する項目をさらに理解する必要がある場合は、インシデント グラフを使用して、関連する証拠とエンティティの視覚的なリンケージを確認できます。 または、基になる調査を確認できます。これにより、セキュリティ イベントに関連するエンティティと項目の多くが表示されます。

## <a name="next-steps"></a>次の手順

AIR が承認する必要があるアクション 項目に重点を置く場合は、 *アクション センター* を使用して、組織内のすべてのインシデントの保留中のアクション アイテムに対して処理を開始できます。  

## <a name="more-information"></a>詳細情報

[Microsoft 365 Defender |でインシデントを管理するMicrosoft Docs](../../defender/manage-incidents.md)

[Microsoft Defender for Office 365での自動調査と対応のしくみ](../automated-investigation-response-office.md)

[Microsoft Defender for Office 365の修復アクション](../air-remediation-actions.md)