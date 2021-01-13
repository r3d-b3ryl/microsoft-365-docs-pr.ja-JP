---
title: Microsoft 365 での法的調査の管理
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: 組織の法的 &調査を管理するには、Office 365 のセキュリティ/コンプライアンス センターの電子情報開示ケースを使用します。
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840706"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Microsoft 365 での法的調査の管理

組織には、組織内の特定の役員または他の従業員が関係する法的事例に対応する多くの理由があります。 これには、電子メール、ドキュメント、インスタント メッセージングの会話、およびユーザーが毎日の作業タスクで使用するその他のコンテンツの場所に関する調査固有の情報をすばやく見つけて保持する必要があります。 セキュリティ/コンプライアンス センターの電子情報開示ケース ツールを使用して、これらのアクティビティや他の多くの同様のアクティビティを実行できます。
  
**Microsoft が電子情報開示調査を管理する方法を知りたい場合** ここでは、同じ検索 [および](https://go.microsoft.com/fwlink/?linkid=852161) 調査ツールを使用して内部の電子情報開示ワークフローを管理する方法について説明した技術ホワイト ペーパーをダウンロードできます。

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>電子情報開示ケースを使用して法的調査を管理する

電子情報開示ケースを使用すると、組織内で電子情報開示ケースを作成、アクセス、および管理できるユーザーを制御できます。 Use cases to add members and control what types of actions they can perform, place a hold on content locations relevant to a legal case, and use the Content Search tool to search the locations on hold for content that might be responsive to your case. その後、外部のレビュー担当者による詳細な調査のために、これらの結果をエクスポートしてダウンロードできます。
  
- [組織が実施する必要](ediscovery-cases.md) があるすべての法的調査に対して電子情報開示ケースを作成して使用して、電子情報開示ワークフローを管理します。

- [電子情報開示のアクセス許可を割り](assign-ediscovery-permissions.md) 当て、組織内で電子情報開示ケースを作成および管理できるユーザーを制御します。

- [コンプライアンスの境界を設定して](set-up-compliance-boundaries.md) 、電子情報開示管理者が検索できるユーザー コンテンツの場所を制御します。

- [組織内のコンテンツ](search-for-content.md) を検索します。

### <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオでスクリプトを使用する

コンテンツ検索シナリオのスクリプトを一覧表示した前のセクションと同様に、電子情報開示ケースの管理に役立つセキュリティ & コンプライアンス センターの PowerShell スクリプトもいくつか作成しました。
  
- [組織内の電子情報開示ケースに](create-a-report-on-holds-in-ediscovery-cases.md) 関連付けられているすべての保留リストに関する情報を含む電子情報開示ホールド レポートを作成します。

- [ユーザーの一覧のメールボックスと OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) の場所を電子情報開示の保留リストに追加します。
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Microsoft 365 の Advanced eDiscovery ソリューションを使用して法的調査を管理する

Microsoft 365 の Advanced eDiscovery ソリューションは、Microsoft 365 の既存の電子情報開示および分析機能Officeされています。 *Advanced eDiscovery* と呼ばれるこの新しいソリューションは、組織の内部および外部の調査に対応するコンテンツを保持、収集、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。 また、法務チームは、法的情報保留通知ワークフロー全体を管理して、ケースに関係する保管担当者と通信できます。

Advanced eDiscovery には、Microsoft 365 または Office 365 組織の E5 サブスクリプションが必要です。 ライセンスの詳細については [、「Advanced eDiscovery のセットアップ」を参照してください](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

Advanced eDiscovery の組み込みワークフローの簡単な概要を次に示します。 詳細については [、「Advanced eDiscovery ワークフローの管理」を参照してください](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

- [開始するケースを](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) 作成します。

- [カストディアンを](managing-custodians.md) ケースに追加し、自分のメールボックス、OneDrive アカウント、およびメンバーである Microsoft Teams のコンテンツを法的情報保留にすることで管理します。

- [法的情報](managing-custodian-communications.md) 保留通知プロセスを自動化して、カストディアンとの通信を管理します。

- [調査のために効果的にデータ](processing-data-for-case.md) を収集できるよう、カストディアン データにインデックスを付け、インデックス作成エラーを修正します。

- [ケースの](collecting-data-for-ediscovery.md) データを収集し、さらに [調査するためにレビュー](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) セットに追加します。

- [レビュー](view-documents-in-review-set.md)セット内の[ドキュメント、クエリ](review-set-search.md)[データ、タグ](tagging-documents.md)アイテムを表示します。

- [高度な分析ツールを](analyzing-data-in-review-set.md) 使用してケース データを分析します。

- [外部の弁護士によるレビュー](exporting-data-ediscover20.md) のためにケース データをエクスポートします。

- Advanced eDiscovery[で長時間実行される](managing-jobs-ediscovery20.md)ジョブを管理します。
