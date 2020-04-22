---
title: Microsoft の脅威保護によってサポートされるサービスを展開する
description: Microsoft の脅威保護、ライセンスの要件、および展開手順によって統合できる Microsoft セキュリティサービスについて説明します。
keywords: 展開、ライセンス、サポートされているサービス、プロビジョニング、構成 Microsoft Threat Protection、M365、ライセンス資格、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、MCAS、advanced Threat Protection、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c29027bb641530ba2d3c7a22c578770c098f53ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633473"
---
# <a name="deploy-supported-services"></a>サポートされるサービスを展開する

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft の脅威保護](microsoft-threat-protection.md)では、さまざまな microsoft セキュリティサービスが統合され、高度な攻撃に対する一元的な検出、防止、調査の機能を提供します。 この記事では、サポートされるサービス、ライセンス要件、1つ以上のサービスの展開に関連する利点と制限事項、およびそれらを個別に完全に展開する方法へのリンクについて説明します。

## <a name="supported-services"></a>サポートされるサービス
Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンス、あるいはライセンスの有効な組み合わせにより、次のサポートされているサービスへのアクセスが可能になり、microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用できるようになります。 [ライセンス要件を参照してください。](prerequisites.md#licensing-requirements)

| サポートされるサービス | 説明 |
| ------ | ------ |
| Microsoft Defender ATP | 強力な動作センサー、クラウド分析、脅威インテリジェンスに基づいて構築されたエンドポイント保護スイート |
| Office 365 ATP | Office 365 でのアプリとデータの高度な保護 (電子メールやその他のコラボレーションツールを含む) |
| Azure ATP | 高度な脅威、侵害された id、および悪意のある内部者に対して、関連付けられた Active Directory シグナルを使用した防御 |
| Microsoft Cloud App Security | Microsoft およびサードパーティ製のクラウドサービスの脅威を特定し、戦闘する |

## <a name="deployed-services-and-functionality"></a>展開されたサービスと機能
Microsoft の脅威保護では、より多くのサポートされるサービスを展開することにより、可視性、相互関係、および修復が向上します。

### <a name="benefits-of-full-deployment"></a>完全な展開の利点
Microsoft の脅威保護の完全なメリットを得るために、サポートされているすべてのサービスを展開することをお勧めします。 完全な展開の主な利点は次のとおりです。
- インシデントは、利用可能なすべてのセンサーおよびサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連しています。
- 自動化された調査と修復 (AIR) のプレイブックは、デバイス、メールボックス、ユーザーアカウントなどのさまざまなエンティティの種類に適用されます。
- デバイス、メールボックス、およびその他のエンティティのイベントおよびエンティティデータについて、より詳細な検索スキーマを照会することができます。

### <a name="limited-deployment-scenarios"></a>限定的な展開シナリオ
展開するサポートされているサービスごとに、非常に豊富な未加工の信号と、相関情報が提供されます。 制限のある展開では、Microsoft の脅威保護機能がオフになることはありませんが、エンドポイント間で包括的な可視性を提供する機能、アプリ、データ、および id が影響を受けることはありません。 同時に、すべての修復機能は、展開したサービスで管理できるエンティティにのみ適用されます。

次の表に、サポートされている各サービスが追加データを提供する方法、データを関連付けることによってさらに詳細な情報を得る方法、および改善と応答の機能を示します。

| サービス | データ (& 関連付けられる情報) | 修復 & 応答の範囲 |
| ------ | ------ | ------ |
| Microsoft Defender ATP | -エンドポイントの状態と生のイベント<br />-ウイルス対策、EDR、攻撃対象領域の削減を含むエンドポイントの検出と通知<br />-エンドポイントで監視されたファイルやその他のエンティティに関する情報 | エンドポイント |
| Office 365 ATP | -メールとメールボックスの状態および生のイベント<br />-電子メール、添付ファイル、およびリンクの検出 | -メールボックス<br />-Microsoft 365 アカウント |
| Azure ATP | -Active Directory シグナル (認証イベントを含む)<br />-Id 関連の動作の検出 | ID |
| Microsoft Cloud App Security | -承認されていないクラウドアプリおよびサービスの検出 (シャドウ IT)<br />-クラウドアプリへのデータの公開<br />-クラウドアプリに関連付けられている脅威アクティビティ | クラウド アプリ |

## <a name="deploy-the-services"></a>サービスを展開する
通常、各サービスを展開するには、テナントに対するプロビジョニングと、いくつかの初期構成が必要です。 これらの各サービスの展開方法については、次の表を参照してください。

| サービス | プロビジョニング手順 | 初期構成 |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Microsoft Defender ATP 展開ガイド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *プロビジョニングの手順を参照してください。* |
| Office 365 ATP | *なし。 Office 365 でプロビジョニングされます。* | [ATP ポリシーを構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [クイックスタート: Azure ATP インスタンスを作成する](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *プロビジョニングの手順を参照してください。* |
| Microsoft Cloud App Security | *なし* | [クイックスタート: Microsoft Cloud App Security を使い始める](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

サポートされているサービスを展開したら、 [Microsoft の脅威保護を有効](mtp-enable.md)にします。

## <a name="related-topics"></a>関連項目

- [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
- [Microsoft Threat Protection を有効にする](mtp-enable.md)
- [Microsoft Defender ATP の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
