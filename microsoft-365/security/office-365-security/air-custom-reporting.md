---
title: 自動調査と対応を備えたカスタム レポート ソリューション
keywords: SIEM, API, AIR, autoIR, ATP, 自動調査, 統合, カスタム レポート
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
description: 自動調査と対応をカスタムまたはサード パーティ製のレポート ソリューションに統合する方法について説明します。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142977"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 向けカスタム またはサード パーティ製のレポート ソリューション

Microsoft [Defender for Office 365](office-365-atp.md)では、自動調査に関する [詳細情報を取得できます](air-view-investigation-results.md)。 ただし、一部の組織では、カスタムまたはサード パーティ製のレポート ソリューションも使用します。 自動調査に関する情報をそのようなソリューション[](office-365-air.md)と統合する場合は、Office 365 マネージメント アクティビティ API を使用できます。

統合を構成するリソース

|関連情報|説明|
|:---|:---|
|[Office 365 管理 API の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 管理アクティビティ API は、Microsoft 365 と Azure Active Directory のアクティビティ ログから、さまざまなユーザー、管理者、システム、およびポリシー アクションとイベントに関する情報を提供します。|
|[Office 365 管理 API の使用を開始する](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 管理 API は、Azure AD を使用して、アプリケーションが Microsoft 365 データにアクセスする認証サービスを提供します。 この記事の手順に従って設定します。|
|[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 管理アクティビティ API を使用して、Microsoft 365 および Azure AD アクティビティ ログから、ユーザー、管理者、システム、およびポリシー アクションとイベントに関する情報を取得できます。 この機能の詳細については、この記事を参照してください。|
|[Office 365 管理アクティビティ API のスキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 マネージメント アクティビティ API を通じて利用できる特定の種類のデータについて学習するには、共通スキーマと[Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)用 Defender と脅威の調査と対応スキーマの概要を説明します。 [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)|
|

## <a name="see-also"></a>こちらもご覧ください

- [Microsoft Defender for Office 365](office-365-atp.md)
- [Microsoft 365 Defender での自動調査と対応](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
