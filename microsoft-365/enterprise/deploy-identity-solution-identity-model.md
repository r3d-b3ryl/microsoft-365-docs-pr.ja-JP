---
title: 手順 1. クラウド ID モデルの決定
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
  - Ent_O365
  - M365-identity-device-management
  - M365-security-compliance
f1.keywords:
  - CSH
ms.custom:
  - Adm_O365
  - seo-marvel-mar2020
search.appverid:
  - MET150
  - MOE150
  - BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 手順 1. Microsoft クラウド ID モデルを決定する
---

# <a name="step-1-determine-your-cloud-identity-model"></a>手順 1. クラウド ID モデルの決定

Microsoft 365は、Azure Active Directory サブスクリプションに含まれるクラウドベースのユーザー ID および認証サービスである Azure Active Directory (Microsoft 365 Azure AD) を使用して、Microsoft 365 の ID と認証を管理します。 ID インフラストラクチャを正しく構成することは、組織のユーザー アクセスMicrosoft 365アクセス許可を管理する上で重要です。

開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

最初の計画の選択は、クラウド ID モデルです。

## <a name="microsoft-cloud-identity-models"></a>Microsoft クラウド ID モデル

ユーザー アカウントを計画するには、まず、ユーザー アカウントの 2 つの ID モデルをMicrosoft 365。 組織の ID はクラウドでのみ維持するか、オンプレミスの Active Directory ドメイン サービス (AD DS) ID を維持し、ユーザーが Microsoft 365 クラウド サービスにアクセスするときに認証に使用できます。

ID の 2 種類と、最適なフィット感と利点を次に示します。

| 属性 | クラウド専用 ID | ハイブリッド ID |
|:-------|:-----|:-----|
| **定義** | ユーザー アカウントは、ユーザー サブスクリプションAzure ADテナントにのみMicrosoft 365されます。 | ユーザー アカウントは DS AD存在し、コピーはサブスクリプションの Azure ADテナントMicrosoft 365です。 ユーザー アカウントには、Azure AD DS ユーザー アカウント のパスワードにハッシュ化されたバージョンAD含まれる場合があります。 |
| **ユーザー Microsoft 365認証方法** | サブスクリプションAzure ADテナントMicrosoft 365、クラウド ID アカウントを使用して認証を実行します。 | サブスクリプションAzure ADテナントMicrosoft 365認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。 |
| **最適シナリオ** | DS を使用するオンプレミスの組織または必要AD組織。 | DS または別AD ID プロバイダーを使用している組織。 |
| **最大のメリット** | 使いやすい。 追加のディレクトリ ツールやサーバーは必要ありません。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||

## <a name="cloud-only-identity"></a>クラウド専用 ID

クラウドのみの ID は、Azure AD にのみ存在するユーザー アカウントを使用します。 クラウド専用 ID は、通常、オンプレミス のサーバーを持たない、またはローカル ID を管理するために AD DS を使用しない小規模な組織で使用されます。

クラウド専用 ID の基本的なコンポーネントを次に示します。

![クラウド専用 ID の基本的なコンポーネント。](../media/about-microsoft-365-identity/cloud-only-identity.png)

オンプレミスとリモート (オンライン) の両方のユーザーは、ユーザー アカウントAzure ADパスワードを使用して、クラウド Microsoft 365アクセスします。 Azure AD は、保存されたユーザー アカウントとパスワードに基づいて、ユーザー資格情報を認証します。

