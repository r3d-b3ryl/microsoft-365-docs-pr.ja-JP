---
title: Contoso Corporation の概要
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ビジネスとしての Contoso Corporation について、さらに同社の世界規模のオフィスの階層構造について説明します。
ms.openlocfilehash: 402c8c1cbb1484d8a0ad2ce4159b90107856167d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637081"
---
# <a name="overview-of-contoso-corporation"></a>Contoso Corporation の概要

![Contoso 社](../media/contoso-overview/contoso-icon.png)

Contoso Corporation は、パリに本社がある多国籍企業です。同社は、10万を超える製品を使用した製造、販売、サポートの組織です。

## <a name="contoso-around-the-world"></a>世界の Contoso

図1は、パリ、地域ハブ、およびさまざまな大陸のサテライトオフィスの本社を示しています。

![世界各地の Contoso 支社](../media/contoso-overview/contoso-overview-fig1.png)

**図 1: 世界各地の Contoso 支社**
 
Contoso には、次の3つのオフィスの層があります。

- 本社

  Contoso 本社は、パリの outskirts にある企業キャンパスで、多数の建物を管理、エンジニアリング、製造施設に備えています。Contoso データセンターとそのインターネットプレゼンスは、すべてパリ本社に収納されています。

  本社には 25,000 人のワーカーがいます。

- 地域ハブ

  ハブオフィスは、世界の特定の地域 (60% の売上とサポートスタッフ) を提供します。各地域ハブは、広帯域 WAN リンクを介してパリ本社に接続されています。

  地域ハブには、平均2000ワーカーがあります。

- サテライト オフィス

  サテライトオフィスには、80% の売上およびサポートスタッフが含まれています。これにより、重要都市または subregions の Contoso お客様のためのオンサイトプレゼンスが提供されます。各サテライトオフィスは、広帯域 WAN リンクを介して地域のハブに接続されています。

  サテライトオフィスには、平均で250ワーカーがあります。

Contoso の従業員の約25% は、モバイルのみです。 これらのワーカーの数は、地域ハブとサテライトオフィスの割合が高くなります。 モバイル専門のワーカーにより良いサポートを提供することが、Contoso 社の重要なビジネス目標です。

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>Microsoft 365 for enterprise の設計上の考慮事項

Contoso 社の IT アーキテクトは、エンタープライズ向けの Microsoft 365 を展開するための以下の設計要件を特定しました。

- 地理的に複数の場所にあり、地域に応じた規制とコンプライアンスの要件がある
- 本社オフィスの中央イントラネットデータセンターと、内部の基幹業務アプリケーションをホストする地域のアプリケーションサーバー
- 既存の Microsoft Endpoint Configuration Manager インフラストラクチャ
- Windows、Mac、Linux を実行するクライアントコンピューティングデバイスの組み合わせ
- iOS (iPhone と iPad) や Android のスマートフォンやタブレットを含め、個人および会社が所有するモバイル デバイスは各種混合
- リモートおよびモバイルのワーカーが多数
- ビジネス パートナーが多数
- 顧客やその他の機密情報を管理および保護するための、多くの機密情報
- 製品の設計仕様、および製造上の機密情報の形式で、重要な知的財産の量が多い

## <a name="next-step"></a>次の手順

Contoso 社のオンプレミスの IT インフラストラクチャと、企業のビジネスニーズが Microsoft 365 for enterprise でどのように扱われるかについて[説明](contoso-infra-needs.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
