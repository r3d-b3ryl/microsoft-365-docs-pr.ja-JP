---
title: Microsoft 365 Defender がサポートするサービスを展開する
description: Microsoft 365 Defender によって統合できる Microsoft セキュリティ サービス、ライセンス要件、展開手順について説明します。
keywords: 展開、ライセンス、サポートされるサービス、プロビジョニング、構成 Microsoft Threat Protection、M365、ライセンス適格性、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、MCAS、Advanced Threat Protection、E5、A5、EMS
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
ms.openlocfilehash: 434c318be404ffb04cac7a05664c8f001bb46507
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198863"
---
# <a name="deploy-supported-services"></a>サポートされているサービスを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender は](microsoft-365-defender.md) 、さまざまな Microsoft セキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、および調査機能を提供します。 この記事では、サポートされているサービス、ライセンス要件、1 つ以上のサービスの展開に関連する利点と制限、およびそれらを個別に完全に展開する方法へのリンクについて説明します。

## <a name="supported-services"></a>サポートされているサービス
Microsoft 365 E5、E5 Security、A5、または A5 セキュリティ ライセンス、またはライセンスの有効な組み合わせにより、次のサポートされているサービスにアクセスし、Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用できます。 [「ライセンス要件」を参照してください。](prerequisites.md#licensing-requirements)

| サポートされているサービス | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 強力な行動センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート |
|Microsoft Defender for Office 365 | メールなどのコラボレーション ツールを含む、Office 365 でのアプリとデータの高度な保護 |
| Microsoft Defender for Identity | 関連付けされた Active Directory シグナルを使用して、高度な脅威、侵害された ID、悪意のあるインサイダーから防御する |
| Microsoft Cloud App Security | Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定して対処する |

## <a name="deployed-services-and-functionality"></a>展開されたサービスと機能
Microsoft 365 Defender は、サポートされるサービスの展開に合って、可視性、相関関係、修復を向上します。

### <a name="benefits-of-full-deployment"></a>完全展開の利点
Microsoft 365 Defender の完全な利点を得る場合は、サポートされているサービスを展開することをお勧めします。 完全展開の主な利点を次に示します。
- インシデントは、使用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連付けされます。
- 自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。
- デバイス、メールボックス、その他のエンティティからのイベントおよびエンティティ データに対して、より包括的な高度なハンティング スキーマを照会できます。

### <a name="limited-deployment-scenarios"></a>限られた展開シナリオ
展開するサポートされている各サービスは、生の信号と関連情報の非常に豊富なセットを提供します。 限定的な展開では Microsoft 365 Defender の機能がオフにされませんが、エンドポイント、アプリ、データ、および ID 全体で包括的な可視性を提供する機能が影響を受ける。 同時に、修復機能は、展開したサービスによって管理できるエンティティにのみ適用されます。

次の表に、サポートされている各サービスが追加のデータを提供する方法、データを関連付けて追加の分析情報を取得する機会、および改善と対応の機能を示します。

| サービス | データ (関連情報&シグナル) | 応答スコープ&修復 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | - エンドポイントの状態と生のイベント<br />- ウイルス対策、EDR、攻撃表面の縮小などのエンドポイントの検出とアラート<br />- エンドポイントで観察されたファイルや他のエンティティに関する情報 | エンドポイント |
|Microsoft Defender for Office 365 | - メールとメールボックスの状態と生のイベント<br />- メール、添付ファイル、およびリンクの検出 | - メールボックス<br />- Microsoft 365 アカウント |
| Microsoft Defender for Identity | - Active Directory 信号 (認証イベントを含む)<br />- ID 関連の動作の検出 | ID |
| Microsoft Cloud App Security | - 非許可のクラウド アプリとサービスの検出 (シャドウ IT)<br />- クラウド アプリへのデータの露出<br />- クラウド アプリに関連付けられた脅威アクティビティ | クラウド アプリ |

## <a name="deploy-the-services"></a>サービスの展開
通常、各サービスを展開するには、テナントへのプロビジョニングと初期構成が必要です。 これらの各サービスの展開方法については、次の表を参照してください。

| サービス | プロビジョニング手順 | 初期構成 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint 展開ガイド](../defender-endpoint/deployment-phases.md) | *「プロビジョニングの手順」を参照してください。* |
|Microsoft Defender for Office 365 | *None(365 Officeプロビジョニング)* | [Microsoft Defender for Office 365 のポリシーを構成する](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [クイック スタート: Microsoft Defender for Identity インスタンスを作成する](/azure-advanced-threat-protection/install-atp-step1) | *「プロビジョニングの手順」を参照してください。* |
| Microsoft Cloud App Security | *なし* | [クイック スタート: Microsoft Cloud App Security の使用を開始する](/cloud-app-security/getting-started-with-cloud-app-security) |

サポートされているサービスを展開したら [、Microsoft 365 Defender をオンにしてください](m365d-enable.md)。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender の概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)
- [Microsoft Defender for Endpoint の概要](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365 の概要](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security の概要](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity の概要](/azure-advanced-threat-protection/what-is-atp)
