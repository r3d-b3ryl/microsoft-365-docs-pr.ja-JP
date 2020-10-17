---
title: Microsoft 365 テスト環境のパスワード ハッシュ同期
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
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
- seo-marvel-apr2020
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境のパスワード ハッシュ同期とサインインを構成して実例を示します。'
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487460"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワード ハッシュ同期

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

多くの組織では、Azure AD Connect とパスワード ハッシュ同期を使用して、オンプレミスの Active Directory Domain Services (AD DS) フォレスト内のアカウント セットを、Microsoft 365 サブスクリプションの Azure AD テナント内のアカウント セットに同期します。 

この記事では、パスワードハッシュの同期を Microsoft 365 テスト環境に追加する方法について説明します。この構成は次のようになります。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
このテスト環境のセットアップには、3つのフェーズが含まれます。
- [フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [フェーズ 2: testlab ドメインを作成および登録する](#phase-2-create-and-register-the-testlab-domain)
- [フェーズ 3: APP1 に Azure AD Connect をインストールする](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 のシミュレートされたエンタープライズ テスト環境を作成する

「 [Microsoft 365 のシミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)」の手順に従います。 結果の構成は次のようになります。
  
![シミュレートされたエンタープライズ基本構成](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワーク内の DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。 DC1 は、testlab のドメインコントローラー <ます。 *パブリックドメイン名*> AD DS ドメインを指定します。

## <a name="phase-2-create-and-register-the-testlab-domain"></a>フェーズ 2: testlab ドメインを作成および登録する

このフェーズでは、パブリック DNS ドメインを追加し、サブスクリプションに追加します。

最初に、パブリック DNS 登録プロバイダと連携して、現在のドメイン名に基づいた新しいパブリック DNS ドメイン名を作成し、サブスクリプションに追加します。 「Testlab」という名前を使用することをお勧め**します。*パブリックドメイン* > <**。 たとえば、パブリックドメイン名が** <span>contoso</span>.com**の場合は、パブリックドメイン名** <span>testlab</span>contoso.com**を追加します。
  
次に、ドメイン登録プロセスを実行して、Microsoft 365 試用版または有料版サブスクリプションに、 ***パブリックドメイン* > ドメイン <** を追加します。 これは、他の DNS レコードを testlab に追加することで構成され**ます。*パブリックドメイン* > ドメイン <** します。 詳細については、「 [Microsoft 365 にドメインを追加する](../admin/setup/add-domain.md)」を参照してください。

結果の構成は次のようになります。
  
![testlab ドメイン名の登録](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
この構成は、次の内容で成立します。

- DNS domain testlab を使用した Microsoft 365 E5 試用版または有償版サブスクリプション <> 登録済みの *パブリックドメイン名* を指定します。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。

ここで、testlab <> の *パブリックドメイン名* が次のようになっていることに注目してください。

- パブリック DNS レコードによるサポート。
- Microsoft 365 サブスクリプションに登録済み。
- シミュレートされたイントラネット上の AD DS ドメイン。
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>フェーズ 3: APP1 に Azure AD Connect をインストールする

このフェーズでは、の Azure AD Connect ツールをインストールして構成し、正常に動作することを確認します。
  
最初に、Azure AD Connect をインストールして、[インストール] に構成します。

1. [Azure portal](https://portal.azure.com) から、全体管理者アカウントでサインインします。その後、TESTLAB\\User1 アカウントで APP1 に接続します。
    
2. APP1 のデスクトップから、管理者レベルの Windows PowerShell コマンド プロンプトを起動して、次に示すコマンドを実行して Internet Explorer セキュリティ強化を無効にします。
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. タスクバーから [ **Internet Explorer** ] を選択し、に移動し [https://aka.ms/aadconnect](https://aka.ms/aadconnect) ます。
    
4. [Microsoft Azure Active Directory Connect] ページで、[ **ダウンロード**] を選択し、[ **実行**] を選択します。
    
5. [ **AZURE AD Connect へようこそ** ] ページで、[ **同意**します] を選択し、[ **続行**] を選択します。
    
6. [ **簡易設定** ] ページで、[ **エクスプレス設定を使用する**] を選択します。
    
7. [ **AZURE AD に接続** ] ページで、[ **ユーザー名]** に全体管理者のアカウント名を入力し、[ **パスワード**] にパスワードを入力して、[ **次へ**] を選択します。
    
8. [ **AD DS に接続**] ページで、[**ユーザー名]** に「 **testlab \\ User1** 」と入力し、[パスワード **] にパスワードを入力**して、[**次へ**] を選択します。
    
9. [ **構成の準備完了** ] ページで、[ **インストール**] を選択します。
    
10. [ **構成の完了** ] ページで、[ **終了**] を選択します。
    
11. Internet Explorer で Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動します。
    
12. 左側のナビゲーションウィンドウで、[ **ユーザー > アクティブユーザー**] を選択します。
    
    **User1** という名前のアカウントを記録します。 これは TESTLAB AD DS ドメインからのアカウントであり、ディレクトリ同期が機能していることを証明します。
    
13. **User1**アカウントを選択し、[**ライセンスとアプリ**] を選択します。
    
14. [ **製品ライセンス**] で、場所 (必要な場合) を選択し、 **Office 365 e5** ライセンスを無効にしてから、 **Microsoft 365 E5** ライセンスを有効にします。 

15. ページの下部にある [ **保存** ] を選択し、[ **閉じる**] を選択します。
    
次に、user1@testlab を使用してサブスクリプションにサインインできることをテスト**します。*ドメイン名* > ** user1 アカウントのユーザー名を <します。

1. APP1 からサインアウトし、その後サインインし直しますが、そのときに別のアカウントを指定します。

2. ユーザー名とパスワードの入力を求められたら user1@testlab を指定し**ます。*ドメイン名* > **と user1 のパスワードを <します。 User1 として正常にサインインできるはずです。
 
User1 は、TESTLAB AD DS ドメインのドメイン管理者のアクセス許可を持っていますが、グローバル管理者ではないことをご注意ください。 そのため、**[管理者]** アイコンはオプションとして表示されません。 

結果の構成は次のようになります。

![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

この構成は、次の内容で成立します。 
  
- DNS domain TESTLAB を使用した Microsoft 365 E5 または Office 365 E5 試用版または有料サブスクリプション。 <*ドメイン名*> 登録されています。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。 Azure AD Connect は、Outlook で実行され、TESTLAB AD DS ドメインと Microsoft 365 サブスクリプションの Azure AD テナントを定期的に同期します。
- TESTLAB AD DS ドメインの User1 アカウントは、Azure AD テナントと同期されています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
