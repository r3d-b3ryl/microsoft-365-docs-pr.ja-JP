---
title: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオンを構成してテストします。'
ms.openlocfilehash: 2d6af0600044dea59cbcdd9ee51f76c061e3dcd7
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093330"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン

*このテスト ラボ ガイドは、エンタープライズ環境とOffice 365 Enterpriseテスト環境の両方のMicrosoft 365に使用できます。*

シームレス シングル Sign-On (シームレス SSO) をAzure AD、PC または組織のネットワークに接続されているデバイスにいるユーザーは自動的にサインインします。 シームレス SSO Azure AD、追加のオンプレミス コンポーネントを必要とせずに、クラウドベースのアプリケーションに簡単にアクセスできます。

この記事では、シームレス SSO をAzure ADするためにMicrosoft 365テスト環境を構成する方法について説明します。

シームレス SSO Azure ADセットアップには、次の 2 つのフェーズがあります。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

[Microsoft 365のパスワード ハッシュ同期の手順に](password-hash-sync-m365-ent-test-environment.md)従います。 

結果の構成は次のようになります。
  
![パスワード ハッシュ同期テスト環境を備えたシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。
- Azure AD Connectは APP1 で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインをMicrosoft 365 サブスクリプションのAzure AD テナントに定期的に同期します。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する

このフェーズでは、APP1 でシームレス SSO をAzure ADするためのAzure AD Connectを構成し、動作することを確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1. [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2. APP1 デスクトップから、Azure AD Connectを実行します。

3. [ **ようこそ] ページで**、[ **構成**] を選択します。

4. [ **その他のタスク** ] ページ **で、[ユーザー サインインの変更**] を選択し、[ **次へ**] を選択します。

5. **[Azure ADするConnect**] ページで、グローバル管理者アカウントの資格情報を入力し、[**次へ**] を選択します。

6. **[ユーザー サインイン**] ページで、[**シングル サインオンを有効にする**] を選択し、[**次へ**] を選択します。

7. [ **シングル サインオンを有効にする] ページで** 、[ **資格情報の入力**] を選択します。

8. **[Windows セキュリティ**] ダイアログ ボックスで、**user1 と user1** アカウントのパスワードを入力し、[**OK] を** 選択して、[**次へ**] を選択します。

9. [ **構成の準備完了]** ページで、[構成] を選択 **します**。

10. [ **構成の完了]** ページで、[終了] を選択 **します**。

11. Azure portalの左側のウィンドウで、**Azure Active Directory** >  **Azure AD Connect** を選択します。 **シームレス シングル サインオン** 機能が **[有効]** として表示されることを確認します。

次に、user1@testlabを使用してサブスクリプションにサインインする機能をテストします <strong>。</strong>\<*your public domain*> を使用してサブスクリプションにサインインする機能をテストします。

1. APP1 の Internet Explorer で設定アイコンを選択し、 **インターネット オプション** を選択します。
 
2. **[インターネット オプション]** で、[**セキュリティ**] タブを選択します。

3. [ **ローカル イントラネット**] を選択し、[サイト] を選択 **します**。

4. **ローカル イントラネット** で、[詳細設定] を選択 **します**。

5. **[この Web サイトをゾーンに追加する**] に **「https <span>://</span>autologon.microsoftazuread-sso.com**」と入力し、**AddCloseOKOK** >  >  >  を選択します。

6. サインアウトして、再度サインインします。その際に、別のアカウントを指定します。

7. サインインを求められたら、user1@testlab指定します <strong>。</strong>\<*your public domain*> 名前を指定し、[ **次へ**] を選択します。 パスワードの入力を求められることなく、User1 として正常にサインインできるはずです。 サインインできた場合、Azure AD シームレス SSO が機能していることになります。

User1 には TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可がありますが、Azure AD のグローバル管理者ではないことにご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証テスト環境を備えたシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- DNS ドメイン testlab を使用したMicrosoft 365 E5試用版または有料サブスクリプション。\<*your domain name*> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。
- Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。
- Azure ADシームレス SSO が有効になっているため、シミュレートされたイントラネット上のコンピューターは、ユーザー アカウントのパスワードを指定せずにクラウド リソースMicrosoft 365にサインインできます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)