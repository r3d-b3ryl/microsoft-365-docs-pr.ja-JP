---
title: 適切な設定で高度なハンティング範囲を拡張する
description: Windows デバイスの監査設定や他の設定を確認して、高度な検索で最も包括的なデータを確実に取得できます。
keywords: 高度な捜索、インシデント、ピボット、エンティティ、監査設定、ユーザー アカウント管理、セキュリティ グループ管理、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929588"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>適切な設定で高度なハンティング範囲を拡張する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[高度な検索](advanced-hunting-overview.md) は、デバイス、Office 365 ワークスペース、Azure AD、Id 用 Microsoft Defender など、さまざまなソースからのデータに依存します。 最も包括的なデータを取得するには、対応するデータ ソースに正しい設定が存在していることを確認します。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows デバイスでの高度なセキュリティ監査
これらの高度な監査設定を有効にし、ローカル アカウント管理、ローカル セキュリティ グループ管理、サービス作成など、デバイス上のアクティビティに関するデータを取得します。

| データ | 説明 | スキーマ テーブル | 構成する方法 |
| --- | --- | --- | --- |
| アカウント管理 | ローカル アカウントの作成、削除、その他のアカウント関連アクティビティを示すさまざまな値 `ActionType` としてキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [ユーザー アカウント管理の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| セキュリティ グループの管理 | ローカル セキュリティ グループの作成および他 `ActionType` のローカル グループ管理アクティビティを示すさまざまな値としてキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーを展開する: [セキュリティ グループ管理の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| サービスのインストール | 値を使用してキャプチャ `ActionType` されたイベント `ServiceInstalled` (サービスが作成されたことを示す) | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーを展開する: [セキュリティ システム拡張機能の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>ドメイン コントローラーの Id センサー用 Microsoft Defender
オンプレミスで Active Directory を実行している場合は、ドメイン コントローラーに Microsoft Defender for Identity センサーをインストールして、Id 用 Microsoft Defender のデータを取得する必要があります。 インストールされ、適切に構成されている場合、このデータは、Microsoft Defender for Identity を介した高度な検索にもフィードされ、ネットワーク内の ID 情報とイベントのより包括的な画像を提供します。 また、このデータにより、高度な検索の対象となる関連するアラートを生成する Microsoft Defender for Identity の機能も強化されます。 

| データ | 説明 | スキーマ テーブル | 構成する方法 |
| --- | --- | --- | --- |
| ドメイン コントローラ | Id 用に Microsoft Defender に送信されたオンプレミスの Active Directory からのデータ。アカウントの詳細、ログオン アクティビティ、Active Directory クエリなどの ID 関連情報が充実しています。 | [IdentityInfo、IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)など、複数の[テーブル](advanced-hunting-identityqueryevents-table.md)[](advanced-hunting-identityinfo-table.md)  | - [Microsoft Defender for Identity センサーをインストールする](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [関連する Windows イベントを有効にする](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
