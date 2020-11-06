---
title: Title 23 NYCRR Part 500
description: Microsoft では、23 NYCRR 500 の要件を満たすために金融機関が Azure、Office 365、Power BI を役立てる方法を説明するガイドを作成しました。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: fa76fefbeea2c8fc0226a85d5b12599839eba8ca
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920409"
---
# <a name="title-23-nycrr-part-500"></a>Title 23 NYCRR Part 500

## <a name="title-23-nycrr-part-500-overview"></a>Title 23 NYCRR Part 500 の概要

In response to the significant and ever-increasing threats to the cybersecurity of information and financial systems, in 2017, the State of New York Department of Financial Services imposed a new set of cybersecurity requirements on financial institutions that are licensed or authorized to do business in the state. This regulation — Title 23 New York Codes, Rules, and Regulation Part 500: Cybersecurity Requirements for Financial Services Companies — is designed to protect customer data and the information technology systems of financial institutions such as state-chartered, private, and international banks, mortgage brokers, and insurance companies.

## <a name="microsoft-and-title-23-nycrr-part-500"></a>Microsoft と Title 23 NYCRR Part 500

Microsoft provides a comprehensive guide, [Microsoft Cloud Services: Supporting Compliance with NYDFS Cybersecurity Requirements](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides), for financial services regulated under Title 23 NYCRR Part 500. It explains in depth how Azure, Office 365, and Power BI cloud services support compliance with the requirements. Financial institutions that seek to operate in the global financial center of New York must meet them, so compliance is critical for many institutions.

ガイダンス『Microsoft クラウド サービス: [NYDFS サイバーセキュリティ要件への準拠支援](https://go.microsoft.com/fwlink/p/?linkid=2098969)』に従うことで、Title 23 NYCRR Part 500 への準拠を加速させることができます。

ニューヨーク州の規制では、各金融機関に対して以下の活動が要求されます。

- **Develop and maintain a robust cybersecurity program** starting with an assessment of the institution’s specific risk profile and then designing a program that addresses them. The [Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332) was created to help financial services assess the risks of using Microsoft cloud services. It includes direct engagement with our engineers and corporate risk officers and access to our compliance and security experts.
- **Implement a comprehensive cybersecurity policy** that addresses information security, data governance and classification, access controls, business continuity, and the like. Microsoft offers guidance for developing this policy with in-depth information about our certifications and risk assessments; business continuity and disaster recovery metrics; and diagnostics for logging and auditing.
- **最高情報セキュリティ責任者 (CISO) の任命** :サイバーセキュリティ プログラムの管理およびポリシーの適用の最高責任者です。CISO を支援するために、Microsoft では Microsoft のクラウド展開に関する詳細なサイバーセキュリティ情報を[Azure Defender*](https://azure.microsoft.com/services/security-center/?v=17.23h)、[Office 365 Advanced Threat Analytics](https://docs.microsoft.com/advanced-threat-analytics/)、および[Power BI Security](https://go.microsoft.com/fwlink/?LinkId=829185)を通して提供しています。
- **Monitor and test the effectiveness of its cybersecurity program** : Microsoft provides information from audits of its cybersecurity practices that include continuous monitoring, periodic penetration testing, and vulnerability assessments. Customers can conduct their own tests without advance permission from Microsoft.
- **Maintain an audit trail.** Built-in audit functionalities of Azure, Office 365, and Power BI customers generate information that can be used to reconstruct financial transactions and develop audit trail information.
- **非公開情報が含まれる情報システムへのアクセスの制限** : Azure、Office 365、および Power BI で提供されている対策で、各サービス固有の役割ベースのアクセス制御 (RBAC) プロセス、すべての Microsoft 管理者に対する厳格なセキュリティとアクセス要件、およびすべての昇格されたアクセス権の要求に対する監査が含まれます。
- **外部で開発されたアプリケーションのセキュリティの評価とテスト** : Visual Studio を使用する開発者の場合、管理コードのための [セキュリティ ルール](https://docs.microsoft.com/visualstudio/code-quality/security-rules-rule-set-for-managed-code)を使用すると、コードの展開前にアプリケーションのサイバーセキュリティの脅威を検出し、軽減できます。
- **Use periodic risk assessments to design and enhance cybersecurity programs** : For customers, Microsoft aggregates information about security threats, provides roadmaps of change management, and regularly updates information about subcontractors. Microsoft also regularly conducts risk assessments of its own services, the results of which are available to customers.
- **Use qualified personnel to manage cybersecurity risks and oversee cybersecurity functions** : Microsoft employs stringent procedures for our employee access to your customer data. If we hire subcontractors, we remain responsible for service delivery, and ensure that subcontractors fully comply with Microsoft privacy and security commitments, including requirements for handling sensitive data, background checks, and non-disclosure agreements.
- **サードパーティ サービス プロバイダーが保持する情報のセキュリティを確保するためのポリシーと手順の適用** : Azure、Office 365、および Power BI では、会社のネットワークへのすべての受信接続で多要素認証が利用でき、外部ネットワークで転送中または保管中の非公開情報を保護するための暗号化を含む制御が実装され、顧客通知、インシデント調査、およびセキュリティ インシデントのリスク軽減を提供する [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)が提供されます。
- **データの保持と削除のポリシーと手順の実装** : Azure、Office 365、および Power BI に保存されている顧客データにいつでもアクセスし、抽出できます。
- **Monitor the activity of authorized users, detect unauthorized access, and offer regular cybersecurity awareness training to employees** : Azure, Office 365, and Power BI include outside-in monitoring to raise alerts about incidents, and extensive diagnostics for logging and auditing. [Microsoft Virtual Academy](https://mva.microsoft.com/) offers online training that covers the cybersecurity of Microsoft cloud services.
- **Develop plans to respond to and recover from cybersecurity incidents** : Microsoft helps you prepare for cybersecurity incidents using a defensive strategy to detect, predict, and prevent security breaches before they occur. When developing your own plans, you can draw on our incident management plan for responding to cybersecurity breaches.

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

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
