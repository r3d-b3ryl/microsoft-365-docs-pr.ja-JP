---
title: 医療保険の携行性と責任に関する法律と HITECH 法 (Health Insurance Portability and Accountability (HIPAA) & HITECH Acts)
description: Microsoft は、医療保険の携行性と責任に関する法律のビジネス アソシエイト契約 (BAA) を提供しています。
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
ms.openlocfilehash: 52752c31ae52fa75a3a50dbd6a4aa27605f6d921
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228513"
---
# <a name="health-insurance-portability-and-accountability-hipaa--hitech-acts"></a>医療保険の携行性と責任に関する法律と HITECH 法 (Health Insurance Portability and Accountability (HIPAA) & HITECH Acts)

## <a name="hipaa-and-the-hitech-act-overview"></a>HIPAA と HITECH 法の概要

健康保険の携行性と責任に関する法律 (HIPAA) は、個人を特定できる健康情報の使用、開示、および保護に関する要件を定めた米国の医療法です。 患者の保護された健康情報 (PHI) にアクセスできる対象事業体 (医師のオフィス、病院、健康保険会社、およびその他のヘルスケア企業) および代理で PHI を処理するクラウド サービスや IT プロバイダーなどのビジネス関係者に適用されます。 (ほとんどの対象事業体は、クレームやデータ処理などの機能を単独では実行しません。それらの機能の実行については、ビジネス関係者に依存しています。)

法律は、4 つの一般的な分野での PHI の使用および普及を規制しています。

- プライバシー。患者の機密性を対象とします。
- セキュリティ。物理的、技術的、および管理面での保護を含む情報の保護を扱います。
- 識別子。これは、調査目的で収集された場合に公開できない情報の種類です。
- 医療関連の取引におけるデータの電子送信のためのコード。適格性および保険金の請求や支払いを含みます。

HIPAA の範囲は、経済的および臨床的健全性のための健康情報技術 (HITECH) 法の制定により拡張されました。HIPAA および HITECH 法のルールには以下が含まれます。

- 個人が各自の個人情報の使用をコントロールする権利に焦点を当てる HIPAA プライバシー ルールは、PHI の機密性を対象とし、その使用と開示を制限します。
- HIPAA セキュリティ ルール。管理面、技術的、および物理的な保護の基準を設定し、電子 PHI を不正なアクセス、使用、および開示から保護します。 また、ビジネス アソシエイト契約 (BAA) などの組織の要件も含まれます。

HITECH 違反の通知に関する最終ルール。セキュリティ保護されていない PHI 違反が発生した場合、個人および政府に通知する必要があります。

## <a name="microsoft-and-hipaa-and-the-hitech-act"></a>Microsoft と HIPAA および HITECH 法

HIPAA 規制では、対象事業体およびそのビジネス関係者 (この場合、対象事業体にクラウド サービスなどを含むサービスを提供する Microsoft) が、これらのビジネス関係者による PHI の適切な保護を保証する契約を締結する必要があります。 これらの契約、または BAA は、ビジネス関係者が PHI を処理する方法を明確化および制限し、HIPAA および HITECH 法に定められたセキュリティおよびプライバシーの規定を各当事者が遵守することを定めます。BAA が導入されると、Microsoft のお客様 (対象事業体) は、そのサービスを使用して PHI を処理および保存することができます。

現在、HIPAA または HITECH 法のコンプライアンスに関する公式の認定資格はありません。 ただし、BAA の対象となるこれらの Microsoft サービスは、Microsoft ISO/IEC 27001 認定の独立監査人によって実施された監査を受けています。

Microsoft エンタープライズ クラウド サービスも FedRAMP 評価の対象です。 Microsoft Azure と Microsoft Azure Government は、FedRAMP 合同認定委員会から規定業務認可を受けました。Microsoft Dynamics 365 U.S. Government は、米国保健福祉省の Microsoft Office 365 U.S. Government と同様に、米国住宅都市開発省からエージェンシー業務認可を受けました。

Microsoft クラウドがお客様の HIPAA および HITECH 要件への準拠をどのように支援するかについては、「[Microsoft のお客様事例](https://customers.microsoft.com)」をご覧ください。

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
- Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに組み込まれているサービス)
- Azure DevOps Services

## <a name="accelerate-your-deployment-of-hipaahitrust-solutions-on-azure"></a>Azure での HIPAA/HITRUST ソリューションの展開を加速する

Azure のセキュリティとコンプライアンスのブループリント (HIPAA/HITRUST 健康データおよび AI) を使用して、健康データ ソリューション向けのクラウドの利点を活用する上での有利なスタートを切りましょう。 このブループリントは、HIPAA/HITRUST ソリューションの構築を今日から始めるためのツールとガイダンスを提供します。

