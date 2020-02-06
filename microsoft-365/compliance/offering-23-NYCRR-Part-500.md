---
title: Title 23 NYCRR Part 500
description: Microsoft では、23 NYCRR 500 の要件を満たすために金融機関が Azure、Office 365、Power BI を役立てる方法を説明するガイドを作成しました。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: e5d9c847173af4155d6c9eb0f8c59a07053435c2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602894"
---
# <a name="title-23-nycrr-part-500"></a>Title 23 NYCRR Part 500

## <a name="title-23-nycrr-part-500-overview"></a>Title 23 NYCRR Part 500 の概要

深刻で、増加の一途をたどる情報や財務システムのサイバーセキュリティに対する脅威に対応するために、ニューヨーク州金融サービス局は 2017 年に、州内での業務の免許または承認を受けている金融機関に対して新しいサイバーセキュリティ要件を適用しました。 この規制は 「Title 23 New York Codes, Rules, and Regulation Part 500: Cybersecurity Requirements for Financial Services Companies (金融サービス会社向けサイバーセキュリティ要件)」と呼ばれ、州政府の認可を受けた、民間、または国際的な銀行、住宅ローン ブローカー、保険会社などの顧客データおよび IT システムを保護することを目的としています。

## <a name="microsoft-and-title-23-nycrr-part-500"></a>Microsoft と Title 23 NYCRR Part 500

Microsoft では、Title 23 NYCRR Part 500 の規制を受ける金融サービスに対して、包括的ガイド[『Microsoft クラウド サービス: NYDFS サイバーセキュリティ要件への準拠支援』(Microsoft Cloud Services: Supporting Compliance with NYDFS Cybersecurity Requirements)](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides) を提供しています。 規制の要求事項へ準拠が Azure、Office 365、Power BI の各クラウド サービスでサポートされる方法ついて詳しく説明しています。 世界の金融の中心地であるニューヨークでの操業を希望する金融機関はこれらの要求事項を満たす必要があるため、多くの機関にとってコンプライアンスは重要課題です。

