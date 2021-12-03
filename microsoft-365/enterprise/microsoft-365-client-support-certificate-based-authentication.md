---
title: 'Microsoft 365 クライアント アプリのサポート: 証明書ベースの認証'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、証明書ベース認証Microsoft 365クライアント アプリのサポートに関する詳細を確認します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57f86d7cba4e6723b2f7ef6261a708f16b6e74be
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284423"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 クライアント アプリのサポート: 証明書ベースの認証

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

最新の認証は、認証と承認方法の組み合わせの傘下の用語です。 以下のようなメソッドがあります。

- **認証方法**: 多要素認証。クライアント証明書ベースの認証。
- **承認方法**: Microsoft による Open Authorization (OAuth) の実装。

最新の認証は、Microsoft 認証ライブラリ [(MSAL) のような認証ライブラリを使用して有効になります](/azure/active-directory/develop/msal-overview)。 最新の認証とは、クライアントがリソースへのアクセスを認証および承認するために使用Microsoft 365です。 最新の認証では、OAuth を使用し、クライアントがユーザー資格情報にアクセスすることなく、Microsoft 365サービスにアクセスするための安全なメカニズムを提供します。 サインイン時に、ユーザーはユーザーに対して直接認証Azure Active Directoryアクセス/更新トークンのペアを受け取ります。 アクセス トークンは、クライアント がテナント内の適切なリソースにアクセスMicrosoft 365します。 更新トークンは、現在のアクセス トークンの有効期限が切れたときに、新しいアクセス トークンまたは更新トークンのペアを取得するために使用されます。

最新の認証では、証明書ベースの認証など、さまざまな認証メカニズムがサポートされています。 デバイス、Windows、または iOS デバイス上のクライアントは、証明書ベース認証 (CBA) を使用して、Azure Active Directoryを使用して認証できます。 一般的なユーザー名/パスワードの代わりに、証明書を使用してアクセス/更新トークンのペアをAzure Active Directory。

証明書ベースの [認証の詳細については、次のページを参照してください](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>サポートされているクライアント&プラットフォーム

次のクライアントとプラットフォームの最新バージョンでは、クライアント内の Azure Active Directory アカウントにサインインするときに証明書ベースの認証がサポートされます (たとえば、アプリにアカウントを追加する場合)。 プラットフォームサポートの詳細については、「Microsoft 365のシステム要件」[を参照Microsoft 365。](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

> [!NOTE]
> iOS と Android のエッジは、アカウントの追加フロー中に証明書ベースの認証をサポートします。 iOS と Android のエッジは、通常はイントラネット サイトである Web サイトに対して認証を実行する場合、証明書ベースの認証をサポートします。 <br><br>  このシナリオでは、ユーザーは Web サイト (通常はイントラネット上) に移動し、Web サイトはユーザーに証明書による認証を要求します。 これは、最新の認証を全く伴うのではなく、Microsoft 認証ライブラリを活用する必要があります。 これは、iOS の制限による影響です。iOS は、サード パーティ製アプリが証明書が保存されているシステムキーチェーンにアクセスするのを防止します (Apple アプリと [Safari Webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) コントローラーだけがシステムキーチェーンにアクセスできます)。 <br><br> Edge は [WebKit](https://developer.apple.com/documentation/webkit) フレームワークを使用して Web サイトをレンダリングします。Edge はシステムキーチェーンにアクセスできず、証明書の選択肢をユーザーに提示できません。 これは、残念ながら、Apple のアーキテクチャによる設計です。

## <a name="supported-powershell-modules"></a>サポートされている PowerShell モジュール

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
