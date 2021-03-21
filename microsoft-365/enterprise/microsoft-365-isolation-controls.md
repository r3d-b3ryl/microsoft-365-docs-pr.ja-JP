---
title: Microsoft 365 分離コントロール
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
description: Microsoft 365 内で分離制御がどのように機能するかについて説明します。サービスは必要に応じて運用間または自律的な状態を維持できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918944"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 分離コントロール 

Microsoft は継続的に、Microsoft 365 のマルチテナント アーキテクチャがエンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、ローカル、国際、可用性の[](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)標準をサポートします。 Microsoft が提供するサービスの規模と範囲により、Microsoft 365 を大幅な人間のやり取りで管理することは困難で経済的ではありません。 Microsoft 365 サービスは、複数のグローバルに分散されたデータ センターを介して提供され、それぞれが高度に自動化され、人間のタッチや顧客コンテンツへのアクセスを必要とする操作が少ない。 弊社のスタッフは、自動化されたツールと高度に安全なリモート アクセスを使用して、これらのサービスとデータ センターをサポートしています。 

Microsoft 365 は、重要なビジネス機能を提供し、Microsoft 365 エクスペリエンス全体に貢献する複数のサービスで構成されています。 これらの各サービスは、自己格納型であり、互いに統合するように設計されています。

Microsoft 365 は、次の原則に従って設計されています。

 - **[サービス指向アーキテクチャ](/previous-versions/aa480021(v=msdn.10)): 適切** に定義されたビジネス機能を提供する相互運用可能なサービスの形式でソフトウェアを設計および開発します。
 - **[運用セキュリティアシュア](https://www.microsoft.com/download/details.aspx?id=40872)ランス:** [Microsoft](https://www.microsoft.com/sdl/default.aspx)セキュリティ開発ライフサイクル [、Microsoft](https://technet.microsoft.com/library/dn440717.aspx)セキュリティ応答センター、サイバーセキュリティ脅威の状況に対する深い認識など、Microsoft 固有のさまざまな機能によって得られる知識を組み込んだフレームワーク。

Microsoft 365 サービスは相互に運用されますが、互いに独立した自律サービスとして展開および運用できるよう設計および実装されています。 Microsoft は、組織の資産の無許可または意図しない変更または誤用の機会を減らすために、Microsoft 365 の義務と責任領域を分離します。 Microsoft 365 チームは、役割を包括的な役割ベースのアクセス制御メカニズムの一部として定義しています。

## <a name="customer-content-isolation"></a>顧客コンテンツの分離

テナント内のすべての顧客コンテンツは、他のテナントと、Microsoft 365 の管理で使用される運用およびシステム データから分離されます。 Microsoft 365 には複数の保護形態が実装されており、Microsoft 365 のサービスやアプリケーションが侵害される危険を最小限に抑えることができます。 複数の形式の保護により、テナントまたは Microsoft 365 システム自体の情報への不正アクセスも防止されます。

Microsoft が Microsoft 365 内でテナント データの論理的な分離を実装する方法については [、「Microsoft 365](microsoft-365-tenant-isolation-overview.md)のテナント分離」を参照してください。