---
title: 適切な設定で高度な狩猟範囲を拡張する
description: 高度な検索で最も包括的なデータを取得するために、Windows デバイスや他の設定の監査設定を確認する
keywords: 高度なハンティング、インシデント、ピボット、エンティティ、監査設定、ユーザー アカウント管理、セキュリティ グループ管理、脅威狩猟、検索、クエリ、テレメトリ、mdatp、Microsoft Defender ATP、Microsoft Defender for Endpoint、Windows Defender、Windows Defender ATP、Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500613"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>適切な設定で高度な狩猟範囲を拡張する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[高度な検索は](advanced-hunting-overview.md) 、組織全体からのデータに依存します。 可能な限り包括的なデータを取得するには、対応するデータ ソースに正しい設定が含されていることを確認します。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows デバイスでの高度なセキュリティ監査

これらの高度な監査設定をオンにし、ローカル アカウント管理、ローカル セキュリティ グループ管理、サービスの作成など、デバイス上のアクティビティに関するデータを取得します。

データ | 説明 | スキーマ テーブル | 構成する方法
-|-|-|-
アカウント管理 | ローカル アカウントの作成、削除、その他のアカウント関連のアクティビティを示すさまざまな値 `ActionType` としてキャプチャされるイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [ユーザー アカウント管理の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
セキュリティ グループの管理 | ローカル セキュリティ グループの作成および他のローカル グループ管理アクティビティを示すさまざまな `ActionType` 値としてキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [セキュリティ グループ管理の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
サービスのインストール | サービスが作成されたことを示 `ActionType` す値 `ServiceInstalled` でキャプチャされたイベント | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 高度なセキュリティ監査ポリシーの展開: [セキュリティ システム拡張機能の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](overview-custom-detections.md)
