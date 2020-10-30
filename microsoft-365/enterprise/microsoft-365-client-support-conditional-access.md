---
title: 'Microsoft 365 クライアントアプリケーションのサポート: 条件付きアクセス'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 の条件付きアクセスをサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806684"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365 クライアントアプリケーションのサポート: 条件付きアクセス

モダンワークプレースでは、ユーザーはさまざまなデバイスやアプリを使用してどこからでも組織のリソースにアクセスできます。 そのため、リソースにアクセスできるユーザーだけでは十分ではないことに注目してください。 組織は、アクセス制御インフラストラクチャでリソースにアクセスする方法と場所もサポートする必要があります。

Azure Active Directory デバイス、場所、および多要素認証ベースの条件付きアクセスを使用すると、この新しい要件を満たすことができます。 条件付きアクセスとは、環境内のアプリへのアクセスに対して、特定の条件に基づいて管理されたアプリケーションへのアクセスの制御を可能にする Azure Active Directory の機能です。

詳細については、「 [Azure Active Directory の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/)」を参照してください。

## <a name="supported-clients--platforms"></a>サポートされているクライアント & プラットフォーム

次のクライアントおよびプラットフォームの最新バージョンは、条件付きアクセスをサポートしています。 Microsoft 365 でのプラットフォームサポートの詳細については、「 [microsoft 365 のシステム要件](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)」を参照してください。

<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> モダンアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Azure 管理者 | N/A | N/A | N/A | N/A | N/A |
| 会社のポータル | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Cortana | 計画 | 計画 | N/A | ![サポート](../media/check-mark.png) | N/A |
| Delve | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Edge | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Exchange Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| フォーム | N/A | N/A | N/A | N/A | N/A |
| Office 365 管理 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |  |
| Kaizala | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Office mobile | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| OneNote | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Outlook | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Planner | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power アプリ | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | 計画 | N/A |
| Power Automate | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power BI | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| PowerPoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Project | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Publisher | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A ||
| SharePoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| SharePoint Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| 付箋 | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Stream | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |
| やるべきこと | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | 計画 | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Workplace analysis | N/A | N/A | N/A | N/A | N/A |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
