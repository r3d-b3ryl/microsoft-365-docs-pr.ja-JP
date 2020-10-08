---
title: Microsoft 365 クライアントアプリケーションのサポート-シングルサインオン
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 のシングルサインオンをサポートするプラットフォーム、クライアント、および Powershell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0a45c30ffe736cf67e811bce6eb029d6fb50674
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384805"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Microsoft 365 クライアントアプリケーションのサポート-シングルサインオン

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

シングルサインオン (SSO) を使用すると、ユーザーが Azure Active Directory (Azure AD) のアプリケーションにサインオンするときに、セキュリティと利便性が向上します。 シングルサインオンを使用すると、ユーザーは1回サインインするだけで、オンプレミスの Active Directory ドメインサービス (AD DS)、ドメインに参加しているデバイス、サービス (SaaS) アプリケーションとしてのソフトウェア、web アプリケーションにアクセスできます。

[シングルサインオン](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)の詳細については、こちらを参照してください。

## <a name="supported-platforms"></a>サポートされるプラットフォーム

 - Windows 10 デスクトップ<sup>2</sup>
 - Windows 10 モダンアプリ
 - Web ブラウザー
 - Android<sup>3</sup>
 - iOS<sup>1</sup>
 - macOS<sup>4</sup>

Microsoft 365 でのプラットフォームサポートの詳細については、「 [microsoft 365 のシステム要件](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)」を参照してください。

## <a name="supported-clients"></a>サポートされるクライアント

次のクライアントの最新バージョンは、シングルサインオンをサポートしています。

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access アイコン](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![会社のポータルのアイコン](../media/o365-microsoft-64x64.png) <br> [会社 <br> ポータル<sup>3、4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Delve アイコン](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![エッジアイコン](../media/o365-edge-64x64.png) <br> [エッジ<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Excel アイコン](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Kaizala アイコン](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com アイコン](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![レンズアイコン](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive for Business アイコン](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![OneNote アイコン](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Outlook アイコン](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Planner アイコン](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![電源の自動化アイコン](../media/o365-flow-64x64.png) <br> [電源の <br> 自動化](https://flow.microsoft.com) | ![PowerBI アイコン](../media/o365-powerbi-64x64.png) <br> [Power BI<sup>2</sup>](https://powerbi.microsoft.com)| ![PowerPoint アイコン](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project アイコン](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher アイコン](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint アイコン](../media/o365-sharepoint-64x64.png) <br> [Sharepoint](https://products.office.com/sharepoint) | ![付箋アイコン](../media/o365-stickynotes-64x64.png) <br> [付箋](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Sway アイコン](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![Teams アイコン](../media/o365-teams-64x64.png) <br> [Teams<sup>2、4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![To Do アイコン](../media/o365-todo-64x64.png) <br> [やるべきこと](https://todo.microsoft.com) | ![Visio アイコン](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard アイコン](../media/o365-whiteboard-64x64.png) <br> [ホワイトボード<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Word アイコン](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Yammer アイコン](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure アイコン](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange アイコン](../media/o365-exchange-64x64.png) <br> [Exchange Online の <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint アイコン](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> iOS でのエッジと Kaizala のサポートはすぐにご利用いただけます。 <br>
> <sup>2</sup> Windows 10 デスクトップでの OneNote、PowerBI、Teams、Yammer のサポートが近日中に利用可能になります。 <br>
> <sup>3</sup> Android On ホワイトボードのサポートが近日中に利用可能になります。 <br>
> <sup>4</sup> MacOS の Outlook、Teams、およびポータルサイトのサポートが近日中に利用可能になります。 <br>

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
