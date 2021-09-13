---
title: 自動調査と対応によるカスタム レポート ソリューション
keywords: SIEM、API、AIR、autoIR、Microsoft Defender for Endpoint、自動調査、統合、カスタム レポート
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 自動調査と対応をカスタムまたはサード パーティのレポート ソリューションに統合する方法について説明します。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219903"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender 用のカスタムまたはサード パーティ製のレポート Office 365

Microsoft [Defender for Office 365、](defender-for-office-365.md)自動調査に関する[詳細情報を取得します](air-view-investigation-results.md)。 ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。 組織が自動調査に関する情報を[](office-365-air.md)そのようなソリューションと統合する場合は、管理アクティビティ API Office 365使用できます。

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft [Defender for Office 365、](defender-for-office-365.md)自動調査に関する[詳細情報を取得します](air-view-investigation-results.md)。 ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。 組織が自動調査に関する情報をそのようなソリューションと統合する場合は、Office 365管理アクティビティ API を使用できます。

|関連情報|説明|
|:---|:---|
|[Office 365 管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview)|管理Office 365 API は、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を、Microsoft 365およびAzure Active Directory提供します。|
|[Office 365 管理 API の使用を開始する](/office/office-365-management-api/get-started-with-office-365-management-apis)|このOffice 365管理 API は、Azure ADを使用して、アプリケーションがデータにアクセスする認証Microsoft 365します。 この記事の手順に従って、これを設定します。|
|[Office 365 管理アクティビティ API リファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 管理アクティビティ API を使用して、ユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を Microsoft 365 および Azure AD アクティビティ ログから取得できます。 この機能の詳細については、この記事を参照してください。|
|[Office 365 管理アクティビティ API のスキーマ](/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 管理アクティビティ[](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)API で使用できる特定の種類のデータについて学習するには、共通スキーマと Defender for [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) Office 365 および脅威の調査と応答スキーマの概要を確認します。|
|

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender での自動調査と応答](/microsoft-365/security/defender/m365d-autoir)
