---
title: Microsoft 365 テスト環境でのパススルー認証
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: '要約: Microsoft 365 テスト環境でパススルー認証を構成します。'
ms.openlocfilehash: 6919c3f85e076232c864642ada020daaeff8f566
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58357067"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境でのパススルー認証

*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*

Microsoft のクラウド ベースのサービスとアプリケーションへの認証のためにオンプレミスの Active Directory Domain Services (AD DS) インフラストラクチャを直接使用する場合、組織はパススルー認証を使用できます。 この記事では、Microsoft 365 テスト環境でパススルー認証を構成し、以下のような構成を作成する方法を説明します。
  
![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
このテスト環境は、次に示す 2 つのフェーズで設定します。

1.    パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。
2.    APP1 で、パススルー認証用の Azure AD Connect を構成する。
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](../downloads/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

「[Microsoft 365 でのパスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。 
  
- Microsoft 365 E5または有料サブスクリプションを使用します。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに定期的に同期されます。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>フェーズ 2: APP1 で、パススルー認証用の Azure AD Connect を構成します。

このフェーズでは、パススルー認証の使用に向けて Azure AD Connect を APP1 で構成し、正常な動作を確認します。

### <a name="configure-azure-ad-connect-on-app1"></a>APP1 上で Azure AD Connect を構成する

1.    [Azure ポータル](https://portal.azure.com)で、全体管理者アカウントでサインインします。その後、TESTLAB\User1 アカウントで APP1 に接続します。

2.    APP1 のデスクトップで、Azure AD Connect を実行します。

3.    **[ようこそ]** ページで、**[構成]** をクリックします。

4.    [追加のタスク] ページで、[**ユーザー サインインの変更**]、[**次へ**] の順にクリックします。

5.    **[Azure AD に接続]** ページで、全体管理者の資格情報を入力して、**[次へ]** をクリックします。

6.    **[ユーザー サインイン**] ページで、[**パススルー認証**] をクリックした後に [**次へ**] をクリックします。

7.    **[構成の準備完了]** ページで、**[構成]** をクリックします。

8.    **[構成が完了しました]** ページで、**[終了]** をクリックします。

9.    Azure ポータルの左側のウィンドウで、**[Azure Active Directory]、[Azure AD Connect]** の順でクリックします。**パススルー認証** 機能が **有効** と表示されていることを確認します。

10.    [**パススルー認証**] をクリックします。[**パススルー認証**] ウィンドウには、認証エージェントがインストールされているサーバーの一覧が表示されます。一覧の中に APP1 が表示されているはずです。[**パススルー認証**] ウィンドウを閉じます。

次に、サブスクリプションにサインインする機能をテストし <strong>、user1@testlab。</strong>\<your public domain> を使用してサブスクリプションにサインインする機能をテストします。

1. APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。

2. ユーザー名とパスワードの入力を求めるダイアログが表示されたら、<strong>user1@testlab.</strong>\<your public domain> と User1 のパスワードを指定します。 User1 として正常にサインインできるはずです。

User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
この構成は、次の内容で成立します。

- テストMicrosoft 365 E5の試用版または有料サブスクリプションをDNS ドメインします。\<your domain name> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントからのパススルー認証要求を処理します。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)