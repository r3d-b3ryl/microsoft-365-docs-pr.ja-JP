---
title: Contoso Corporation の概要
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ビジネスとしての Contoso Corporation について、さらに同社の世界規模のオフィスの階層構造について説明します。
ms.openlocfilehash: ec9df867252fe672f73dc7387c996f23ba476726
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093462"
---
# <a name="overview-of-contoso-corporation"></a>Contoso Corporation の概要

Contoso Corporation は、パリに本社を置く多国籍企業です。 会社は、100,000 を超える製品を持つ製造、販売、およびサポート組織です。

## <a name="contoso-around-the-world"></a>世界の Contoso

図 1 は、パリの本社オフィスと、さまざまな大陸の地域ハブとサテライト オフィスを示しています。

![世界中の Contoso オフィス。](../media/contoso-overview/contoso-overview-fig1.png)

**図 1: 世界中の Contoso オフィス**
 
Contoso には、次の 3 つのレベルのオフィスがあります。

- Headquarters

  Contoso 本社は、パリの郊外にある企業キャンパスで、管理、エンジニアリング、製造施設用に数十の建物があります。 Contoso のすべてのデータセンターとそのインターネットプレゼンスは、パリ本社に格納されています。

  本社には 25,000 人のワーカーがいます。

- 地域ハブ

  ハブ オフィスは、60% の売上とサポート スタッフを持つ世界の特定の地域にサービスを提供しています。 各リージョン ハブは、高帯域幅 WAN リンクを介してパリ本社に接続されます。

  地域ハブの平均従業員数は 2,000 人です。

- サテライト オフィス

  サテライト オフィスには、80% の売上とサポート スタッフが含まれています。 主要な都市またはサブリージョンで Contoso のお客様にオンサイトプレゼンスを提供します。 各サテライト オフィスは、高帯域幅 WAN リンクを介してリージョン ハブに接続されます。

  サテライト オフィスには、平均 250 人の従業員がいます。

Contoso の従業員の約 25% がモバイル専用です。 地域のハブとサテライト オフィスには、これらのワーカーの割合が高くなります。 モバイル専門のワーカーにより良いサポートを提供することが、Contoso 社の重要なビジネス目標です。

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>エンタープライズ向けのMicrosoft 365の設計に関する考慮事項

Contoso IT アーキテクトは、エンタープライズ向けのMicrosoft 365を展開するための次の設計要件要因を特定しました。

- 地理的に複数の場所にあり、地域に応じた規制とコンプライアンスの要件がある
- 社内基幹業務アプリケーションをホストする、本社オフィスと地域のアプリケーション サーバー内の中央イントラネット データセンター
- 既存の Microsoft Endpoint Configuration Manager インフラストラクチャ
- Windows、Mac、Linux を実行するクライアント コンピューティング デバイスの組み合わせ
- iOS (iPhone と iPad) や Android のスマートフォンやタブレットを含め、個人および会社が所有するモバイル デバイスは各種混合
- リモートおよびモバイルのワーカーが多数
- ビジネス パートナーが多数
- 管理およびセキュリティ保護のための大量の顧客およびその他の機密情報
- 製品の設計仕様、および製造上の機密情報の形式で、重要な知的財産の量が多い

## <a name="next-step"></a>次の手順

Contoso Corporation [のオンプレミス IT インフラストラクチャ](contoso-infra-needs.md)と、企業向けのMicrosoft 365を使用して会社のビジネス ニーズに対処する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
