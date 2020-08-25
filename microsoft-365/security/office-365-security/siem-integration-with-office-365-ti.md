---
title: Advanced Threat Protection と SIEM 統合
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
description: Office 365 Activity Management API で、Office 365 Advanced Threat Protection と関連する脅威イベントと組織の SIEM サーバーを統合します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860691"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Advanced Threat Protection と SIEM 統合

組織でセキュリティ インシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection (Office 365 ATP) を SIEM サーバーと統合できます。 この統合は [、Office 365 アクティビティ管理 API を使用してセットアップできます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

SIEM 統合を使用すると、SIEM サーバー レポート内で、Office 365 ATP によって検出されたマルウェアやフィッシング対策などの情報を表示できます。 

- Office 365 ATP との SIEM 統合の例については、テクニカル [ブログ: Office 365 ATP および O365 Management API を使用して SOC の効果を向上させる方法を参照してください](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

- Office 365 Management API の詳細については [、Office 365 管理 API の概要を参照してください](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 統合のしくみ

Office 365 アクティビティ管理 API は、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を、組織の Microsoft 365 および Azure Active Directory のアクティビティ ログから取得します。 組織が Office 365 ATP プラン 1 または Office office 365 E5 を利用している場合は [、Office 365 ATP スキーマを使用できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。  

最近では [、Office 365 ATP](office-365-atp.md#office-365-atp-plan-1-and-plan-2) プラン 2 の自動調査および対応機能のイベントが、Office 365 管理アクティビティ API に追加されました。 ID、名前、状態などの主要な調査の詳細に関するデータを含めることに加えて、API には調査処理とエンティティに関する詳細な情報も含まれています。

SIEM サーバーまたはその他の類似システムは **、audit.general workload をポーリング** して検出イベントにアクセスします。 詳細については [、「Get started with Office 365 Management APIs (Office 365 Management API の使用を開始する」を参照してください](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

次の表は、ATP の **ATP イベントに関連する AuditLogRecordType** Officeの値をまとしたしています。

|値|メンバ名|説明|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection と 365 ATP からのフィッシングとマルウェアOfficeと。|
|41|ThreatIntelligenceUrl|ATP の安全なリンク時のブロック時 --、365 ATP からのイベントOfficeブロックします。|
|47|ThreatIntelligenceAtpContent|SharePoint Online、OneDrive for Business、Microsoft Teams のファイルに対するフィッシングとマルウェアのイベント (Office 365 ATP)。|
|64|AIR 調査|Office 365 ATP プラン 2 の調査の詳細や関連する成果物などの自動調査および対応イベント。|
|

> [!IMPORTANT]
> SIEM と Office 365 Advanced Threat Protection の統合をセットアップするには、グローバル管理者であるか、セキュリティ & コンプライアンス センターにセキュリティ管理者ロールが割り当てられている必要があります。<br/>Microsoft 365 環境に対して監査ログを有効にする必要があります。 この問題についてヘルプを参照するには、「監査 [ログの検索を有効または無効にする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)


