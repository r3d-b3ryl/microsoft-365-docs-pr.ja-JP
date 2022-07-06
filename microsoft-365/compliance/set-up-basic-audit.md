---
title: Microsoft 365 で監査 (Standard) を設定する
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
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MOE150
- MET150
description: この記事では、組織内のユーザーと管理者が実行する監査アクティビティの検索を開始できるように、監査 (Standard) を設定する方法について説明します。
ms.openlocfilehash: 17f9e24f4c3159186011d3faefbd8796f51cc5ce
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632203"
---
# <a name="set-up-microsoft-purview-audit-standard"></a>Microsoft Purview 監査を設定する (Standard)

Microsoft 365 のMicrosoft Purview 監査 (Standard) を使用すると、ユーザーと管理者がさまざまな Microsoft 365 サービスで実行されたアクティビティの監査レコードを検索できます。 監査 (Standard) は、ほとんどの Microsoft 365 およびOffice 365組織で既定で有効になっているため、自分や組織内の他のユーザーが監査ログを検索する前に行う必要があるのはごくわずかです。

この記事では、監査 (Standard) を設定するために必要な次の手順について説明します。

![監査 (Standard) を設定する手順。](../media/BasicAuditingWorkflow.png)

これらの手順には、監査レコードの生成と保持に必要な適切な組織のサブスクリプションとユーザー ライセンスの確保と、監査ログを検索できるようにセキュリティ運用、IT、コンプライアンス、および法務チームのチーム メンバーにアクセス許可を割り当てることが含まれます。

詳細については、 [Microsoft 365 の監査 (Standard) に関するページを](auditing-solutions-overview.md#audit-standard)参照してください。

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>手順 1: 組織のサブスクリプションとユーザー ライセンスを確認する

監査 (Standard) のライセンスには、監査ログ検索ツールへのアクセスを提供する適切な組織サブスクリプションと、監査レコードのログ記録と保持に必要なユーザーごとのライセンスが必要です。

監査されたアクティビティがユーザーや管理者によって実行されると、監査記録が生成され、組織の監査ログに保存されます。 監査 (Standard) では、監査レコードは 90 日間監査ログに保持され、検索可能です。

監査 (Standard) のサブスクリプションとライセンス要件の一覧については、 [Microsoft 365 の監査ソリューションに関するページを](auditing-solutions-overview.md#licensing-requirements)参照してください。

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>手順 2: 監査ログを検索するためのアクセス許可を割り当てる

監査ログを検索するには、調査チームの管理者とメンバーにView-Only監査ログまたは監査ログ ロールをExchange Onlineに割り当てる必要があります。 既定では、これらの役割は <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>の [**アクセス許可**] ページでコンプライアンス管理役割グループまたは組織管理役割グループに割り当てられています。 Office 365 および Microsoft 365 のグローバル管理者は自動的に、組織管理役割グループのメンバーとして Exchange Online に追加されます。 最小限の特権レベルで監査ログを検索する権限をユーザーに付与するには、Exchange Online でカスタムの役割グループを作成し、閲覧限定の監査ログまたは監査ログの役割を追加し、この新しい役割グループのメンバーとしてユーザーを追加します。 詳細については、「[Exchange Online で役割グループを管理する](/Exchange/permissions-exo/role-groups)」を参照してください。

次のスクリーンショットは、Exchange 管理センターの組織管理役割グループに割り当てられた 2 つの監査関連のロールを示しています。

![Exchange Onlineの役割グループに割り当てられているロールを監査します。](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>手順 3: 監査ログを検索する

これで、Microsoft Purview コンプライアンス ポータルで監査ログを検索する準備ができました。

1. <https://compliance.microsoft.com>適切な監査アクセス許可が割り当てられているアカウントに移動してサインインします。

2. コンプライアンス ポータルの左側のナビゲーション ウィンドウで、[ **すべて表示** ] をクリックし、[ **監査**] をクリックします。

3. [ **監査** ] ページの [検索] タブで、次の条件を使用して **検索** を構成します。 

   ![監査ログ検索の構成設定。](../media/AuditLogSearchToolMCCCallouts.png)

   1. **日付と時刻の範囲**。 日付と時間の範囲を選択し、その期間内に発生したイベントを表示します。 日付と時刻は、ローカル時刻で表示されます。 既定では、過去 7 日間が選択されます。
  
   2. **アクティビティ**。 検索するアクティビティを選択します。 検索ボックスを使用して、リストに追加するアクティビティを検索します。 監査されたアクティビティの一部については、「 [監査された](search-the-audit-log-in-security-and-compliance.md#audited-activities)アクティビティ」を参照してください。 監査されたすべてのアクティビティのエントリを返すには、このボックスを空白のままにします。
  
   3. **ユーザー**。  このボックスをクリックし、検索結果を表示するユーザーの名前の入力を開始します。 このボックスで選択したユーザーによって実行された選択したアクティビティの監査ログ エントリが、結果の一覧に表示されます。 組織のすべてのユーザー (およびサービス アカウント) のエントリを返すには、このボックスを空白のままにします。
  
   4. **ファイル、フォルダー、またはサイト**。 指定したキーワードを含むフォルダーのファイルに関連するアクティビティを検索するには、ファイル名またはフォルダー名の一部またはすべてを入力します。 ファイルまたはフォルダーの URL を指定することもできます。 ファイルまたはフォルダーの URL を使用する場合は、完全な URL パスを入力するか、URL の一部を入力する場合は、特殊文字やスペースを含めないでください。 組織内のすべてのファイルおよびフォルダーのエントリを返すには、このボックスを空白のままにします。

4. [ **検索** ] をクリックして検索を実行します。

監査ログ検索が実行されていることを示す新しいページが表示されます。 検索が完了すると、監査レコードがページに表示されます。 レコードをクリックすると、詳細なプロパティを含むポップアップ ページが表示されます。

詳細な手順については、「 [コンプライアンス センターで監査ログを検索する」を参照してください](search-the-audit-log-in-security-and-compliance.md)。
