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
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '要約: Microsoft 365 テスト環境でパススルー認証を構成します。'
ms.openlocfilehash: 26222f04617999104a1ad010eb189a0c01370a6d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869193"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境でのパススルー認証

Microsoft のクラウド ベースのサービスとアプリケーションへの認証のためにオンプレミスの Windows Server Active Directory (AD) インフラストラクチャを直接使用する場合は、組織はパススルー認証を使用してそれを行うことができます。この記事では、Microsoft 365 テスト環境でパススルー認証を構成し、以下のような構成を作成する方法を説明します。
  
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
  
この構成は、次の内容で構成されます: 
  
- Office 365 E5 および EMS E5 試用版または永続的なサブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、TESTLAB Windows Server AD ドメインを定期的に Office 365 および EMS E5 サブスクリプションの Azure AD テナントに同期します。

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

次に、User1 アカウントの ユーザー名である user1@testlab./\<お客様のパブリック ドメイン名> で Office 365 サブスクリプションにサインインできることをテストします。

1. APP1 から、Office 365 のサインアウトを実行します。その後で、別のアカウントを指定して再度サインインします。

2. ユーザー名とパスワードの入力を求めるダイアログが表示されたら、user1@testlab.\<お客様のパブリック ドメイン名> と User1 のパスワードを指定します。User1 として正常にサインインできるはずです。

User1 には、TESTLAB Windows Server AD ドメインに対するドメイン管理者アクセス許可がありますが、Office 365 全体管理者ではない点に注意してください。そのため、[**管理者**] アイコンがオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
この構成は、次の内容で成立します。

- DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、Office 365 および EMS E5 サブスクリプションの Azure AD テナントからのパススルー認証要求を処理します。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)


