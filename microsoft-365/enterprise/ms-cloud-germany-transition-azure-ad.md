---
title: Microsoft Cloud deutschland Azure Active Directory移行に関する追加情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Azure Active Directory Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域Office 365サービスに移行する際の追加情報。'
ms.openlocfilehash: 349df1366c76eb23c8aaaf0447ef90a031e6e52d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189059"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud deutschland Azure Active Directory移行に関する追加情報

Azure German クラウドから Azure パブリック クラウドへの移行を完了するには、OpenID Connect (OIDC) エンドポイントが商用クラウド エンドポイントの報告を開始するときに、アプリケーションの認証エンドポイント、Azure Active Directory (Azure AD) Graph、および MS Graph エンドポイントを商用クラウドのエンドポイントに更新することをお勧めします。 `https://login.microsoftonline.com/<TenantIdOrDomain>/.well-known/openid-configuration` 
 
**いつこの変更を行う必要がありますか?**

テナントがドイツのクラウドから商用クラウドへの移行を完了すると、Azure/Office ポータルで通知を受け取ります。 これらの更新プログラムを完了するには、この通知を受信して 30 日後に、Azure Germany クラウドから Azure Public cloud に移行されたテナントでアプリが引き続き動作するようにします。
 
サインイン機関の更新には、次の 3 つの条件があります。

 - テナントの OIDC 検出エンドポイントは `https://login.microsoftonline.com/<TenantIdOrDomain>/.well-known/openid-configuration` 、Azure ADパブリック クラウド エンドポイントを返します。

 - テナントがフェデレーション用に設定されている場合は、Active Directory フェデレーション サービス (AD FS) が更新され、Azure ADパブリックと同期されます。 この変更を行う手順に従って Azure AD Connect設定を更新できます。

 - アプリケーションで使用されているリソース アプリケーションがある場合は、Azure AD および Azure AD Public の両方によって署名されたトークンを受け入ADされます。
 
**どのような種類のアプリケーションですか?**

アプリケーションには、次に示す任意のアプリケーションを指定できます。

