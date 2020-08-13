---
title: 自動化された調査と対応によるカスタムレポートソリューションの使用
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
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
ms.collection: M365-security-compliance
description: 自動化された調査と応答を、カスタムまたはサードパーティのレポートソリューションと統合する方法について説明します。
ms.openlocfilehash: cd7eb016ecd250eef56039e0135237c1caebadf8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656899"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>カスタムまたはサードパーティのレポートソリューションに管理アクティビティ API を使用する

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)を使用すると、[自動調査に関する詳細情報](air-view-investigation-results.md)を取得できます。 ただし、組織によっては、カスタムまたはサードパーティのレポートソリューションを使用する場合もあります。 このようなソリューションで自動調査に関する情報を統合する必要がある組織では、Office 365 Management Activity API を使用できます。

これを設定するには、次のリソースを使用します。

****

|関連情報|説明|
|---|---|
|[Office 365 管理 API の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 Management Activity API は、Microsoft 365 および Azure Active Directory のアクティビティログから、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を提供します。|
|[Office 365 管理 API の使用を開始する](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 管理 API は、Azure AD を使用して、アプリケーションが Microsoft 365 データにアクセスするための認証サービスを提供します。 これを設定するには、この記事の手順に従います。|
|[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Office 365 Management Activity API を使用して、Microsoft 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。 この機能の詳細については、この記事を参照してください。|
|[Office 365 管理アクティビティ API のスキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、 [共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) と [OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) の概要を説明します。|
|

## <a name="related-articles"></a>関連記事

- [Office 365 Advanced Threat Protection](office-365-atp.md)

- [Microsoft の脅威保護の自動化された調査と対応について説明します。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)