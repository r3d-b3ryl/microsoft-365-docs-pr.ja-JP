---
title: Microsoft 365 テスト環境でのパススルー認証
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '要約: Microsoft 365 テスト環境でパススルー認証を構成します。'
ms.openlocfilehash: e925f0b48194c94993e7bf3e08f1f18650b19a23
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400111"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境でのパススルー認証

Microsoft のクラウド ベースのサービスとアプリケーションへの認証のためにオンプレミスの Active Directory Domain Services (AD DS) インフラストラクチャを直接使用する場合、組織はパススルー認証を使用できます。 この記事では、Microsoft 365 テスト環境でパススルー認証を構成し、以下のような構成を作成する方法を説明します。
  
![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
このテスト環境は、次に示す 2 つのフェーズで設定します。

1.  パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。
2.  APP1 で、パススルー認証用の Azure AD Connect を構成する。
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。 
  
- Office 365 E5 および EMS E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Office 365 および EMS E5 サブスクリプションの Azure AD テナントに定期的に同期されます。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>フェーズ 2: APP1 で、パススルー認証用の Azure AD Connect を構成します。

このフェーズでは、パススルー認証の使用に向けて Azure AD Connect を APP1 で構成し、正常な動作を確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1.  [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2.  APP1 のデスクトップで、Azure AD Connect を実行します。

3.  **[ようこそ]** ページで、**[構成]** をクリックします。

4.  [追加のタスク] ページで、[**ユーザー サインインの変更**]、[**次へ**] の順にクリックします。

5.  **[Azure AD に接続]** ページで、全体管理者の資格情報を入力して、**[次へ]** をクリックします。

6.  **[ユーザー サインイン**] ページで、[**パススルー認証**] をクリックした後に [**次へ**] をクリックします。

7.  **[構成の準備完了]** ページで、**[構成]** をクリックします。

8.  **[構成が完了しました]** ページで、**[終了]** をクリックします。

9.  Azure ポータルの左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順でクリックします。**パススルー認証**機能が**有効**と表示されていることを確認します。

10. [**パススルー認証**] をクリックします。[**パススルー認証**] ウィンドウには、認証エージェントがインストールされているサーバーの一覧が表示されます。一覧の中に APP1 が表示されているはずです。[**パススルー認証**] ウィンドウを閉じます。

次に、<strong>user1@testlab.</strong>\< お客様のパブリック ドメイン > User1 アカウントのユーザー名で、Office 365 サブスクリプションにサインインできることをテストします。

1. APP1 から、Office 365 のサインアウトを実行します。その後で、別のアカウントを指定して再度サインインします。

2. ユーザー名とパスワードの入力を求めるダイアログが表示されたら、<strong>user1@testlab.</strong>\<お客様のパブリック ドメイン名> と User1 のパスワードを指定します。 User1 として正常にサインインできるはずです。

User1 は、TESTLAB AD DS ドメインに対するドメイン管理者のアクセス許可を持っていますが、Office 365 のグローバル管理者ではありません。 そのため、**[管理者]** アイコンはオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
この構成は、次の内容で成立します。

- DNS ドメイン testlab.\<お客様のドメイン名> が登録されている Office 365 E5 および EMS E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、Office 365 および EMS E5 サブスクリプションの Azure AD テナントからのパススルー認証要求を処理します。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)


