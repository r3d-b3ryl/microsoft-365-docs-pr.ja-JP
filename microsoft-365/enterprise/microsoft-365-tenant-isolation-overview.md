---
title: Microsoft 365 でのテナントの分離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 のようなクラウド サービスでテナント分離を適用する方法の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923078"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Microsoft 365 でのテナントの分離

クラウド コンピューティングの主な利点の 1 つは、多数の顧客間で同時に共有される共通のインフラストラクチャの概念で、規模の経済性につながる点です。 この概念は、マルチ *テナンシーと呼ばれる。* Microsoft は、クラウド サービスのマルチテナント アーキテクチャによって、エンタープライズレベルのセキュリティ、機密性、プライバシー、完全性、可用性の基準をサポートするため、継続的に取り組んでいます。

信頼できるコンピューティングとセキュリティ開発ライフサイクルから収集された多[](https://www.microsoft.com/trust-center)大な投資と経験に[](https://www.microsoft.com/securityengineering/sdl/)基づいて、Microsoft クラウド サービスは、すべてのテナントが他のすべてのテナントに対して敵対的である可能性があるという前提で設計され、あるテナントのアクションが別のテナントのセキュリティやサービスに影響を与え、または別のテナントのコンテンツにアクセスするのを防ぐためのセキュリティ対策を実装しました。

マルチテナント環境でテナントの分離を維持する 2 つの主な目標は次のとおりです。

1.    テナント間の顧客コンテンツの漏洩または不正アクセスの防止。そして
2.    あるテナントのアクションが別のテナントのサービスに悪影響を及ぼすのを防ぐ

Microsoft 365 のサービスやアプリケーションを侵害したり、他のテナントや Microsoft 365 システム自体の情報に対する不正アクセスを防止したりするために、Microsoft 365 全体に複数の保護が実装されています。

- Microsoft 365 サービスの各テナント内の顧客コンテンツの論理的な分離は、Azure Active Directory の承認と役割ベースのアクセス制御によって実現されます。
- SharePoint Online は、ストレージ レベルでデータ分離メカニズムを提供します。
- Microsoft では、厳密な物理的セキュリティ、バックグラウンド スクリーニング、多層暗号化戦略を使用して、顧客コンテンツの機密性と整合性を保護します。 すべての Microsoft 365 データセンターには生体認証アクセス制御が備わっています。ほとんどの場合、物理的なアクセスを得るために手のひらの印刷が必要です。 さらに、米国に拠点を置く Microsoft のすべての従業員は、採用プロセスの一環として標準のバックグラウンド チェックを正常に完了する必要があります。 Microsoft 365 の管理アクセスに使用されるコントロールの詳細については [、「Microsoft 365 管理アクセス制御」を参照してください](/compliance/assurance/assurance-administrative-access-controls-overview)。
- Microsoft 365 では、BitLocker、ファイルごとの暗号化、トランスポート層セキュリティ (TLS)、インターネット プロトコル セキュリティ (IPsec) など、保存中および転送中の顧客コンテンツを暗号化するサービス側テクノロジを使用します。 Microsoft 365 での暗号化の詳細については [、「Microsoft 365 のデータ暗号化テクノロジ」を参照してください](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)。

上記の保護を組み合わせて、物理的な分離によって提供されるのと同等の脅威保護と軽減策を提供する堅牢な論理分離制御を提供します。

## <a name="related-links"></a>関連リンク

- [Azure Active Directory での分離とアクセス制御](microsoft-365-isolation-in-azure-active-directory.md)
- [Office Graph と Delve でのテナントの分離](microsoft-365-isolation-in-graph-and-delve.md)
- [Microsoft 365 の検索でのテナントの分離](microsoft-365-isolation-in-microsoft-365-search.md)
- [Office 365 でのテナントの分離のビデオ](microsoft-365-isolation-in-microsoft-365-video.md)
- [リソースの制限](/compliance/assurance/assurance-resource-limits)
- [テナント境界の監視とテスト](/compliance/assurance/assurance-monitoring-and-testing)
- [Microsoft 365 での分離とアクセス制御](microsoft-365-isolation-in-microsoft-365.md)