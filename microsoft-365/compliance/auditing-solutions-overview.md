---
title: Microsoft Purview 監査ソリューション
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365 組織内のユーザーや管理者のアクティビティを監査する方法をご紹介します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ceaea2b888c144fb5c6bc34d9d7788ab595b56b
ms.sourcegitcommit: 5fe7f2954a89406245416fc1a218cf4bf19abb85
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65864586"
---
# <a name="auditing-solutions-in-microsoft-purview"></a>Microsoft Purview での監査ソリューション

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview 監査ソリューションは、セキュリティ イベント、フォレンジック調査、内部調査、コンプライアンス義務に組織が効果的に対応するための統合ソリューションが用意されています。 何十もの Microsoft 365 サービスやソリューションで実行された何千ものユーザーや管理者の操作は、組織の統一された監査ログにキャプチャされ、記録されて保持されます。 これらのイベントの監査記録は、組織内のセキュリティ オペレーション、IT 管理者、インサイダー リスク チーム、コンプライアンスや法務調査担当者が検索できます。 この機能により、Microsoft 365 の組織全体で行われているアクティビティを可視化することができます。

## <a name="microsoft-purview-auditing-solutions"></a>Microsoft Purview 監査ソリューション

Microsoft Purview では、監査 (標準) と監査 (プレミアム) の 2 つの監査ソリューションが用意されています。

![監査 (標準) および監査 (プレミアム) の主な機能。](..\media\AuditingSolutionsComparison.png)

### <a name="audit-standard"></a>監査 (標準)

Microsoft Purview 監査 (標準) では、監査されたアクティビティのログや検索を行い、フォレンジック調査、IT 調査、コンプライアンス調査、法務調査などに役立てることができます。

