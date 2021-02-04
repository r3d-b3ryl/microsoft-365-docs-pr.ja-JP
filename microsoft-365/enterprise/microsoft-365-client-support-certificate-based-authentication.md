---
title: 'Microsoft 365 クライアント アプリのサポート: 証明書ベースの認証'
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
description: この記事では、証明書ベースの認証に対する Microsoft 365 クライアント アプリのサポートの詳細について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097260"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 クライアント アプリのサポート: 証明書ベースの認証

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

最新の認証は、認証と承認方法の組み合わせの用語です。 これには次のものが含まれます。

- **認証方法**: 多要素認証クライアント証明書ベースの認証。
- **承認方法**: Microsoft による Open Authorization (OAuth) の実装。

Active Directory 認証ライブラリ (ADAL) や Microsoft 認証ライブラリ (MSAL) など、認証ライブラリを使用して、最新の認証を有効にします。 最新の認証とは、クライアントが Microsoft 365 リソースへのアクセスを認証および承認するために使用する認証です。 最新の認証は OAuth を活用し、クライアントがユーザーの資格情報にアクセスすることなく、Microsoft 365 サービスにアクセスするためのセキュリティで保護されたメカニズムを提供します。 サインイン時に、ユーザーは Azure Active Directory で直接認証を行い、アクセス/更新トークンのペアを受け取ります。 アクセス トークンは、Microsoft 365 テナント内の適切なリソースへのアクセスをクライアントに付与します。 更新トークンは、現在のアクセス トークンの有効期限が切れると、新しいアクセス トークンと更新トークンのペアを取得するために使用されます。

最新の認証は、証明書ベースの認証など、さまざまな認証メカニズムをサポートします。 Windows、Android、または iOS デバイス上のクライアントは、証明書ベース認証 (CBA) を使用して、デバイス上のクライアント証明書を使用して Azure Active Directory に対する認証を行えます。 一般的なユーザー名/パスワードの代わりに、Azure Active Directory からアクセス/更新トークンのペアを取得するために証明書が使用されます。

証明書ベースの認証 [について詳しくは、次のリンクを参照してください](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>サポートされているクライアント&プラットフォーム

次のクライアントとプラットフォームの最新バージョンは、クライアント内の Azure Active Directory アカウントにサインインするときに証明書ベースの認証をサポートします (たとえば、アプリにアカウントを追加する場合)。 Microsoft 365 でのプラットフォーム サポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。
<br>
<br>

| クライアント | Android | iOS | Mac| Windows 10 <br> 最新のアプリ| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Access | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Azure Admin | N/A | N/A | N/A | N/A | N/A |
| ポータル サイト | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Cortana | 計画済み | 計画済み | N/A | ![サポート](../media/check-mark.png) | N/A |
| Delve | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| エッジ<sup>1</sup> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Exchange Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| Forms | N/A | N/A | N/A | N/A | N/A |
| Office 365 管理 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |  |
| Kaizala | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Office モバイル | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画済み | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
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
| SharePoint Online 管理者 | 計画済み | 計画済み | N/A | N/A | N/A |
| 付箋 | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Stream | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | 計画済み |
| To Do | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | 計画済み | 計画済み | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| 職場の分析 | N/A | N/A | N/A | N/A | N/A |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画済み | N/A | 計画済み |

>[!NOTE]
><sup>iOS および</sup> Android 用の 1 つのエッジは、アカウントの追加フロー中に証明書ベースの認証をサポートします。 iOS および Android 用のエッジは、Web サイト (通常はイントラネット サイト) に対して認証を実行する場合、証明書ベースの認証をサポートしていない。 <br><br>  このシナリオでは、ユーザーは Web サイト (通常はイントラネット上) に移動します。このサイトでは、ユーザーが証明書を使用して認証する必要があります。 これには、最新の認証は含まれるのではなく、Microsoft 認証ライブラリを利用する必要もあります。 これは iOS の制限による影響です。iOS は、サード パーティ製アプリが証明書が保存されているシステム キーチェーンにアクセスするのを防止します (Apple アプリと [Safari Webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) コントローラーだけがシステム キーチェーンにアクセスできます)。 <br><br> Edge が Web サイトのレンダリングに [WebKit](https://developer.apple.com/documentation/webkit) フレームワークに依存している場合、Edge はシステム キーチェーンにアクセスできず、証明書の選択肢をユーザーに提示できません。 これは、残念ながら、Apple のアーキテクチャによる設計です。

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

