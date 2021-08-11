---
title: 適切な設定で高度な狩猟範囲を拡張する
description: 高度なWindowsで最も包括的なデータを取得するために、デバイスや他の設定の監査設定を確認する
keywords: 高度なハンティング、インシデント、ピボット、エンティティ、監査設定、ユーザー アカウント管理、セキュリティ グループ管理、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、Microsoft 365、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f0b5218ccfb17c4c3681628200bb42afbfd312cc9ec383f524e6721340da461a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53833293"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>適切な設定で高度な狩猟範囲を拡張する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[高度な検索](advanced-hunting-overview.md)は、デバイス、Office 365 ワークスペース、Azure AD、Microsoft Defender for Identity など、さまざまなソースからのデータに依存します。 可能な限り包括的なデータを取得するには、対応するデータ ソースに正しい設定が含されていることを確認します。

## <a name="advanced-security-auditing-on-windows-devices"></a>デバイスの高度なWindows監査
これらの高度な監査設定をオンにし、ローカル アカウント管理、ローカル セキュリティ グループ管理、サービスの作成など、デバイス上のアクティビティに関するデータを取得します。

| データ | Description | スキーマ テーブル | 構成する方法 |
| --- | --- | --- | --- |
| アカウント管理 | ローカル アカウントの作成、削除、その他のアカウント関連のアクティビティを示すさまざまな値 `ActionType` としてキャプチャされるイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [ユーザー アカウント管理の監査](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [高度なセキュリティ監査ポリシーの詳細](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| セキュリティ グループの管理 | ローカル セキュリティ グループの作成および他のローカル グループ管理アクティビティを示すさまざまな `ActionType` 値としてキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [セキュリティ グループ管理の監査](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [高度なセキュリティ監査ポリシーの詳細](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| サービスのインストール | サービスが作成されたことを示 `ActionType` す値 `ServiceInstalled` でキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [セキュリティ システム拡張機能の監査](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [高度なセキュリティ監査ポリシーの詳細](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>ドメイン コントローラー上の Id センサー用 Microsoft Defender
オンプレミスで Active Directory を実行している場合は、Microsoft Defender for Identity のデータを取得するには、ドメイン コントローラーに Microsoft Defender for Identity センサーをインストールする必要があります。 インストールされ、適切に構成されている場合、このデータは、Microsoft Defender for Identity を介した高度な検索にもフィードされ、ネットワーク内の ID 情報とイベントの全体像を提供します。 また、このデータを使用すると、Microsoft Defender for Identity が高度な狩猟の対象となる関連するアラートを生成する機能も強化されます。 

| データ | Description | スキーマ テーブル | 構成する方法 |
| --- | --- | --- | --- |
| ドメイン コントローラ | Microsoft Defender for Identity に送信されるオンプレミスの Active Directory からのデータ、アカウントの詳細、ログオン アクティビティ、Active Directory クエリなどの ID 関連情報の強化 | [IdentityInfo、IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)などの複数の[](advanced-hunting-identityinfo-table.md)[テーブル](advanced-hunting-identityqueryevents-table.md)  | - [Microsoft Defender for Identity センサーのインストール](/azure-advanced-threat-protection/install-atp-step4)<br>- [関連するイベントをWindowsする](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。 [複数のデータ Microsoft 365 Defender](m365d-enable.md)を使用して脅威を検出するには、このオプションをオンにしてください。 高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defenderに移動するには、「Advanced Hunting [queries](advanced-hunting-migrate-from-mde.md)を Microsoft Defender for Endpoint から移行する」の手順に従います。

## <a name="related-topics"></a>関連トピック
- [高度な追求の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)