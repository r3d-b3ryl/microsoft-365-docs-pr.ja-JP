---
title: Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
ms.openlocfilehash: 4a420da5251ecef900f2efe9573db1d51a6bd597
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202825"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境用の Azure AD のシームレスなシングル サインオン

*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*

Azure ADシームレス シングル Sign-On (シームレス SSO) は、ユーザーが自分の PC または組織ネットワークに接続されているデバイス上にあるときに自動的にサインインします。 Azure ADシームレス SSO を使用すると、追加のオンプレミス コンポーネントを必要とせずに、クラウドベースのアプリケーションに簡単にアクセスできます。

この記事では、シームレス SSO 用に Azure Microsoft 365テスト環境を構成するAD説明します。

シームレス SSO の Azure ADセットアップには、次の 2 つのフェーズがあります。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

パスワード ハッシュ同期の手順[に従](password-hash-sync-m365-ent-test-environment.md)って、Microsoft 365。 

結果の構成は次のように表示されます。
  
![パスワード ハッシュ同期テスト環境を持つシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。
- Azure AD Connect APP1 で実行され、TESTLAB Active Directory ドメイン サービス (AD DS) ドメインを AD サブスクリプションの Azure AD Microsoft 365 テナントに定期的に同期します。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>フェーズ 2: Azure AD シームレス SSO 用に APP1 上で Azure AD Connect を構成する

このフェーズでは、シームレス SSO AD Connect APP1 で Azure ADを構成し、動作を確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1. [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2. APP1 デスクトップから Azure サーバーを実行AD Connect。

3. [ようこそ] **ページで、[** 構成] を **選択します**。

4. [追加タスク **] ページで** 、[ユーザー サインインの変更] **を** 選択し、[次へ] を **選択します**。

5. [Azure **Connect] ページで** AD管理者アカウントの資格情報を入力し、[次へ] を選択 **します**。

6. [ユーザー サインイン **] ページで、[** シングル サインオンを有効にする] **を** 選択し、[次へ] を **選択します**。

7. [シングル **サインオンを有効にする] ページで** 、[資格情報の **入力] を選択します**。

8. [ユーザーの **Windows セキュリティ]** ダイアログ ボックスで **、user1** と user1 アカウントのパスワードを入力し **、[OK]** を選択し、[次へ] を選択 **します**。

9. [構成の **準備完了] ページで、[** 構成] を **選択します**。

10. [構成の **完了] ページで** 、[終了] を **選択します**。

11. Azure portal の左側のウィンドウで、[Azureポータル] をAzure Active Directory  >  **選択AD Connect。** シームレス シングル **サインオン機能が** [有効] と表示されるのを **確認します**。

次に、サブスクリプションにサインインする機能をテストし <strong>、user1@testlab。</strong>\<*your public domain*> を使用してサブスクリプションにサインインする機能をテストします。

1. APP1 Internet Explorerから設定アイコンを選択し、[インターネット オプション] **を選択します**。
 
2. [ **インターネット オプション] で**、[セキュリティ] **タブを選択** します。

3. [ローカル **イントラネット] を** 選択し、[サイト] を **選択します**。

4. [ **ローカル イントラネット] で**、[詳細設定] **を選択します**。

5. [**この Web サイトをゾーンに追加する**] で **、「https <span>://」</span>** と入力し autologon.microsoftazuread-sso.com [OK を閉じる **]**  >    >  **を**  >  **選択します**。

6. サインアウトして、再度サインインします。その際に、別のアカウントを指定します。

7. サインインを求めるメッセージが表示されたら、次の <strong>user1@testlab。</strong>\<*your public domain*> をクリックし、[次へ] を **選択します**。 パスワードの入力を求められることなく、User1 として正常にサインインできるはずです。 サインインできた場合、Azure AD シームレス SSO が機能していることになります。

User1 には TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可がありますが、Azure AD のグローバル管理者ではないことにご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証テスト環境を持つシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- テストMicrosoft 365 E5の試用版または有料サブスクリプションをDNS ドメインします。\<*your domain name*> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。
- Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。
- Azure ADシームレス SSO が有効になっているので、シミュレートされたイントラネット上のコンピューターは、ユーザー アカウントのパスワードを指定せずに、Microsoft 365クラウド リソースにサインインできます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)