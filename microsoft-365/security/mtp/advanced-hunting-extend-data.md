---
title: 高度な検索範囲を適切な設定で拡張する
description: 詳細な検索で最も包括的なデータを確実に取得できるように、Windows デバイスおよびその他の設定の監査設定を確認します。
keywords: 高度な検索、インシデント、ピボット、エンティティ、監査設定、ユーザーアカウントの管理、セキュリティグループの管理、脅威の検索、サイバー脅威の検索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft の脅威保護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 39beff1ea5e983af53cdb954783c11f13569a022
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413952"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>高度な検索範囲を適切な設定で拡張する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

[高度な](advanced-hunting-overview.md) 検索は、デバイス、Office 365 ワークスペース、azure AD、azure ATP など、さまざまなソースから取得されるデータに依存します。 最も包括的なデータを取得するには、対応するデータソースの設定が正しいことを確認してください。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows デバイスの高度なセキュリティ監査
これらの高度な監査設定を有効にして、ローカルアカウント管理、ローカルセキュリティグループの管理、サービスの作成など、デバイス上のアクティビティに関するデータを確実に取得します。

| データ | 説明 | スキーマテーブル | 構成する方法 |
| --- | --- | --- | --- |
| アカウント管理 | `ActionType`ローカルアカウントの作成、削除、その他のアカウント関連のアクティビティを示す、さまざまな値として取得されたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -高度なセキュリティ監査ポリシーを展開する: [監査ユーザーアカウントの管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [高度なセキュリティ監査ポリシーについて説明します。](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| セキュリティグループの管理 | `ActionType`ローカルセキュリティグループの作成とその他のローカルグループ管理アクティビティを示すさまざまな値として取得されたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -高度なセキュリティ監査ポリシーを展開する: [監査セキュリティグループの管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [高度なセキュリティ監査ポリシーについて説明します。](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| サービスのインストール | `ActionType`値 `ServiceInstalled` (サービスが作成されたことを示す) でキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -高度なセキュリティ監査ポリシーを展開する: [セキュリティシステムの拡張の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [高度なセキュリティ監査ポリシーについて説明します。](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>ドメインコントローラーの Azure ATP センサー
オンプレミスの Active Directory を実行している場合は、Azure ATP のデータを取得するために、ドメインコントローラーに Azure ATP センサーをインストールする必要があります。 このデータは、をインストールして適切に構成すると、Azure ATP によって高度な検索にも追加され、ネットワーク内の id 情報とイベントの全体的な図が提供されます。 また、このデータは、高度な検索によっても対象となる関連のアラートを Azure ATP が生成する機能を拡張します。 

| データ | 説明 | スキーマテーブル | 構成する方法 |
| --- | --- | --- | --- |
| ドメイン コントローラー | オンプレミスの Active Directory から Azure ATP に送信されたデータによって、id 関連情報 (アカウントの詳細、ログオンアクティビティ、Active Directory クエリなど) が表示されます。 | 複数のテーブル ("identity [info](advanced-hunting-identityinfo-table.md)"、"id"[イベント](advanced-hunting-identitylogonevents-table.md)、および "イベント id"[イベント](advanced-hunting-identityqueryevents-table.md)を含む)  | - [Azure ATP センサーをインストールする](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [関連する Windows イベントを有効にする](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
