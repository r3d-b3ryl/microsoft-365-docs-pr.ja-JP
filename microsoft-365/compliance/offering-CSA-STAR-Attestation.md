---
title: クラウド セキュリティ アライアンス (CSA) STAR 証明
description: Azure と Intune には独立した監査に基づき、クラウド セキュリティ アライアンス STAR 証明が授与されています。
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
ms.openlocfilehash: 7741d23d83b7f21b61801fd51ed6332f2fb02718
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602584"
---
# <a name="cloud-security-alliance-csa-star-attestation"></a>クラウド セキュリティ アライアンス (CSA) STAR 証明

## <a name="csa-star-attestation-overview"></a>CSA STAR 証明の概要

クラウド セキュリティ アライアンス (CSA) は、セキュリティ、信頼および保証レジストリ (STAR) を管理しています。STAR は、クラウド サービス プロバイダー (CSP) が CSA 関連の評価を公開できる、無償の、一般からアクセス可能な登録簿です。 STAR は CSA クラウド コントロール マトリックス (CCM) のコントロール目標に即した 3 つのレベルの保証で構成されています。 (CCM は 16 のドメインを対象とする基本のセキュリティ原則を扱っており、クラウドのお客様がクラウド サービスの全体的なセキュリティ リスクを評価できるよう支援します)。

- Level 1: STAR 自己診断
- Level 2: STAR 証明、STAR 認定資格、および C-STAR 診断 (第三者監査により判定)
- Level 3: STAR 継続的監視 (プログラム要件は CSA により現在策定中)

STAR 証明には、クラウド プロバイダーのセキュリティ態勢について、SOC 2 Type 2 の監査を基に CCM 基準を使用した、独立した監査人による厳格な監査が必要です。 STAR 証明に関してクラウド プロバイダーの製品やサービスを評価する独立した監査人は、公認会計士 (CPA) で、CSA Certificate in Cloud Security Knowledge (CCSK) を取得している必要があります。  
  
SOC 2 タイプ 2 の監査は、米国公認会計士協会 (AICPA) のトラスト サービスの原則と基準に基づき、セキュリティ、可用性、機密性、処理の整合性と、CCM の基準について評価します。 STAR 証明では、Microsoft クラウド サービスの SOC 2 コントロールの設計適合性と運用効率に関する監査人の調査結果を提供します。 上記の AICPA 基準と、CCM で規定されている要件の両方を満たすことが目的です。

## <a name="microsoft-in-scope-cloud-services"></a>対象となるマイクロソフトのクラウド サービス

Microsoft Azure と Microsoft Intune は CSA STAR 証明の認定を取得しました。 STAR 証明では、Microsoft クラウド サービスの SOC 2 コントロールの設計適合性と運用効率に関する監査人の調査結果を提供します。

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- [Azure Germany](https://aka.ms/AzureCompliance)
- Cloud App Security
- Graph
- Intune
- Microsoft マネージド デスクトップ
- Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランまたはスイートに搭載されているサービス)
- PowerApps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス) 
- Power BI

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

- [CSA STAR 証明および認定資格](https://cloudsecurityalliance.org/star/registry/microsoft/)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CSA CCM が対応しているのはどの業界標準ですか?**

CCM は、ISO/IEC 27001、PCI DSS、HIPAA、AICPA SOC 2、NERC CIP、FedRAMP、NIST など、業界で受け入れられているさまざまなセキュリティ基準、規制、管理フレームワークに対応しています。 最新のリストについては [CSA の Web サイト](https://cloudsecurityalliance.org/)にアクセスしてください。

**Microsoft クラウド サービスの CSA STAR 証明はどこで確認できますか?**

Azure の [CSA STAR 証明](https://aka.ms/CSASTAR-Attestation) は CSA 登録簿からダウンロードできます。この Certification は、IntuneI にも対応しています。

**Microsoft のビジネス クラウド サービスは、CSA STAR のどの保証レベルを達成していますか?**

- **Level 1**: **CSA STAR 自己診断**: Azure、Microsoft Dynamics 365、Microsoft Office 365。 [自己診断](offering-csa-star-self-assessment.md)は、お客様がサービスのセキュリティを評価できるように、クラウド サービス プロバイダーが自社のセキュリティ コントロールの文書化に使用でき、無料で提供されます。
- **Level 2**: **CSA STAR 認定資格**: Azure、Cloud App Security、Intune、Microsoft Power BI。 STAR 認定資格は、ISO/IEC 27001 認定を取得しているか、また、CCM において規定されている基準を満たしているかで判定されます。 この認証は、クラウド サービス プロバイダーにおけるセキュリティの制御と取り組みについて、第三者による厳格な評価を経て付与されます。
- **レベル 2**: **CSA STAR 評価証明**: Azure および Intune。 CSA と AICPA が協力して、CPA が SOC 2 の作成業務を行う際に使用できるガイドラインを提供しています。このガイドラインは、AICPA (Trust Service Principles, AT 101) および CSA CCM の基準に基づいています。 [STAR 評価証明](offering-CSA-STAR-Attestation.md)はこれらのガイドラインに基づくもので、クラウド プロバイダーに対する独立機関による厳格な評価を経て付与されます。

## <a name="resources"></a>リソース

- [情報要求に対する Azure の標準応答](https://aka.ms/AzureStandardRequestForInformation)
- [Azure クラウド セキュリティ アライアンス CAIQ](https://aka.ms/AzureCSACAIQ)
- [CSA クラウド コントロール マトリックスの Office 365 のマッピング](https://aka.ms/Office365CSACloudControlMatrix)
- [クラウド セキュリティ アライアンス](https://cloudsecurityalliance.org/)
- [CSA Security, Trust & Assurance Registry (STAR)](https://cloudsecurityalliance.org/star/)
- [SOC 1、2、および 3 レポート](offering-soc.md)
- [クラウド コントロール マトリックス (CCM)](https://cloudsecurityalliance.org/group/cloud-controls-matrix/)
- [Microsoft Common Controls Hub コンプライアンス フレームワーク](https://www.microsoft.com/trust-center/compliance/compliance-overview)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景解説をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/0/0/F/00F2766F-00E5-4235-8CE8-90FE657D768F/CSA-STAR-Attestation-Compliance.pdf) ファイルをダウンロードできます。
