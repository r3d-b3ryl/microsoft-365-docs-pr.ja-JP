---
title: Microsoft 365 で法的調査を管理する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: 組織の法的調査を管理するには、Microsoft 365 コンプライアンス センターの電子情報開示ケースを使用します。
ms.openlocfilehash: fc4e89645ef1912c33ab89ec190c87dc9c8a8965
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189383"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Microsoft 365 で法的調査を管理する

組織には、組織内の特定の役員または他の従業員が関与する法的ケースに対応する多くの理由があります。 これには、電子メール、ドキュメント、インスタント メッセージングの会話、および毎日の作業タスクでユーザーが使用するその他のコンテンツの場所に関する調査固有の情報をすばやく見つけて保持する必要があります。 セキュリティとコンプライアンス センターの電子情報開示ケース ツールを使用して、これらと他の多くの同様のアクティビティを実行できます。
  
**Microsoft が電子情報開示調査を管理する方法を知りたがっていますか?** ここでは、社内の [電子](https://go.microsoft.com/fwlink/?linkid=852161) 情報開示ワークフローを管理するために同じ検索および調査ツールを使用する方法を説明するテクニカル ホワイト ペーパーをダウンロードできます。

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>電子情報開示ケースを使用して法的調査を管理する

電子情報開示ケースを使用すると、組織内で電子情報開示ケースを作成、アクセス、および管理できるユーザーを制御できます。 メンバーを追加し、実行できるアクションの種類を制御し、法的ケースに関連するコンテンツの場所を保留にし、コンテンツ検索ツールを使用して、ケースに対応する可能性のあるコンテンツの保留場所を検索します。 次に、外部レビュー担当者による詳細な調査のために、これらの結果をエクスポートおよびダウンロードできます。
  
- [組織が行う必要がある](./get-started-core-ediscovery.md) すべての法的調査に対して電子情報開示ケースを作成して使用して、電子情報開示ワークフローを管理します。

- [電子情報開示のアクセス許可を割](assign-ediscovery-permissions.md) り当て、組織内で電子情報開示ケースを作成および管理できるユーザーを制御します。

- [コンプライアンスの境界を設定して](set-up-compliance-boundaries.md) 、電子情報開示管理者が検索できるユーザー コンテンツの場所を制御します。

- [組織内のコンテンツ](search-for-content.md) を検索します。

### <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオでスクリプトを使用する

コンテンツ検索シナリオのスクリプトを一覧表示した前のセクションと同様に、電子情報開示ケースの管理に役立つセキュリティ & コンプライアンス センター PowerShell スクリプトも作成しました。
  
- [組織内の電子情報開示ケースに](create-a-report-on-holds-in-ediscovery-cases.md) 関連付けられているすべてのホールドに関する情報を含む電子情報開示ホールド レポートを作成します。

- [電子情報開示ホールドにOneDriveの](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)メールボックスと場所を追加します。
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>ソリューションを使用して法的Advanced eDiscoveryを管理Microsoft 365

このAdvanced eDiscoveryソリューションはMicrosoft 365既存の電子情報開示と分析機能に基Office 365。 *Advanced eDiscovery と* 呼ばれるこの新しいソリューションは、組織の内部および外部調査に対応するコンテンツを保存、収集、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。 また、訴訟チームが法的情報保留通知ワークフロー全体を管理して、ケースに関係するカストディアンとコミュニケーションを取ることができます。

Advanced eDiscovery組織に E5 サブスクリプションがMicrosoft 365必要Office 365です。 ライセンスの詳細については、「Set [up Advanced eDiscovery」 を参照してください](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

次に、ワークフロー内の組み込みワークフローの概要をAdvanced eDiscovery。 詳細については、「Manage [the Advanced eDiscovery ワークフロー」を参照してください](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

- [開始するケースを](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) 作成します。

- [保管担当者を](managing-custodians.md)ケースに追加し、メールボックス、OneDrive アカウント、およびメンバーのコンテンツを法的に保持Microsoft Teams管理します。

- [法的ホールド通知](managing-custodian-communications.md) プロセスを自動化して、保管担当者との通信を管理します。

- [カストディアン データのインデックス](processing-data-for-case.md) を作成し、インデックス作成エラーを修正して、調査のデータを効果的に収集できます。

- [ケースの](collecting-data-for-ediscovery.md) データを収集し、レビュー [セットに](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) 追加して詳細な調査を行います。

- [レビュー](view-documents-in-review-set.md) セット内の [ドキュメント、クエリ](review-set-search.md) データ、 [タグ](tagging-documents.md) アイテムを表示します。

- [高度な分析ツールを](analyzing-data-in-review-set.md) 使用してケース データを分析します。

- [外部弁護士によるレビュー](exporting-data-ediscover20.md) 用のケース データをエクスポートします。

- [サーバーで長時間実行されている](managing-jobs-ediscovery20.md)ジョブをAdvanced eDiscovery。