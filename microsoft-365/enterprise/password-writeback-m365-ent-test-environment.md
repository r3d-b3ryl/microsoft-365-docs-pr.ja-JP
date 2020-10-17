---
title: Microsoft 365 テスト環境のパスワードの書き戻し
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: '概要: Microsoft 365 テスト環境用のパスワードの書き戻しを構成する。'
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487130"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードの書き戻し

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

ユーザーは、パスワードの書き戻しを使用して、Azure Active Directory (Azure AD) 経由でパスワードを更新できます。これは、ローカルの Active Directory ドメインサービス (AD DS) にレプリケートされます。パスワードの書き戻しを使用すると、ユーザーは、元のユーザーアカウントが保存されているオンプレミスの AD DS を経由してパスワードを更新する必要がありません。これにより、オンプレミスネットワークへのリモートアクセス接続を持たない、ローミングまたはリモートユーザーがサポートされます。

この記事では、Microsoft 365 テスト環境のパスワード書き戻しを構成する方法について説明します。

パスワードの書き戻しのテスト環境を構成するには、次の2つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

最初に、「 [パスワードハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の指示に従います。結果の構成は次のようになります。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。
- Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。

まずはじめに、User 1 をグローバル管理者ロールとして構成します。

1. [Microsoft 365 管理センター](https://portal.microsoft.com)から、全体管理者アカウントでサインインします。

2. [ **アクティブなユーザー**] を選択します。
 
3. [ **アクティブなユーザー** ] ページで、[ **user1** ] アカウントを選択します。

4. [ **User1** ] ウィンドウで、[**役割**] の横にある [**編集**] を選択します。

5. User1 の [ **ユーザーロールの編集** ] ウィンドウで、[ **全体管理者**] を選択し、[ **保存**] を選択して、[ **閉じる**] を選択します。

次に、TESTLAB AD DS ドメインで他のユーザーの代理としてパスワードを変更できるように、User 1 アカウント のセキュリティ設定を構成します。

1. [[Azure ポータル](https://portal.azure.com)] からグローバル管理者アカウントでサインインし、TESTLAB\User1 アカウントで APP1 に接続します。

2. のデスクトップから、[ **スタート**] を選択し、[ **アクティブ**] を選択して、[ **active Directory ユーザーとコンピューター**] を選択します。

3. メニューバーで、[ **表示**] を選択します。 **高度な機能**が有効になっていない場合は、それを選択して有効にします。

4. ツリーウィンドウで、ドメインを選択して保持 (または右クリック) し、[ **プロパティ**] を選択して、[ **セキュリティ** ] タブを選択します。

5. **[詳細設定]** を選択します。

6. [ **アクセス許可** ] タブで、[ **追加**] を選択します。

7. [ **プリンシパルの選択**] を選択し、 **User1**を入力して、[ **OK]** を選択します。

8. [**適用先**] で、[**ユーザーの子孫オブジェクト**] を選択します。

9. [**アクセス許可**] で、次の項目を選択します。

    - **[パスワードの変更]**
    - **パスワードのリセット**

10. [**プロパティ**] で、次の項目を選択します。
    - **LockoutTime の書き込み**
    - **pwdLastSet の書き込み**

11. [ **OK]** を3回選択して、変更を保存します。

12. [**Active Directory ユーザーとコンピューター**] を閉じます。

次に、APP1 で、パスワード書き戻し用の Azure AD Connect を構成します。

1. 必要に応じて、TESTLAB\User1 アカウントを使用して APP1 に接続します。

2. APP1 のデスクトップで、[**Azure AD Connect**] をダブルクリックします。

3. [ **ようこそ] ページ**で、[ **構成**] を選択します。

4. [ **追加のタスク** ] ページで、[ **同期オプションのカスタマイズ**] を選択し、[ **次へ**] を選択します。

5. [ **AZURE AD に接続** ] ページで、全体管理者アカウントの資格情報を入力し、[ **次へ**] を選択します。

6. [ **接続ディレクトリ** と **ドメイン/OU のフィルタリング** ] ページで、[ **次へ**] を選択します。

7. [ **オプション機能** ] ページで、[ **パスワードの書き戻し**] を選択し、[ **次へ**] を選択します。

8. [ **構成の準備完了** ] ページで、[ **構成** ] を選択し、プロセスが完了するまで待ちます。

9. 構成の完了が表示されたら、[ **終了**] を選択します。

これで、シミュレートされたイントラネットの仮想ネットワークに接続していないコンピューター上のユーザーに対してパスワードの書き戻しをテストする準備が整いました。

結果の構成は次のようになります。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- DNS ドメインのテストラボでの Microsoft 365 E5 試用版または有料サブスクリプション。\<*your domain name*> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。
- Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。
- パスワードの書き戻しが有効になっているため、ユーザーは簡略化されたイントラネットに接続せずに、Azure AD 経由でパスワードを変更できます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)


