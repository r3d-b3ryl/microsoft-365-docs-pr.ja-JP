---
title: SIEM との Microsoft Defender との統合 (Office 365)
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
description: 組織の SIEM サーバーを Microsoft Defender と統合して、Office 365 アクティビティ管理 API Office関連する脅威イベントを検出します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8f86c831df16568ae569e7b21c7e0a33475948
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205176"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM との Microsoft Defender との統合 (Office 365)

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、Microsoft Defender for Office 365 を SIEM サーバーに統合できます。 この統合は [、365](/office/office-365-management-api/office-365-management-activity-api-reference)アクティビティOffice API を使用して設定できます。

SIEM 統合を使用すると、MICROSOFT Defender が 365 用に検出したマルウェアやOfficeなどの情報を SIEM サーバー レポートで表示できます。

- microsoft Defender for Office 365 との SIEM 統合の例については、「Tech Community blog: Improve the EFFECTIVENESS of your SOC with [Defender for Office 365」および「O365 Management API」](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)を参照してください。

- 365 管理 API Office詳細については [、「365 管理](/office/office-365-management-api/office-365-management-apis-overview)API Office概要」を参照してください。

## <a name="how-siem-integration-works"></a>SIEM 統合の仕組み

Office 365 アクティビティ管理 API は、組織の Microsoft 365 アクティビティ ログと Azure Active Directory アクティビティ ログから、ユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を取得します。 組織に microsoft Defender for Office 365 Plan 1 または 2、または Office 365 E5 がある場合は、Microsoft Defender を Office [365 スキーマに使用できます](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。

最近では、microsoft Defender for [Office 365 プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) の自動調査と対応機能のイベントが Office 365 管理アクティビティ API に追加されました。 ID、名前、状態などの主要な調査の詳細に関するデータを含めるだけでなく、API には調査アクションやエンティティに関する高レベルの情報も含まれる。

SIEM サーバーまたは他の同様のシステムは **、audit.general** ワークロードをポーリングして検出イベントにアクセスします。 詳細については [、「365 管理 API のOffice」を参照してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

次の表に、Microsoft Defender の 365 イベントに関連する **AuditLogRecordType** の値Office示します。

|値|メンバ名|説明|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。|
|41|ThreatIntelligenceUrl|365 の Microsoft Defender からのセーフ リンクのタイム オブ ブロックイベントとブロック オーバーライド イベントOfficeします。|
|47|ThreatIntelligenceAtpContent|SharePoint Online、OneDrive for Business、Microsoft Teams のファイルのフィッシングおよびマルウェア イベント (Microsoft Defender for microsoft Defender for Office 365)。|
|64|AIR 調査|Microsoft Defender for microsoft Defender for Office 365 プラン 2 の調査の詳細や関連する成果物など、自動調査および応答イベント。|
|

> [!IMPORTANT]
> Microsoft Defender との SIEM 統合を 365 用にセットアップするには、グローバル管理者またはセキュリティ & コンプライアンス センターにセキュリティ管理者の役割が割り当てられているOfficeがあります。
>
> Microsoft 365 環境で監査ログを有効にする必要があります。 このヘルプを表示するには、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)