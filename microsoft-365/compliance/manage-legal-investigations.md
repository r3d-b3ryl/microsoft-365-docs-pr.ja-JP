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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Microsoft 365 コンプライアンスセンターの電子情報開示ケースを使用して、組織の法的調査を管理します。 E5 サブスクリプションを持っている場合は、高度な電子情報開示のテキスト分析、machine learning、および予測コーディング機能を使用して、ケースデータをさらに分析できます。
ms.openlocfilehash: 0db2187259c0c828c492f56698963bf9f61c9c18
ms.sourcegitcommit: 825037f166eea3ba70f8980cedc5492f90c1cc56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "43097200"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Microsoft 365 で法的調査を管理する

組織には、組織内の特定の役員または他の従業員に関連する訴訟に対応する理由が多数あります。 これにより、電子メール、ドキュメント、インスタントメッセージの会話、ユーザーが毎日の作業タスクで使用したその他のコンテンツの場所について、調査に関する詳細情報をすばやく見つけて保持することができます。 セキュリティ/コンプライアンスセンターの電子情報開示ケースツールを使用すると、このような他の多くの操作を実行できます。
  
**Microsoft が電子情報開示の調査を管理する方法を知りたいですか。** 同じ Office 365 検索ツールと調査ツールを使用して内部電子情報開示ワークフローを管理する方法について説明する[テクニカルホワイトペーパー](https://go.microsoft.com/fwlink/?linkid=852161)をダウンロードすることができます。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>電子情報開示ケースを使用して法的調査を管理する

電子情報開示ケースを使用すると、組織内で電子情報開示ケースを作成、アクセス、および管理できるユーザーを制御できます。 ケースを使用して、メンバーを追加したり、実行できるアクションの種類を制御したり、法的訴訟に関連するコンテンツの場所を保持したり、コンテンツ検索ツールを使用して、ケースに応答する可能性があるコンテンツを保持している場所を検索したりすることができます。 さらに、外部のレビューアーによる詳細な調査のために、それらの結果をエクスポートしてダウンロードすることもできます。
  
- 組織が行う必要のあるすべての法的調査に対して電子情報開示のケースを作成して使用することによって[、電子情報開示ワークフローを管理](ediscovery-cases.md)する 
    
- [電子情報開示のアクセス許可を割り当て](assign-ediscovery-permissions.md)て、組織内で電子情報開示ケースを作成および管理できるユーザーを制御します。 
    
- [コンプライアンスの境界を設定](tagging-and-assessment-in-advanced-ediscovery.md)して、電子情報開示マネージャーが検索できるユーザーコンテンツの場所を制御する 
    
- 組織内の[コンテンツを検索する](search-for-content.md) 
    
### <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオでスクリプトを使用する

コンテンツ検索シナリオのスクリプトが記載されている前のセクションと同様に、電子情報開示ケースの管理に役立つセキュリティ & コンプライアンスセンターの PowerShell スクリプトも作成しました。
  
- 組織内の電子情報開示ケースに関連付けられたすべての保留リストに関する情報を含む[電子情報開示保持レポートを作成し](create-a-report-on-holds-in-ediscovery-cases.md)ます。 
    
- 電子情報開示ホールドにユーザーのリストの[メールボックスと OneDrive の場所を追加](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)する 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Microsoft 365 の高度な電子情報開示ソリューションを使用して法的調査を管理する

Microsoft 365 の高度な電子情報開示ソリューションは、Office 365 の既存の電子情報開示および分析機能に基づいて構築されています。 *Advanced eDiscovery*と呼ばれるこの新しいソリューションは、組織の内部および外部の調査に応答するコンテンツを保持、収集、確認、分析、およびエクスポートするためのエンドツーエンドのワークフローを提供します。 また、法務部門は法的情報保留通知ワークフロー全体を管理して、ケースに関与する保管担当者と通信することもできます。

高度な電子情報開示では、Microsoft 365 または Office 365 組織の E5 サブスクリプションが必要です。 ライセンスの詳細については、「 [Advanced eDiscovery の概要](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)」を参照してください。

高度な電子情報開示における組み込みワークフローの概要を次に示します。 詳細については、「 [Advanced eDiscovery ワークフローを調査する](get-started-with-advanced-ediscovery.md#explore-the-advanced-ediscovery-workflow)」を参照してください。

- [ケースを作成](create-new-ediscovery-case.md)して開始する

- [保管担当者を管理](managing-custodians.md)するには、それらをケースに追加し、自分のメールボックス、OneDrive アカウント、およびそれらのメンバーである Microsoft Teams のコンテンツに法的情報を含めることによって行います。

- 法的情報保留通知プロセスを自動化して保管担当者との[通信を管理](managing-custodian-communications.md)する

- [保管担当者データをインデックス](processing-data-for-case.md)化し、インデックス作成エラーを修正して、調査のためにデータを効果的に収集できるようにする

- ケースの[データを収集](collecting-data-for-ediscovery.md)して、さらに調査するために[レビューセットに追加する](collecting-data-for-ediscovery.md#adding-search-results-to-a-review-set)

- 校閲セット内のドキュメント、[クエリ](review-set-search.md)データ、および[タグ](tagging-documents.md)アイテムを[表示](view-documents-in-review-set.md)する

- 高度な分析ツールを使用して[ケースデータを分析](analyzing-data-in-review-set.md)する

- 外部の弁護士によるレビューの[ケースデータのエクスポート](exporting-data-ediscover20.md)

- 高度な電子情報開示で[長時間実行されているジョブを管理](managing-jobs-ediscovery20.md)する
