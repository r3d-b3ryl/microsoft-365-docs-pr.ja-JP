---
title: siem integration with Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Office 365 アクティビティ管理 API で、組織の SIEM サーバーを Microsoft Defender for Office 365 および関連する脅威イベントと統合します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290395"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>siem integration with Microsoft Defender for Office 365

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、Microsoft Defender for Office 365 を SIEM サーバーと統合できます。 この統合は、Office [365 Activity Management API を使用して設定できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。

SIEM 統合を使用すると、Microsoft Defender for Office 365 で検出されたマルウェアやフィッシングなどの情報を SIEM サーバー レポートで表示できます。

- Office 365 向け Microsoft Defender との SIEM 統合の例については、Tech Community ブログを参照してください。Office [365 および O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)管理 API の Defender を使用して SOC の効果を向上させる。

- Office 365 管理 API の詳細については、「Office [365 管理 API の概要」を参照してください](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 統合のしくみ

Office 365 アクティビティ管理 API は、組織の Microsoft 365 および Azure Active Directory アクティビティ ログから、ユーザー、管理者、システム、およびポリシー アクションとイベントに関する情報を取得します。 Office 365 プラン 1 または 2 用の Microsoft Defender または Office 365 E5 を使用している組織では [、microsoft Defender for Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)スキーマを使用できます。

最近 [、microsoft Defender for Office 365 プラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) の自動調査および対応機能のイベントが Office 365 マネージメント アクティビティ API に追加されました。 ID、名前、状態などの主要な調査の詳細に関するデータを含めるだけでなく、この API には調査アクションとエンティティに関する高レベルの情報も含まれる。

SIEM サーバーまたは他の同様のシステムは **、audit.general** ワークロードをポーリングして、検出イベントにアクセスします。 詳細については、「Office [365 Management API の使用を開始する」を参照してください](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>列挙値: AuditLogRecordType - 型: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

次の表に、365 イベントの Microsoft Defender に関連する **AuditLogRecordType** Office示します。

|値|メンバ名|説明|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。|
|41|ThreatIntelligenceUrl|「安全なリンク」のブロック時間と、365 年 365 日の Microsoft Defender からのオーバーライド イベントOfficeブロックします。|
|47|ThreatIntelligenceAtpContent|Microsoft Defender for Office 365 の SharePoint Online、OneDrive for Business、Microsoft Teams のファイルに対するフィッシングおよびマルウェア イベント。|
|64|AIR 調査|Microsoft Defender for Office 365 プラン 2 の調査および対応イベント (調査の詳細や関連アーティファクトなど)|
|

> [!IMPORTANT]
> Office 365 向け Microsoft Defender との SIEM 統合をセットアップするには、グローバル管理者か、セキュリティ & コンプライアンス センターにセキュリティ管理者の役割が割り当てられている必要があります。
>
> Microsoft 365 環境で監査ログを有効にする必要があります。 このヘルプについては、「監査ログの検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>関連項目

[Office 365 脅威の調査および対応](office-365-ti.md)

[Office 365 での自動調査および対応 (AIR)](automated-investigation-response-office.md)

