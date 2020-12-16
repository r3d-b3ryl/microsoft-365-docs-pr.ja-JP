---
title: Microsoft Cloud Deutschland からの移行に関するその他の Azure Active Directory 情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する場合の追加の Azure Active Directory 情報。'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688801"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行に関するその他の Azure Active Directory 情報

Azure German クラウドから Azure パブリック クラウドへの移行を完了するには、OpenID Connect (OIDC) エンドポイントが商用クラウド エンドポイントのレポートを開始するときに、アプリケーションの認証エンドポイント、Azure Active Directory (Azure AD) Graph、および MS Graph エンドポイントを商用クラウドのエンドポイントに更新することをお勧めします。 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 
 
**この変更は、いつ行う必要がありますか?**

テナントがドイツのクラウドから商用クラウドへの移行を完了すると、Azure/Office ポータルで通知を受け取ります。 Azure Germany クラウドから Azure Public cloud に移行されたテナントでアプリが引き続き動作するように、これらの更新を完了するには、この通知を受信して 30 日後になります。
 
サインイン機関の更新には、次の 3 つの事前条件があります。

 - テナントの OIDC 検出エンドポイントは `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 、Azure ADパブリック クラウド エンドポイントを返します。

 - テナントがフェデレーション用に設定されている場合、Active Directory フェデレーション サービス (AD FS) が更新され、Azure AD Public と同期されます。 この変更を行う手順に従って、Azure AD Connect の設定を更新できます。

 - アプリケーションで使用されるリソース アプリケーションがある場合は、Azure AD Germany と Azure AD Public の両方によって署名されたトークンを受け入ADされます。
 
**どのような種類のアプリケーションですか?**

アプリケーションには、次の種類があります。

- [シングルページ アプリ (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [ユーザーにサインインする Web アプリ](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Web API を呼び出す Web アプリ](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [保護された Web API](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Web API を呼び出す Web API](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [デスクトップ アプリ](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [デーモン アプリ](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [モバイル アプリ](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> アプリケーションが権限としての使用に切 `login.microsoftonline.com` り替えた場合、トークンはこの新しい機関によって署名されます。 他のアプリが呼び出すリソース アプリケーションをホストする場合は、lax トークンの検証を許可する必要があります。 つまり、アプリは、Azure AD Germany と Azure ADパブリック クラウドの両方によって署名されたトークンを許可する必要があります。 この時間不足トークンの検証は、サービスを呼び出すすべてのクライアント アプリケーションがパブリック クラウドの Azure ADされるまで必要です。 移行後、リソース アプリケーションは、Azure によって署名されたトークンをパブリック クラウドAD受け入れる必要があります。

**更新する必要があるもの**

1. Azure Germany または Office 365 Germany ユーザーの認証に使用されるアプリケーションを Azure Germany でホストしている場合は、認証コンテキストで権限として使用してください。 `https://login.microsoftonline.com`

    - Azure 認証コンテキストAD参照してください。
    - これは、アプリケーションの認証と、アプリケーションが呼び出している可能性がある API (Microsoft Graph、Azure AD Graph、Azure Resource Manager) に対する認証の両方に適用されます。

2. Azure AD Graph エンドポイントを更新します `https://graph.windows.net` 。

3. MS Graph エンドポイントを更新します `https://graph.microsoft.com` 。

4. アプリケーションで使用されているドイツのクラウド エンドポイント (Exchange Online や SharePoint Online 用など) をパブリック クラウドのエンドポイントに更新します。

5. 管理ツールとスクリプトの `AzurePublic` 環境パラメーターを (代わりに) 次 `AzureGermany` の値に更新します。

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**発行するアプリケーションについて**

テナント外のユーザーが利用できるアプリケーションを公開する場合は、継続性を確保するためにアプリケーションの登録を変更する必要があります。 アプリケーションを使用する他のテナントは、テナントとは異なる時刻に移動される可能性があります。 アプリケーションへのアクセス権が失われるのを確実に行わないには、アプリが Azure Germany から Azure パブリックに同期されるのに同意する必要があります。

## <a name="additional-considerations"></a>その他の考慮事項

