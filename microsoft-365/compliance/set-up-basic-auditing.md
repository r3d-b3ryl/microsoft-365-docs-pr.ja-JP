---
title: '[基本監査の設定] Microsoft 365'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: この記事では、組織のユーザーと管理者が実行する監査アクティビティの検索を開始できるよう、基本監査をセットアップする方法について説明します。
ms.openlocfilehash: ff1f973226378e5408dfae1d467394a5a5153196
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314353"
---
# <a name="set-up-basic-auditing-in-microsoft-365"></a>[基本監査の設定] Microsoft 365

ユーザーと管理者Microsoft 365異なるサービスで実行されるアクティビティの監査レコードMicrosoft 365を検索できます。 ほとんどの Microsoft 365 組織と Office 365 組織では、基本監査が既定で有効になっているため、組織内の他のユーザーが監査ログを検索するには、その前に必要な操作はわずかです。

この記事では、基本監査をセットアップするために必要な以下の手順について説明します。

![基本監査を設定する手順](../media/BasicAuditingWorkflow.png)

これらの手順には、監査レコードの生成と保持に必要な適切な組織のサブスクリプションとユーザー ライセンスの確保、および監査ログを検索するためのセキュリティ操作、IT、コンプライアンス、法務チームのチーム メンバーへのアクセス許可の割り当てが含まれます。

詳細については、「基本監査」[を参照Microsoft 365。](auditing-solutions-overview.md#basic-auditing)

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>手順 1: 組織のサブスクリプションとユーザー ライセンスを確認する

基本監査のライセンスには、監査ログ検索ツールへのアクセスを提供する適切な組織のサブスクリプションと、監査レコードの記録と保持に必要なユーザーごとのライセンスが必要です。

ユーザーまたは管理者が監査アクティビティを実行すると、監査レコードが生成され、組織の監査ログに保存されます。 基本監査では、監査レコードは保持され、監査ログで 90 日間検索できます。

基本監査のサブスクリプション要件とライセンス要件の一覧については、「監査ソリューション」を参照[Microsoft 365。](auditing-solutions-overview.md#licensing-requirements)

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>手順 2: 監査ログを検索するためのアクセス許可を割り当てる

監査ログを検索するには、調査チームの管理者とメンバーに、View-Only監査ログまたは監査ログの役割Exchange Online割り当てる必要があります。 既定では、これらの役割は Exchange 管理センターの [**アクセス許可**] ページでコンプライアンス管理役割グループまたは組織管理役割グループに割り当てられています。 組織と組織Office 365 Microsoft 365のグローバル管理者は、組織の組織の管理役割グループのメンバーとして自動的にExchange Online。 最小限の特権レベルで監査ログを検索する権限をユーザーに付与するには、Exchange Online でカスタムの役割グループを作成し、閲覧限定の監査ログまたは監査ログの役割を追加し、この新しい役割グループのメンバーとしてユーザーを追加します。 詳細については、「[Exchange Online で役割グループを管理する](/Exchange/permissions-exo/role-groups)」を参照してください。

次のスクリーンショットは、管理センターの組織の管理役割グループに割り当てられた 2 つの監査Exchange示しています。

![グループ内の役割グループに割り当てられたExchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>手順 3: 監査ログを検索する

これで、コンプライアンス センターで監査ログを検索Microsoft 365準備ができました。

1. 適切な <https://compliance.microsoft.com> 監査アクセス許可が割り当てられているアカウントを使用して、アクセスしてサインインします。

2. コンプライアンス センターの左側のナビゲーション ウィンドウMicrosoft 365、[すべて表示]をクリックし、[監査] を **クリックします**。

3. [監査 **] ページ** で、[検索] タブの次の条件を使用して検索 **を構成** します。 

   ![監査ログ検索の構成設定](../media/AuditLogSearchToolMCCCallouts.png)

   1. **日付と時刻の範囲** です。 日付と時間の範囲を選択し、その期間内に発生したイベントを表示します。 日付と時刻は、ローカル時刻で表示されます。 既定では、最後の 7 日間が選択されています。
  
   2. **アクティビティ**. 検索するアクティビティを選択します。 リストに追加するアクティビティを検索するには、検索ボックスを使用します。 監査されたアクティビティの一部の一覧については、「 [監査されたアクティビティ」を参照してください](search-the-audit-log-in-security-and-compliance.md#audited-activities)。 すべての監査アクティビティのエントリを返す場合は、このボックスを空白のままにします。
  
   3. **ユーザー**。  このボックスをクリックして、検索結果を表示するユーザーの名前を入力します。 このボックスで選択したユーザーが実行した選択したアクティビティの監査ログ エントリが、結果の一覧に表示されます。 組織のすべてのユーザー (およびサービス アカウント) のエントリを返すには、このボックスを空白のままにします。
  
   4. **ファイル、フォルダー、またはサイト**。 指定したキーワードを含むフォルダーのファイルに関連するアクティビティを検索するには、ファイル名またはフォルダー名の一部またはすべてを入力します。 ファイルまたはフォルダーの URL を指定することもできます。 ファイルまたはフォルダーの URL を使用する場合は、完全な URL パスを入力するか、URL の一部を入力する場合は、特殊文字やスペースを含めることはできません。 組織内のすべてのファイルおよびフォルダーのエントリを返すには、このボックスを空白のままにします。

4. [検索 **] を** クリックして検索を実行します。

監査ログの検索が実行されている新しいページが表示されます。 検索が完了すると、監査レコードがページに表示されます。 詳細なプロパティを含むフライアウト ページを表示するには、レコードをクリックします。

詳細な手順については、「コンプライアンス センターで監査 [ログを検索する」を参照してください](search-the-audit-log-in-security-and-compliance.md)。
