---
title: 手順 3. MICROSOFT 365 DEFENDERサービスの SOC カタログとの統合を計画する
description: Microsoft 365 Defenderをサービスのセキュリティ操作カタログに統合する基本。
keywords: インシデント, アラート, 調査, 相関関係, 攻撃, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365, インシデント対応, サイバー攻撃, secops, セキュリティ操作, soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f6cab6be7d41f1d71a6ccf69fbedfa616694ee78
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65438490"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>手順 3. MICROSOFT 365 DEFENDERサービスの SOC カタログとの統合を計画する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

確立されたセキュリティ オペレーション センター (SOC) には、次を含む可能性のあるサービスのカタログが必要です。

- 侵入&マルウェア分析
- リバース エンジニアリング&属性
- 脅威インテリジェンス
- 分析
- ハンティング調査
- フォレンジクス
- インシデント対応 
- コンピューター セキュリティ インシデント対応チーム (CSIRT) (SOC から分離される可能性があります) 
- コンプライアンス テスト
- インサイダー脅威&不正監視
- セキュリティ インシデント&イベント監視 
- 脆弱性スキャン
- 拡張検出と応答 (XDR)/セキュリティ オーケストレーション、自動化、応答 (SOAR)
- フィッシング詐欺
- データ損失防止
- ブランドの監視

Microsoft 365 Defenderテクノロジはさまざまな機能に及ぶため、SOC チームは、Microsoft 365 Defenderの各コンポーネントを管理し、サービス機能に合わせるのに最適なロールと責任を特定する必要があります。

Microsoft 365 Defenderのコンポーネントは次のとおりです。

- **Microsoft Defender for Identity** (旧称 Azure Advanced Threat Protection、別名 Azure ATP) は、Active Directory Domain Services (AD DS) シグナルを使用して高度な脅威、侵害された ID、悪意のあるインサイダー アクションを特定、検出、調査するクラウドベースのセキュリティ ソリューションです。組織。

- **Microsoft Defender for Endpoint** は、リスクベースの脆弱性の管理と評価、攻撃面の削減、行動ベースとクラウドを利用した次世代保護、エンドポイントでの検出と対応 (EDRを含むデバイス向けの包括的なクラウド配信エンドポイント セキュリティ ソリューションです。)、自動調査と修復、マネージド ハンティング サービス、豊富な API、統合セキュリティ管理。

 - **Microsoft Defender for Office 365** は、組織を未知のマルウェアやウイルスから保護するのに役立つクラウドベースの電子メール フィルター サービスです。堅牢なゼロデイ保護を提供し、組織を有害なリンクからリアルタイムで保護する機能が含まれています。 また、調査と捜索、対応と修復、認識とトレーニング、およびセキュリティで保護された姿勢機能の包括的なスレートも提供されます。

- **Microsoft Defender for Cloud Apps** は、ログ収集、API コネクタ、リバース プロキシなど、さまざまなデプロイ モードをサポートするクラウド アクセス セキュリティ ブローカー (CASB) です。 これにより、Microsoft およびサード パーティのすべてのクラウド サービス全体でサイバー脅威を特定して対処するための、豊富な可視性、データ移動の制御、高度な分析が提供されます。

Microsoft 365 Defenderコンポーネントとテクノロジはさまざまな機能に及ぶため、SOC チームは、Microsoft 365 Defenderの各コンポーネントを管理し、サービス機能に合わせるのに最適なロールと責任を判断する必要があります。

Microsoft 365 Defenderの機能を統合するには、SOC サービスを調整する必要があります。 Microsoft 365 Defenderの機能の詳細については、次の記事を参照してください。

- [Microsoft Defender for Endpoint とは](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
- [Microsoft Defender for Identity とは?](/defender-for-identity/what-is)
- [Defender for Office 365 とは](/microsoft-365/security/defender/microsoft-365-defender)
- [Microsoft Defender for Cloud Apps とは](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>次の手順

[手順 4.Microsoft 365 Defenderロール、責任、監視を定義する](integrate-microsoft-365-defender-secops-roles.md)
