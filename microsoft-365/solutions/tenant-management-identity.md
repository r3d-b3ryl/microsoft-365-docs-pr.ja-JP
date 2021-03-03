---
title: 手順 3. エンタープライズ テナント用の Microsoft 365 の ID
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントに適切な ID モデルを展開し、強力なユーザー サインインを適用します。
ms.openlocfilehash: ca545e0152b567cd566ce939e369988f864042a9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407172"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>手順 3. エンタープライズ テナント用の Microsoft 365 の ID

Microsoft 365 テナントには、サインインの ID と認証を管理するための Azure Active Directory (Azure AD) テナントが含まれています。組織の Microsoft 365 ユーザー アクセスとアクセス許可を管理するには、ID インフラストラクチャを正しく構成する必要があります。

## <a name="cloud-only-vs-hybrid"></a>クラウド専用とハイブリッド

ID モデルの 2 種類と、最適な適合と利点を次に示します。


| モデル | 説明 | Microsoft 365 がユーザー資格情報を認証する方法 | 最適シナリオ | 最大のメリット |
|:-------|:-----|:-----|:-----|:-----|
| クラウド専用 | ユーザー アカウントは、Microsoft 365 テナントの Azure ADテナントにのみ存在します。 | Microsoft 365 ADの Azure クライアント テナントは、クラウド ID アカウントを使用して認証を実行します。 | DS を使用するオンプレミスの組織または必要AD組織。 | 使いやすい。 追加のディレクトリ ツールやサーバーは必要ありません。 |
| ハイブリッド |  ユーザー アカウントはオンプレミスの Active Directory ドメイン サービス (AD DS) に存在し、コピーは Microsoft 365 テナントの Azure AD テナントにも存在します。 Azure AD接続は、オンプレミス サーバー上で実行され、DS ADを Azure ADテナントに同期します。 Azure ADのユーザー アカウントには、既にハッシュされた DS ユーザー アカウント のパスワードADが含まれる場合があります。 | Microsoft 365 ADの Azure クライアント テナントは、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。 | DS または別AD ID プロバイダーを使用している組織。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||||

クラウド専用 ID の基本的なコンポーネントを次に示します。
 
![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

この図では、オンプレミスユーザーとリモート ユーザーは、Microsoft 365 テナントの Azure ADアカウントでサインインします。

ハイブリッド ID の基本的なコンポーネントを次に示します。

![ハイブリッド ID の基本的なコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

AD この図では、オンプレミスユーザーとリモート ユーザーは、オンプレミスの DS からコピーされた Azure AD テナントのアカウントを使用して Microsoft 365 テナントにサインインします。

## <a name="synchronizing-your-on-premises-ad-ds"></a>オンプレミスの DS のADする

ビジネス ニーズと技術的要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、Microsoft 365 を採用している企業のお客様にとって最も一般的な選択肢です。 ディレクトリ同期を使用すると、AD DS の ID を管理し、ユーザー アカウント、グループ、連絡先に対する更新はすべて、Microsoft 365 テナントの Azure AD テナントに同期されます。

>[!Note]
>DS ADが初めて同期される場合、Microsoft 365 ライセンスが自動的に割り当てられるのではなく、電子メールなどの Microsoft 365 サービスにアクセスできません。 最初に使用場所を割り当てる必要があります。 次に、グループ メンバーシップを使用して、個別または動的にこれらのユーザー アカウントにライセンスを割り当てる。
>

ハイブリッド ID モデルを使用する場合の 2 種類の認証を次に示します。

| 認証の種類 | 説明 |
|:-------|:-----|
| 管理された認証 | Azure ADは、ローカルに保存されたハッシュ バージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスのソフトウェア エージェントに資格情報を送信して、オンプレミスの AD DS によって認証されます。 <br> <br>  管理認証には、パスワード ハッシュ同期 (PHS) とパススルー認証 (PTA) の 2 種類があります。 PHS を使用すると、Azure AD認証自体が実行されます。 PTA を使用すると、Azure AD DS AD認証が実行されます。 |
| フェデレーション認証 | Azure AD認証を要求するクライアント コンピューターを別の ID プロバイダーにリダイレクトします。 |
|  |  |

詳細 [については、「適切な認証方法の選択](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。

## <a name="enforcing-strong-sign-ins"></a>強力なサインインのエンフォース

ユーザー サインインのセキュリティを強化するには、次の表の機能を使用します。

| 機能 | 説明 | 詳細情報 | ライセンスの要件 |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello for Business | Windows デバイスに署名するときに、パスワードを強力な 2 要素認証に置き換える。 この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。 | [Windows Hello for Business の概要](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 または E5 |
| Azure AD パスワード保護 | 既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織に固有の追加の弱い用語をブロックすることもできます。 | [Azure ADパスワード保護を構成する](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 または E5 |
| 多要素認証 (MFA) を使用する | MFA では、ユーザー サインインは、スマートフォン アプリでの検証やスマートフォンに送信されるテキスト メッセージなど、ユーザー アカウントのパスワードを超えた追加の検証の対象となる必要があります。 ユーザー [が MFA を](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 設定する方法については、このビデオを参照してください。 | [エンタープライズ向け Microsoft 365 の MFA](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 または E5 |
| ID とデバイスのアクセス構成 | 推奨される前提条件機能とその設定と条件付きアクセス、Intune、Azure AD Identity Protection ポリシーを組み合わせて構成される設定とポリシー。  | [ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 または E5 |
| Azure AD Identity Protection | 資格情報の侵害から保護します。攻撃者がユーザーのアカウント名とパスワードを決定して、組織のクラウド サービスとデータにアクセスします。 | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 または Microsoft 365 E3 &脅威防止アドオン |
|  |  |  |



## <a name="results-of-step-3"></a>手順 3 の結果

Microsoft 365 テナントの ID については、次の点を決定しました。

- 使用する ID モデル。
- ユーザーとデバイスへの強力なアクセスを強制する方法。

新しいハイブリッド ID 要素が強調表示されたテナントの例を次に示します。

![テナントのハイブリッド ID の例](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

この図では、テナントには次の機能があります。

- DirSync ADおよび Azure AD Connect を使用して Azure ADテナントと同期されている DS フォレストをADします。
- DS フォレストからAD DS ユーザー アカウントおよび他のオブジェクトADコピー。
- ユーザー アカウントに基づいてセキュリティで保護されたユーザー サインインとアクセスを強制するための一連の条件付きアクセス ポリシー。 

## <a name="ongoing-maintenance-for-identity"></a>ID の継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- ユーザー アカウントとグループを追加または変更します。 クラウド専用 ID の場合は、Microsoft 365 管理センターや PowerShell などの Azure AD ツールを使用して、クラウドベースのユーザーとグループを維持します。 ハイブリッド ID の場合は、DS ツールを使用してオンプレミスのユーザーとグループAD維持します。
- サインイン セキュリティ要件を適用するために、ID とデバイス アクセス構成を追加または変更します。

## <a name="next-step"></a>次の手順

[![手順 4.オンプレミスのサーバーとデータOffice移行する](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

移行を [続行して](tenant-management-migration.md) 、オンプレミスのサーバーとそのOffice Microsoft 365 に移行します。
