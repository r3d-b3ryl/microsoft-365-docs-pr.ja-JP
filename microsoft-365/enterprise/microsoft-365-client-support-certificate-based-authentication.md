---
title: 'Microsoft 365 クライアントアプリケーションのサポート: 証明書ベースの認証'
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
description: この記事では、Microsoft 365 クライアントアプリによる証明書ベース認証のサポートに関する詳細を確認します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fde124fcefdf3b949ec35a3b2ed99b15ee36f85e
ms.sourcegitcommit: 2beefb695cead03cc21d6066f589572d3ae029aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349682"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 クライアントアプリケーションのサポート: 証明書ベースの認証

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

先進認証は、認証と承認の方法を組み合わせた包括的な用語です。 これには次のものが含まれます。

- **認証方法**: 多要素認証。クライアント証明書ベースの認証。
- **承認方法**: Microsoft がオープン認証を実装しています (OAuth)。

モダン認証は、Active Directory Authentication Library (ADAL) や Microsoft Authentication Library (MSAL) などの認証ライブラリを使用して有効にします。 モダン認証は、クライアントが Microsoft 365 リソースへのアクセスを認証および承認するために使用します。 モダン認証は OAuth を活用し、クライアントが Microsoft 365 サービスにアクセスするための安全なメカニズムを提供します。ユーザー資格情報へのアクセスは必要ありません。 サインイン時に、ユーザーは Azure Active Directory を使用して直接認証を行い、アクセス/更新トークンのペアを取得します。 アクセストークンにより、クライアントは Microsoft 365 テナントの適切なリソースにアクセスできるようになります。 更新トークンは、現在のアクセストークンの有効期限が切れたときに、新しいアクセスまたは更新トークンのペアを取得するために使用されます。

モダン認証は、証明書ベースの認証などのさまざまな認証メカニズムをサポートします。 Windows、Android、iOS デバイス上のクライアントは、証明書ベースの認証 (CBA) を使用して、デバイス上のクライアント証明書を使用して Azure Active Directory を認証できます。 通常のユーザー名とパスワードの代わりに、証明書を使用して、Azure Active Directory からアクセス/更新トークンのペアを取得します。

[証明書ベースの認証](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)の詳細について説明します。

## <a name="supported-clients--platforms"></a>サポートされているクライアント & プラットフォーム

次のクライアントおよびプラットフォームの最新バージョンは、クライアント内で Azure Active Directory アカウントにサインインするときに、証明書ベースの認証をサポートします (たとえば、アカウントをアプリに追加する場合)。 Microsoft 365 でのプラットフォームサポートの詳細については、「 [microsoft 365 のシステム要件](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)」を参照してください。
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
| エッジ<sup>1</sup> | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Excel | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Exchange Online 管理者 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |
| フォーム | N/A | N/A | N/A | N/A | N/A |
| Office 365 管理 | N/A | N/A | N/A | N/A | ![サポート](../media/check-mark.png) |  |
| Kaizala | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office Lens| ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | ![サポート](../media/check-mark.png) | N/A |
| Office mobile | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Office ポータル | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| OneDrive | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
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
| SharePoint Online 管理者 | 計画 | 計画 | N/A | N/A | N/A |
| 付箋 | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Stream | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | N/A | N/A |
| Sway | N/A | N/A | N/A | ![サポート](../media/check-mark.png) | N/A |
| Teams | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A | 計画 |
| やるべきこと | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | N/A |
| Visio | N/A | ![サポート](../media/check-mark.png) | N/A | N/A | ![サポート](../media/check-mark.png) |
| Whiteboard | 計画 | 計画 | N/A | ![サポート](../media/check-mark.png) | N/A |
| Word | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) |
| Workplace analysis | N/A | N/A | N/A | N/A | N/A |
| Yammer | ![サポート](../media/check-mark.png) | ![サポート](../media/check-mark.png) | 計画 | N/A | 計画 |

>[!NOTE]
>iOS および Android 用の<sup>1</sup>エッジは、アカウントの追加フロー時に証明書ベースの認証をサポートします。 IOS および Android のエッジでは、web サイト (通常はイントラネットサイト) に対して認証を実行するときに、証明書ベースの認証をサポートしていません。 <br><br>  このシナリオでは、ユーザーが web サイト (通常はイントラネット) に移動し、web サイトで証明書による認証をユーザーに要求する必要があります。 これには先進認証は含まれておらず、Microsoft 認証ライブラリは利用されません。 これは、iOS の制限によるもので、サードパーティ製のアプリは、証明書が格納されているシステムキーチェーンにアクセスできません (Apple アプリと [Safari webview controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) のみがシステムキーチェーンにアクセスできる)。 <br><br> エッジが web サイトをレンダリングするために [WebKit](https://developer.apple.com/documentation/webkit) フレームワークに依存している場合、エッジはシステムキーチェーンにアクセスできず、ユーザーに証明書選択が表示されません。 残念ながら、これは Apple のアーキテクチャに起因する仕様です。

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

