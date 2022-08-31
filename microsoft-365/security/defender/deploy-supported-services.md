---
title: Microsoft 365 Defenderでサポートされているサービスをデプロイする
description: Microsoft 365 Defenderによって統合できる Microsoft セキュリティ サービス、ライセンス要件、展開手順について説明します
keywords: デプロイ, ライセンス, サポートされているサービス, プロビジョニング, 構成Microsoft 365 Defender, M365, ライセンスの適格性, Microsoft Defender for Endpoint, Microsoft Defender for Office 365,Microsoft Defender for Identity、Microsoft Cloud App Security、MCAS、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365solution-getstarted
- highpri
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 8c7b5f44097bcf2e18b1b9d39e82c4ca468c38aa
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480715"
---
# <a name="deploy-supported-services"></a>サポートされているサービスを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md)さまざまな Microsoft セキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、および調査機能を提供します。 この記事では、サポートされているサービス、そのライセンス要件、1 つ以上のサービスのデプロイに関連する利点と制限事項、およびそれらを個別に完全にデプロイする方法へのリンクについて説明します。

## <a name="supported-services"></a>サポートされているサービス

Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティ ライセンス、または有効なライセンスの組み合わせにより、サポートされている次のサービスにアクセスでき、Microsoft 365 Defenderを使用できます。 [ライセンス要件を確認する](prerequisites.md#licensing-requirements)

| サポートされているサービス | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 強力な行動センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート |
|Microsoft Defender for Office 365 | メールやその他のコラボレーション ツールを含む、Office 365内のアプリとデータの高度な保護 |
| Microsoft Defender for Identity | 高度な脅威、侵害された ID、悪意のあるインサイダーから、相関 Active Directory 信号を使用して防御する |
| Microsoft Defender for Cloud Apps | Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定して対処する |

## <a name="deployed-services-and-functionality"></a>デプロイされたサービスと機能

Microsoft 365 Defenderでは、より多くのサポートされているサービスをデプロイすると、可視性、相関関係、修復が向上します。

### <a name="benefits-of-full-deployment"></a>完全デプロイの利点

Microsoft 365 Defenderの完全な利点を得るには、サポートされているすべてのサービスをデプロイすることをお勧めします。 ここでは、完全な展開の主なメリットをご紹介します。

- 使用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント信号に基づいて、インシデントが識別され、関連付けられます
- 自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。
- より包括的な高度なハンティング スキーマを、デバイス、メールボックス、およびその他のエンティティからのイベントデータとエンティティ データに対して照会できます。

### <a name="limited-deployment-scenarios"></a>限定的な展開シナリオ

デプロイするサポートされている各サービスは、非常に豊富な未加工のシグナルセットと、関連付けられた情報を提供します。 展開が制限されている場合、Microsoft 365 Defender機能が無効になることはありませんが、エンドポイント、アプリ、データ、ID 全体で包括的な可視性を提供する機能は影響を受けます。 同時に、修復機能は、展開したサービスで管理することができるエンティティにのみ適用されます。

次の表は、サポートされている各サービスが追加のデータを提供する方法、データを関連付けることで追加の分析情報を取得する機会、改善と対応の機能を示しています。

| サービス | データ (相関情報&シグナル) | 修復&応答スコープ |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint |<ul><li>エンドポイントの状態と未加工のイベント</li><li>ウイルス対策、EDR、攻撃面の縮小など、エンドポイントの検出とアラート</li><li>エンドポイントで観察されるファイルとその他のエンティティに関する情報</li></ul> | エンドポイント |
|Microsoft Defender for Office 365 |<ul><li>メールとメールボックスの状態と未加工のイベント</li><li>Email、添付ファイル、リンクの検出</li></ul> | <ul><li>メールボックス</li><li>Microsoft 365 アカウント</li></ul> |
| Microsoft Defender for Identity |<ul><li>認証イベントを含む Active Directory シグナル</li><li>ID 関連の動作検出</li></ul> | ID |
| Microsoft Defender for Cloud Apps |<ul><li>承認されていないクラウド アプリとサービスの検出 (シャドウ IT)</li><li>クラウド アプリへのデータの公開</li><li>クラウド アプリに関連付けられた脅威アクティビティ</li></ul> | クラウド アプリ |

## <a name="deploy-the-services"></a>サービスの展開

各サービスを展開するには、通常、テナントへの事前設定といくつかの初期構成が必要です。 これらのサービスを展開する方法については、次のテーブルを参照してください。

| サービス | 事前設定の手順 | 初期構成 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint 展開ガイド](../defender-endpoint/deployment-phases.md) | *事前設定の手順を確認する* |
|Microsoft Defender for Office 365 | *なし、Office 365 で事前設定済み* | [Microsoft Defender for Office 365 のポリシーを構成する](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [クイックスタート: Microsoft Defender for Identity インスタンスを作成する](/azure-advanced-threat-protection/install-atp-step1) | *事前設定の手順を確認する* |
| Microsoft Defender for Cloud Apps | *なし* | [クイックスタート: Microsoft Defender for Cloud Apps の使用を開始する](/cloud-app-security/getting-started-with-cloud-app-security) |

サポートされているサービスをデプロイしたら、[Microsoft 365 Defenderを有効にします](m365d-enable.md)。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)
- [Microsoft Defender for Endpointの概要](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365の概要](../office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps の概要](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identityの概要](/azure-advanced-threat-protection/what-is-atp)