- **既定で有効**。 監査 (標準) は、適切なサブスクリプションを持つすべての組織で既定でオンになります。 つまり、監査されたアクティビティの記録がキャプチャされ、検索可能になるということです。 必要な設定は、監査ログ検索ツール (および対応するコマンドレット) にアクセスするために必要なアクセス許可を割り当て、ユーザーに Microsoft Purview 監査 (プレミアム) 機能の正しいライセンスが割り当てられていることを確認することだけです。
- **検索可能な数千件の監査イベント**。 組織内のほとんどの Microsoft 365 のサービスで発生する、幅広く監査されるアクティビティを検索することができます。 検索可能なアクティビティの一部のリストについては、「[監査されるアクティビティ](search-the-audit-log-in-security-and-compliance.md#audited-activities)」を参照してください。 監査活動をサポートするサービスや機能のリストについては、「[監査ログ記録タイプ](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)」を参照してください。
- **Microsoft Purview コンプライアンス ポータルの監査検索ツール**。 コンプライアンス ポータルで監査ログ検索ツールを使用して監査記録を検索します。 特定のアクティビティ、特定のユーザーが行ったアクティビティ、日付の範囲内で発生したアクティビティを検索できます。 こちらは、コンプライアンス センターの監査検索ツールのスクリーンショットです。

   ![コンプライアンス ポータルの監査ログ検索ツール。](../media/AuditLogSearchToolMCC.png)

- **Search-UnifiedAuditLog cmdlet**。Exchange Online PowerShell の **Search-UnifiedAuditLog** コマンドレット (検索ツールの基礎となるコマンドレット) を使用して、監査イベントを検索したり、スクリプトで使用したりすることができます。詳しくは以下を参照してください:

  - [Search-UnifiedAuditLog コマンドレットのリファレンス](/powershell/module/exchange/search-unifiedauditlog)
  - [PowerShell スクリプトを使用して監査ログを検索する](audit-log-search-script.md)

- **監査記録を CSV ファイルにエクスポートします**。 コンプライアンス ポータルで監査ログ検索ツールを実行した後、検索で返された監査記録を CSV ファイルにエクスポートすることができます。 これにより、Microsoft Excel を使用して、異なる監査レコードのプロパティで並べ替えやフィルター処理を行うことができます。 また、Excel Power Query の変換機能を使って、AuditData JSON オブジェクトの各プロパティを個別の列に分割することもできます。 これにより、異なるイベントの類似データを効果的に表示し、比較することができます。 詳細については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。

- **Office 365 マネージメント アクティビティ API を介した監査ログにアクセスします**。 監査記録にアクセスして取得する 3 つ目の方法は、Office 365 マネージメント アクティビティ API を使用することです。 これにより、企業は監査データを既定の 90 日よりも長い期間保持し、監査データを SIEM ソリューションにインポートすることができます。 詳細については、「[Office 365 管理アクティビティ API のリファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)」を参照してください。

- **90 日間の監査ログの保持**。 監査されたアクティビティがユーザーや管理者によって実行されると、監査記録が生成され、組織の監査ログに保存されます。 監査 (標準) では、記録は 90 日間保持されるため、過去 3 か月以内に発生したアクティビティを検索することができます。

### <a name="audit-premium"></a>監査 (プレミアム)

監査 (プレミアム) は、監査 (標準) の機能をベースに、監査ログの保持ポリシー、監査記録の長期保持、価値の高い重要なイベント、Office 365 マネージメント アクティビティ API への高い帯域幅でのアクセスが用意されています。

- **監査ログの保持ポリシー**。 カスタマイズした監査ログの保持ポリシーを作成すれば、最大 1 年間 (必要なアドオン ライセンスを持つユーザーは最大 10 年間)、長期にわたって監査レコードを保持できます。 監査されたアクティビティが発生するサービス、特定の監査されたアクティビティ、または監査されたアクティビティを実行するユーザーに基づいて、監査記録を保持するポリシーを作成することができます。

- **監査記録の長期保持**。 Exchange、SharePoint、および Azure Active Directory の監査レコードは、既定で 1 年間保持されます。 その他のアクティビティの監査記録は、既定では 90 日間保持されますが、監査ログの保持ポリシーを使用して、より長い保持期間を構成することができます。

- **価値が高く、重要な監査 (プレミアム) イベント**。重要なイベントの監査レコードは、メール アイテムにアクセスしたとき、メールア イテムに返信して転送したとき、ユーザーが Exchange Online と SharePoint Online でいつ何を検索したかなどのイベントを可視化することで、組織がフォレンジックおよびコンプライアンスの調査を実施するのに役立ちます。これらの重大なイベントは、考えられる侵害を調査し、侵害の範囲を特定するのに役立ちます。

- **Office 365 管理アクティビティ API への高帯域幅**。 監査 (プレミアム) は、組織が Office 365 マネージメント アクティビティ API を通じて監査ログにアクセスするための帯域幅を増やします。 すべての組織 (監査 (標準) または監査 (プレミアム) を使用している組織) には、最初に 1 分あたり 2,000 リクエストの基準値が割り当てられますが、この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。 この結果、監査 (プレミアム) を導入した組織は、監査 (標準) を導入した組織の約 2 倍の帯域幅を得ることができます。

監査 (プレミアム) 機能の詳細については、「[Microsoft 365 の監査 (プレミアム)](advanced-audit.md)」を参照してください。

## <a name="comparison-of-key-capabilities"></a>主要機能の比較

次の表は、監査 (標準) と監査 (プレミアム) で使用できる主な機能を比較したものです。 すべての監査 (標準) 機能は、監査 (プレミアム) に含まれています。

|機能|監査 (標準)|監査 (プレミアム)|
|:------|:-------------|:-------------|
|既定で有効|![サポートされています。](../media/check-mark.png)|![サポートされています。](../media/check-mark.png)|
|検索可能な数千件の監査イベント|![サポートされています。](../media/check-mark.png)|![サポートされています。](../media/check-mark.png)|
|コンプライアンス ポータルの監査検索ツール。|![サポートされています。](../media/check-mark.png)|![サポートされています。](../media/check-mark.png)|
|Search-UnifiedAuditLog コマンドレット|![サポートされています。](../media/check-mark.png)|![サポートされています。](../media/check-mark.png)|
|監査記録を CSV ファイルにエクスポートします|![サポートされています。](../media/check-mark.png)|![サポートされています。](../media/check-mark.png)|
|Office 365 マネージメント アクティビティ API <sup>1</sup> を介した監査ログにアクセスする|![サポート対象です。](../media/check-mark.png)|![サポート対象です。](../media/check-mark.png)</sup>|
|90 日間の監査ログの保持|![サポートされています。](../media/check-mark.png)|![サポートされています。](../media/check-mark.png)|
|1 年間の監査ログの保持||![サポート対象です。](../media/check-mark.png)|
|10 年間の監査ログの保持 <sup>2</sup>||![サポート](../media/check-mark.png)|
|監査ログの保持ポリシー||![サポート](../media/check-mark.png)|
|価値の高い、重要なイベント||![サポート](../media/check-mark.png)|

> [!NOTE]
> <sup>1</sup> 監査 (プレミアム) には、Office 365 マネージメント アクティビティ API へのより高い帯域幅のアクセスが含まれており、監査データへのアクセスが高速化されます。<br/><sup>2</sup> 監査 (プレミアム) に必要なライセンス (次のセクションで説明) に加えて、監査記録を 10 年間保持するためには、ユーザーはライセンスに 10 年監査ログ保持を割り当てる必要があります。

## <a name="licensing-requirements"></a>ライセンスの要件

以下のセクションでは、監査 (標準) と監査 (プレミアム) のライセンス要件を特定します。 監査 (標準) 機能は、監査 (プレミアム) に付属しています。

### <a name="audit-standard"></a>監査 (標準)

- Microsoft 365 Business Basic サブスクリプション
- Microsoft Business Standard サブスクリプション
- Microsoft 365 Apps for Business サブスクリプション
- Microsoft 365 Enterprise E3 サブスクリプション
- Microsoft 365 Business Premium
- Microsoft 365 Education A3 サブスクリプション
- Microsoft 365 Government G3 サブスクリプション
- Microsoft 365 Government G1 サブスクリプション
- Microsoft 365 Frontline F1 または F3 サブスクリプション、または F5 セキュリティ アドオン
- Office 365 Enterprise E3 サブスクリプション
- Office 365 Enterprise E1 サブスクリプション
- Office 365 Education A1 サブスクリプション
- Office 365 Education A3 サブスクリプション

### <a name="audit-premium"></a>監査 (プレミアム)

- Microsoft 365 Enterprise E5 サブスクリプション
- Microsoft 365 E5 コンプライアンス アドオンが含まれている Microsoft 365 Enterprise E3 サブスクリプション
- Microsoft 365 E5 電子情報開示および監査アドオンが含まれている Microsoft 365 Enterprise E3 サブスクリプション
- Microsoft 365 Education A5 サブスクリプション
- Microsoft 365 A5 コンプライアンス アドオンが含まれている Microsoft 365 Education A3 サブスクリプション
- Microsoft 365 A5 電子情報開示および監査アドオンが含まれている Microsoft 365 Education A3 サブスクリプション
- Microsoft 365 Government G5 サブスクリプション
- Microsoft 365 G5 コンプライアンス アドオンが含まれている Microsoft 365 Government G3 サブスクリプション
- Microsoft 365 G5 電子情報開示および監査アドオンが含まれている Microsoft 365 Government G3 サブスクリプション
- Microsoft 365 Frontline F5 コンプライアンス、または F5 セキュリティおよびコンプライアンス アドオン
- Office 365 Enterprise E5 サブスクリプション
- Office 365 Education A5 サブスクリプション

## <a name="set-up-microsoft-purview-auditing-solutions"></a>Microsoft Purview 監査ソリューションの設定

Microsoft Purview の監査ソリューションの使用を開始するには、以下のセットアップ ガイダンスを参照してください。

### <a name="set-up-audit-standard"></a>監査の設定 (標準)

最初の手順は、監査 (標準) を設定し、監査ログ検索を開始します。

![監査 (標準) を設定するためのワークフロー。](../media/BasicAuditingWorkflow.png)

1. 監査 (標準) をサポートするサブスクリプションと、必要に応じて監査 (プレミアム) をサポートするサブスクリプションが組織にあることを確認します。

2. コンプライアンス ポータルの監査ログ検索ツールまたは **Search-UnifiedAuditLog** コマンドレットを使用する組織内のユーザーに、Exchange Online でアクセス許可を割り当てます。 具体的には、ユーザーは Exchange Online で閲覧限定の監査ログまたは監査ログの役割が割り当てられている必要があります。

3. 監査ログを検索します。手順 1 と手順 2 が完了したら、組織内のユーザーは監査ログ検索ツール (または対応するコマンドレット) を使用して、監査されたアクティビティを検索することができます。

詳しい説明は、「[監査 (標準) の設定](set-up-basic-audit.md)」をご覧ください。

### <a name="set-up-audit-premium"></a>監査の設定 (プレミアム)

監査 (プレミアム) をサポートするサブスクリプションがある場合は、以下の手順で監査 (プレミアム) の追加機能を設定し、使用することができます。

![監査 (プレミアム) を設定するためのワークフロー。](../media/AdvancedAuditWorkflow.png)

1. ユーザーの監査 (プレミアム) を設定します。 この手順は、次のタスクで構成されています。

   - ユーザーに監査 (プレミアム) の適切なライセンスまたはアドオン ライセンスが割り当てられていることを確認します。
  
   - それらのユーザーに対して監査 (プレミアム) アプリ/サービス プランを有効にします。
  
   - 重要なイベントの監査を有効にして、そのユーザーに高度な監査 (Premium) アプリやサービス プランをオンにします。

2. ユーザーが Exchange Online や SharePoint Online で検索を行った場合に、監査 (プレミアム) イベントをログに記録することができます。

3. 監査ログの保持ポリシーを設定します。Exchange、SharePoint、および Azure AD の監査記録を 1 年間保持する既定のポリシーに加えて、組織のセキュリティ運用チーム、IT チーム、およびコンプライアンス チームの要件に合わせて、監査ログの保持ポリシーを追加で作成することができます。

4. フォレンジック調査を行う場合の、重要な監査 (プレミアム) イベントやその他のアクティビティの検索。手順 1 と手順 2 が完了したら、侵害されたアカウントのフォレンジック調査や、その他の種類のセキュリティ調査やコンプライアンス調査を行う場合に、監査 (プレミアム) イベントやその他のアクティビティの監査ログを検索することができます。

詳しい説明は、「[監査 (プレミアム) の設定](set-up-advanced-audit.md)」をご覧ください。

<!--
## Encrypt audit records using Customer Key

You can enable Customer Key encryption for audit records. Auditing builds on the [Service encryption with Customer Key](customer-key-overview.md) to encrypt sensitive information in your organization's auditing data. Implementing Customer Key provides extra protection by preventing unauthorized systems or Microsoft data center personnel from viewing your auditing data in the auditing pipeline and at rest. Using Customer Key to encrypt your auditing data also helps you meet regulatory or compliance obligations because your organization provides and controls the encryption keys.

To implement Customer Key for auditing, you have to create a multi-workload Data Encryption Policy (DEP), which defines the encryption hierarchy. For detailed step-by-step instructions, see [Set up Customer Key](customer-key-set-up.md).

> [!NOTE]
> Not all audit records in your organization are encrypted. The Microsoft Purview service that generates specific audit records for activity in that service defines whether the audit record is encrypted or not.
-->

## <a name="training"></a>トレーニング

セキュリティ運用チーム、IT 管理者、コンプライアンス調査チームに監査 (標準) と監査 (プレミアム) の基礎についてトレーニングを行うことで、組織がより迅速に監査を利用して調査に役立てることができます。 Microsoft Purview は、組織内のこれらのユーザーが監査を始めるのに役立つ以下のリソースを提供します: [Microsoft Purview の電子情報開示と監査機能を説明する](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365)。
