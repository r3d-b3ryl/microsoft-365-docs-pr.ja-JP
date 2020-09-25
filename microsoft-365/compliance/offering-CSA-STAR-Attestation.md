---
title: クラウド セキュリティ アライアンス (CSA) STAR 証明
description: Azure と Intune には独立した監査に基づき、クラウド セキュリティ アライアンス STAR 証明が授与されています。
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
ms.openlocfilehash: 56f01880e3e2f381d85ed386ac413d4dbff38ff4
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208599"
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
- Microsoft Cloud App Security
- Microsoft Graph
- Intune
- Microsoft マネージド デスクトップ
- Power Automate (旧称 Microsoft Flow) スタンドアロン サービス、または Office 365 や Dynamics 365 ブランド プランあるいはスイートに搭載されているサービスとしてのクラウド サービス
- Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス) 
- Power BI

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

- [CSA STAR 証明および認定資格](https://cloudsecurityalliance.org/star/registry/microsoft/)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CSA CCM が対応しているのはどの業界標準ですか?**

CCM は、ISO/IEC 27001、PCI DSS、HIPAA、AICPA SOC 2、NERC CIP、FedRAMP、NIST など、業界で受け入れられているさまざまなセキュリティ基準、規制、管理フレームワークに対応しています。 最新のリストについては [CSA の Web サイト](https://cloudsecurityalliance.org/)にアクセスしてください。

**Microsoft クラウド サービスの CSA STAR 証明はどこで確認できますか?**

Azure の [CSA STAR 証明](https://aka.ms/CSASTAR-Attestation) は CSA 登録簿からダウンロードできます。この Certification は、IntuneI にも対応しています。

**Microsoft のビジネス クラウド サービスは、CSA STAR のどの保証レベルを達成していますか?**

- **Level 1**: **CSA STAR 自己診断**: Azure、Microsoft Dynamics 365、Microsoft Office 365。 [自己評価](offering-csa-star-self-assessment.md)は、クラウド サービス プロバイダーにより提供される無償のサービスで、顧客がサービスのセキュリティを評価できるよう、プロバイダーが自社のセキュリティ制御を文書化したものです。
- **Level 2**: **CSA STAR 認定資格**: Azure、Microsoft Cloud App Security、Intune、Microsoft Power BI。 STAR 認証は、ISO/IEC 27001 認証の取得および CCM に規定されている基準への適合に基づきます。 この認証は、クラウド サービス プロバイダーにおけるセキュリティの制御と取り組みについて、第三者による厳格な評価を経て付与されます。
- **レベル 2**: **CSA STAR 評価証明**: Azure および Intune。 CSA と AICPA が協力して、CPA が SOC 2 の作成業務を行う際に使用できるガイドラインを提供しています。このガイドラインは、AICPA (Trust Service Principles, AT 101) および CSA CCM の基準に基づいています。 [STAR 評価証明](offering-CSA-STAR-Attestation.md)はこれらのガイドラインに基づくもので、クラウド プロバイダーに対する独立機関による厳格な評価を経て付与されます。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Microsoft コンプライアンス マネージャーを使用してリスクを評価する

[Microsoft コンプライアンス マネージャー](compliance-manager.md)は、[ Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)の機能で、組織のコンプライアンスに対する姿勢を把握し、リスクを軽減するための処置を実行できるようにします。 コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアム テンプレートが用意されています。 コンプライアンスマネージャーの**評価テンプレート** ページでテンプレートを見つけます。 [コンプライアンスマネージャーで評価をする方法](compliance-manager-assessments.md)について説明します。

## <a name="resources"></a>リソース

- [情報要求に対する Azure の標準応答](https://aka.ms/AzureStandardRequestForInformation)
- [Azure クラウド セキュリティ アライアンス CAIQ](https://aka.ms/AzureCSACAIQ)
- [CSA クラウド コントロール マトリックスの Office 365 のマッピング](https://aka.ms/Office365CSACloudControlMatrix)
- [クラウド セキュリティ アライアンス](https://cloudsecurityalliance.org/)
- [CSA Security, Trust & Assurance Registry (STAR)](https://cloudsecurityalliance.org/star/)
- [SOC 1、2、および 3 レポート](offering-soc.md)
- [クラウド コントロール マトリックス (CCM)](https://cloudsecurityalliance.org/group/cloud-controls-matrix/)
- [Microsoft Common Controls Hub コンプライアンス フレームワーク](https://www.microsoft.com/trust-center/compliance/compliance-overview)
- [Microsoft セキュリティ センターのコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)
