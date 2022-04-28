---
title: Microsoft 365 テスト環境のパスワードの書き戻し
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/22/2019
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
description: '概要: Microsoft 365 テスト環境用のパスワードの書き戻しを構成する。'
ms.openlocfilehash: 0477e2200db7252dcce4351b2f96298e075f3b29
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091107"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードの書き戻し

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

ユーザーはパスワード ライトバックを使用して、Azure Active Directory (Azure AD) を使用してパスワードを更新し、ローカル Active Directory Domain Services (AD DS) にレプリケートできます。 パスワード ライトバックを使用すると、ユーザーは元のユーザー アカウントが格納されているオンプレミスの AD DS を使用してパスワードを更新する必要はありません。 これにより、オンプレミス ネットワークへのリモート アクセス接続を持たないローミングユーザーまたはリモート ユーザーに役立ちます。

この記事では、パスワード ライトバック用にMicrosoft 365テスト環境を構成する方法について説明します。

パスワード ライトバック用のテスト環境の構成には、次の 2 つのフェーズがあります。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

まず、 [パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)の手順に従います。 結果の構成は次のようになります。
  
![パスワード ハッシュ同期テスト環境を備えたシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。
- Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。

まずはじめに、User 1 をグローバル管理者ロールとして構成します。

1. [Microsoft 365 管理センター](https://portal.microsoft.com)から、全体管理者アカウントでサインインします。

2. **[アクティブなユーザー] を選択します**。
 
3. [ **アクティブなユーザー** ] ページで、 **user1** アカウントを選択します。

4. **ユーザー 1** ウィンドウで、[**ロール**] の横にある **[編集]** を選択します。

5. user1 の [**ユーザー ロールの編集]** ウィンドウで、**グローバル管理者** を選択し、[**保存]** を選択して、[**閉じる**] を選択します。

次に、TESTLAB AD DS ドメインで他のユーザーの代理としてパスワードを変更できるように、User 1 アカウント のセキュリティ設定を構成します。

1. [[Azure ポータル](https://portal.azure.com)] からグローバル管理者アカウントでサインインし、TESTLAB\User1 アカウントで APP1 に接続します。

2. APP1 のデスクトップから **[スタート]** を選択し、「**アクティブ」** と入力して **、Active Directory ユーザーとコンピューター** を選択します。

3. メニュー バーの [表示] を選択 **します**。 **高度な機能** が有効になっていない場合は、それを選択して有効にします。

4. ツリー ウィンドウで、ドメインを選択して保持 (または右クリック) し、[ **プロパティ**] を選択して、[ **セキュリティ** ] タブを選択します。

5. **[詳細設定]** を選択します。

6. [ **アクセス許可** ] タブで、[ **追加**] を選択します。

7. [ **プリンシパルの選択] を選択** し、「 **User1」** と入力して、[OK] を選択 **します**。

8. [**適用先**] で、[**ユーザーの子孫オブジェクト**] を選択します。

9. [**アクセス許可**] で、次の項目を選択します。

    - **[パスワードの変更]**
    - **パスワードのリセット**

10. [**プロパティ**] で、次の項目を選択します。
    - **LockoutTime の書き込み**
    - **pwdLastSet の書き込み**

11. [ **OK] を** 3 回選択して変更を保存します。

12. [**Active Directory ユーザーとコンピューター**] を閉じます。

次に、APP1 で、パスワード書き戻し用の Azure AD Connect を構成します。

1. 必要に応じて、TESTLAB\User1 アカウントを使用して APP1 に接続します。

2. APP1 のデスクトップで、[**Azure AD Connect**] をダブルクリックします。

3. [ **ようこそ] ページで**、[ **構成**] を選択します。

4. [ **その他のタスク** ] ページで、[ **同期オプションのカスタマイズ**] を選択し、[ **次へ**] を選択します。

5. **[Azure ADするConnect**] ページで、グローバル管理者アカウントの資格情報を入力し、[**次へ**] を選択します。

6. **Connect ディレクトリ** と **Domain/OU フィルター 処理** ページで、[**次へ**] を選択します。

7. **[オプション機能**] ページで、[**パスワード ライトバック**] を選択し、[**次へ**] を選択します。

8. [ **構成の準備完了]** ページで、[ **構成** ] を選択し、プロセスが完了するまで待ちます。

9. 構成の完了が表示されたら、[終了] を選択 **します**。

これで、シミュレートされたイントラネットの仮想ネットワークに接続されていないコンピューター上のユーザーのパスワード ライトバックをテストする準備ができました。

結果の構成は次のようになります。

![パススルー認証テスト環境を備えたシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- DNS ドメイン TESTLAB を使用したMicrosoft 365 E5試用版または有料サブスクリプション。\<*your domain name*> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。
- Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。
- パスワードの書き戻しが有効になっているため、ユーザーは簡略化されたイントラネットに接続せずに、Azure AD 経由でパスワードを変更できます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)