「[Start using the Azure HIPAA/HITRUST Blueprint (Azure HIPAA/HITRUST ブループリントの使用を開始する)](https://docs.microsoft.com/azure/governance/blueprints/samples/hipaa-hitrust/)」

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**自分の所属組織は Microsoft と BAA を締結できますか ?**

Microsoft は、対象企業またはそのサプライヤーに、範囲内の Microsoft サービスを対象とする BAA を提供します。

Microsoft クラウド サービスの場合: [HIPAA ビジネス アソシエイト契約](https://aka.ms/BAA)は、HIPAA の対象事業体またはビジネス関係者であるすべての顧客が、オンライン サービスの使用条件を介して既定で利用できます。 この BAA の対象となるクラウド サービスの一覧については、この Web ページの「対象となる Microsoft のクラウド サービス」を参照してください。

Microsoft Professional Services サービスの場合: HIPAA ビジネス アソシエイト の修正は、Microsoft サービス担当者への要求に応じて、範囲内のMicrosoft Professional Services で利用できます。

**Microsoft との BAA を締結することで、組織が HIPAA および HITECH 法に準拠していることを保証できますか ?**

いいえ。 BAA を提供することにより、Microsoft は HIPAA コンプライアンスへの準拠の支援をしますが、Microsoft のサービスを使用するだけでは達成できません。 組織は、適切なコンプライアンス プログラムと内部プロセスを整備し、Microsoft サービスの特定の使用が HIPAA および HITECH 法と整合するように調整する責任があります。

**Microsoft は組織の BAA を変更できますか ?**

Microsoft のサービスはすべての顧客に対して一貫しているため、HIPAA BAA を変更することはできません。したがって、すべてのお客様が同じ手順に従っていただく必要があります。 ただし、Microsoft の HIPAA 規制対象の顧客およびそのサービスを対象とする BAA を作成するために、Microsoft はいくつかの主要な米国の医学部とその HIPAA プライバシー弁護士、およびその他の公的および民間セクターの HIPAA 対象事業体と協力しました。

**監査人の報告書のコピーはどのようにして入手できますか ?**

[Service Trust Portal](https://www.microsoft.com/trustcenter/STP/default.aspx) では、中立的な監査によるコンプライアンス レポートを提供しています。 貴社の監査人が Microsoft のクラウド サービスの監査結果と貴社の法的および規制要件を比較できるようにするために、ポータルで監査レポートをリクエストすることができます。

**HIPAA および HITECH 法への準拠に関する詳細を知るには、どうすればよいですか ?**

このタスクをサポートするために、Microsoft は次のガイドを公開しています。

- [Azure](https://aka.ms/azurehipaaguidance) 向けおよび [Dynamics 365 および Office 365](https://go.microsoft.com/fwlink/?LinkID=257510) 向けの *HIPAA/HITECH 法実装ガイダンス*。 プライバシー、セキュリティ、コンプライアンス責任者、および HIPAA および HITECH 法の実装を担当するその他の担当者向けに作成され、コンプライアンスを維持するために組織が実行できる具体的な手順について説明しています。
- 「[Practical guide to designing secure health solutions using Microsoft Azure (Microsoft Azure を使用して安全な健康ソリューションを設計するための実践ガイド)](https://aka.ms/azureindustrysecurity)」は、クラウド サービスを安全な方法で適切に導入するために必要なことをよりよく理解するために役立ちます。
- 「[Microsoft クラウドでの HIPAA セキュリティおよびプライバシー要件への対応](https://smb.blob.core.windows.net/smbproduction/Content/Microsoft_Cloud_Healthcare_HIPAA_Security_Privacy.pdf)」では、規制要件の概要を説明しています。 また、Microsoft のクラウド サービスがそれらの要件に対応する手法を用いてどのように構築されているかについての詳細な分析、およびコンプライアンス対応ソリューションの構築方法に関するガイダンスも提供しています。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Microsoft コンプライアンス スコアを使用してリスクを評価する

[Microsoft コンプライアンス スコア](compliance-score.md)は、[ Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。 [コンプライアンス スコアの設定](compliance-score-setup.md)後、[**テンプレート**] ドロップダウン メニューから事前に構成された [HIPAA Office 365 テンプレート](https://go.microsoft.com/fwlink/?linkid=2118005)と [HIPAA Intune テンプレート](https://go.microsoft.com/fwlink/?linkid=2118006)を選択してこの規制の要件を満たすようにします。

## <a name="resources"></a>リソース

- [HIPAA オムニバス ルール](https://aka.ms/HIPAA-omnibus) (最終規制を修正する HIPAA ルール)
- [Microsoft Common Controls Hub コンプライアンス フレームワーク](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)
- [Microsoft Government クラウド](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Azure の HIPAA コンプライアンスについて](https://www.youtube.com/embed/6ptdye1LZ5k?autoplay=0) (2016 年 5 月 19 日)
- [Azure HIPAA 実装ガイダンス](https://aka.ms/azure-hipaa-guide)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景解説をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/4/6/B/46BB3C98-AE2B-42C1-A2CD-F7C0040FB6B8/HIPAA_Compliance_Backgrounder.pdf) ファイルをダウンロードできます。