### <a name="administration"></a>管理
ユーザー アカウントはユーザー アカウントにのみ格納Azure AD、クラウド ID を管理するツール (Microsoft 365 管理センター、[Windows PowerShell。](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)[](/admin)

## <a name="hybrid-identity"></a>ハイブリッド ID

ハイブリッド ID は、オンプレミスの DS で発生し、AD サブスクリプションの Azure AD テナントにコピー Microsoft 365します。 ほとんどの変更は、特定のアカウント属性を [除き、](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)1 つの方法でのみフローします。 DS ユーザー アカウントに対して行AD変更は、DS ユーザー アカウントのコピーと同期Azure AD。

Azure AD Connectは、継続的なアカウント同期を提供します。 これは、オンプレミス サーバー上で実行され、DS の変更をADし、それらの変更をサーバーに転送Azure AD。 Azure AD Connectは、同期するアカウントと、ハッシュ化されたバージョンのユーザー パスワード (パスワード ハッシュ同期 (PHS) と呼ばれる) を同期するかどうかをフィルター処理する機能を提供します。

ハイブリッド ID を導入した場合、オンプレミスの AD DS がアカウント情報の信頼できるソースとなります。 つまり、管理タスクは主にオンプレミスで実行され、そのタスクはオンプレミスに同期Azure AD。

ハイブリッド ID のコンポーネントを次に示します。

![ハイブリッド ID のコンポーネント。](../media/about-microsoft-365-identity/hybrid-identity.png)

テナントAzure AD DS アカウントのコピー ADがあります。 この構成では、クラウド サービスにアクセスするオンプレミスユーザーとリモート ユーザーの両方Microsoft 365に対して認証Azure AD。

> [!NOTE]
> ハイブリッド ID のユーザー アカウントを同期Azure AD Connect常にユーザー アカウントを使用する必要があります。 ライセンスの割り当てとグループAzure AD、アクセス許可の構成、およびユーザー アカウントを含むその他の管理タスクを実行するには、同期されたユーザー アカウントが必要です。

### <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>ハイブリッド ID とディレクトリ同期によるMicrosoft 365

ビジネス ニーズと技術的要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、ハイブリッド ID モデルとディレクトリ同期を採用している企業のお客様にとって最も一般的な選択肢Microsoft 365。 ディレクトリ同期を使用すると、Active Directory ドメイン サービス (AD DS) の ID を管理し、ユーザー アカウント、グループ、および連絡先に対する更新はすべて、Microsoft 365 サブスクリプションの Azure Active Directory (Azure AD) テナントに同期されます。

>[!Note]
>DS ADアカウントが初めて同期された場合、ds ユーザー アカウントには Microsoft 365 ライセンスが自動的に割り当てられるのではなく、電子メールなどの Microsoft 365 サービスにアクセスできません。 最初に使用場所を割り当てる必要があります。 次に、グループ メンバーシップを使用して、個別または動的にこれらのユーザー アカウントにライセンスを割り当てる。
>

#### <a name="authentication-for-hybrid-identity"></a>ハイブリッド ID の認証

ハイブリッド ID モデルを使用する場合、認証には次の 2 種類があります。

- 管理された認証

  Azure ADは、ローカルに保存されたハッシュ バージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスのソフトウェア エージェントに資格情報を送信して、オンプレミスの AD DS によって認証されます。

- フェデレーション認証

  Azure AD認証を要求するクライアント コンピューターを別の ID プロバイダーにリダイレクトします。

#### <a name="managed-authentication"></a>管理された認証

管理認証には、次の 2 種類があります。

- パスワード ハッシュ同期 (PHS)

  Azure AD認証自体を実行します。

- パススルー認証 (PTA)

  Azure AD DS がADを実行している場合。


##### <a name="password-hash-synchronization-phs"></a>パスワード ハッシュ同期 (PHS)

PHS を使用すると、DS ユーザー ADと同期し、Microsoft 365をオンプレミスで管理できます。 ユーザー パスワードのハッシュは、AD DS から Azure ADに同期され、ユーザーがオンプレミスとクラウドで同じパスワードを使用します。 これは、ユーザーの DS ID に対する認証を有効AD最も簡単な方法Azure AD。 

![パスワード ハッシュ同期 (PHS)。](../media/plan-for-directory-synchronization/phs-authentication.png)

パスワードをオンプレミスで変更またはリセットすると、新しいパスワード ハッシュが Azure AD に同期され、ユーザーはクラウド リソースとオンプレミス リソースに対して常に同じパスワードを使用できます。 ユーザー のパスワードは、ユーザーに送信Azure AD、クリア テキストAzure ADに保存されません。 Id Protection など、Azure ADの一部のプレミアム機能では、どの認証方法が選択されているに関係なく PHS が必要です。
  
詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。
  
##### <a name="pass-through-authentication-pta"></a>パススルー認証 (PTA)

PTA は、1 つ以上のオンプレミス サーバーで実行されているソフトウェア エージェントを使用して、Azure AD 認証サービスに対する簡単なパスワード検証を提供し、ユーザーを AD DS で直接検証します。 PTA を使用すると、DS ADアカウントとMicrosoft 365を同期し、オンプレミスのユーザーを管理します。 

![パススルー認証 (PTA)。](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA を使用すると、ユーザーはオンプレミスのアカウントとパスワードを使用して、Microsoft 365とアプリケーションの両方にサインインできます。 この構成は、ユーザーのパスワード ハッシュをユーザーに保存せずに、AD DS に対してユーザーのパスワードを直接検証Azure AD。 

PTA は、セキュリティ要件を持つ組織でも、オンプレミスのユーザー アカウントの状態、パスワード ポリシー、ログオン時間を直ちに適用します。 
  
詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。
  
##### <a name="federated-authentication"></a>フェデレーション認証

フェデレーション認証は、主に、より複雑な認証要件を持つ大規模なエンタープライズ組織向けです。 AD DS ID は、Microsoft 365と同期され、ユーザー アカウントはオンプレミスで管理されます。 フェデレーション認証を使用すると、ユーザーはオンプレミスとクラウドで同じパスワードを持ち、ユーザーはパスワードを使用するために再びサインインする必要Microsoft 365。 

フェデレーション認証は、スマートカードベース認証やサードパーティの多要素認証などの追加の認証要件をサポートできます。通常、組織が Azure AD でネイティブにサポートされていない認証要件を持っている場合に必要です。
 
詳細 [については、「適切な認証方法の選択](/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。
  
サード パーティ認証および ID プロバイダーの場合、オンプレミスのディレクトリ オブジェクトは、主にサード パーティ ID プロバイダー (IdP) によって管理される Microsoft 365 およびクラウド リソース アクセスに同期できます。 組織でサード パーティのフェデレーション ソリューションを使用している場合は、サード パーティフェデレーション ソリューションが Azure AD と互換性がある場合は、Microsoft 365 用にそのソリューションを使用してサインオンを構成できます。
  
詳細については[Azure ADフェデレーション互換性リスト](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility)を参照してください。
  
### <a name="administration"></a>管理

元のユーザー アカウントと権限のあるユーザー アカウントはオンプレミスの AD DS に格納されますので、AD DS を管理するのと同じツールを使用して id を管理します。

同期されたユーザー アカウントを管理Microsoft 365 管理センター、Microsoft 365または PowerShell を使用Azure AD。

## <a name="next-step"></a>次のステップ

[![特権アカウントMicrosoft 365保護する](../media/deploy-identity-solution-overview/protect-your-global-administrator-accounts.png)](protect-your-global-administrator-accounts.md)

手順 [2 に進み](protect-your-global-administrator-accounts.md) 、グローバル管理者アカウントをセキュリティで保護します。
