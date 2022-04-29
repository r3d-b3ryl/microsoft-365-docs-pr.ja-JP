---
title: SIEM と Microsoft Defender for Office 365の統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: ''
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーを、Office 365 Activity Management API のMicrosoft Defender for Office 365および関連する脅威イベントと統合します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ffa1e59f368af4b3e99cee9939ed0ead0cc686e
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131000"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM と Microsoft Defender for Office 365の統合

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、Microsoft Defender for Office 365を SIEM サーバーと統合できます。 この統合は、[Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference) を使用して設定できます。

SIEM 統合を使用すると、MICROSOFT DEFENDER FOR OFFICE 365によって検出されたマルウェアやフィッシングなどの情報を SIEM サーバー レポートに表示できます。

- Microsoft Defender for Office 365との SIEM 統合の例については、「[Tech Community ブログ: Defender for Office 365と O365 Management API を使用して SOC の有効性を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)」を参照してください。
- Office 365管理 API の詳細については、「[Office 365管理 API の概要」を](/office/office-365-management-api/office-365-management-apis-overview)参照してください。

## <a name="how-siem-integration-works"></a>SIEM 統合のしくみ

Office 365 Activity Management API は、組織のMicrosoft 365およびAzure Active Directoryアクティビティ ログから、ユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を取得します。 組織にプラン 1 または 2 Microsoft Defender for Office 365、またはOffice 365 E5がある場合は、[Microsoft Defender for Office 365 スキーマ](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)を使用できます。

最近、Office 365 Management Activity API に[、Microsoft Defender for Office 365プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) の自動調査と対応機能からのイベントが追加されました。 ID、名前、状態などのコア調査の詳細に関するデータを含めることに加えて、API には、調査アクションとエンティティに関する高度な情報も含まれています。

SIEM サーバーまたはその他の同様のシステムは **、audit.general** ワークロードをポーリングして検出イベントにアクセスします。 詳細については、「[Office 365 Management API の概要」を](/office/office-365-management-api/get-started-with-office-365-management-apis)参照してください。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

次の表は、Microsoft Defender for Office 365 イベントに関連する **AuditLogRecordType** の値をまとめたものです。<br/><br/>

| 値 | メンバ名 | 説明 |
|---|---|---|
| 28| ThreatIntelligence | Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。 |
| 41| ThreatIntelligenceUrl | セーフ リンクのブロック時間とブロックのオーバーライド イベントをMicrosoft Defender for Office 365からリンクします。 |
| 47| ThreatIntelligenceAtpContent | Microsoft Defender for Office 365から、SharePoint Online、OneDrive for Business、およびMicrosoft Teams内のファイルのフィッシングおよびマルウェア イベント。 |
| 64| AIR 調査 | Microsoft Defender for Office 365プラン 2 の調査の詳細や関連する成果物などの自動調査および対応イベント。 |

> [!IMPORTANT]
> Microsoft Defender for Office 365との SIEM 統合を設定するには、Microsoft 365 Defender ポータルでグローバル管理者またはセキュリティ管理者ロールが割り当てられている必要があります。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。
>
> Microsoft 365環境で監査ログを有効にする必要があります。 これに関するヘルプについては、「 [監査ログ検索のオンとオフを切り替える](../../compliance/turn-audit-log-search-on-or-off.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)
