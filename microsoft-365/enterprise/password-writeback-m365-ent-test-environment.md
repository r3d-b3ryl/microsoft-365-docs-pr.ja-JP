---
title: Microsoft 365 テスト環境のパスワードの書き戻し
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用のパスワードの書き戻しを構成する。'
ms.openlocfilehash: 98838bd61fb5664e0b8c8aed4f4b20dee39e0dec
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757684"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードの書き戻し

*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*

ユーザーが Azure Active Directory (Azure AD) からパスワードを更新できるようにします。更新されたパスワードはローカルの Active Directory Domain Services (AD DS) にレプリケートされます。パスワードの書き戻しにより、ユーザーは元のユーザー アカウントが保存されているオンプレミスの AD DS でパスワードを更新する必要がなくなります。オンプレミス ネットワークにリモート アクセス接続できないローミング ユーザーやリモート ユーザーにとって便利な機能です。

この記事では、Microsoft 365 テスト環境でのパスワード書き戻しを構成する方法について説明します。

設定は 2 つのフェーズで行います。

1.  パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。
2.  TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

まず、「[パスワード ハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。 
  
- Microsoft 365 E5 または Office 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 または Office 365 サブスクリプションの Azure AD テナントに同期されます。

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。

まずはじめに、User 1 をグローバル管理者ロールとして構成します。

1. [Microsoft 365 管理センター](https://portal.microsoft.com)から、全体管理者アカウントでサインインします。

2. **[アクティブなユーザー]** をクリックします。
 
3. [**アクティブなユーザー**] ページで、[**user1**] アカウントをクリックします。

4. [**User1**] ウィンドウで、[**役割**] の横にある [**編集**] をクリックします。

5. user1 の [**ユーザー役割の編集**] ウィンドウで、[**グローバル管理者**] をクリックします。[**保存**] をクリックし、[**閉じる**] をクリックします。

次に、TESTLAB AD DS ドメインで他のユーザーの代理としてパスワードを変更できるように、User 1 アカウント のセキュリティ設定を構成します。

1. [[Azure ポータル](https://portal.azure.com)] からグローバル管理者アカウントでサインインし、TESTLAB\User1 アカウントで APP1 に接続します。

2.  APP1 のデスクトップで [**開始**] をクリックして [**active**] と入力し、[**Active Directory ユーザーとコンピューター**] をクリックします。

3. メニュー バーで [**表示**] をクリックします。[**高度な機能**] が有効になっていない場合は、クリックして有効にします。

4. ツリー ウィンドウでドメインを右クリックし、[**プロパティ**] をクリックします。次に、[**セキュリティ**] タブをクリックします。

5. [**詳細設定**] をクリックします。

6. [**アクセス許可**] タブで [**追加**] をクリックします。

7. [**プリンシパルの選択**] をクリックし、 [**User1**] と入力し、[**OK**] をクリックします。

8. [**適用先**] で、[**ユーザーの子孫オブジェクト**] を選択します。

9. [**アクセス許可**] で、次の項目を選択します。

    - パスワードの変更
    - パスワードのリセット

10. [**プロパティ**] で、次の項目を選択します。
    - LockoutTime の書き込み
    - pwdLastSet の書き込み

11. [**OK**] を 3 回クリックして変更を保存します。

12. [**Active Directory ユーザーとコンピューター**] を閉じます。

次に、APP1 で、パスワード書き戻し用の Azure AD Connect を構成します。

1. 必要に応じて、TESTLAB\User1 アカウントを使用して APP1 に接続します。

2. APP1 のデスクトップで、[**Azure AD Connect**] をダブルクリックします。

3. [**ようこそ**] ページで、[**構成**] をクリックします。

4. [**追加のタスク**] ページで [**同期オプションのカスタマイズ**] をクリックし、[**次へ**] をクリックします。

5. **[Azure AD に接続]** ページで、グローバル管理者の資格情報を入力して、**[次へ]** をクリックします。

6. [**ディレクトリの接続**] ページと [**ドメインと OU のフィルタ リング**] ページで、[**次へ**] をクリックします。

7. **[オプション機能]** ページで、**[パスワードの書き戻し]** を選択し、**[次へ]** をクリックします。 

8. [**構成の準備完了**] ページで [**構成**] をクリックし、処理が完了するのを待ちます。

9. 構成の完了が表示されたら、[**終了**] をクリックします。

これで、シミュレートされたイントラネットの仮想ネットワークに接続されていないコンピューター上のユーザーに対してパスワードの書き戻しをテストする準備が整いました。

最終的な構成をここに示します。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、Microsoft 365 または Office 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。 
- パスワードの書き戻しが有効になっているため、ユーザーは簡略化されたイントラネットに接続せずに、Azure AD 経由でパスワードを変更できます。

実稼働環境でのパスワードの書き戻しの構成に関する情報およびリンクについては、ID フェーズの手順、「[パスワードの更新を簡素化する](identity-add-user-accounts.md#identity-pw-writeback)」を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)


