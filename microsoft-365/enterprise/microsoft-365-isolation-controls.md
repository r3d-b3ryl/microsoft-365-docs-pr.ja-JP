---
title: Microsoft 365 の分離コントロール
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
description: 分離制御がMicrosoft 365内でどのように機能し、サービスが必要に応じて相互運用または自律的な状態を維持できるかについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464095"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 の分離コントロール 

Microsoft は、Microsoft 365のマルチテナント アーキテクチャがエンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、ローカル、国際、可用性[の標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)をサポートするように継続的に取り組んでいます。 Microsoft が提供するサービスの規模と範囲により、人間とのやり取りが大幅に行われ、Microsoft 365を管理することは困難で経済的ではありません。 Microsoft 365 サービスは、複数のグローバルに分散されたデータ センターを通じて提供されます。それぞれが高度に自動化されており、人間のタッチや顧客コンテンツへのアクセスを必要とする操作はほとんどありません。 弊社のスタッフは、自動化されたツールと安全性の高いリモート アクセスを使用して、これらのサービスとデータ センターをサポートしています。 

Microsoft 365は、重要なビジネス機能を提供し、Microsoft 365エクスペリエンス全体に貢献する複数のサービスで構成されています。 これらの各サービスは自己完結型であり、相互に統合するように設計されています。

Microsoft 365は、次の原則に従って設計されています。

 - **[サービス指向アーキテクチャ](/previous-versions/aa480021(v=msdn.10)): 明確に定義された** ビジネス機能を提供する相互運用可能なサービスの形式でソフトウェアを設計および開発します。
 - **[運用セキュリティ アシュアランス](https://www.microsoft.com/download/details.aspx?id=40872): Microsoft セキュリティ**[開発ライフサイクル](https://www.microsoft.com/sdl/default.aspx)、Microsoft [セキュリティ応答センター](https://technet.microsoft.com/library/dn440717.aspx)、サイバーセキュリティの脅威の状況に対する深い認識など、Microsoft 固有のさまざまな機能を通じて得られた知識を組み込んだフレームワーク。

Microsoft 365 サービスは相互に動作しますが、相互に独立して自律サービスとしてデプロイおよび運用できるように設計および実装されています。 Microsoft は、組織の資産の不正または意図しない変更や誤用の機会を減らすために、Microsoft 365の職務と責任領域を分離します。 Microsoft 365 チームは、包括的なロールベースのアクセス制御メカニズムの一部としてロールを定義しています。

## <a name="customer-content-isolation"></a>顧客コンテンツの分離

テナント内のすべての顧客コンテンツは、他のテナントから分離され、Microsoft 365の管理で使用される操作およびシステム データから分離されます。 Microsoft 365 には複数の保護形態が実装されており、Microsoft 365 のサービスやアプリケーションが侵害される危険を最小限に抑えることができます。 また、複数の形式の保護により、テナントまたはMicrosoft 365 システム自体の情報への不正アクセスも防止されます。

Microsoft がMicrosoft 365内でテナント データの論理的な分離を実装する方法については、「[Microsoft 365のテナントの分離](microsoft-365-tenant-isolation-overview.md)」を参照してください。