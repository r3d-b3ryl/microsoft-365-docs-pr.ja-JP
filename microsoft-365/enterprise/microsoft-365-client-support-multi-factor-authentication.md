---
title: 'Microsoft 365 クライアント アプリのサポート: 多要素認証'
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
description: この記事では、Microsoft 365 の多要素認証をサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097470"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 クライアント アプリのサポート: 多要素認証

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

サインインの追加レベルのセキュリティを提供するために、クライアントは多要素認証 (MFA) を使用するように構成できます。MFA は、次に基づいてユーザー パスワードと追加のユーザー検証方法の両方を使用します。

- スマートフォンなど、簡単に複製できない所有物。
- 指紋、顔、その他の生体認証属性など、ユーザーが独自に持っているもの

多要素認証 [について詳しくは、次のリンクを参照してください](/azure/active-directory/authentication/multi-factor-authentication)。

## <a name="supported-clients--platforms"></a>サポートされているクライアント&プラットフォーム

次のクライアントとプラットフォームの最新バージョンは、多要素認証をサポートしています。 Microsoft 365 でのプラットフォーム サポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。
<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> 最新のアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Azure Admin | N/A | N/A | N/A | N/A | N/A |
| ポータル サイト | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Cortana | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Delve | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Edge | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Exchange Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Forms | N/A | N/A | N/A | N/A | N/A |
| Office 365 管理 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |  |
| Kaizala | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Office モバイル | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| OneNote | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Outlook | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Planner | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power アプリ | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Power Automate | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power BI | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| PowerPoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Project | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Publisher | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| SharePoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| SharePoint Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| 付箋 | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Stream | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |
| To Do | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | 計画済み | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| 職場の分析 | N/A | N/A | N/A | N/A | N/A |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)