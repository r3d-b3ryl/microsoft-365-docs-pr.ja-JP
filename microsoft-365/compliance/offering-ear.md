---
title: US 輸出管理の規制 (EAR)
description: Microsoft クラウドサービスは、お客様が米輸出管理規則 (EAR) に準拠したコンプライアンス要件を満たし、輸出規制リスクを管理する手助けをしています。
keywords: Microsoft 365、コンプライアンス、オファーリング
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 283b6a45807547f9a8d0521cf2c6793a2a15c4d6
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690722"
---
# <a name="compliance-offering-us-export-administration-regulations-ear"></a>コンプライアンスオファリング: US Export Administration の規制 (EAR)

## <a name="about-the-ear"></a>イヤーについて

米国商務省は、[業界およびセキュリティ (BIS) のビューロー](https://www.bis.doc.gov/)で輸出管理の規則 (イヤー) を適用します。 この耳は、商業および軍事の目的と特定の防衛物の両方で使用できる "デュアルユース" のアイテムを含む、ほとんどの商用商品、ソフトウェア、およびテクノロジの輸出および再輸出に関する制御を幅広く制御し、課しています。

BIS ガイダンスでは、データまたはソフトウェアがクラウドにアップロードされるとき、またはユーザーノード間で転送されるときに、クラウドプロバイダーではなく、顧客が "エクスポーター" となり、そのデータまたはソフトウェアの転送、保存、およびアクセスを確実に行うことができるようになります。イヤーに準拠します。

[BIS によれ](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file)ば、*輸出*とは、保護された技術または技術データを米国内の国外の人物に転送すること (または*エクスポート*とも呼ばれます) を指します。 耳になることは、次のとおりです。

- 米国からエクスポートします。
- 元のアイテムと特定の外部元アイテムを再輸出または再転送します。これには、 *minimis*の一部のコンテンツが含まれています。
- 他の国から個人に連絡または開示を行います。

EAR の対象となるアイテムは、各アイテムに固有の[エクスポート制御分類番号 (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn)が割り当てられている Commerce コントロールリスト (ccl) にあります。 CCL に記載されていないアイテムは EAR99 として指定されており、ほとんどの EAR99 市販製品ではライセンスをエクスポートする必要はありません。 ただし、宛先、エンドユーザー、またはアイテムの使用終了によっては、EAR99 アイテムでも、BIS エクスポートライセンスが必要になることがあります。

2016年6月に公開された[最終的なルール](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations)では、サードツーエンドで FIPS 140-2 の検証済み暗号化モジュールを使用して、サードツーエンドで暗号化されていて、故意に軍事によって禁止されていない国またはロシアのフェデレーションに保存されていなかった場合にも、そのことを明確にします

## <a name="microsoft-and-the-ear"></a>Microsoft とイヤー

Microsoft のテクノロジ、製品、およびサービスは、輸出管理の規制 (EAR) の対象となります。 EAR のコンプライアンス認定はありませんが、Microsoft Azure、Microsoft Azure Government、および Microsoft Office 365 Government (GCCHigh および DoD 環境) には、お客様にとって、EAR 管理のエクスポートの対象となる重要な機能とツールがあります。リスクを制御し、コンプライアンス要件を満たします。

この米コマース部門は、Microsoft などのクラウドサービスプロバイダーではなく、顧客データのエクスポーターと見なされるというお客様の地位を獲得しています。 ほとんどのお客様のデータは、耳になる輸出規制の対象となる "テクノロジ" または "技術データ" とは見なされませんが、Microsoft の範囲内のクラウドサービスは、お客様が管理し、発生する可能性のある輸出規制リスクを大幅に軽減できるように構造化されています。 Microsoft は一般に、対象ユーザーに対して政府機関のクラウドサービスの使用を推奨していますが、排他的ではありません。 適切な計画があれば、お客様は次のツールと独自の内部手順を使用して、輸出規制に関する完全なコンプライアンスを実現できます。

- **データの場所を制御**します。 お客様は、データが保存されている場所を確認でき、ストレージを制限する堅牢なツールにアクセスできます。 そのため、データを米国内に格納し、管理対象テクノロジまたは技術データを米国外で転送することを最小限に抑えることができます。 さらに、顧客データは、データが「故意に格納される」というイヤー prohibitions と一致していません。 Azure データセンターは、25か d のいずれかの国またはロシアのフェデレーションにありません。
- **エンドツーエンドの暗号化**。 耳で指定された物理的な格納場所に対してエンドツーエンドの暗号化セーフハーバーを利用することにより、Microsoft のスコープ内のクラウドサービスは、輸出管理のリスクに対する保護に役立つ暗号化機能を提供します。 また、転送中および保存中の[データを暗号化するためのさまざまなオプション](https://aka.ms/Azure-Encryption-Overview)をお客様に提供します。また、暗号化オプションの中から柔軟に選択できます。
- **許可されていないエクスポートを防止するためのツールとプロトコル**。 また、暗号化を使用すると、非 US のユーザーが暗号化されたデータにアクセスしている場合でも、暗号化されたデータを読み取ることができない場合や、データを認識していない場合でも、データの読み取りまたは認識ができない場合には何も表示されません。したがって、制御されたデータの "リリース" はありません。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft スコープ内クラウドサービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 Government (GCC-高および DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>実装方法

お客様が耳の下での義務を評価するための輸出規制とガイダンスの概要を説明します。

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Microsoft クラウドサービスを使用する際に、輸出規制に準拠するにはどうすればよいですか。**

この耳では、データが Microsoft クラウドなどのクラウドサーバーにアップロードされるときに、クラウドサービスプロバイダーではなく、データを所有する顧客がエクスポーターと見なされます。 そのため、データの所有者 (Microsoft のお客様) は、Microsoft cloud の使用方法を慎重に評価する必要があります。輸出規制を implicate し、使用しているデータやストアに格納されているデータがイヤーにあるかどうかを判断します。、適用される場合は、どのようなコントロールが適用されます。 [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)と[Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI)のクラウドサービスを使用して、お客様が輸出規制を完全に遵守できるようにする方法について説明します。

**マイクロソフトのテクノロジ、製品、サービスは、耳の対象となりますか?**

ほとんどの Microsoft テクノロジ、製品、およびサービスは、次のいずれかです。

- は、EAR の対象ではないため、Commerce コントロールリストには含まれず、ECCN もありません。
- または、Microsoft による自己分類の対象となる EAR99 または5D992 の大規模な市場を対象としており、ライセンスを必要とせずにライセンスを持たない国にエクスポートすることはできません (NLR)。

ということですが、一部の Microsoft 製品には、ライセンスを必要とする場合としない場合がある ECCN が割り当てられています。 イヤーまたは法律顧問を参照して、適切なライセンスの種類および輸出目的の国を決定します。

**召集 (ITAR) における EAR と国際トラフィックの違いは何ですか?**

最も広範なアプリケーションを使用した基本的な輸出規制は、同社の米国防省によって管理されるイヤーです。 この耳は、商業および軍用アプリケーションを含むデュアル使用のアイテムと、純粋に商用アプリケーションのアイテムに適用されます。

また、米国には、ITAR などの特殊な輸出規制規則もあります。これにより、最も機密性の高いアイテムやテクノロジを制御できます。 米国の州署によって管理され、関連する技術データを含む、多くの軍事、防衛、および諜報部のアイテム (「防衛記事」とも呼ばれる) のエクスポート、一時インポート、再エクスポート、転送に関する制御を行います。

## <a name="resources"></a>リソース

- [Microsoft 製品をエクスポートする: 概要](https://www.microsoft.com/exporting/overview.aspx)
- [Microsoft 製品をエクスポートする: よく寄せられる質問](https://www.microsoft.com/exporting/faq.aspx)
- [Microsoft 製品のエクスポート: 製品検索](https://www.microsoft.com/exporting/exporting-information.aspx)
- [暗号化に対するエクスポートの制限](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft および FIPS 140-2](offering-fips-140-2.md)
- [Microsoft および ITAR](offering-itar.md)
- [Microsoft セキュリティセンターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
