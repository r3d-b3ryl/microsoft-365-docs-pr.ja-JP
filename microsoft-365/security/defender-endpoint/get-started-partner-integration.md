---
title: Microsoft Defender for Endpoint パートナーになる
ms.reviewer: ''
description: ソリューションを Microsoft Defender for Endpoint と統合し、パートナーになる手順と要件について説明します。
keywords: パートナー、統合、ソリューション検証、認定、要件、メンバー、ミス、アプリケーション ポータル
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 988632e84614b49262c9cc7b8a74b493c1a48b01
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171973"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Microsoft Defender for Endpoint パートナーになる

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Defender for Endpoint ソリューション パートナーになるためには、次の手順に従って完了する必要があります。

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-license"></a>手順 1: Microsoft Defender for Endpoint ライセンスをサブスクライブする

Defender for Endpoint を試す場合は、 [無料試用版にサインアップします。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink) サブスクライブを使用すると、最大 3 つのデバイスを備える Microsoft Defender for Endpoint テナントを使用して、Microsoft Defender for Endpoint と統合するソリューションを開発できます。

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>手順 2: ソリューションの検証と認定の要件を満たす

テクノロジ パートナーが統合が機能することを証明する最善の方法は、共同顧客に提案された統合設計を承認し (顧客は Microsoft Defender セキュリティ センターの [パートナー アプリケーション[](https://securitycenter.microsoft.com/interoperability/partners)] ページの [パートナー アプリケーションの推奨] オプションを使用して)、Microsoft Defender for Endpoint チームにテストしてデモを行う方法です。

Microsoft Defender for Endpoint チームが統合を確認して承認したら、Microsoft インテリジェント セキュリティ協会にパートナーとして参加するように指示します。

## <a name="step-3-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>手順 3: Microsoft Defender for Endpoint パートナー アプリケーション ポータルに表示される情報を取得する

Microsoft Defender for Endpoint は、Microsoft Defender for Endpoint[](partner-applications.md)管理ポータルに埋め込まれている製品内パートナー ページを使用して、サードパーティアプリケーションの検出と統合をサポートします。

会社をパートナーとして製品内パートナー ページに表示するには、次の情報を提供する必要があります。

1. 四角形のロゴ (SVG)。
2. 表示する製品の名前。
3. 15 語の製品の説明を入力します。
4. 顧客のための十分な情報を含む統合またはブログ投稿を完了するためのランディング ページへのリンク。 Microsoft Defender for Endpoint 製品名を含むすべてのプレスリリースは、マーケティングチームとエンジニアリング チームによって確認する必要があります。 レビュープロセスが完了するまで、少なくとも 10 日間待ちます。
5. マルチテナント の方法を使用Azure AD、アプリケーションの使用状況を追跡Azure ADアプリケーション名が必要になります。
6. Microsoft Defender for Endpoint User-Agent一連の API またはセキュリティ API に対して行われた各 API 呼び出しに、Graphフィールドを含める。 これは、統計的な目的、トラブルシューティング、およびパートナー認識に使用されます。 さらに、この手順は、Microsoft インテリジェント セキュリティアソシエーション (MISA) のメンバーシップの要件です。

   次の手順を実行します。

   - 各 HTTP 要求ヘッダーUser-Agentフィールドを以下の形式に設定します。

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     たとえば、User-Agent は次のようになります。

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - 詳細については [、「RFC 2616 section-14.43」を参照してください](https://tools.ietf.org/html/rfc2616#section-14.43)。

Microsoft Defender for Endpoint とのパートナーシップは、相互のお客様が防御をさらに合理化、統合、および調整するのに役立ちます。 Microsoft Defender for Endpoint パートナーになり、最新の脅威を一緒に防止して対応することで、顧客とその資産を効果的に保護する共通の目標を達成することを選んだのは嬉しく思います。

## <a name="misa-nomination"></a>MISA の指名 
マネージド セキュリティ サービス プロバイダー (MSSP) と独立したソフトウェア ベンダー (ISV) は、Microsoft インテリジェント セキュリティ アソシエーション (MISA) にノミネートできます。 詳細については [、「MISA 情報ページ」を参照してください](https://www.microsoft.com/security/business/intelligent-security-association)。


## <a name="related-topics"></a>関連項目

- [テクニカル パートナーの機会](partner-integration.md)
