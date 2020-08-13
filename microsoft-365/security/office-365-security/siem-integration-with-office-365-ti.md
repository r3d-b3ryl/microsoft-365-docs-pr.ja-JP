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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーと Office 365 Advanced Threat Protection および関連する脅威イベントを Office 365 アクティビティ管理 API に統合します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3ed2efd2b59397853623ffcec93e8011793ab43
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656601"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>高度な脅威保護との SIEM の統合

組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection を SIEM サーバーに統合することができます。 SIEM の統合により、SIEM サーバーのレポートにある、Office 365 Advanced Protection によって検出されたマルウェアやフィッシングなどの情報を表示できます。 SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。

Office 365 Activity Management API は、組織の Microsoft 365 for business および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。 [Office 365 Advanced Threat protection スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)は Advanced threat protection と共に動作するため、組織が Office 365 Advanced Threat protection プラン1または Plan 2 または Office 365 E5 を使用している場合でも、SIEM サーバー統合に同じ API を使用できます。

最近の更新プログラムの一部として、office 365 Management Activity API 内の Office 365 ATP Plan 2 の自動調査および応答機能からのイベントも追加されました。 ID、名前、状態などの主要な調査の詳細に関するデータに加えて、調査のアクションおよびエンティティに関する概要情報も含まれています。

SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり **ます。一般的な** ワークロードを検出イベントにアクセスします。 詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。 また、 **AuditLogRecordType** の次の値は、OFFICE 365 ATP イベントに関連しています。

### <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

****

|値|メンバ名|説明|
|---|---|---|
|個|ThreatIntelligence|Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベント。|
|41|ThreatIntelligenceUrl|ATP の安全なリンクは、Office 365 Advanced Threat Protection からのイベントをブロックする時間とブロックします。|
|47|ThreatIntelligenceAtpContent|SharePoint Online、OneDrive for Business、および Microsoft Teams for Office 365 Advanced Threat Protection のファイルのフィッシングとマルウェアイベント。|
|64|AIR 調査|Office 365 Advanced Threat Protection プラン2の調査詳細や関連する成果物など、自動化された調査および応答イベント。|
|

> [!IMPORTANT]
> Office 365 Advanced Threat Protection との SIEM の統合をセットアップするには、全体管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。<br/>Microsoft 365 環境では、監査ログを有効にする必要があります。 この問題に関するヘルプを表示するには、「 [監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。

## <a name="related-topics"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[セキュリティ/コンプライアンスセンターのスマートレポートと洞察 &amp;](reports-and-insights-in-security-and-compliance.md)

[セキュリティ/コンプライアンスセンターのアクセス許可 &amp;](permissions-in-the-security-and-compliance-center.md)
