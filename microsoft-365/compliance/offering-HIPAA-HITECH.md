---
title: 健康保険の携行性と責任 (HIPAA) & のヒット処理機能
description: Microsoft では、医療保険の携行性 & アカウンタビリティ Act ビジネスアソシエイトアグリーメント (BAAs) を提供しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
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
ms.openlocfilehash: 9224261cd0700796bdeccd35b68995c99300e591
ms.sourcegitcommit: a6686a68b068adec29b72f998ac9bc95992981df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628093"
---
# <a name="health-insurance-portability-and-accountability-hipaa--hitech-acts"></a>健康保険の携行性と責任 (HIPAA) & のヒット処理機能

## <a name="hipaa-and-the-hitech-act-overview"></a>HIPAA とヒット法の概要

健康保険の携行性と責任に関する法律 (HIPAA) は、個人を特定できる健康情報を使用、公開、保護するための要件を確立する米医療法です。 これは、医師の事務所、病院、健康 insurers、その他の医療会社 (患者の保護された健康情報 (PHI) へのアクセス、およびクラウドサービスや IT プロバイダーなどのビジネス関連のため、PHI を処理する) に適用されます。をお客様に代わって行います。 (最も一般的に使用されているエンティティは、自分でのクレームやデータの処理など) を実行しません。そのためには、ビジネス関連の関係者に依存します。

法律は、次の4つの一般的な領域での PHI の使用と配布を規制します。

- プライバシー。患者の機密保持を対象としています。
- セキュリティ。物理的な保護、技術保護、管理保護など、情報の保護を処理します。
- 識別子。調査目的で収集された場合には解放できない情報の種類です。
- 資格および保険の請求と支払いを含む、医療関連のトランザクションにおけるデータの電子情報送信のコード。

HIPAA の範囲は、経済および臨床状態 (エコー) 法の健康情報テクノロジを使用して拡張されました。HIPAA とヒット法ルールは共に、次のとおりです。

- HIPAA プライバシールールは、個人情報の使用を制御するために個人の権限を持ち、PHI の機密性を対象としており、使用と公開を制限します。
- HIPAA のセキュリティルール。管理、技術、および物理的な安全対策の標準を設定して、不正なアクセス、使用、および開示から電子 PHI を保護します。 また、ビジネスアソシエイトアグリーメント (BAAs) などの組織の要件も含まれます。

セキュリティで保護されていない PHI の違反が発生した場合に、個人と政府に通知することを要求する、ブリーチ違反の通知の最終ルール。

## <a name="microsoft-and-hipaa-and-the-hitech-act"></a>Microsoft および HIPAA およびエコー行為

HIPAA 規制では、対象となるエンティティとそのビジネスに関連するものが必要です。ここでは、クラウドサービスを含むサービスを対象エンティティに提供する場合は、契約に入力して、それらのビジネス関係が適切に行われるようにします。ファイを保護します。 これらのコントラクトまたは BAAs では、ビジネス関連が PHI を処理する方法を明確にし、各当事者が HIPAA およびお客様に対して設定されたセキュリティとプライバシーに関する規定に準拠するように設定します。BAA が配置されると、Microsoft のお客様 (対象となるエンティティ) は、そのサービスを使用して PHI を処理および保存できるようになります。

現時点では、HIPAA または、コンプライアンスのための公式認証はありません。 ただし、BAA で扱われている Microsoft サービスは、Microsoft ISO/IEC 27001 の認定資格を持つ、認定された独立した監査者が実施した監査にも対応しています。

Microsoft エンタープライズクラウドサービスは、FedRAMP 評価にも含まれています。 Microsoft Azure および Microsoft Azure Government は、FedRAMP ジョイント認証ボードから操作するための仮の機関を受け取りました。Microsoft Dynamics 365 米国政府機関が、米国および米国の米国政府機関からの米国政府機関からの米国政府機関との関係において、米国の住宅および都市の開発部門を対象とした機関を受け取っ365ています。

