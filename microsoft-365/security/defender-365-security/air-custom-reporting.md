---
title: 自動調査と対応によるカスタム レポート ソリューション
keywords: SIEM、API、AIR、autoIR、ATP、自動調査、統合、カスタム レポート
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065635"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender for Office 365

Microsoft [Defender for Office 365 では](defender-for-office-365.md)、自動調査に関する [詳細情報を取得できます](air-view-investigation-results.md)。 ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。 組織が自動調査に関する情報を[](office-365-air.md)そのようなソリューションと統合する場合は、Office 365 Management Activity API を使用できます。

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft [Defender for Office 365 では](defender-for-office-365.md)、自動調査に関する [詳細情報を取得できます](air-view-investigation-results.md)。 ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。 組織が自動調査に関する情報をそのようなソリューションと統合する場合は、365 管理アクティビティ API Office使用できます。

|関連情報|説明|
|:---|:---|
|[Office 365 管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview)|365 Office管理アクティビティ API は、Microsoft 365 および Azure Active Directory アクティビティ ログからのさまざまなユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を提供します。|
|[Office 365 管理 API の使用を開始する](/office/office-365-management-api/get-started-with-office-365-management-apis)|365 Office 365 管理 API は、Azure ADを使用して、アプリケーションが Microsoft 365 データにアクセスする認証サービスを提供します。 この記事の手順に従って、これを設定します。|
|[Office 365 管理アクティビティ API リファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 管理アクティビティ API を使用して、Microsoft 365 および Azure AD アクティビティ ログからユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を取得できます。 この機能の詳細については、この記事を参照してください。|
|[Office 365 管理アクティビティ API のスキーマ](/office/office-365-management-api/office-365-management-activity-api-schema)|[Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の共通スキーマと Defender と脅威の調査と応答スキーマの概要を確認し、Office 365 管理アクティビティ API で利用できる特定の種類のデータについて説明します。 [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)|
|

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender での自動調査と対応](/microsoft-365/security/defender/m365d-autoir)