ガイダンス『Microsoft クラウド サービス: [NYDFS サイバーセキュリティ要件への準拠支援](https://go.microsoft.com/fwlink/p/?linkid=2098969)』に従うことで、Title 23 NYCRR Part 500 への準拠を加速させることができます。

ニューヨーク州の規制では、各金融機関に対して以下の活動が要求されます。

- **強力なサイバーセキュリティ プログラムの整備と維持**: 最初に機関固有のリスク プロファイルの評価を行い、次にそれに対処するためのプログラムを設計します。 [Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332) は、Microsoft クラウド サービスを使用する際のリスクを金融サービス企業が評価できるようにするために作られました。 このサービスには、Microsoft のエンジニアや企業リスク責任者への直接の相談や Microsoft のコンプライアンスとセキュリティの専門家へのアクセスが含まれています。
- **包括的なサイバーセキュリティ ポリシーの実施**: 情報のセキュリティ、データ ガバナンスと分類、アクセス制御、事業継続性などに対応するポリシーを実施します。 Microsoft では、このポリシーを整備するためのガイダンスを提供しています。これには、認定とリスク評価、事業継続性と障害復旧指標、ログと監査に関する診断のそれぞれについての詳細情報が含まれます。
- **最高情報セキュリティ責任者 (CISO) の任命**: サイバーセキュリティ プログラムの管理およびポリシーの適用における最高責任者です。 CISO を支援するために、Microsoft では Microsoft のクラウド展開に関する詳細なサイバーセキュリティ情報を [Azure Security Center](https://azure.microsoft.com/services/security-center/?v=17.23h)、[Office 365 Advanced Threat Analytics](https://docs.microsoft.com/advanced-threat-analytics/)、および [Power BI セキュリティ](https://go.microsoft.com/fwlink/?LinkId=829185)を通して提供しています。
- **サイバーセキュリティ プログラムの有効性の監視とテスト**: Microsoft では、継続的な監視、定期的な侵入テスト、脆弱性評価などを含む、Microsoft によるサイバーセキュリティ活動の監査結果情報を提供しています。 お客様は、Microsoft からの事前の許可なしに独自のテストを実施できます。
- **監査証跡の管理**:  お客様は、Azure、Office 365、および Power BI の組み込みの監査機能を使用して、財務取引の再現に使用できる情報の生成や監査証跡情報の整備を行えます。
- **非公開情報が含まれる情報システムへのアクセスの制御**: Azure、Office 365、および Power BI で提供されている対策で、各サービス固有の役割ベースのアクセス制御 (RBAC) プロセス、すべての Microsoft 管理者に対する厳格なセキュリティとアクセス要件、およびすべての昇格されたアクセス権の要求に対する監査が含まれます。
- **外部で開発されたアプリケーションのセキュリティの評価とテスト**: Visual Studio を使用する開発者の場合、管理コードのための[セキュリティ ルール](https://docs.microsoft.com/visualstudio/code-quality/security-rules-rule-set-for-managed-code)を使用すると、コードの展開前にアプリケーションのサイバーセキュリティの脅威を検出し、軽減できます。
- **定期的なリスク評価を使用した、サイバーセキュリティプログラムの設計と強化**: Microsoft はお客様のために、セキュリティの脅威に関する情報をまとめ、変更管理のロードマップを提供し、委託先会社に関する情報を定期的に更新します。 また、Microsoft では Microsoft 自体のサービスのリスク評価を定期的に実施し、評価結果をお客様に提供します。
- **有資格担当者によるサイバーセキュリティのリスク管理とサイバーセキュリティ機能の監視**: Microsoft では、Microsoft の従業員による顧客データへのアクセスに対して厳密な手順を適用しています。 Microsoft が下請け業者を使用する場合、サービスの提供に対して Microsoft が責任を持ち、機密情報の取り扱い要件、身辺調査、機密保持契約を含む、Microsoft のプライバシーとセキュリティに関するコミットメントへの完全な準拠を下請け業者に対して要求します。
- **サードパーティ サービス プロバイダーが保持する情報のセキュリティを確保するためのポリシーと手順の適用**: Azure、Office 365、および Power BI では、会社のネットワークへのすべての受信接続で多要素認証が利用でき、外部ネットワークで転送中または保管中の非公開情報を保護するための暗号化を含む制御が実装され、顧客通知、インシデント調査、およびセキュリティ インシデントのリスク軽減を提供する [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)が提供されます。
- **データの保持と削除のポリシーと手順の実装**: Azure、Office 365、および Power BI に保存されている顧客データにいつでもアクセスし、抽出できます。
- **承認されたユーザーのアクティビティの監視、許可されていないアクセスの検出、従業員へのサイバーセキュリティに関する定期的な意識向上研修の提供**: Azure、Office 365、および Power BI では、外部からの内部の監視によるインシデント警告機能およびログ記録と監査のための広範な診断機能が提供されています。 [Microsoft Virtual Academy](https://mva.microsoft.com/): Microsoft クラウド サービスを取り扱うオンライン トレーニングを提供します。
- **サイバーセキュリティ インシデントでの対応と復旧に関する計画の整備**: Microsoft では、セキュリティ侵害を発生前に検出、予測、および回避する防御戦略を使用して、サイバーセキュリティ インシデントへの準備をお手伝いします。 独自の計画を整備する際でも、Microsoft のインシデント管理プランを参考にして、サイバーセキュリティ侵害に対応することができます。

## <a name="microsoft-in-scope-cloud-services"></a>対象 Microsoft クラウド サービス

- [Azure](https://aka.ms/AzureCompliance)
- Intune
- [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**この規制の対象となるのはどの機関ですか?**

お客様の機関がこの規制の対象かどうかを特定するには、ニューヨーク州金融サービス局の [Who we Supervise (監督対象機関)](https://go.microsoft.com/fwlink/p/?linkid=2099374) を参照してください。

## <a name="resources"></a>リソース

- [おすすめのリソース](https://www.microsoft.com/trustcenter/compliance/NYCRR)
- [ニューヨーク州金融サービス局 23 NYCRR 500: Cybersecurity Requirements for Financial Services Companies (金融サービス会社向けサイバーセキュリティ要件)](https://go.microsoft.com/fwlink/p/?linkid=2098976)
- [FAQ: 23 NYCRR Part 500–サイバーセキュリティ](https://go.microsoft.com/fwlink/p/?linkid=2098977)
- [Microsoft クラウド サービス: NYDFS サイバーセキュリティ要件への準拠支援](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="other-microsoft-resources-for-financial-services"></a>金融サービス向けのその他の Microsoft リソース

- [Microsoft 法人向けクラウド サービスおよび金融サービス](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332)
- [Azure における金融サービス コンプライアンス](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [クラウド コンピューティングの共同責任](https://aka.ms/sharedresponsibility)- 

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/9/F/B/9FB6EE03-0096-4820-A5BF-B633EE2BE0B7/23NYCRR_Part500-Compliance.pdf) ファイルをダウンロードできます。
