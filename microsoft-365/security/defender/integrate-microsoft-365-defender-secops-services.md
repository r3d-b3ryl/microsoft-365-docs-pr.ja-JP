---
title: 手順 3. サービスの SOC Microsoft 365 Defenderとの統合を計画する
description: サービスのセキュリティ操作カタログMicrosoft 365 Defender統合の基本。
keywords: インシデント、アラート、調査、相関関係、攻撃、デバイス、ユーザー、ID、ID、メールボックス、メール、365、microsoft、m365、インシデント対応、サイバー攻撃、secops、セキュリティ操作、soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7053616ebee7a0c8a63394e2db98704910d1ff10
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121449"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>手順 3. サービスの SOC Microsoft 365 Defenderとの統合を計画する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

確立されたセキュリティ 運用センター (SOC) には、次のようなサービスのカタログが含まれる必要があります。

- 侵入&マルウェア分析
- 属性&リバース エンジニアリング
- 脅威インテリジェンス
- 分析
- 狩猟調査
- フォレンジクス
- インシデント対応 
- コンピューター セキュリティ インシデント対応チーム (CSIRT) (SOC から分離される可能性があります) 
- コンプライアンス テスト
- インサイダーの脅威&監視
- セキュリティ インシデント&監視 
- 脆弱性スキャン
- 拡張検出と応答 (XDR)/セキュリティ オーケストレーション、オートメーション、および応答 (SOAR)
- フィッシング詐欺
- データ損失防止
- ブランドの監視

Microsoft 365 Defenderテクノロジはさまざまな機能にまたがっていますので、SOC チームは、Microsoft 365 Defender の各コンポーネントを管理し、サービス機能に合わせて調整するために最適な役割と責任を決定する必要があります。

次に示すMicrosoft 365 Defenderコンポーネントを示します。

- **Microsoft Defender for Identity** (旧 Azure Advanced Threat Protection( 旧 Azure ATP とも呼ばれる) は、Active Directory ドメイン サービス (AD DS) シグナルを使用して、組織向け高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、調査するクラウドベースのセキュリティ ソリューションです。

- **Microsoft Defender for Endpoint** は、リスクベースの 脆弱性の管理 と評価、攻撃表面の縮小、行動ベースおよびクラウドベースの次世代保護、エンドポイントの検出と応答 (EDR)、自動調査と修復、管理された狩猟サービス、豊富な API、統合セキュリティ管理を含むデバイス向け、総合的なクラウド提供エンドポイント セキュリティ ソリューションです。

 - **Microsoft Defender for Office 365** は、堅牢なゼロデイ保護を提供することで未知のマルウェアやウイルスから組織を保護し、組織を有害なリンクからリアルタイムで保護する機能を備えるクラウドベースの電子メール フィルター サービスです。 また、調査と狩猟、対応と修復、認識とトレーニング、安全な姿勢機能の包括的なスレートも提供します。

- **Microsoft Defender for Cloud Apps** は、ログ 収集、API コネクタ、リバース プロキシなど、さまざまな展開モードをサポートするクラウド アクセス セキュリティ ブローカー (CASB) です。 豊富な可視性、データ移動の制御、高度な分析を提供し、Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定し、対処します。

Microsoft 365 Defenderコンポーネントとテクノロジはさまざまな機能にまたがるため、SOC チームは、Microsoft 365 Defender の各コンポーネントを管理し、サービス機能に合わせて調整するために最適な役割と責任を決定する必要があります。

サービスの機能を統合するにはMicrosoft 365 Defender SOC サービスを絞り込む必要があります。 アプリケーションの機能の詳細については、Microsoft 365 Defender記事を参照してください。

- [Microsoft Defender for Endpoint とは](/defender-endpoint/microsoft-defender-endpoint)
- [Microsoft Defender for Identity とは?](/defender-for-identity/what-is)
- [Defender for Office 365 とは](/office-365-security/defender-for-office-365)
- [Microsoft Defender for Cloud Apps とは](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>次の手順

[手順 4.役割Microsoft 365 Defender監督の定義](integrate-microsoft-365-defender-secops-roles.md)
