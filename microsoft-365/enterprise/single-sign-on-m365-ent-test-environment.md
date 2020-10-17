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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオンを構成してテストします。'
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487608"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

Azure AD のシームレスなシングル Sign-On (シームレスな SSO) は、ユーザーが自分の組織のネットワークに接続されている Pc またはデバイスにいるときに、自動的にサインインします。Azure AD のシームレスな SSO を使用すると、ユーザーは追加のオンプレミスコンポーネントを必要とせずに、クラウドベースのアプリケーションに簡単にアクセスできます。

この記事では、Azure AD シームレス SSO 用に Microsoft 365 テスト環境を構成する方法について説明します。

Azure AD のシームレスな SSO を設定するには、次の2つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

「 [Microsoft 365 のパスワードハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。 

結果の構成は次のようになります。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。
- Azure AD Connect は、Outlook で実行され、TESTLAB Active Directory ドメインサービス (AD DS) ドメインと Microsoft 365 サブスクリプションの Azure AD テナントを定期的に同期します。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する

このフェーズでは、Azure AD シームレス SSO 用に Azure AD Connect を構成し、正常に動作することを確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1. [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2. 元のデスクトップで、Azure AD Connect を実行します。

3. [ **ようこそ] ページ**で、[ **構成**] を選択します。

4. [ **追加のタスク** ] ページで、[ユーザーの **サインインを変更**する] を選択し、[ **次へ**] を選択します。

5. [ **AZURE AD に接続** ] ページで、全体管理者アカウントの資格情報を入力し、[ **次へ**] を選択します。

6. [ **ユーザーサインイン** ] ページで、[ **シングルサイン**オンを有効にする] を選択し、[ **次へ**] を選択します。

7. [ **シングルサインオンを有効にする** ] ページで、[ **資格情報の入力**] を選択します。

8. [ **Windows セキュリティ** ] ダイアログボックスで、 **user1** と user1 アカウントのパスワードを入力し、[ **OK**] を選択して、[ **次へ**] を選択します。

9. [ **構成の準備完了** ] ページで、[ **構成**] を選択します。

10. [ **構成の完了** ] ページで、[ **終了**] を選択します。

11. Azure portal の左側のウィンドウで、[azure **Active Directory**  >  **azure AD Connect**] を選択します。 **シームレスなシングルサインオン**機能が**有効**として表示されることを確認します。

次に、user1@testlab を使用してサブスクリプションにサインインできることをテストし <strong>ます。</strong>\<*your public domain*> を使用してサブスクリプションにサインインする機能をテストします。

1. [すべて] の Internet Explorer で、[設定] アイコンを選択し、[ **インターネットオプション**] を選択します。
 
2. [ **インターネットオプション**] で、[ **セキュリティ** ] タブを選択します。

3. [ **ローカルイントラネット**] を選択し、[ **サイト**] を選択します。

4. [ **ローカルイントラネット**] で、[ **詳細設定**] を選択します。

5. [**この web サイトをゾーンに追加する**] で、「 **https:<span>/</span>autologon.microsoftazuread-sso.com**」と入力し、[**追加**] [  >  **Close**  >  **ok**  >  **ok]** を選択します。

6. サインアウトして、再度サインインします。その際に、別のアカウントを指定します。

7. サインインするように求めるメッセージが表示されたら、user1@testlab を指定し <strong>ます。</strong>\<*your public domain*> 名前を入力し、[ **次へ**] を選択します。 パスワードの入力を求められることなく、User1 として正常にサインインできるはずです。 サインインできた場合、Azure AD シームレス SSO が機能していることになります。

User1 には TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可がありますが、Azure AD のグローバル管理者ではないことにご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- DNS ドメインのテストラボでの Microsoft 365 E5 試用版または有料サブスクリプション。\<*your domain name*> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。
- Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。
- Azure AD のシームレスな SSO が有効になっているので、シミュレートされたイントラネット上のコンピューターは、ユーザーアカウントのパスワードを指定せずに Microsoft 365 cloud リソースにサインインできます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
