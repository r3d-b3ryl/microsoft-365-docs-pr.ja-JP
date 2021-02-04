---
title: 'Microsoft 365 クライアント アプリのサポート: 単一Sign-On'
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
description: この記事では、Microsoft 365 のシングル サインオンをサポートするプラットフォーム、クライアント、PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a685f04ed64a89cda026ff9380aac7c6c2b3ea4
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097200"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365 クライアント アプリのサポート: 単一Sign-On

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

シングル サインオン (SSO) を使用すると、ユーザーが Azure Active Directory のアプリケーションにサインオンするときにセキュリティと利便性が向上します。 シングル サインオンでは、ユーザーは 1 つのアカウントで 1 回サインインして、オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインに参加しているデバイス、サービスとしてのソフトウェア (SaaS) アプリケーション、および Web アプリケーションにアクセスします。

シングル サインオンについて [詳しくは、次のリンクを参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。

## <a name="supported-clients--platforms"></a>サポートされているクライアント&プラットフォーム

次のクライアントとプラットフォームの最新バージョンでは、シングル サインオンがサポートされています。 Microsoft 365 でのプラットフォーム サポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。
<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> 最新のアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| ポータル サイト | N/A | ![サポート](../media/check-mark.png) | 計画済み | ![サポート](../media/check-mark.png) | N/A |
| Cortana | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Delve | 計画済み | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Edge | ![サポート](../media/check-mark.png) | 計画済み | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Kaizala | ![サポート](../media/check-mark.png) | 計画済み | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office モバイル | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画済み | ![サポート](../media/check-mark.png) | 計画済み |
| OneNote | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画済み |
| Outlook | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画済み | ![サポート](../media/check-mark.png) |
| Planner | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power アプリ | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | 計画済み | N/A |
| Power Automate | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Power BI | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | 計画済み |
| PowerPoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Project | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Publisher | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Skype for Business | 計画済み | 計画済み | N/A | N/A | N/A |
| SharePoint | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| 付箋 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Stream | 計画済み | 計画済み | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画済み | N/A | 計画済み |
| To Do | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | N/A | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | 計画済み |

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
