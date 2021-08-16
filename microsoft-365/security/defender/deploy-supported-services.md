---
title: ユーザーがサポートするサービスをMicrosoft 365 Defender
description: ユーザーのライセンス要件、および展開手順によって統合Microsoft 365 Defender Microsoft のセキュリティ サービスについて説明します。
keywords: 展開、ライセンス、サポートされるサービス、プロビジョニング、構成 Microsoft 365 Defender、M365、ライセンスの適格性、Microsoft Defender for Endpoint、Office 365 用 Microsoft Defender、Microsoft Defender for Identity、Microsoft Cloud App Security、MCAS、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4a3aac06f19c7ed86af67f3b72bac8bf367628a8
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58258464"
---
# <a name="deploy-supported-services"></a>サポートされているサービスを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) Microsoft のセキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、および調査機能を提供します。 この記事では、サポートされているサービス、ライセンス要件、1 つ以上のサービスの展開に関連する利点と制限、およびそれらを個別に完全に展開する方法へのリンクについて説明します。

## <a name="supported-services"></a>サポートされているサービス
E5 Microsoft 365 E5、A5、または A5 のセキュリティ ライセンス、またはライセンスの有効な組み合わせにより、以下のサポートされているサービスにアクセスし、Microsoft 365 Defender を使用できます。 [「ライセンス要件」を参照してください。](prerequisites.md#licensing-requirements)

| サポートされているサービス | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 強力な行動センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート |
|Microsoft Defender for Office 365 | メールなどのコラボレーション ツールを含む、Office 365データの高度な保護 |
| Microsoft Defender for Identity | 関連付けされた Active Directory シグナルを使用して、高度な脅威、侵害された ID、悪意のあるインサイダーから防御する |
| Microsoft Cloud App Security | Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定して対処する |

## <a name="deployed-services-and-functionality"></a>展開されたサービスと機能
Microsoft 365 Defenderサポートされているサービスを展開する場合、より良い可視性、相関関係、および修復が提供されます。

### <a name="benefits-of-full-deployment"></a>完全展開の利点
このサービスの完全な利点を得Microsoft 365 Defenderサポートされているサービスを展開することをお勧めします。 完全展開の主な利点を次に示します。
- インシデントは、使用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連付けされます。
- 自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。
- デバイス、メールボックス、その他のエンティティからのイベントおよびエンティティ データに対して、より包括的な高度なハンティング スキーマを照会できます。

### <a name="limited-deployment-scenarios"></a>限られた展開シナリオ
展開するサポートされている各サービスは、生の信号と関連情報の非常に豊富なセットを提供します。 限定的な展開では、Microsoft 365 Defender機能がオフになされませんが、エンドポイント、アプリ、データ、および ID 全体で包括的な可視性を提供する機能が影響を受ける。 同時に、修復機能は、展開したサービスによって管理できるエンティティにのみ適用されます。

次の表に、サポートされている各サービスが追加のデータを提供する方法、データを関連付けて追加の分析情報を取得する機会、および改善と対応の機能を示します。

| サービス | データ (関連情報&シグナル) | 応答スコープ&修復 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | - エンドポイントの状態と生のイベント<br />- ウイルス対策、ウイルス対策、脅威、攻撃EDRを含むエンドポイントの検出とアラート<br />- エンドポイントで観察されたファイルや他のエンティティに関する情報 | エンドポイント |
|Microsoft Defender for Office 365 | - メールとメールボックスの状態と生のイベント<br />- メール、添付ファイル、およびリンクの検出 | - メールボックス<br />- Microsoft 365アカウント |
| Microsoft Defender for Identity | - Active Directory 信号 (認証イベントを含む)<br />- ID 関連の動作の検出 | ID |
| Microsoft Cloud App Security | - 非許可のクラウド アプリとサービスの検出 (シャドウ IT)<br />- クラウド アプリへのデータの露出<br />- クラウド アプリに関連付けられた脅威アクティビティ | クラウド アプリ |

## <a name="deploy-the-services"></a>サービスの展開
通常、各サービスを展開するには、テナントへのプロビジョニングと初期構成が必要です。 これらの各サービスの展開方法については、次の表を参照してください。

| サービス | プロビジョニング手順 | 初期構成 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint 展開ガイド](../defender-endpoint/deployment-phases.md) | *「プロビジョニングの手順」を参照してください。* |
|Microsoft Defender for Office 365 | *None、プロビジョニングは、Office 365* | [Microsoft Defender for Office 365 のポリシーを構成する](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [クイック スタート: Microsoft Defender for Identity インスタンスを作成する](/azure-advanced-threat-protection/install-atp-step1) | *「プロビジョニングの手順」を参照してください。* |
| Microsoft Cloud App Security | *なし* | [クイック スタート: クイック スタートMicrosoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

サポートされているサービスを展開したら、[次の](m365d-enable.md)Microsoft 365 Defender。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)
- [Microsoft Defender for Endpoint の概要](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365概要](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security の概要](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity の概要](/azure-advanced-threat-protection/what-is-atp)
