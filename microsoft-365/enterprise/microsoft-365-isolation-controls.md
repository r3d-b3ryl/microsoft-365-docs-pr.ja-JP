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
description: 分離制御がネットワーク内でどのように機能Microsoft 365、必要に応じてサービスが相互運用または自律的な状態を維持できるようにします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464095"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 の分離コントロール 

Microsoft は継続的に、Microsoft 365 のマルチテナント アーキテクチャがエンタープライズ レベルのセキュリティ、機密性、プライバシー、整合性、ローカル、国際、可用性の標準をサポートします[。](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) Microsoft が提供するサービスの規模と範囲により、人間の重要なやり取りを使用してMicrosoft 365を管理することは困難で経済的ではありません。 Microsoft 365サービスは、複数のグローバルに分散されたデータ センターを介して提供され、それぞれが高度に自動化され、人間のタッチや顧客コンテンツへのアクセスを必要とする操作が少ない。 弊社のスタッフは、自動化されたツールと高度に安全なリモート アクセスを使用して、これらのサービスとデータ センターをサポートしています。 

Microsoft 365は、重要なビジネス機能を提供し、ビジネス エクスペリエンス全体に貢献する複数のサービスMicrosoft 365されています。 これらの各サービスは、自己格納型であり、互いに統合するように設計されています。

Microsoft 365は、次の原則に従って設計されています。

 - **[サービス指向アーキテクチャ](/previous-versions/aa480021(v=msdn.10)): 適切** に定義されたビジネス機能を提供する相互運用可能なサービスの形式でソフトウェアを設計および開発します。
 - **[運用セキュリティアシュア](https://www.microsoft.com/download/details.aspx?id=40872)ランス:** [Microsoft](https://www.microsoft.com/sdl/default.aspx)セキュリティ開発ライフサイクル [、Microsoft](https://technet.microsoft.com/library/dn440717.aspx)セキュリティ応答センター、サイバーセキュリティ脅威の状況に対する深い認識など、Microsoft 固有のさまざまな機能によって得られる知識を組み込んだフレームワーク。

Microsoft 365は相互に運用されますが、互いに独立した自律サービスとして展開および運用できるよう設計および実装されています。 Microsoft は、組織の資産の無許可または意図しない変更または誤用の機会を減らすMicrosoft 365の義務と責任領域を分離します。 Microsoft 365チームは、包括的な役割ベースのアクセス制御メカニズムの一部として役割を定義しています。

## <a name="customer-content-isolation"></a>顧客コンテンツの分離

テナント内のすべての顧客コンテンツは、他のテナントと、テナントの管理で使用される操作およびシステム データからMicrosoft 365。 Microsoft 365 には複数の保護形態が実装されており、Microsoft 365 のサービスやアプリケーションが侵害される危険を最小限に抑えることができます。 複数の形式の保護により、テナントまたはシステム自体の情報へのMicrosoft 365も防止されます。

Microsoft でテナント データの論理的な分離を実装する方法については、「Microsoft 365 でのテナントの分離」[を参照Microsoft 365。](microsoft-365-tenant-isolation-overview.md)