---
title: Microsoft 365 Defender でサポートされているサービスを展開する
description: Microsoft 365 Defender によって統合できる Microsoft セキュリティ サービス、ライセンス要件、展開手順について説明します。
keywords: 展開, ライセンス, サポートされているサービス, プロビジョニング, 構成 Microsoft Threat Protection, M365, ライセンスの利用資格, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, Advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928964"
---
# <a name="deploy-supported-services"></a>サポートされているサービスを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) は、さまざまな Microsoft セキュリティ サービスを統合して、高度な攻撃に対する一元的な検出、防止、調査機能を提供します。 この記事では、サポートされるサービス、ライセンス要件、1 つ以上のサービスの展開に関連する利点と制限事項、およびそれらを個別に完全に展開する方法へのリンクについて説明します。

## <a name="supported-services"></a>サポートされているサービス
Microsoft 365 E5、E5 Security、A5、または A5 Security ライセンス、またはライセンスの有効な組み合わせにより、次のサポートされているサービスにアクセスできます。また、Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用することができます。 [ライセンス要件を確認する](prerequisites.md#licensing-requirements)

| サポートされているサービス | 説明 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 強力な動作センサー、クラウド分析、脅威インテリジェンスを中心に構築されたエンドポイント保護スイート |
|Microsoft Defender for Office 365 | Office 365 のアプリとデータの高度な保護 (メールなどのコラボレーション ツールを含む) |
| Microsoft Defender for Identity | 関連付けされた Active Directory シグナルを使用して、高度な脅威、侵害された ID、悪意のあるインサイダーから防御する |
| Microsoft Cloud App Security | Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定し、対処する |

## <a name="deployed-services-and-functionality"></a>展開されたサービスと機能
Microsoft 365 Defender は、より多くのサポートされるサービスを展開するに当たって、可視性、相関関係、修復を向上します。

### <a name="benefits-of-full-deployment"></a>完全展開の利点
Microsoft 365 Defender の完全なメリットを得る場合は、サポートされているサービスを展開することをお勧めします。 完全展開の主な利点を次に示します。
- インシデントは、利用可能なすべてのセンサーとサービス固有の分析機能からのアラートとイベント シグナルに基づいて識別され、関連付けされます。
- 自動調査と修復 (AIR) プレイブックは、デバイス、メールボックス、ユーザー アカウントなど、さまざまなエンティティの種類に適用されます。
- より包括的な高度な検索スキーマを使用して、デバイス、メールボックス、その他のエンティティからのイベント データとエンティティ データを照会できます。

### <a name="limited-deployment-scenarios"></a>限定的な展開シナリオ
展開するサポートされている各サービスは、豊富な生信号と関連情報を提供します。 限定的な展開によって Microsoft 365 Defender の機能が無効にされるのとは限らないが、エンドポイント、アプリ、データ、ID 全体を包括的に可視化する機能は影響を受ける。 同時に、修復機能は、展開したサービスによって管理できるエンティティにのみ適用されます。

次の表は、サポートされている各サービスが追加のデータを提供する方法、データを関連付けて追加の洞察を得る機会、および改善と対応の機能を示しています。

| サービス | データ (シグナル&情報) | 応答&の修復 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | - エンドポイントの状態と生のイベント<br />- ウイルス対策、EDR、攻撃表面の縮小など、エンドポイントの検出とアラート<br />- エンドポイントで観察されたファイルと他のエンティティに関する情報 | エンドポイント |
|Microsoft Defender for Office 365 | - メールとメールボックスの状態と生のイベント<br />- 電子メール、添付ファイル、およびリンクの検出 | - メールボックス<br />- Microsoft 365 アカウント |
| Microsoft Defender for Identity | - Active Directory 信号 (認証イベントを含む)<br />- ID 関連の動作検出 | ID |
| Microsoft Cloud App Security | - 未指定のクラウド アプリとサービスの検出 (シャドウ IT)<br />- クラウド アプリへのデータの露出<br />- クラウド アプリに関連付けられている脅威アクティビティ | クラウド アプリ |

## <a name="deploy-the-services"></a>サービスを展開する
各サービスを展開するには、通常、テナントへのプロビジョニングと初期構成が必要です。 これらの各サービスの展開方法については、次の表をご覧ください。

| サービス | プロビジョニング手順 | 初期構成 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint 展開ガイド](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *プロビジョニング手順を参照する* |
|Microsoft Defender for Office 365 | *なし (Office 365 でプロビジョニング)* | [Microsoft Defender for Office 365 のポリシーを構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender for Identity | [クイック スタート: Id インスタンス用に Microsoft Defender を作成する](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *プロビジョニング手順を参照する* |
| Microsoft Cloud App Security | *なし* | [クイック スタート: Microsoft Cloud App Security の使用を開始する](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

サポートされているサービスを展開したら [、Microsoft 365 Defender を有効にしてください](mtp-enable.md)。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft 365 Defender を有効にする](mtp-enable.md)
- [Microsoft Defender for Endpoint の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender for Office 365 の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Id 用 Microsoft Defender の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
