---
title: SIEM との Microsoft Defender との統合 (Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーを Microsoft Defender と統合して、Office 365アクティビティ管理 API Office 365関連する脅威イベントを検出します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f80ac15ef26cac6eddcc2c8c6219f64e62c8400bbb9e305f5961c08d1b6ab0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56807187"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM との Microsoft Defender との統合 (Office 365

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、MICROSOFT Defender for Office 365 SIEM サーバーに統合できます。 この統合は、アクティビティ管理 API Office 365[使用して設定できます](/office/office-365-management-api/office-365-management-activity-api-reference)。

SIEM 統合を使用すると、SIEM サーバー レポートで Microsoft Defender によって検出されたマルウェアやフィッシングなどの情報Office 365を表示できます。

- microsoft Defender for Office 365 との SIEM 統合の例については、「Tech Community ブログ: Office 365 および[O365 管理 API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)の Defender を使用した SOC の有効性の向上」を参照してください。
- 管理 API の詳細については、「Office 365管理 API[のOffice 365」を参照してください](/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 統合の仕組み

このOffice 365アクティビティ管理 API は、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を、組織の Microsoft 365 および Azure Active Directoryログから取得します。 組織に Microsoft Defender for Office 365 プラン 1 または 2、または Office 365 E5 がある場合は[、Microsoft Defender](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)を使用してスキーマOffice 365できます。

最近では、Microsoft Defender for Office 365[プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)の自動調査と対応機能のイベントが Office 365管理アクティビティ API に追加されました。 ID、名前、状態などの主要な調査の詳細に関するデータを含めるだけでなく、API には調査アクションやエンティティに関する高レベルの情報も含まれる。

SIEM サーバーまたは他の同様のシステムは **、audit.general** ワークロードをポーリングして検出イベントにアクセスします。 詳細については、「管理 API の使用[Office 365」を参照してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

次の表に、Microsoft Defender のイベントに関連する **AuditLogRecordType** の値Office 365示します。

| 値 | メンバ名 | 説明 |
|---|---|---|
| 28| ThreatIntelligence | Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。 |
| 41| ThreatIntelligenceUrl | セーフMicrosoft Defender のタイム オブ ブロックイベントとブロック オーバーライド イベントをリンクして、Office 365。 |
| 47| ThreatIntelligenceAtpContent | Microsoft Defender for SharePoint オンライン、OneDrive for Business、Microsoft Teamsのファイルのフィッシングイベントとマルウェア イベントOffice 365。 |
| 64| AIR 調査 | Microsoft Defender for microsoft Defender for Office 365プラン 2 の調査の詳細や関連する成果物などの、自動調査およびOffice 365イベント。 |
|

> [!IMPORTANT]
> Microsoft Defender との SIEM 統合をセットアップするには、Microsoft 365 Defender ポータルでグローバル管理者またはセキュリティ管理者の役割が割り当てられている必要Office 365。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。
>
> 監査ログは、ユーザーの環境Microsoft 365する必要があります。 このヘルプを表示するには、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)