---
title: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオンを構成してテストします。'
ms.openlocfilehash: 10444b094e09705e93cb32c10cd0d41c19913985
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869550"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン

Azure AD のシームレスなシングル サインオンは、ユーザーが組織のネットワークに接続されている PC またはデバイス上に存在するときに、自動的にサインインします。Azure AD シームレス SSO で、ユーザーはクラウド ベースのアプリケーションに簡単にアクセスできるようになります。アクセスする際、オンプレミスの追加コンポーネントは必要ありません。

この記事では、Azure AD シームレス SSO 用の Microsoft 365 テスト環境を構成する方法について説明します。

このテスト環境は、次に示す 2 つのフェーズで設定します。

1.  パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。
2.  Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する。
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-create-the-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を作成する

「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。以下が、作成された構成です。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で構成されます: 
  
- Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、TESTLAB Windows Server AD ドメインが、Office 365 および EMS E5 サブスクリプションの Azure AD テナントに定期的に同期されます。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する

このフェーズでは、Azure AD シームレス SSO 用に Azure AD Connect を APP1 で構成し、正常な動作を確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1. [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2. APP1 のデスクトップで、Azure AD Connect を実行します。

3. **[ようこそ]** ページで、**[構成]** をクリックします。

4. [追加のタスク] ページで、[**ユーザー サインインの変更**]、[**次へ**] の順にクリックします。

5. **[Azure AD に接続]** ページで、全体管理者の資格情報を入力して、**[次へ]** をクリックします。

6. **[ユーザー サインイン]** ページで、**[シングル サインオンを有効にする]** を選び、**[次へ]** をクリックします。

7. **[シングル サインオンを有効にする]** ページで、**[資格情報を入力する]** をクリックします。

8. **[Windows セキュリティ]** ダイアログ ボックスで、**user1** と入力し、user1 アカウントのパスワードも入力します。入力後、**[OK]**、**[次へ]** の順にクリックします。

9. **[構成の準備完了]** ページで、**[構成]** をクリックします。

10. **[構成が完了しました]** ページで、**[終了]** をクリックします。

11. Azure portal の左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順にクリックします。**シームレスなシングル サインオン**機能が**有効**と表示されていることを確認します。

次に、<strong>user1@testlab.</strong>\< お客様のパブリック ドメイン > User1 アカウントのユーザー名で、Office 365 サブスクリプションにサインインできることをテストします。

1. APP1 で Internet Explorer から [設定] アイコンをクリックし、**[インターネット オプション]** をクリックします。
 
2. **[インターネット オプション]** で、**[セキュリティ]** タブをクリックします。

3. **[ローカル イントラネット]** をクリックし、**[サイト]** をクリックします。

4. **[ローカル イントラネット]** で、**[詳細]** をクリックします。

5. **[この Web サイトをゾーンに追加する]** で、**https<span>://</span>autologon.microsoftazuread-sso.com** と入力し、**[追加]、[閉じる]、[OK]、[OK]** の順にクリックします。

6. Office 365 からサインアウトし、再度サインインします。その際に、別のアカウントを指定します。

7. サインインを求められたら、<strong>user1@testlab.</strong>\<お客様のパブリック ドメイン > 名前を指定して、**[次へ]** をクリックします。パスワードの入力を求められることなく User1 としてサインインできるはずです。サインインできれば、シームレス SSO が正常に動作していることになります。

User1 には、TESTLAB Windows Server AD ドメインに対するドメイン管理者アクセス許可がありますが、Office 365 全体管理者ではない点に注意してください。そのため、[**管理者**] アイコンがオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
この構成は、次の内容で成立します。

- DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、Office 365 および EMS E5 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB Windows Server AD ドメインに同期されます。 
- Azure AD シームレス SSO が有効になっており、シミュレートされたイントラネット上のコンピューターは、ユーザー アカウントのパスワードを指定せずに Microsoft 365 のクラウド リソースにサインオンできます。

実稼働環境での Azure AD シームレス SSO の構成に関する情報およびリンクについては、ID フェーズの手順、「[ユーザー サインインを簡素化する](identity-single-sign-on.md)」を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)


