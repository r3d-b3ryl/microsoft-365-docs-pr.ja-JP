---
title: 調査と応答を自動化したカスタム レポート ソリューション
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, 自動調査, 統合, カスタム レポート
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 自動調査と対応をカスタムまたはサードパーティのレポート ソリューションと統合する方法について説明します。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ff4317fc195a175a2b622c13ea4683a5e010b1c
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680711"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365用のカスタムまたはサードパーティのレポート ソリューション

[Microsoft Defender for Office 365](defender-for-office-365.md)を使用すると、[自動調査に関する詳細情報を取得できます](air-view-investigation-results.md)。 ただし、一部の組織では、カスタムまたはサード パーティのレポート ソリューションも使用しています。 組織が[自動調査](office-365-air.md)に関する情報をそのようなソリューションと統合する場合は、Office 365 Management Activity API を使用できます。

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)を使用すると、[自動調査に関する詳細情報を取得できます](air-view-investigation-results.md)。 ただし、一部の組織では、カスタムまたはサード パーティのレポート ソリューションも使用しています。 組織が自動調査に関する情報をそのようなソリューションと統合する場合は、Office 365 Management Activity API を使用できます。

|関連情報|説明|
|:---|:---|
|[Office 365 管理 API の概要](/office/office-365-management-api/office-365-management-apis-overview)|Office 365 Management アクティビティ API は、Microsoft 365およびAzure Active Directoryアクティビティ ログから、さまざまなユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を提供します。|
|[Office 365 管理 API の使用を開始する](/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 Management API では、Azure ADを使用して、アプリケーションがMicrosoft 365データにアクセスするための認証サービスを提供します。 この記事の手順に従って設定します。|
|[Office 365 管理アクティビティ API リファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 Management アクティビティ API を使用して、ユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報をMicrosoft 365およびAzure ADアクティビティ ログから取得できます。 この動作の詳細については、この記事を参照してください。|
|[Office 365 管理アクティビティ API のスキーマ](/office/office-365-management-api/office-365-management-activity-api-schema)|[共通スキーマ](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[Defender for Office 365と脅威の調査と対応スキーマ](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を確認し、Office 365 Management Activity API を使用して使用可能な特定の種類のデータについて説明します。|

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender での自動調査と応答](/microsoft-365/security/defender/m365d-autoir)
