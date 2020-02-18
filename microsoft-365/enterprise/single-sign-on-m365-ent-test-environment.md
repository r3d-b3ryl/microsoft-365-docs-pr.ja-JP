---
title: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオンを構成してテストします。'
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083806"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン

*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*

Azure AD のシームレスなシングル サインオンは、ユーザーが組織のネットワークに接続されている PC またはデバイス上に存在するときに、自動的にサインインします。Azure AD シームレス SSO で、ユーザーはクラウド ベースのアプリケーションに簡単にアクセスできるようになります。アクセスする際、オンプレミスの追加コンポーネントは必要ありません。

この記事では、Azure AD シームレス SSO 用の Microsoft 365 テスト環境を構成する方法について説明します。

設定は 2 つのフェーズで行います。

1.  パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。
2.  Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する。
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。 
  
- Microsoft 365 E5 または Office 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 または Office 365 サブスクリプションの Azure AD テナントに定期的に同期されます。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する

このフェーズでは、Azure AD シームレス SSO 用に Azure AD Connect を APP1 で構成し、正常な動作を確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1. [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2. APP1 のデスクトップで、Azure AD Connect を実行します。

3. [**ようこそ**] ページで、[**構成**] をクリックします。

4. **[追加のタスク]** ページで、**[ユーザー サインインの変更]**、**[次へ]** の順にクリックします。

5. **[Azure AD に接続]** ページで、グローバル管理者の資格情報を入力して、**[次へ]** をクリックします。

6. **[ユーザー サインイン]** ページで、**[シングル サインオンを有効にする]** を選び、**[次へ]** をクリックします。

7. **[シングル サインオンを有効にする]** ページで、**[資格情報を入力する]** をクリックします。

8. **[Windows セキュリティ]** ダイアログ ボックスで、**user1** と入力し、user1 アカウントのパスワードも入力します。入力後、**[OK]**、**[次へ]** の順にクリックします。

9. **[構成の準備完了]** ページで、**[構成]** をクリックします。

10. **[構成が完了しました]** ページで、**[終了]** をクリックします。

11. Azure portal の左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順にクリックします。**シームレスなシングル サインオン**機能が**有効**と表示されていることを確認します。

次に、User1 アカウントの<strong>user1@testlab.</strong>\< 自分のパブリック ドメイン > ユーザー名を使用して、サブスクリプションにサインインする機能をテストします。

1. APP1 で Internet Explorer から [設定] アイコンをクリックし、**[インターネット オプション]** をクリックします。
 
2. **[インターネット オプション]** で、**[セキュリティ]** タブをクリックします。

3. **[ローカル イントラネット]** をクリックし、**[サイト]** をクリックします。

4. **[ローカル イントラネット]** で、**[詳細]** をクリックします。

5. **[この Web サイトをゾーンに追加する]** で、**https<span>://</span>autologon.microsoftazuread-sso.com** と入力し、**[追加]、[閉じる]、[OK]、[OK]** の順にクリックします。

6. サインアウトして、再度サインインします。その際に、別のアカウントを指定します。

7. サインインを求められたら、<strong>user1@testlab.</strong>\< お客様のパブリック ドメイン> という名前を指定して、**[次へ]** をクリックします。 パスワードの入力を求められることなく、User1 として正常にサインインできるはずです。 サインインできた場合、Azure AD シームレス SSO が機能していることになります。

User1 には TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可がありますが、Azure AD のグローバル管理者ではないことにご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
この構成は、次の内容で成立します。

- DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、Microsoft 365 または Office 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。 
- Azure AD シームレス SSO が有効になっており、シミュレートされたイントラネット上のコンピューターは、ユーザー アカウントのパスワードを指定せずに Microsoft 365 のクラウド リソースにサインインできます。

実稼働環境での Azure AD シームレス SSO の構成に関する情報およびリンクについては、ID フェーズの手順、「[ユーザー サインインを簡素化する](identity-secure-your-passwords.md#identity-sso)」を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)


