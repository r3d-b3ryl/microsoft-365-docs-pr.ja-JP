---
title: GDPR に関するアカウンタビリティ対応準備チェックリスト
description: この記事では、Microsoft の製品とサービスを使用するときに GDPR をサポートするために必要な情報にアクセスできるよう、アカウンタビリティ対応準備チェックリストについて説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214812"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>アカウンタビリティ対応準備チェックリストを使用して GDPR プログラムをサポートする

一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。 詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。

## <a name="accountability-readiness-checklists"></a>アカウンタビリティ対応準備チェックリスト

Microsoft の製品とサービスを使用するときに GDPR をサポートするために必要な情報に簡単にアクセスできるよう、アカウンタビリティ対応準備チェックリストを提供します。 チェックリストには GDPR に基づく潜在的な義務が記載されており、組織のコンプライアンスをサポートするために使用できる情報を示しています。

4 つの Microsoft 製品とサービス ファミリに関する詳しいガイドが用意されています:

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Microsoft サポート/プロフェッショナル サービス](gdpr-arc-prof-services.md)

[コンプライアンス マネージャー](compliance-manager.md)で、GDPR タイル内の顧客管理コントロールの下にあるコントロール ID とコントロール タイトルを参照することによって、このチェックリストの項目を管理できます。

チェックリストには、GDPR をサポートするプライバシー プログラムに関する以下の 4 つのカテゴリの基本的な考慮事項と、要件の例が含まれています。

1. データの収集と処理の条件:

    - いつ同意を得ましたか?  
    - 目的を特定して文書化する  
    - プライバシー影響評価

2. データ主体の権利  

    - PII プリンシパル (データ主体) に関する情報の判別  
    - 同意を修正または撤回するメカニズムの提供

3. 意図的な既定のプライバシー  

    - 収集の制限  
    - 識別レベルへの準拠  
    - 一時ファイル

4. データ保護とセキュリティ  

    - 組織とそのコンテキストについての理解  
    - 計画  
    - 情報セキュリティ ポリシー

## <a name="customer-agreements"></a>顧客契約

