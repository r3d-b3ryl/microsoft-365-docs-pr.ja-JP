---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期
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
description: '概要: Microsoft 365 テスト環境のパスワード ハッシュ同期とサインインを構成して実例を示します。'
ms.openlocfilehash: 3cee2b69ce34647627cb2b72f9e0f59a6fba17e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869573"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワード ハッシュ同期

多くの組織は、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Windows Server Active Directory (AD) フォレスト内のアカウントのセットを Office 365 と EMS E5 サブスクリプションの Azure AD テナント内のアカウントのセットに同期しています。この記事では、Microsoft 365 テスト環境にパスワード ハッシュ同期を追加する方法について説明します。最終的な構成は、次のとおりになります。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
このテスト環境は、次に示す 2 つのフェーズで設定します。
  
1. Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する。
2. APP1 に Azure AD Connect をインストールして構成する。
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する

「[Microsoft 365 用のシミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)」の手順を実行します。次に、最終的な構成を示します。
  
![シミュレートされたエンタープライズ基本構成](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で構成されます: 
  
- Office 365 E5 および EMS E5 試用版または永続的なサブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワーク内の 3 つの仮想マシン (DC1、APP1、および CLIENT1) で構成されます。DC1 は、testlab.\<パブリック ドメイン名> Windows Server AD のドメイン コントローラーです。

## <a name="phase-2-create-and-register-the-testlab-domain"></a>フェーズ 2: testlab ドメインを作成および登録する

このフェーズでは、パブリック DNS ドメインを追加して、そのドメインをサブスクリプションに追加します。

まず、パブリック DNS 登録プロバイダーと協力して、現在のドメイン名に基づいた新しいパブリック DNS ドメイン名を作成し、Office 365 サブスクリプションに追加します。**testlab.**\<パブリック ドメイン> という名前を使用することをお勧めします。たとえば、パブリック ドメイン名が <span>**contoso</span>.com** である場合は、パブリック ドメイン名 **<span>testlab</span>.contoso.com** を追加します。
  
次に、ドメイン登録プロセスを通じて **testlab.**\<パブリック ドメイン> ドメインを Office 365 の試用版サブスクリプションまたは永続サブスクリプションに追加します。この内容は、**testlab.**\<パブリック ドメイン> ドメインに、さらに DNS レコードを追加することです。詳細については、「[ユーザーとドメインを Office 365 に追加する](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」を参照してください。 

最終的な構成をここに示します。
  
![testlab ドメイン名の登録](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
この構成は、次の内容で構成されます:

- DNS ドメイン testlab.\<パブリック ドメイン名> が登録されている Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。

この時点での testlab.\<パブリック ドメイン名> の状態に注目してください。

- パブリック DNS レコードによるサポート。
- Office 365 および EMS サブスクリプションでの登録。
- シミュレートされたイントラネット上の Windows Server AD ドメイン。
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>フェーズ 3: APP1 に Azure AD Connect をインストールする

このフェーズでは、Azure AD Connect を APP1 にインストールして構成します。その後で、動作を確認します。
  
まず、APP1 上に Azure AD Connect をインストールして構成します。

1. [Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。
    
2. APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行します。
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. タスク バーで **[Internet Explorer]** をクリックし、[https://aka.ms/aadconnect](https://aka.ms/aadconnect)に移動します。
    
4. [Microsoft Azure Active Directory Connect] ページで、**[ダウンロード]** をクリックして、**[実行]** をクリックします。
    
5. **[Azure AD Connect へようこそ]** ページで、**[同意する]** をクリックして、**[続行]** をクリックします。
    
6. **[簡単設定]** ページで、**[簡単設定を使う]** をクリックします。
    
7. **[Azure AD に接続]** ページで、**[ユーザー名]** に Office 365 全体管理者のアカウント名、**[パスワード]** にそのパスワードを入力して、**[次へ]** をクリックします。
    
8. **[AD DS に接続]** ページで、**[ユーザー名]** に「**TESTLAB\\User1**」と入力し、**[パスワード]** にそのパスワードを入力して、**[次へ]** をクリックします。
    
9. **[構成の準備完了]** ページで、**[インストール]** をクリックします。
    
10. **[構成が完了しました]** ページで、**[終了]** をクリックします。
    
11. Internet Explorer で、Office 365 ポータルに移動します ([https://portal.office.com](https://portal.office.com))。
    
12. ポータルのメイン ページで、**[管理]** をクリックします。
    
13. 左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。
    
    **User1** という名前のアカウントを記録します。これは TESTLAB Windows Server AD ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。
    
14. **[User1]** アカウントをクリックします。製品ライセンスの **[編集]** をクリックします。
    
15. **[製品ライセンス]** で、国を選択してから、**[Office 365 Enterprise E5]** の **[オフ]** コントロールをクリックします (**[オン]** に切り替わります)。**[Enterprise Mobility + Security E5]** ライセンスに対しても同じ操作を実行します。 

16. ページの下側にある **[保存]** をクリックしてから **[閉じる]** をクリックします。
    
次に、User1 アカウントのユーザー名である <strong>user1@testlab.</strong>\<お客様のドメイン名> で Office 365 サブスクリプションにサインインできることをテストします。

1. APP1 から、Office 365 のサインアウトを実行します。その後で、別のアカウントを指定して再度サインインします。

2. ユーザー名とパスワードの入力を求めるダイアログが表示されたら、<strong>user1@testlab.</strong>\<お客様のドメイン名> と User1 のパスワードを指定します。User1 として正常にサインインできるはずです。 
 
User1 には、TESTLAB Windows Server AD ドメインに対するドメイン管理者アクセス許可がありますが、Office 365 全体管理者ではない点に注意してください。そのため、[**管理者**] アイコンがオプションとして表示されません。 

最終的な構成をここに示します。

![パスワード ハッシュ同期テスト環境があるシミュレートされたエンタープライズ](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

この構成は、次の内容で成立します。 
  
- DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Office 365 E5 および EMS E5 試用版サブスクリプションまたは永続サブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。Azure AD Connect は APP1 上で実行され、TESTLAB Windows Server AD ドメインを定期的に Office 365 および EMS E5 サブスクリプションの Azure AD テナントに同期します。
- TESTLAB Windows Server AD ドメインの User1 アカウントは、Azure AD テナントと同期されています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)


