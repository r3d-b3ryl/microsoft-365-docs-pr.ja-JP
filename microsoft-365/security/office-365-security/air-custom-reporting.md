---
title: 自動化された調査と対応によるカスタムレポートソリューションの使用
keywords: SIEM、API、AIR、自動赤外線、ATP、自動調査、統合、カスタムレポート
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 自動化された調査と応答を、カスタムまたはサードパーティのレポートソリューションと統合する方法について説明します。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 9bc5de44700b7f1b7207f8fae002adcb55d32841
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446685"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>カスタムまたはサードパーティのレポートソリューションに管理アクティビティ API を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 の Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)では、[自動調査に関する詳細情報](air-view-investigation-results.md)を入手できます。 ただし、組織によっては、カスタムまたはサードパーティのレポートソリューションを使用する場合もあります。 このようなソリューションで自動調査に関する情報を統合する必要がある組織では、Office 365 Management Activity API を使用できます。

これを設定するには、次のリソースを使用します。

****

|関連情報|説明|
|---|---|
|[Office 365 管理 API の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 Management Activity API は、Microsoft 365 および Azure Active Directory のアクティビティログから、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を提供します。|
|[Office 365 管理 API の使用を開始する](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 管理 API は、Azure AD を使用して、アプリケーションが Microsoft 365 データにアクセスするための認証サービスを提供します。 これを設定するには、この記事の手順に従います。|
|[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 Management Activity API を使用して、Microsoft 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。 この機能の詳細については、この記事を参照してください。|
|[Office 365 管理アクティビティ API のスキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、 [共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) と [OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) の概要を説明します。|
|

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Office 365](office-365-atp.md)

- [Microsoft 365 Defender での自動調査と応答](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