HIPAA と Microsoft Cloud でのエコーの利点について説明します。「 [Zwanger-Pesiri Radiology Customer Story」を参照](https://customers.microsoft.com/story/radiology-clinics-ease-compliance-drive-innovation-with-cloud-based-data-network)してください。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- Cloud App Security
- Microsoft Health Bot サービス
- Microsoft Stream
- Microsoft プロフェッショナル サービス: Azure、Dynamics 365、Intune と、Office 365 の Medium Business および Enterprise のお客様への Premier およびオンプレミス サポート
- [Dynamics 365、Dynamics 365 U.S. Government](https://aka.ms/d365-compliance-list)
- Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)
- Intune
- [Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- PowerApps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)
- Power BI cloud service をスタンドアロンサービスとして、または Office 365 または Dynamics 365 ブランドプランまたはスイートに含める
- Azure DevOps Services

## <a name="accelerate-your-deployment-of-hipaahitrust-solutions-on-azure"></a>Azure での HIPAA/HITRUST ソリューションの展開を促進する

Azure のセキュリティとコンプライアンスに関するブループリント (HIPAA/HITRUST Health データと AI) を使用した正常性データソリューションのクラウドのメリットの活用について、すぐに開始できます。 この青写真は、今日の HIPAA/HITRUST ソリューションの構築を開始するのに役立つツールとガイダンスを提供します。

[Azure HIPAA/HITRUST ブループリントの使用を開始する](https://docs.microsoft.com/azure/governance/blueprints/samples/hipaa-hitrust/)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**組織が Microsoft の BAA に入ることはできますか?**

Microsoft は、Microsoft のサービスを対象範囲とする、資格のある企業またはそのサプライヤーを BAA に提供しています。

Microsoft クラウドサービスの場合: [hipaa 法人関連付け契約](https://aka.ms/BAA)は、オンラインサービスの利用規約に既定で提供されています。 この BAA で扱われているクラウドサービスの一覧については、この web ページの「Microsoft scope cloud services」を参照してください。

Microsoft プロフェッショナルサービスサービスの場合: HIPAA Business アソシエイトへの修正は、Microsoft サービス担当者への要求に応じて、Microsoft プロフェッショナルサービスを対象範囲として提供されています。

**Microsoft で BAA があることによって、組織が HIPAA に準拠していることと、エコーが発生することが保証されますか。**

いいえ。 BAA を提供することで、Microsoft は HIPAA コンプライアンスをサポートしていますが、Microsoft サービスを使用しても、それを実現することはできません。 お客様の組織では、適切なコンプライアンスプログラムと内部プロセスが実施されており、Microsoft サービスの特定の使用が HIPAA およびお客様のものと一致していることを確認する責任があります。

**Microsoft は組織の BAA を変更できますか?**

Microsoft サービスはすべてのお客様にとって一貫しており、すべてのユーザーに対して同じ手順を実行する必要があるため、microsoft は HIPAA BAA を変更することはできません。 しかし、Microsoft の HIPAA 規制を利用しているお客様とそのサービスのための BAA を作成するために、Microsoft は、お客様のお客様および HIPAA の主要な診療学校の一部と、その他の公的および民間部門の HIPAA をカバーするエンティティについても共同で作業しています。

**監査者のレポートのコピーを取得するには、どうすればよいですか。**

[Service Trust Portal](https://www.microsoft.com/trustcenter/STP/default.aspx) では、中立的な監査によるコンプライアンス レポートを提供しています。 ポータルを使用して監査レポートを要求することにより、監査者が Microsoft のクラウドサービスの結果を、自分の法律および規制の要件に合わせて比較できるようにすることができます。

**HIPAA およびエコー行為への準拠の詳細については、どうすればわかりますか?**

このタスクについてお客様を支援するため、Microsoft は次のガイドを公開しています。

- *HIPAA/* 「excel の実装ガイダンス」、および「 [Dynamics 365 および Office 365](https://go.microsoft.com/fwlink/?LinkID=257510) [」をご](https://aka.ms/azurehipaaguidance)利用ください。 プライバシー、セキュリティ、法令遵守責任者、および HIPAA およびヒット性の実装を担当するその他の組織について記述されており、コンプライアンスを維持するために組織が講じることができる具体的な手順について説明します。
- [Microsoft Azure を使用してセキュリティで保護された正常性ソリューションを設計するための実践的なガイド](https://aka.ms/azureindustrysecurity)。クラウドサービスを安全な方法で適切に導入するために必要なことを理解するのに役立つ情報を示します。
- [Microsoft クラウドでの HIPAA のセキュリティとプライバシーの要件への対応に](https://smb.blob.core.windows.net/smbproduction/Content/Microsoft_Cloud_Healthcare_HIPAA_Security_Privacy.pdf)は、規制要件の概要が記載されています。 また、これらの要件に対応する方法論を使用して Microsoft のクラウドサービスがどのように構築されたかについての詳細な分析と、コンプライアンス対応のソリューションを構築する方法のガイダンスを提供します。

## <a name="resources"></a>リソース

- [Hipaa Omnibus ルール](https://aka.ms/HIPAA-omnibus)(最終規則の変更、hipaa ルールの変更)
- [Microsoft Common Controls Hub コンプライアンス フレームワーク](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)
- [Microsoft Government クラウド](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Azure に関する HIPAA 準拠について](https://www.youtube.com/embed/6ptdye1LZ5k?autoplay=0)(2016 年5月19日)
- [Azure HIPAA 実装のガイダンス](https://aka.ms/azure-hipaa-guide)
- [Microsoft セキュリティ センターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景解説をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/4/6/B/46BB3C98-AE2B-42C1-A2CD-F7C0040FB6B8/HIPAA_Compliance_Backgrounder.pdf) ファイルをダウンロードできます。