Azure AD に関するその他の考慮事項を以下に示AD。

- フェデレーション認証の場合:

  - テナント移行の実行中は、フェデレーション ドメインの作成、昇格、または降格を行う必要があります。 Azure AD サービスへの移行が完了した後 (テナントは完全に完了しています)、フェデレーション ドメインの管理を再開できます。

  - Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用している場合は、移行中にオンプレミスの Active Directory ドメイン サービス (AD DS) ですべての認証に使用される発行者 URI を変更する必要があります。 発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。 発行者 URI は、AD FS で直接変更したり、ドメインを管理からフェデレーションに変換したり、その逆に変更したりできます。 Microsoft では、移行する Azure テナントのフェデレーション ドメインを追加、削除、または変換AD勧めします。 発行者 URI は、移行が完全に完了した後で変更できます。

- ネットワークの場合:

  - IPv6 名のネットワークの作成は、Azure portal では機能しません `http://portal.microsoftazure.de/` 。 Azure ポータルを使用して `https://portal.azure.com` IPv6 名のネットワークを作成します。
 
   - Microsoft Cloud Deutschland ポータルから Azure Multi-Factor Authentication (MFA) サービス設定の信頼できる IP アドレス範囲を作成できません。 365 サービス用の Azure AD ポータルをOffice Azure MFA の信頼できる IP アドレス範囲を作成します。


- 条件付きアクセスの場合: 

  - Office 365 サービスへの移行が完了するまで [(Azure](ms-cloud-germany-transition.md#how-is-the-migration-organized) 365 移行フェーズの最終処理後)、次の付与制御を持つ条件付きアクセス ポリシー ADされません。

    - 準拠デバイスが必要
    - 承認済みアプリを要求する
    - アプリ保護ポリシーを要求する
    
  - 条件付きアクセス ポリシー インターフェイスは、無効になっている場合でもテナントに対して有効になっているセキュリティの既定値に関する誤った警告を表示し、条件付きアクセス ポリシーはテナントに対して既に存在します。 この警告は無視するか、Office 365 サービス ポータルを使用して条件付きアクセス ポリシーを管理する必要があります。 

- Intune のシナリオは、テナントの移行が完了した後、すべての Office ワークロードの移行を含む、世界中のエンドポイントに対してだけサポートされます。

- MFA 要求にモバイル アプリ通知メソッドを使用する Microsoft Cloud Deutschland ユーザーには、Microsoft Authenticator アプリのユーザー プリンシパル名 (UPN) の代わりにユーザーの ObjectId (GUID) が表示されます。 Azure AD テナントの移行が完了し、Office 365 サービスでホストされると、新しい Microsoft Authenticator ライセンス認証にユーザーの UPN が表示されます。 既存の Microsoft Authenticator アカウントは引き続きユーザー ObjectId を表示しますが、モバイル アプリ通知では引き続き機能します。 

- 2019 年 10 月 22 日より後に作成されたテナントの場合、Office 365 サービスに移行するときに、そのテナントのセキュリティの既定値が自動的に有効になる場合があります。 テナント管理者は、セキュリティの既定値を有効のままにして MFA に登録するか、機能を無効にできます。 詳細については、「セキュリティの既定値 [を無効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。 

  > [!NOTE]
  > 移行中に自動有効になっていない組織は、将来、セキュリティの既定値を有効にする機能が Office 365 サービスに展開される可能性があります。 セキュリティの既定値を明示的に無効または有効にした管理者は **、Azure Active Directory** の [プロパティ] で機能を更新>できます。 管理者が機能を明示的に有効にすると、その機能は自動有効になりません。

- テナントの移行が完了すると、Office 365 Germany ポータルと Office 365 ポータルの Azure AD Connect のバージョンに関する警告が表示されます。 移行の完了後にバージョンの警告に警告が表示されなくなった場合は、無視できます。 移行前または移行後にいずれかのポータルで警告がある場合は、Azure AD Connect を更新する必要があります。 警告メッセージには、「古いディレクトリ同期ツールを使用しているのが検出されました。 Microsoft ダウンロード センターにアクセスして、Azure AD Connect の最新バージョンを取得することをお勧めします。

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
