---
title: '手順 5: ユーザーのアクセスを簡素化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD のセルフサービスによるパスワードのリセット (SSPR) について理解し、構成します。
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287066"
---
# <a name="step-5-simplify-access-for-users"></a>手順 5: ユーザーのアクセスを簡素化する

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>パスワードの更新を簡素化する

*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

このセクションでは、ユーザーに Azure Active directory (Azure AD) を通じてパスワードを再設定することを許可します。この再設定はローカル Active Directory Domain Services (AD DS) に複製されます。 このプロセスは、パスワードの書き戻しと呼びます。 ユーザーはパスワードの書き戻しを使用すれば、ユーザー アカウントとその属性が保存されているオンプレミス Active Directory Domain Services (AD DS) を通じてパスワードの更新を行う必要がありません。 これは、オンプレミスのネットワークへのリモート アクセス接続を持たないローミング ユーザーやリモート ユーザーにとって価値があります。

パスワードの書き戻しは、Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。

その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。

>[!Note]
>最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。
>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: パスワードの書き戻し](password-writeback-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-writeback)を確認できます。

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>パスワード再設定を簡素化する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、セルフサービスによるパスワードのリセット (SSPR) を有効にして、ユーザーが自分のパスワードやアカウントの再設定やロック解除を行えるようにします。 誤用または悪用について警告するため、通知と共に、ユーザーがいつシステムにアクセスしたかを追跡する詳細なレポート作成機能を使用できます。 パスワード再設定をデプロイする前にパスワードの書き戻しを有効にする必要があります。

「[セルフサービスによるパスワードのリセットを適切にロールアウトする方法](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: パスワードのリセット](password-reset-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pw-reset)を確認できます。


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>ユーザー サインインを簡素化する

*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

このセクションでは、Azure Active Directory シームレス シングル サインオンをセットアップして、ユーザーがパスワードを (さらに、多くの場合ユーザー名も) 入力せずに Azure AD ユーザー アカウントを使用するサービスにサインインできるようにします。 これにより、ユーザーは Office 365 などのクラウド ベースのアプリケーションに簡単にアクセスできるようになります。ID フェデレーション サーバーのような追加のオンプレミス コンポーネントは不要です。

Azure AD Connect ツールを使用して Azure AD シームレス SSO を構成します。

「[Azure Active Directory シームレス シングル サインオン: クイック スタート](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)」を参照してください。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: Azure AD シームレス シングル サインオン](single-sign-on-m365-ent-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-sso)を確認できます。


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Office 365 サインイン ページをカスタマイズする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

このセクションでは、ユーザーが組織のサインイン ページを認識できるように、企業名やロゴなどの認識できる要素を追加します。 

Microsoft 365 Enterprise では、サイン ページと [アクセス パネル] ページの外観をカスタマイズして、企業ロゴ、配色、カスタム ユーザー情報を組み込むことができます。 

*カスタマイズ前*は、ユーザーがデバイスからサインインしようとすると、次の例に示すような Office 365 サインイン ページが表示されます。

![カスタマイズ前の Office 365 サインイン ページの例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

次に、Contoso Corporation の同じユーザーに対して*カスタマイズ後*に表示されるページを示します。

![カスタマイズ後の Office 365 サインイン ページの例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

詳細については、「[会社のブランドを Office 365 サインイン ページに追加する](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)」を参照してください。

構成手順については、「[サインイン ページと [アクセス パネル ページ] に会社のブランドを追加する](http://aka.ms/aadpaddbranding)」を参照してください。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-custom-sign-in)を確認できます。


## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [管理を容易にするためのグループの使用](identity-self-service-group-management.md) |


