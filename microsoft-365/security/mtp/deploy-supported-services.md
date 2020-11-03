---
title: Microsoft 365 Defender でサポートされているサービスを展開する
description: Microsoft 365 Defender に統合できる Microsoft セキュリティサービス、ライセンス要件、および展開手順について説明します。
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4a1bed4d6c6688c266b9df8ce36e4b25a0632d68
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843926"
---
# <a name="deploy-supported-services"></a>サポートされるサービスを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) は、さまざまな microsoft セキュリティサービスを統合して、高度な攻撃に対して集中化された検出、防止、調査の機能を提供します。 この記事では、サポートされるサービス、ライセンス要件、1つ以上のサービスの展開に関連する利点と制限事項、およびそれらを個別に完全に展開する方法へのリンクについて説明します。

## <a name="supported-services"></a>サポートされるサービス
Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンス、あるいはライセンスの有効な組み合わせにより、次のサポートされているサービスへのアクセスが可能になり、microsoft 365 セキュリティセンターで Microsoft 365 Defender を使用することができます。 [ライセンス要件を参照してください。](prerequisites.md#licensing-requirements)

| サポートされるサービス | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 強力な動作センサー、クラウド分析、脅威インテリジェンスに基づいて構築されたエンドポイント保護スイート |
|Microsoft Defender for Office 365 | Office 365 でのアプリとデータの高度な保護 (電子メールやその他のコラボレーションツールを含む) |
| Id の Microsoft Defender | 高度な脅威、侵害された id、および悪意のある内部者に対して、関連付けられた Active Directory シグナルを使用した防御 |
| Microsoft Cloud App Security | Microsoft およびサードパーティ製のクラウドサービスの脅威を特定し、戦闘する |

## <a name="deployed-services-and-functionality"></a>展開されたサービスと機能
Microsoft 365 Defender では、より多くのサポートされているサービスを展開することで、可視性、相互関係、および修復が向上しています。

### <a name="benefits-of-full-deployment"></a>完全な展開の利点
Microsoft 365 Defender の完全なメリットを得るために、サポートされているすべてのサービスを展開することをお勧めします。 完全な展開の主な利点は次のとおりです。
- インシデントは、利用可能なすべてのセンサーおよびサービス固有の分析機能からのアラートとイベント信号に基づいて識別され、関連しています。
- 自動化された調査と修復 (AIR) のプレイブックは、デバイス、メールボックス、ユーザーアカウントなどのさまざまなエンティティの種類に適用されます。
- デバイス、メールボックス、およびその他のエンティティのイベントおよびエンティティデータについて、より詳細な検索スキーマを照会することができます。

### <a name="limited-deployment-scenarios"></a>限定的な展開シナリオ
展開するサポートされているサービスごとに、非常に豊富な未加工の信号と、相関情報が提供されます。 限定的な展開では、Microsoft 365 Defender の機能がオフになることはありませんが、エンドポイント、アプリ、データ、および id に対して包括的な可視性を提供する機能が影響を受けることはありません。 同時に、すべての修復機能は、展開したサービスで管理できるエンティティにのみ適用されます。

次の表に、サポートされている各サービスが追加データを提供する方法、データを関連付けることによってさらに詳細な情報を得る方法、および改善と応答の機能を示します。

| サービス | データ (& 関連付けられる情報) | 修復 & 応答の範囲 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | -エンドポイントの状態と生のイベント<br />-ウイルス対策、EDR、攻撃対象領域の削減を含むエンドポイントの検出と通知<br />-エンドポイントで監視されたファイルやその他のエンティティに関する情報 | エンドポイント |
|Microsoft Defender for Office 365 | -メールとメールボックスの状態および生のイベント<br />-電子メール、添付ファイル、およびリンクの検出 | -メールボックス<br />-Microsoft 365 アカウント |
| Id の Microsoft Defender | -Active Directory シグナル (認証イベントを含む)<br />-Id 関連の動作の検出 | ID |
| Microsoft Cloud App Security | -承認されていないクラウドアプリおよびサービスの検出 (シャドウ IT)<br />-クラウドアプリへのデータの公開<br />-クラウドアプリに関連付けられている脅威アクティビティ | クラウド アプリ |

## <a name="deploy-the-services"></a>サービスを展開する
通常、各サービスを展開するには、テナントに対するプロビジョニングと、いくつかの初期構成が必要です。 これらの各サービスの展開方法については、次の表を参照してください。

| サービス | プロビジョニング手順 | 初期構成 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [エンドポイント展開ガイドの Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *プロビジョニングの手順を参照してください。* |
|Microsoft Defender for Office 365 | *なし。 Office 365 でプロビジョニングされます。* | [Office 365 ポリシーの Microsoft Defender を構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Id の Microsoft Defender | [クイックスタート: Id インスタンス用に Microsoft Defender を作成する](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *プロビジョニングの手順を参照してください。* |
| Microsoft Cloud App Security | *なし* | [クイックスタート: Microsoft Cloud App Security を使い始める](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

サポートされているサービスを展開したら、 [Microsoft 365 Defender をオン](mtp-enable.md)にします。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft 365 Defender をオンにする](mtp-enable.md)
- [エンドポイントの Microsoft Defender の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender for Office 365 の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Id の Microsoft Defender の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
