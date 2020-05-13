---
title: '手順 2: パスワードをセキュリティで保護する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体でパスワードを強力かつ管理しやすいものにする必要があります。
ms.openlocfilehash: 6e5c2567ee2027be2a84121fdad10ba873ec1c43
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214652"
---
# <a name="step-2-secure-your-passwords"></a>手順 2: パスワードをセキュリティで保護する

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>脆弱なパスワードを防止する

*この手順はオプションであり、Microsoft 365 のバージョン E3 および E5 の両方に適用されます。*

すべてのユーザーが [Microsoft のパスワードのガイダンス](https://www.microsoft.com/research/publication/password-guidance)を使用してユーザー アカウントのパスワードを作成する必要があります。

ユーザーがパスワードを容易に作成するのを防ぐため、Azure AD のパスワード保護を使用します。この機能では、グローバル禁止パスワード リストと指定したカスタムの禁止パスワード リスト (省略可能) の両方を使用します。 たとえば、次のような組織固有の用語を指定できます。

- ブランド名
- 製品名
- 場所 (たとえば、会社の本部など)
- 会社固有の内部用語
- 会社固有の意味を持つ略語

[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)および[オンプレミスの Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) に対する脆弱なパスワードを禁止できます。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-password-prot)を確認できます。

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>パスワード再設定を簡素化する

*この手順はオプションであり、Microsoft 365 のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、セルフサービスによるパスワードのリセット (SSPR) を有効にして、ユーザーが自分のパスワードやアカウントの再設定やロック解除を行えるようにします。 誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。 パスワード再設定をデプロイする前にパスワードの書き戻しを有効にする必要があります。

「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: パスワードのリセット](password-reset-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-reset)を確認できます。


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>ユーザー サインインを簡素化する

*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

このセクションでは、Azure Active Directory シームレス シングル サインオン (Azure AD シームレス SSO) をセットアップして、パスワード ハッシュ同期 (PHS) とパススルー認証 (PTA) と連携することにより、ユーザーがパスワードを (さらに、多くの場合ユーザー名も) 入力せずに Azure AD ユーザー アカウントを使用するサービスにサインインできるようにします。 これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。

Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。

「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Azure AD シームレス シングル サインオン](single-sign-on-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-sso)を確認できます。


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a>サインイン ページをカスタマイズする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

このセクションでは、ユーザーが組織のサインイン ページを認識できるように、企業名やロゴなどの認識できる要素を追加します。 

Microsoft 365 Enterprise では、サイン ページと [アクセス パネル] ページの外観をカスタマイズして、企業ロゴ、配色、カスタム ユーザー情報を組み込むことができます。 

詳細については、「[会社のブランドを Microsoft 365 サインイン ページに追加する](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)」を参照してください。

構成手順については、「[サインイン ページと [アクセス パネル ページ] に会社のブランドを追加する](https://aka.ms/aadpaddbranding)」を参照してください。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-custom-sign-in)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 3](../media/stepnumbers/Step3.png)| [ユーザーのサインインをセキュリティで保護して管理する](identity-secure-user-sign-ins.md) |
