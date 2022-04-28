---
title: Microsoft 365 で法的調査を管理する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: Microsoft Purview コンプライアンス ポータルで電子情報開示ケースを使用して、組織の法的調査を管理します。
ms.openlocfilehash: 464996eb160eff520582e82ab87b74b4472f7a5d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077877"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Microsoft 365 で法的調査を管理する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

組織には、組織内の特定の幹部や他の従業員が関与する訴訟に対応する多くの理由があります。 これには、電子メール、ドキュメント、インスタント メッセージングの会話、および日常の作業タスクでユーザーが使用するその他のコンテンツの場所で、調査固有の詳細情報をすばやく見つけて保持することが含まれる場合があります。 セキュリティとコンプライアンス センターの電子情報開示ケース ツールを使用して、これらおよび他の多くの同様のアクティビティを実行できます。
  
**Microsoft が電子情報開示の調査を管理する方法を知りたいですか?** 同じ検索ツールと調査ツールを使用して内部電子情報開示ワークフローを管理する方法について説明した [、ダウンロードできる技術ホワイト ペーパー](https://go.microsoft.com/fwlink/?linkid=852161) を次に示します。

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>電子情報開示ケースを使用して法的調査を管理する

電子情報開示ケースを使用すると、組織内で電子情報開示ケースを作成、アクセス、管理できるユーザーを制御できます。 ユース ケースを使用して、メンバーを追加し、実行できるアクションの種類を制御し、訴訟に関連するコンテンツの場所を保留し、コンテンツ検索ツールを使用して、ケースに対応する可能性があるコンテンツを保留の場所で検索します。 その後、外部レビュー担当者による詳細な調査のために、これらの結果をエクスポートしてダウンロードすることもできます。
  
- 組織が行う必要があるすべての法的調査に対して電子情報開示ケースを作成して使用することで、電子情報開示[ワークフローを管理](./get-started-core-ediscovery.md)します。

- [電子情報開示のアクセス許可を割り当てて](assign-ediscovery-permissions.md) 、組織内の電子情報開示ケースを作成および管理できるユーザーを制御します。

- [コンプライアンス境界を設定して、](set-up-compliance-boundaries.md) 電子情報開示マネージャーが検索できるユーザー コンテンツの場所を制御します。

- 組織内[のコンテンツを検索](search-for-content.md)します。

### <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオにスクリプトを使用する

コンテンツ検索シナリオのスクリプトを示した前のセクションと同様に、電子情報開示ケースの管理に役立つセキュリティ & コンプライアンス センター PowerShell スクリプトも作成しました。
  
- 組織内[の電子情報開示](create-a-report-on-holds-in-ediscovery-cases.md)ケースに関連付けられているすべての保留に関する情報を含む電子情報開示保留レポートを作成します。

- ユーザーの一覧[のメールボックスとOneDriveの場所](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)を電子情報開示ホールドに追加します。
  
## <a name="manage-legal-investigations-with-the-ediscovery-premium-solution-in-microsoft-365"></a>Microsoft 365の電子情報開示 (プレミアム) ソリューションを使用して法的調査を管理する

Microsoft 365の Microsoft Purview 電子情報開示 (プレミアム) ソリューションは、Office 365の既存の電子情報開示と分析機能に基づいています。 *電子情報開示 (プレミアム)* と呼ばれるこの新しいソリューションは、組織の内部および外部の調査に対応するコンテンツを保持、収集、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。 また、訴訟チームが法的情報保留通知ワークフロー全体を管理して、ケースに関係するカストディアンとコミュニケーションを取ることができます。

電子情報開示 (プレミアム) には、Microsoft 365またはOffice 365組織の E5 サブスクリプションが必要です。 ライセンスの詳細については、「[電子情報開示のセットアップ (プレミアム)](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)」を参照してください。

電子情報開示 (プレミアム) の組み込みワークフローの概要を次に示します。 詳細については、「[電子情報開示 (プレミアム) ワークフローの管理](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)」を参照してください。

- 開始[するケースを作成](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case)します。

- [カストディアンをケース](managing-custodians.md)に追加し、メールボックス、OneDrive アカウント、およびメンバーであるMicrosoft Teamsのコンテンツに法的ホールドを配置して管理します。

- 訴訟ホールド通知プロセスを自動化して、カストディアンとの[通信を管理](managing-custodian-communications.md)します。

- [インデックス保管担当者データ](processing-data-for-case.md) を作成し、インデックス作成エラーを修正して、調査用のデータを効果的に収集できるようにします。

- ケースの[データを収集](collecting-data-for-ediscovery.md)し、さらに調査するために[レビュー セットに追加](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set)します。

- レビュー セット内のドキュメント、[クエリ](review-set-search.md) データ、[およびタグ](tagging-documents.md)アイテムを[表示](view-documents-in-review-set.md)します。

- 高度な分析ツールを使用して[ケース データ](analyzing-data-in-review-set.md)を分析します。

- 外部の相談者によるレビュー用の[ケース データをエクスポート](exporting-data-ediscover20.md)します。

- 電子情報開示 (プレミアム) で[実行時間の長いジョブを管理](managing-jobs-ediscovery20.md)します。