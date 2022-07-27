---
title: Microsoft Defender for Endpoint パートナーになる
ms.reviewer: ''
description: ソリューションをMicrosoft Defender for Endpointと統合し、パートナーになる手順と要件について説明します
keywords: パートナー, 統合, ソリューション検証, 認定, 要件, メンバー, misa, application portal
ms.prod: m365-security
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
ms.openlocfilehash: 276f411699f4a9db61850a04da3ff18d3c6bb2a7
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051208"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Microsoft Defender for Endpoint パートナーになる

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Defender for Endpoint ソリューション パートナーになるには、次の手順に従って完了する必要があります。

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-license"></a>手順 1: Microsoft Defender for Endpoint ライセンスをサブスクライブする

Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink). サブスクライブを使用すると、最大 3 台のデバイスでMicrosoft Defender for Endpoint テナントを使用して、Microsoft Defender for Endpointと統合するソリューションを開発できます。

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>手順 2: ソリューションの検証と認定要件を満たす

テクノロジ パートナーが統合機能を認定する最善の方法は、共同顧客が推奨される統合設計を承認することです (顧客は、Microsoft 365 Defenderの **[パートナー** アプリケーション] ページの [パートナー アプリケーション] ページでパートナー オプション\(パートナーと API >[パートナー アプリケーション](https://security.microsoft.com/interoperability/partnersapps)\)の推奨を使用し、テストしてデモを行うことができます。Microsoft Defender for Endpointチーム。

Microsoft Defender for Endpoint チームが統合を確認して承認したら、Microsoft Intelligent Security Association のパートナーとして参加するよう指示します。

## <a name="step-3-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>手順 3: Microsoft Defender for Endpoint パートナー アプリケーション ポータルに一覧表示する

Microsoft Defender for Endpointでは、Microsoft Defender for Endpoint管理ポータルに埋め込まれている製品内[パートナー ページ](partner-applications.md)を使用したサード パーティ製アプリケーションの検出と統合がサポートされます。

会社を製品内パートナー ページにパートナーとして表示するには、次の情報を指定する必要があります。

1. 正方形のロゴ (SVG)。
2. 表示する製品の名前。
3. 15 語の製品説明を入力します。
4. 顧客に十分な情報を含む統合またはブログ投稿を完了するための顧客のランディング ページにリンクします。 Microsoft Defender for Endpoint製品名を含むすべてのプレス リリースは、マーケティングチームとエンジニアリング チームが確認する必要があります。 確認プロセスが完了するまで少なくとも 10 日間待ちます。
5. マルチテナント Azure AD アプローチを使用する場合は、アプリケーションの使用状況を追跡するために Azure AD アプリケーション名が必要になります。
6. パブリック API または Graph Security API のセットMicrosoft Defender for Endpoint行う各 API 呼び出しに、User-Agent フィールドを含めます。 これは、統計目的、トラブルシューティング、およびパートナー認識に使用されます。 さらに、この手順は、Microsoft インテリジェント セキュリティ アソシエーション (MISA) のメンバーシップの要件です。

   次の手順を実行します。

   - 各 HTTP 要求ヘッダーのUser-Agent フィールドを次の形式に設定します。

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     たとえば、User-Agent:

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - 詳細については、 [RFC 2616 セクション 14.43 を](https://tools.ietf.org/html/rfc2616#section-14.43)参照してください。

Microsoft Defender for Endpointとのパートナーシップは、相互のお客様が防御をさらに合理化、統合、調整するのに役立ちます。 お客様がMicrosoft Defender for Endpointパートナーになることを選択し、現代の脅威を一緒に防止し、対応することで、お客様とその資産を効果的に保護するという共通の目標を達成することを選択されたことをうれしく思います。

## <a name="misa-nomination"></a>MISA の指名 
マネージド セキュリティ サービス プロバイダー (MSSP) と独立系ソフトウェア ベンダー (ISV) は、Microsoft インテリジェント セキュリティ アソシエーション (MISA) に指定できます。 詳細については、 [MISA 情報ページを](https://www.microsoft.com/security/business/intelligent-security-association)参照してください。


## <a name="related-topics"></a>関連トピック

- [テクニカル パートナーの機会](partner-integration.md)
