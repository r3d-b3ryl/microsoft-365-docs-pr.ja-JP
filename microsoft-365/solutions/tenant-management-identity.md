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
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントに適切な ID モデルを展開し、強力なユーザー サインインを適用します。
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908561"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>手順 3. エンタープライズ テナント用の Microsoft 365 の ID

Microsoft 365 テナントには、サインインの ID と認証を管理するための Azure Active Directory (Azure AD) テナントが含まれています。組織の Microsoft 365 ユーザー アクセスとアクセス許可を管理するには、ID インフラストラクチャを正しく構成する必要があります。

## <a name="cloud-only-vs-hybrid"></a>クラウド専用とハイブリッド

2 種類の ID モデルと、その最適な適合と利点を次に示します。


| モデル | 説明 | Microsoft 365 がユーザー資格情報を認証する方法 | 最適シナリオ | 最大のメリット |
|:-------|:-----|:-----|:-----|:-----|
| クラウド専用 | ユーザー アカウントは、Microsoft 365 テナントの Azure AD テナントにのみ存在します。 | Microsoft 365 AD Azure テナントテナントは、クラウド ID アカウントを使用して認証を実行します。 | DS を使用しているオンプレミスの組織または必要AD組織。 | 簡単に使用できます。 追加のディレクトリ ツールやサーバーは必要ありません。 |
| ハイブリッド |  ユーザー アカウントはオンプレミスの Active Directory ドメイン サービス (AD DS) に存在し、コピーは Microsoft 365 テナントの Azure AD テナントにも存在します。 Azure ADオンプレミス サーバー上で Azure AD Ds の変更を Azure ADします。 Azure ADのユーザー アカウントには、既にハッシュ化された DS ユーザー アカウント パスワードのハッシュAD含まれる場合があります。 | Microsoft 365 AD Azure テナントは、認証プロセスを処理するか、ユーザーを別の ID プロバイダーにリダイレクトします。 | AD DS または別の ID プロバイダーを使用している組織。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||||

クラウド専用 ID の基本的なコンポーネントを次に示します。
 
![クラウド専用 ID の基本コンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

この図では、オンプレミスユーザーとリモート ユーザーは、Microsoft 365 テナントの Azure ADアカウントでサインインします。

ハイブリッド ID の基本的なコンポーネントを次に示します。

![ハイブリッド ID の基本コンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

この図では、オンプレミスユーザーとリモート ユーザーは、オンプレミスの AD DS からコピーされた Azure AD テナントのアカウントを使用して Microsoft 365 テナントにサインインします。

## <a name="synchronizing-your-on-premises-ad-ds"></a>オンプレミスの AD DS の同期

ビジネス ニーズと技術要件に応じて、ハイブリッド ID モデルとディレクトリ同期は、Microsoft 365 を採用している企業のお客様にとって最も一般的な選択肢です。 ディレクトリ同期を使用すると、AD DS の ID を管理し、ユーザー アカウント、グループ、および連絡先に対する更新はすべて、Microsoft 365 テナントの Azure AD テナントに同期されます。

>[!Note]
>DS AD初めて同期する場合、DS ユーザー アカウントには自動的に Microsoft 365 ライセンスが割り当てられるのではなく、メールなどの Microsoft 365 サービスにアクセスできません。 最初に、使用場所を割り当てる必要があります。 次に、グループ メンバーシップを使用して、個別に、または動的に、これらのユーザー アカウントにライセンスを割り当てる必要があります。
>

ハイブリッド ID モデルを使用する場合の 2 種類の認証を次に示します。

| 認証の種類 | 説明 |
|:-------|:-----|
| 管理された認証 | Azure AD は、ローカルに保存されたハッシュ バージョンのパスワードを使用して認証プロセスを処理するか、オンプレミスの AD DS によって認証される資格情報をオンプレミスのソフトウェア エージェントに送信します。 <br> <br>  管理認証には、パスワード ハッシュ同期 (PHS) とパススルー認証 (PTA) の 2 種類があります。 PHS では、Azure AD認証自体を実行します。 PTA を使用すると、Azure AD DS AD認証を実行する必要があります。 |
| フェデレーション認証 | Azure AD、認証を要求しているクライアント コンピューターを別の ID プロバイダーにリダイレクトします。 |
|  |  |

詳細 [については、「適切な認証方法の選択](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 」を参照してください。

## <a name="enforcing-strong-sign-ins"></a>強力なサインインを行う

ユーザー サインインのセキュリティを強化するには、次の表の機能を使用します。

| 機能 | 説明 | 詳細情報 | ライセンスの要件 |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello for Business | Windows デバイスにサインインするときに、パスワードを強力な 2 要素認証に置き換える。 この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。 | [Windows Hello for Business の概要](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 または E5 |
| Azure AD パスワード保護 | 既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織に固有の追加の脆弱な用語をブロックすることもできます。 | [Azure ADパスワード保護を構成する](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 または E5 |
| 多要素認証 (MFA) を使用する | MFA では、ユーザー のサインインに、スマートフォン アプリによる検証やスマートフォンに送信されるテキスト メッセージなど、ユーザー アカウントパスワードを超える追加の検証を行う必要があります。 ユーザー [が](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) MFA を設定する方法については、このビデオをご覧ください。 | [Microsoft 365 enterprise の MFA](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 または E5 |
| ID とデバイスのアクセス構成 | 推奨される前提条件の機能とその設定と条件付きアクセス、Intune、Azure AD Identity Protection ポリシーを組み合わせて構成される設定とポリシー。このポリシーは、特定のアクセス要求を付与する必要があるかどうかを決定し、どのような条件で許可するか決定します。  | [ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 または E5 |
| Azure AD Identity Protection | 資格情報の侵害から保護します。攻撃者は、組織のクラウド サービスとデータにアクセスするためにユーザーのアカウント名とパスワードを決定します。 | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | 脅威保護アドオンの ID を持つ Microsoft 365 E5 & Microsoft 365 E3 |
|  |  |  |



## <a name="results-of-step-3"></a>手順 3 の結果

Microsoft 365 テナントの ID については、次の点を決定しました。

- 使用する ID モデル。
- 強力なユーザー アクセスとデバイス アクセスを適用する方法。

新しいハイブリッド ID 要素が強調表示されているテナントの例を次に示します。

![テナントのハイブリッド ID の例](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

この図では、テナントには次の機能があります。

- DirSync AD Azure AD Connect を使用して Azure AD テナントと同期されている DS フォレストAD。
- DS フォレストAD DS ユーザー アカウントおよび他のオブジェクトADコピー。
- ユーザー アカウントに基づいてセキュリティで保護されたユーザー サインインとアクセスを適用するための条件付きアクセス ポリシーのセット。 

## <a name="ongoing-maintenance-for-identity"></a>ID の継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- ユーザー アカウントとグループを追加または変更します。 クラウド専用 ID の場合は、Microsoft 365 管理センターや PowerShell などの Azure AD ツールを使用してクラウドベースのユーザーとグループを維持します。 ハイブリッド ID の場合は、DS ツールを使用してオンプレミスのユーザーとAD維持します。
- サインイン のセキュリティ要件を適用するために、ID とデバイスのアクセス構成を追加または変更します。

## <a name="next-step"></a>次の手順

[![手順 4.オンプレミスのサーバーとデータOffice移行する](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

移行を [続行](tenant-management-migration.md) して、オンプレミスの Officeサーバーとそのデータを Microsoft 365 に移行します。
