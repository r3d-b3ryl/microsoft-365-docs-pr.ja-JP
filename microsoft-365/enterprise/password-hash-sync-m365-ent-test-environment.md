---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワード ハッシュ同期とサインインを構成して実例を示します。'
ms.openlocfilehash: 91d4de08382149b5089f0c06295e77965ea022cf
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093813"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワード ハッシュ同期

*このテスト ラボ ガイドは、エンタープライズ環境とOffice 365 Enterpriseテスト環境の両方のMicrosoft 365に使用できます。*

多くの組織では、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Active Directory Domain Services (AD DS) フォレスト内のアカウント セットを、Microsoft 365 サブスクリプションの Azure AD テナント内のアカウント セットに同期します。 

この記事では、Microsoft 365テスト環境にパスワード ハッシュ同期を追加する方法について説明します。これにより、次の構成が行われます。
  
![パスワード ハッシュ同期テスト環境を備えたシミュレートされたエンタープライズ。](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
このテスト環境の設定には、次の 3 つのフェーズがあります。
- [フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [フェーズ 2: testlab ドメインを作成および登録する](#phase-2-create-and-register-the-testlab-domain)
- [フェーズ 3: APP1 に Azure AD Connect をインストールする](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する

[Microsoft 365のシミュレートされたエンタープライズ ベース構成の手順に](simulated-ent-base-configuration-microsoft-365-enterprise.md)従います。 結果の構成は次のようになります。
  
![シミュレートされたエンタープライズ ベースの構成。](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- Azure 仮想ネットワーク内の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。 DC1 は、 *パブリック ドメイン名*> AD DS ドメイン<testlab.<用のドメイン コントローラーです。

## <a name="phase-2-create-and-register-the-testlab-domain"></a>フェーズ 2: testlab ドメインを作成および登録する

このフェーズでは、パブリック DNS ドメインを追加し、サブスクリプションに追加します。

まず、パブリック DNS 登録プロバイダーと連携して、現在のドメイン名に基づく新しいパブリック DNS ドメイン名を作成し、それをサブスクリプションに追加します。 ***パブリック ドメイン*><testlab.<** という名前を使用することをお勧めします。 たとえば、パブリック ドメイン名が **<span>contoso.com</span>** の場合は、パブリック ドメイン名 **<span>testlab.contoso.com</span>** を追加します。
  
次に、ドメイン登録プロセスを実行して、***パブリック ドメイン*> ドメイン<testlab.Microsoft 365** 試用版または有料サブスクリプションに追加します。 これは、***パブリック ドメイン*> ドメイン<testlab.<** に DNS レコードを追加することで構成されます。 詳細については、「[Microsoft 365にドメインを追加する」を](../admin/setup/add-domain.md)参照してください。

結果の構成は次のようになります。
  
![testlab ドメイン名の登録。](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
この構成は、次の内容で成立します。

- dns ドメイン testlab.<*パブリック ドメイン名* が登録されているMicrosoft 365 E5試用版または有料サブスクリプション>。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。

*パブリック ドメイン名*><testlab.<が次のようになっていることに注目してください。

- パブリック DNS レコードによるサポート。
- Microsoft 365 サブスクリプションに登録済み。
- シミュレートされたイントラネット上の AD DS ドメイン。
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>フェーズ 3: APP1 に Azure AD Connect をインストールする

このフェーズでは、APP1 にAzure AD Connect ツールをインストールして構成し、動作することを確認します。
  
まず、APP1 にAzure AD Connectをインストールして構成します。

1. [Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。
    
2. APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行して Internet Explorer セキュリティ強化を無効にします。
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. タスク バーで Internet **Explorer** を選択し [https://aka.ms/aadconnect](https://aka.ms/aadconnect)、 .
    
4. Microsoft Azure Active Directory Connect ページで[**ダウンロード**]、[**実行**] の順に選択します。
    
5. [**Azure AD Connectへようこそ**] ページで、[**同意** する] を選択し、[**続行**] を選択します。
    
6. [**Express 設定**] ページで、[**高速設定の使用**] を選択します。
    
7. **[Azure AD Connect**] ページで、[**ユーザー名**] にグローバル管理者アカウント名を入力し、[**パスワード**] にパスワードを入力して、[**次へ**] を選択します。
    
8. [**AD DS へのConnect**] ページで、[**ユーザー名****] に「TESTLABUser1\\」** と入力し、[**パスワード**] にパスワードを入力して、[**次へ**] を選択します。
    
9. [ **構成の準備完了]** ページで、[インストール] を選択 **します**。
    
10. [ **構成の完了]** ページで、[終了] を選択 **します**。
    
11. Internet Explorer で Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動します。
    
12. 左側のナビゲーション ウィンドウで、[ **ユーザー] > [アクティブなユーザー**] を選択します。
    
    **User1** という名前のアカウントを記録します。 これは TESTLAB AD DS ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。
    
13. **User1** アカウントを選択し、**ライセンスとアプリ** を選択します。
    
14. **製品ライセンス** で、場所 (必要に応じて) を選択し、**Office 365 E5** ライセンスを無効にしてから **、Microsoft 365 E5** ライセンスを有効にします。 

15. ページの下部にある **[保存] を** 選択し、[ **閉じる**] を選択します。
    
次に、ユーザー 1 アカウントの ***ドメイン名*>ユーザー名をuser1@testlab.<して** サブスクリプションにサインインする機能をテストします。

1. APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。

2. ユーザー名とパスワードの入力を求められたら、 **user1@testlab.<*ドメイン名*>** と User1 パスワードを指定します。 User1 として正常にサインインできるはずです。
 
User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。 

結果の構成は次のようになります。

![パスワード ハッシュ同期テスト環境を備えたシミュレートされたエンタープライズ。](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

この構成は、次の内容で成立します。 
  
- ドメイン名が登録されている DNS ドメイン TESTLAB.<を使用して試用版または有料サブスクリプション *を* Microsoft 365 E5またはOffice 365 E5>。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。 AZURE AD CONNECTは APP1 で実行され、TESTLAB AD DS ドメインをMicrosoft 365 サブスクリプションのAzure AD テナントに定期的に同期します。
- TESTLAB AD DS ドメインの User1 アカウントは、Azure AD テナントと同期されています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)