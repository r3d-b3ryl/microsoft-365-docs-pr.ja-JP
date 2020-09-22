---
title: 高度な脅威保護との SIEM の統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーと Office 365 Advanced Threat Protection および関連する脅威イベントを Office 365 アクティビティ管理 API に統合します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cfb76485fec8eca2f2b62da59fa2d18a56177bba
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203655"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>高度な脅威保護との SIEM の統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection (Office 365 ATP) を SIEM サーバーに統合できます。 この統合は、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用してセットアップできます。 

SIEM の統合により、SIEM サーバーのレポートで、Office 365 ATP によって検出されたマルウェアやフィッシングなどの情報を表示できます。 

- Office 365 ATP との SIEM の統合の例については、「 [Tech Community blog: office 365 ATP および O365 管理 API を使用した SOC の有効性を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)」を参照してください。

- Office 365 管理 Api の詳細については、「 [office 365 管理 api の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)」を参照してください。

## <a name="how-siem-integration-works"></a>SIEM 統合のしくみ

Office 365 Activity Management API は、組織の Microsoft 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。 組織に Office 365 ATP プラン1または2、あるいは Office 365 E5 がある場合は、 [office 365 atp スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)を使用できます。  

最近、 [office 365](office-365-atp.md#office-365-atp-plan-1-and-plan-2) の自動調査および応答機能からのイベントが、Office 365 MANAGEMENT Activity API に追加されました。 API には、ID、名前、状態などの主要な調査の詳細に関するデータだけでなく、調査のアクションとエンティティについての詳細な情報も含まれています。

SIEM サーバーまたはその他の同様のシステムが監査をポーリングして、検出イベントにアクセスし **ます** 。 詳細については、「 [Office 365 管理 api の使用を開始](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)する」を参照してください。 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

次の表は、Office 365 ATP イベントに関連する **AuditLogRecordType** の値の概要を示しています。

|値|メンバ名|説明|
|---|---|---|
|個|ThreatIntelligence|Exchange Online Protection および Office 365 ATP からのフィッシングとマルウェアのイベント。|
|41|ThreatIntelligenceUrl|ATP の安全なリンクの時間帯とブロックは、Office 365 ATP からのイベントを無視します。|
|47|ThreatIntelligenceAtpContent|Office 365 ATP からの、SharePoint Online、OneDrive for Business、Microsoft Teams のファイルのフィッシングとマルウェアのイベント。|
|64|AIR 調査|Office 365 ATP Plan 2 から、調査の詳細や関連する成果物などの自動化された調査および応答イベント。|
|

> [!IMPORTANT]
> Office 365 Advanced Threat Protection との SIEM の統合をセットアップするには、全体管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。<br/>Microsoft 365 環境では、監査ログを有効にする必要があります。 この問題に関するヘルプを表示するには、「 [監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。

## <a name="see-also"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)