- [シングル ページ アプリ (SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [ユーザーにサインインする Web アプリ](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Web API を呼び出す Web アプリ](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [保護された Web API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Web API を呼び出す Web API](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [デスクトップ アプリ](/azure/active-directory/develop/scenario-desktop-overview)
- [Daemon アプリ](/azure/active-directory/develop/scenario-daemon-overview)
- [モバイル アプリ](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> アプリケーションが権限として使用に `login.microsoftonline.com` 切り替えた場合、トークンはこの新しい機関によって署名されます。 他のアプリが呼び出すリソース アプリケーションをホストする場合は、時間の少ないトークンの検証を許可する必要があります。 つまり、アプリは、Azure とドイツと Azure の両方のパブリック クラウドADトークンAD必要があります。 この時間の少ないトークン検証は、サービスを呼び出すすべてのクライアント アプリケーションがパブリック クラウドの Azure ADされるまで必要です。 移行後、リソース アプリケーションは、Azure によって署名されたトークンをパブリック クラウドAD受け入れる必要があります。

**更新する必要があるもの**

1. Azure Germany または Office 365 ドイツ のユーザーの認証に使用されるアプリケーションを Azure Germany でホストしている場合は、認証コンテキストの機関として使用してください `https://login.microsoftonline.com` 。

    - 「Azure AD認証コンテキスト」を参照してください。
    - これは、アプリケーションの認証と、アプリケーションが呼び出す可能性がある任意の API (Microsoft Graph、Azure AD Graph、Azure Resource Manager) への認証の両方に適用されます。

2. Azure AD Graphエンドポイントを更新します `https://graph.windows.net` 。

3. Microsoft Graphエンドポイントを更新します `https://graph.microsoft.com` 。

4. アプリケーションがパブリック クラウドとして使用するドイツのクラウド エンドポイント (Exchange Online および SharePoint Online 用など) を更新します。

5. 管理ツールとスクリプトの `AzurePublic` 環境パラメーターを (代わりに) 更新 `AzureGermany` します。

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**発行するアプリケーションについて**

テナント外のユーザーが利用できるアプリケーションを発行する場合は、継続性を確保するためにアプリケーションの登録を変更する必要があります。 アプリケーションを使用する他のテナントは、テナントとは異なる時刻に移動される可能性があります。 アプリケーションへのアクセスが失われるのを確実に行わないには、アプリが Azure Germany から Azure Public に同期されている状態に同意する必要があります。

**移行中に新しいマルチテナント アプリケーションを追加する方法は?**

別の組織 (マルチテナント アプリケーション) によって発行された新しいアプリケーションを使用する場合は、移行プロセス (フェーズ 2 ~ フェーズ 9) 中にアプリケーションの追加を制限されます。  組織がフェーズ 9 を完了し、Azure パブリック インスタンスに完全に移行するときに、このタスクを実行できます。

## <a name="additional-considerations"></a>その他の考慮事項

Azure の追加の考慮事項を次に示AD。

- フェデレーション認証の場合:

  - テナント移行の実行中は、フェデレーション ドメインを作成、昇格、または降格できません。 Azure AD サービスへの移行が完了した後 (テナントが完全に完了)、フェデレーション ドメインの管理を再開できます。

  - Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用している場合は、移行中にオンプレミスの Active Directory ドメイン サービス (AD DS) ですべての認証に使用される発行者 URI を変更する必要があります。 発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。 発行者 URI は、FS またはドメインAD管理からフェデレーションに変換される場合、またはその逆に直接変更できます。 移行する Azure ドメインのフェデレーション ドメインを追加、削除、または変換AD推奨します。 発行者 URI は、移行が完全に完了した後で変更できます。

- ネットワークの場合:

  - IPv6 名前付きネットワークの作成は、Azure portal では機能しません `http://portal.microsoftazure.de/` 。 Azure portal を使用して `https://portal.azure.com` 、IPv6 名前付きネットワークを作成します。
 
   - Microsoft Cloud Deutschland ポータルから Azure 多要素認証 (MFA) サービス設定の信頼できる IP アドレス範囲を作成できません。 Azure MFA の信頼AD IP アドレスOffice 365作成するには、Azure Office 365 ポータルを使用します。


- 条件付きアクセスの場合: 

  - 次の付与制御を持つ条件付きアクセス ポリシーは、Office 365 サービスへの移行が完了するまでサポートされません[(Finalize Azure](ms-cloud-germany-transition.md#how-is-the-migration-organized) AD移行フェーズの後)。

    - 準拠デバイスを要求する
    - 承認済みアプリを要求する
    - アプリ保護ポリシーを要求する
    
  - 条件付きアクセス ポリシー インターフェイスは、無効になっている場合でもテナントに対して有効になっているセキュリティの既定値に関する誤った警告を表示し、条件付きアクセス ポリシーはテナントに対して既に存在します。 警告を無視するか、サービス ポータルOffice 365条件付きアクセス ポリシーを管理する必要があります。 

- Intune のシナリオは、テナントの移行が完了した後、すべての Office ワークロードの移行を含む、世界中のエンドポイントに対してのみサポートされます。

- MFA 要求にモバイル アプリ通知メソッドを使用する Microsoft Cloud Deutschland ユーザーには、Microsoft Authenticator アプリのユーザー プリンシパル名 (UPN) の代わりに、ユーザーの ObjectId (GUID) が表示されます。 Azure ADテナントの移行がAD Office 365サービスでホストされた後、新しいライセンス認証Microsoft Authenticatorユーザーの UPN が表示されます。 既存のMicrosoft Authenticatorユーザー ObjectId は引き続き表示されますが、モバイル アプリ通知では引き続き機能します。 

- 2019 年 10 月 22 日以降に作成されたテナントの場合、Office 365 サービスに移行するときに、テナントのセキュリティの既定値が自動的に有効になる場合があります。 テナント管理者は、セキュリティの既定値を有効のままにして MFA に登録するか、機能を無効にできます。 詳細については、「セキュリティの既定値 [を無効にする」を参照してください](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。 

  > [!NOTE]
  > 移行中に自動有効化されていない組織は、セキュリティの既定値を有効にする機能が Office 365 サービスに展開される場合があります。 セキュリティの既定値を明示的に無効または有効にした管理者は、[プロパティ] の下の機能を更新Azure Active Directory >**があります**。 管理者が機能を明示的に有効にした後は、自動的に有効になりません。

- テナントの移行が完了すると、Office 365 ドイツ のポータルと Office 365 ポータルの Azure AD Connect のバージョンに関する警告が表示されます。 移行の完了後にバージョンの警告が警告を表示しなくなった場合は、これを無視できます。 移行の前または移行後に、いずれかのポータルで警告が表示される場合は、Azure AD Connect更新する必要があります。 警告メッセージには、「古いディレクトリ同期ツールを使用しているのが検出されました。 Microsoft ダウンロード センターにアクセスして、Azure の最新バージョンを取得することをお勧AD Connect。

## <a name="more-information"></a>詳細情報

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移行プログラム情報](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)
