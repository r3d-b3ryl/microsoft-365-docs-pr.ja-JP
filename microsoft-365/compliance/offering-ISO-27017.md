---
title: ISO/IEC 27017:2015 情報セキュリティ コントロールの実施基準
description: Microsoft クラウド サービスでは、情報セキュリティ コントロールに関するこの実施基準が採用されています。
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
ms.openlocfilehash: 6bd989a5600252ee60ada4eb4e3d1414ef3853d5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602244"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a>ISO/IEC 27017:2015 情報セキュリティ コントロールの実施基準

## <a name="iso-iec-27017-overview"></a>ISO-IEC 27017 の概要

ISO/IEC 27017:2015 実施基準は、組織が ISO/IEC 27002:2013 に基づいてクラウド コンピューティング情報セキュリティ管理システムを実装するときにクラウド サービス情報セキュリティ コントロールを選択するためのリファレンスとして使用することを意図しています。 また、クラウド サービス プロバイダーが、一般に受け入れられている保護コントロールを実装するためのガイダンス資料としても使用できます。

この国際的な基準は、ISO/IEC 27002 に基づくクラウド特有の実装ガイダンスも提供されています。さらに、ISO/IEC 27002: 2013 の 5 項から 18 項で示されるコントロール、実装ガイダンスおよび各種情報に対するクラウド特有の情報セキュリティの脅威とリスクに対応するための追加コントロールも示されています。 具体的にはこの基準では ISO/IEC 27002 の 37 のコントロールに関するガイダンスを提供すると同時に、ISO/IEC 27002 では取り上げられていない 7 つの新しいコントロールにも言及しています。 これらの新しいコントロールは、次の重要な分野に対応しています。

- クラウド コンピューティング環境で共有される役割と責任
- 契約終了時におけるクラウド サービスのお客様の資産の削除と返却
- お客様の仮想環境を他お客様の仮想環境から保護および分離すること
- ビジネス ニーズに応じた仮想マシンの要塞化要件
- クラウド コンピューティング環境の管理運用の手順
- クラウド コンピューティング環境内の関連アクティビティに対する監視手段の提供
- 仮想ネットワークと物理ネットワークのセキュリティ管理の連携

## <a name="microsoft-and-isoiec-27017"></a>Microsoft と ISO/IEC 27017

ISO/IEC 27017 は、クラウド サービス プロバイダーとクラウド サービスお客様の両方にガイダンスを提供している点で独特です。 また、クラウド サービスお客様がクラウド サービス プロバイダーに期待できることに関する実際的な情報も示しています。 お客様が ISO/IEC 27017 から直接得られるメリットとして、クラウドにおける共同責任を理解できます。

Microsoft クラウドでの ISO/IEC 27017 の利点について確認してください: [ISO/IEC 27017: 情報セキュリティ管理の実務基準をダウンロードしてください](https://aka.ms/iso27017-backgrounder)

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure、Azure Government、Azure Germany](https://aka.ms/AzureCompliance)
- Cloud App Security
- [Dynamics 365](https://aka.ms/d365-compliance-list)
- Genomics
- Graph
- Intune
- Microsoft マネージド デスクトップ
- Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)
- Office 365、Office 365 米国政府、Office 365 米国防総省、Office 365 Germany
- Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)
- Office 365 の対象サービスの[詳細なリスト](https://go.microsoft.com/fwlink/p/?linkid=2077751)をご覧ください

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

Microsoft クラウド サービスは、年 1 回、ISO/IEC 27001:2013 の認定プロセスの一環として、ISO/IEC 27017:2015 実施基準に関する監査を受けています。

- [Azure ISO 27017 証明書](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [Azure ISO 27017 評価レポート](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [Azure ISO 27017 適用宣言書](https://aka.ms/AzureISO27017StatementofApplicability)
- [Office 365 ISO 27001、27018、27017 監査評価レポート](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

この標準はだれに適用されますか?

この実施基準では、クラウド サービス プロバイダーとクラウド サービスお客様の両方にコントロールと実装のガイダンスが提供されています。 ISO/IEC 27002:2013 と似た構成になっています。

**Microsoft ISO/IEC 27017:2015 コンプライアンス情報はどこで確認できますか?**

Azure、Intune、Power BI の [ISO/IEC 27017:2015 認定証](https://aka.ms/azureiso27017)をダウンロードできます。

**Microsoft サービスの ISO/IEC 27017 コンプライアンスを私の組織の認定プロセスに利用できますか?**

はい。 ビジネスで求められているのが、Microsoft の適用エンタープライズ クラウド サービスのいずれかにデプロイされている実装の認定である場合は、Microsoft の関連認定をコンプライアンス評価で利用できます。 ただし、コンプライアンスや、組織内の統制およびプロセスに関して、実装を評価する査定人の手配の責任は、審査を受ける組織が負うものとします。

**該当する監査レポートのコピーはどのようにして入手できますか?**

[Service Trust Portal](https://aka.ms/stphelp) では、独立している第三者監査レポートと他の関連資料が提供されています。 このポータルを利用して、お客様の規制要件に役立つ資料をダウンロードおよび確認できます。

## <a name="resources"></a>リソース

- [ISO/IEC 27017:2015 実施基準](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [Microsoft オンライン サービス条件](https://aka.ms/Online-Services-Terms)
- [Microsoft セキュリティ センターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景解説をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf) ファイルをダウンロードできます。
