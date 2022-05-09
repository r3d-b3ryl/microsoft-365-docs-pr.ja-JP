---
title: Microsoft 365のテナント分離
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
description: この記事では、microsoft がクラウド サービス (Microsoft 365 など) でテナント分離を適用する方法の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464094"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Microsoft 365のテナント分離

クラウド コンピューティングの主な利点の 1 つは、多数の顧客間で同時に共有される共通インフラストラクチャの概念であり、規模の経済につながります。 この概念は *マルチテナント* と呼ばれます。 Microsoft は、クラウド サービスのマルチテナント アーキテクチャによって、エンタープライズレベルのセキュリティ、機密性、プライバシー、完全性、可用性の基準をサポートするため、継続的に取り組んでいます。

[信頼できるコンピューティング](https://www.microsoft.com/trust-center)と[セキュリティ開発ライフサイクル](https://www.microsoft.com/securityengineering/sdl/)から収集された多額の投資と経験に基づいて、Microsoft クラウド サービスは、すべてのテナントが他のすべてのテナントに対して敵対する可能性があることを前提として設計されており、あるテナントのアクションが別のテナントのセキュリティまたはサービスに影響を与えないようにするためのセキュリティ対策を実装しています。 または別のテナントのコンテンツにアクセスします。

マルチテナント環境でテナントの分離を維持する 2 つの主な目標は次のとおりです。

1.    テナント間での顧客コンテンツの漏えい、または不正アクセスを防止する。そして
2.    あるテナントのアクションが別のテナントのサービスに悪影響を与えないようにする

お客様がMicrosoft 365サービスやアプリケーションを侵害したり、他のテナントやMicrosoft 365 システム自体の情報に不正にアクセスしたりすることを防ぐために、Microsoft 365全体で複数の形式の保護が実装されています。

- Microsoft 365 サービスの各テナント内の顧客コンテンツの論理的な分離は、Azure Active Directory承認とロールベースのアクセス制御によって実現されます。
- SharePoint Online では、ストレージ レベルでデータ分離メカニズムが提供されます。
- Microsoft では、厳格な物理的なセキュリティ、バックグラウンドスクリーニング、多層暗号化戦略を使用して、顧客コンテンツの機密性と整合性を保護します。 すべてのMicrosoft 365データセンターには生体認証アクセス制御があり、ほとんどの場合、物理的なアクセスを得るために手のひらのプリントが必要です。 さらに、米国に拠点を置く Microsoft のすべての従業員は、採用プロセスの一環として標準のバックグラウンド チェックを正常に完了する必要があります。 Microsoft 365の管理アクセスに使用される制御の詳細については、「[管理アクセス制御のMicrosoft 365」を](/compliance/assurance/assurance-administrative-access-controls-overview)参照してください。
- Microsoft 365では、BitLocker、ファイルごとの暗号化、トランスポート層セキュリティ (TLS)、インターネット プロトコル セキュリティ (IPsec) など、保存中および転送中の顧客コンテンツを暗号化するサービス側テクノロジを使用します。 Microsoft 365での暗号化の詳細については、「[Microsoft 365のデータ暗号化テクノロジ](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)」を参照してください。

一緒に、上記の保護は、物理的な分離だけで提供されるのと同じ脅威の保護と軽減策を提供する堅牢な論理的な分離制御を提供します。

## <a name="related-links"></a>関連リンク

- [Azure Active Directory での分離とアクセス制御](microsoft-365-isolation-in-azure-active-directory.md)
- [Office Graph と Delve でのテナントの分離](microsoft-365-isolation-in-graph-and-delve.md)
- [Microsoft 365 の検索でのテナントの分離](microsoft-365-isolation-in-microsoft-365-search.md)
- [リソースの制限](/compliance/assurance/assurance-resource-limits)
- [テナント境界の監視とテスト](/compliance/assurance/assurance-monitoring-and-testing)
- [Microsoft 365 での分離とアクセス制御](microsoft-365-isolation-in-microsoft-365.md)