- **オンライン サービス使用条件**: GDPR に関する Microsoft の契約責任は、「[オンライン サービス使用条件](https://go.microsoft.com/fwlink/p/?linkid=2052208)」に記載されています。
- **Microsoft 製品使用条件**: Microsoft では、ボリューム ライセンスのすべてのお客様に [GDPR 使用条件の責任](https://go.microsoft.com/fwlink/p/?linkid=2052213)を拡張しています。
- **Data Protection Addendum**: Microsoft サービスは、Microsoft コンサルティング サービスのお客様やその他のお客様にまで[責任を拡張](https://go.microsoft.com/fwlink/p/?linkid=2052215)しています。

## <a name="gdpr-compliance-controls"></a>GDPR コンプライアンスのコントロール

- **コンプライアンス マネージャーの使用**: [コンプライアンス マネージャー](compliance-manager.md)を使用して、Microsoft が GDPR の義務をサポートするために使用しているコントロールをレビューし、組み込みます。
- **GDPR コントロールのマッピング**: GDPR の義務に対する Microsoft コントロールの[総合的なマッピング](https://go.microsoft.com/fwlink/p/?linkid=2052220)にアクセスします。

## <a name="records-of-processing-for-processors"></a>プロセッサの処理のレコード

Microsoft がプロセッサとしてコントローラーの顧客に提供しているオンライン サービスの規模と幅の広さから、Microsoft では、顧客が処理のレコードを探しているサービスを特定し、Microsoft が提供するオンライン ツールで関連するログを取得することを期待しています。 一例としては、Azure の処理のレコードで、どういった種類の処理アクティビティのレコードを求めているかを特定するよう顧客は求められます。

### <a name="azure-logs"></a>Azure ログ

一般的に顧客はアクティビティ ログに、そして潜在的には診断ログに興味を持つでしょう。

- **アクティビティ ログ**: [アクティビティ ログ](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)は、サブスクリプション内のリソースで実行された操作に関する分析情報を提供します。 アクティビティ ログは、操作の開始者、発生時刻、状態の特定に役立ちます。
- **診断ログ**: [診断ログ](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)は、あらゆるリソースによって生成されたログのすべてです。 これらのログには、Windows イベント システム ログ、Azure Storage のログ、Key Vault の監査ログ、Application Gateway のアクセスとファイアウォールのログが含まれています。
- **ログ アーカイブ**: すべての診断ログは、一元化され、暗号化された Azure ストレージ アカウントにアーカイブ用として書き込まれます。 組織固有の保持要件を満たすために、最大で 730 日まで保持期間のユーザーによる構成が可能です。 これらのログは、処理、保存、ダッシュボード レポートの作成のために Azure Monitor のログに接続します。

### <a name="other-logs"></a>その他のログ

さらに、このアーキテクチャの一部として、次の監視ソリューションがインストールされています。 FedRAMP のセキュリティ コントロールに合わせたこれらのソリューションの構成は、お客様の責任となります。

- [AD 評価](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment): Active Directory 正常性チェック ソリューションは、サーバー環境のリスクと正常性を定期的に評価し、展開されたサーバー インフラストラクチャに固有の推奨事項の優先付けされた一覧を提供します。
- [マルウェア対策の評価](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-): マルウェア対策ソリューションは、マルウェア、脅威、保護の状態を報告します。
- [Azure Automation](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker): Azure Automation ソリューションは、Runbook の保存、実行、管理を行います。
- [セキュリティと監査](https://docs.microsoft.com/azure/security-center/security-center-introduction): セキュリティと監査のダッシュボードでは、セキュリティ ドメイン、注目すべき問題、検出、脅威インテリジェンス、一般的なセキュリティ クエリに関するメトリクスを提供することで、リソースのセキュリティ状態についての高レベルの分析情報を提供します。
- [SQL 評価](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment): SQL 正常性チェック ソリューションは、サーバー環境のリスクと正常性を定期的に評価し、展開されたサーバー インフラストラクチャに固有の推奨事項の優先付けされた一覧を顧客に提供します。
- [更新プログラム管理](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview): 更新プログラム管理ソリューションは、利用可能な更新プログラムの状態や必要な更新プログラムのインストール手順など、オペレーティング システムのセキュリティ更新プログラムを顧客が管理できるようにします。
- [エージェントの正常性](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth): エージェントの正常性ソリューションは、展開されているエージェントの数とその地理的分布を報告し、応答のないエージェントの数や運用データを送信しているエージェントの数も報告します。
- [Azure アクティビティ ログ](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): アクティビティ ログ分析ソリューションは、顧客のすべての Azure サブスクリプション全体に渡る Azure アクティビティ ログの分析をサポートします。
- [変更履歴](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): 変更履歴ソリューションは、顧客が環境内の変更点を簡単に特定できるようにします。

Azure の技術的な情報やセキュリティ対策に関する情報については、コントローラーの顧客は「[Azure のセキュリティに関するドキュメント](https://docs.microsoft.com/azure/security/)」を参照してください。 Microsoft は顧客データが個人データかどうかを判別できないため、Azure はすべての顧客データが個人データであるものとして処理します。そのため、顧客はすべての素材が関連性のあるものとして考える可能性が高いです。

### <a name="processor-information"></a>プロセッサ情報

また、顧客がプロセッサの処理情報のレコードを必要としている可能性があるもう 1 つの製品には、Office 365 があります。 Office 365 に関連する情報を表示するには、「[セキュリティ/コンプライアンス センターで監査ログを検索する](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)」の記事を参照してください。

また、セキュリティ/コンプライアンス センターを利用して Dynamics 365 の情報を表示することもできます。  セキュリティ/コンプライアンス センターのページを表示するには、正しいライセンスを取得していることをご確認ください。 ライセンスの詳細については、「[Security & Compliance Center service description (セキュリティ/コンプライアンス センターのサービスの説明)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)」の記事を参照してください。 Dynamics 365 のイベントを検索するには、[セキュリティ/コンプライアンス センター](https://protection.office.com/unifiedauditlog)で統合監査ログにアクセスします。

### <a name="professional-services-information"></a>プロフェッショナル サービスの情報

プロフェッショナル サービスに関して、プロフェッショナル サービスのサポート データは、顧客によって提供され、顧客の担当者を介してサポート エンジニアに提供されます。  これは、顧客がオンライン製品ポータル、サービス ハブ、スマートフォンを介してサービス要求を送信した場合に発生する場合があります。

情報は Microsoft の CRM システムに保存され、次の目的に対してのみ使用されます。

- テクニカル サポート、専門家による計画、アドバイス、ガイド、データの移行、展開、ソリューション/ソフトウェア開発サービスなど、専門的なサービスの提供。  
- トラブルシューティング (セキュリティ インシデントを含む問題の防止、検出、調査、軽減、修復)。 
- 継続的な改善 (最新の更新プログラムのインストール、信頼性、有効性、品質、セキュリティの改善などを含むプロフェッショナル サービスの維持)。 

Microsoft では、サポート業務の規模により、製品グループベースでの CRM システムを運用しています。 処理のレコードは、それらのシステムに含まれています。
処理の履歴は、CRM システム内に維持されているレコードに反映されています。  ほとんどの場合、サービス要求の履歴はポータルまたはサービス ハブで利用可能です。
ポータルに記載されていない特定の詳細情報や、お客様のデータの処理に関連するその他のお問い合わせについては、お客様のテクニカル アカウント マネージャーにお問い合わせいただくか、[Microsoft 技術サポート](https://support.microsoft.com/contactus/)にお問い合わせください。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
