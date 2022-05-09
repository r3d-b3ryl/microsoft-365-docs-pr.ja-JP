---
title: 適切な設定で高度なハンティング カバレッジを拡張する
description: 高度な捜索で最も包括的なデータを確実に取得できるように、Windows デバイスとその他の設定の監査設定を確認する
keywords: 高度な捜索, インシデント, ピボット, エンティティ, 監査設定, ユーザー アカウント管理, セキュリティ グループ管理, 脅威の捜索, サイバー脅威の捜索, 検索, クエリ, テレメトリ, Microsoft 365, Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dd61fa434eaf2130f0fcb0f28df9a20d696e04ec
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60665359"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>適切な設定で高度なハンティング カバレッジを拡張する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[高度な捜索](advanced-hunting-overview.md)は、デバイス、Office 365 ワークスペース、Azure AD、Microsoft Defender for Identityなど、さまざまなソースからのデータに依存しています。 可能な限り包括的なデータを取得するには、対応するデータ ソースに正しい設定があることを確認します。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows デバイスの高度なセキュリティ監査
これらの高度な監査設定をオンにして、ローカル アカウント管理、ローカル セキュリティ グループ管理、サービス作成など、デバイス上のアクティビティに関するデータを確実に取得できるようにします。

| データ | 説明 | スキーマ テーブル | 構成する方法 |
| --- | --- | --- | --- |
| アカウント管理 | ローカル アカウントの作成、削除、およびその他のアカウント関連のアクティビティを示すさまざまな `ActionType` 値としてキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [ユーザー アカウント管理の監査](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [高度なセキュリティ監査ポリシーについて学習する](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| セキュリティ グループの管理 | ローカル セキュリティ グループの作成やその他のローカル グループ管理アクティビティを示すさまざまな `ActionType` 値としてキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーを展開する: [セキュリティ グループ管理の監査](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [高度なセキュリティ監査ポリシーについて学習する](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| サービスのインストール | 値`ServiceInstalled`で`ActionType`キャプチャされたイベント (サービスが作成されたことを示す) | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーを展開する: [セキュリティ システム拡張機能の監査](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [高度なセキュリティ監査ポリシーについて学習する](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>ドメイン コントローラーでセンサーをMicrosoft Defender for Identityする
オンプレミスで Active Directory を実行している場合は、ドメイン コントローラーにMicrosoft Defender for Identity センサーをインストールして、Microsoft Defender for Identityのデータを取得する必要があります。 このデータは、インストールされて適切に構成されると、Microsoft Defender for Identityを介した高度な捜索にもフィードされ、ネットワーク内の ID 情報とイベントの全体像を把握できます。 また、このデータにより、高度な捜索の対象となる関連するアラートを生成するMicrosoft Defender for Identityの機能も強化されます。 

| データ | 説明 | スキーマ テーブル | 構成する方法 |
| --- | --- | --- | --- |
| ドメイン コントローラ | オンプレミスの Active DirectoryからMicrosoft Defender for Identityに送信されたデータ。アカウントの詳細、ログオン アクティビティ、Active Directory クエリなどの ID 関連情報を強化します。 | [IdentityInfo](advanced-hunting-identityinfo-table.md)、[IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md) など、複数[の](advanced-hunting-identityqueryevents-table.md)テーブル  | - [Microsoft Defender for Identity センサーをインストールする](/azure-advanced-threat-protection/install-atp-step4)<br>- [関連するWindows イベントを有効にする](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)