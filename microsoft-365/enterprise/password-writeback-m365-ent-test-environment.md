---
title: Microsoft 365 テスト環境のパスワードの書き戻し
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
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
ms.openlocfilehash: 7ad01942b0da7858895d58ecd3bf5c83207e88b9
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356218"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードの書き戻し

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

ユーザーはパスワード の書き戻しを使用して、Azure Active Directory (Azure AD) を使用してパスワードを更新し、ローカルの Active Directory ドメイン サービス (AD DS) にレプリケートできます。 パスワードの書き戻しを使用すると、ユーザーは、元のユーザー アカウントが保存されているオンプレミスの DS ADパスワードを更新する必要はありません。 これにより、オンプレミス ネットワークへのリモート アクセス接続を持たなかったローミングユーザーまたはリモート ユーザーが役立ちます。

この記事では、パスワードの書き戻しMicrosoft 365テスト環境を構成する方法について説明します。

パスワード ライトバック用にテスト環境を構成するには、次の 2 つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

最初に、パスワード ハッシュ同期の手順 [に従います](password-hash-sync-m365-ent-test-environment.md)。 結果の構成は次のように表示されます。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。
- Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。

まずはじめに、User 1 をグローバル管理者ロールとして構成します。

1. [Microsoft 365 管理センター](https://portal.microsoft.com)から、全体管理者アカウントでサインインします。

2. [アクティブ **ユーザー] を選択します**。
 
3. [アクティブ な **ユーザー] ページ** で **、user1 アカウントを選択** します。

4. [ユーザー **1] ウィンドウで** 、[役割] の **横にある [編集** ] を **選択します**。

5. user1 の **[ユーザー 役割の編集**] ウィンドウで、[グローバル管理者] を選択し、[保存]**を選択****し**、[閉じる] を **選択します**。

次に、TESTLAB AD DS ドメインで他のユーザーの代理としてパスワードを変更できるように、User 1 アカウント のセキュリティ設定を構成します。

1. [[Azure ポータル](https://portal.azure.com)] からグローバル管理者アカウントでサインインし、TESTLAB\User1 アカウントで APP1 に接続します。

2. APP1 のデスクトップから、[スタート] を選択 **し**、[アクティブ] と **入力** し **、[Active Directory ユーザーとコンピューター] を選択します**。

3. メニュー バーで、[表示] を **選択します**。 高度 **な機能が** 有効になっていない場合は、その機能を選択して有効にします。

4. ツリー ウィンドウで、ドメインを選択して保持 (または右クリック) し、[プロパティ] を選択し、[セキュリティ] タブ **を選択** します。

5. **[詳細設定]** を選択します。

6. [アクセス許可 **] タブで** 、[追加] を **選択します**。

7. [**プリンシパルの選択] を選択し****、「User1」と入力** し **、[OK] を選択します**。

8. [**適用先**] で、[**ユーザーの子孫オブジェクト**] を選択します。

9. [**アクセス許可**] で、次の項目を選択します。

    - **[パスワードの変更]**
    - **パスワードのリセット**

10. [**プロパティ**] で、次の項目を選択します。
    - **LockoutTime の書き込み**
    - **pwdLastSet の書き込み**

11. **[OK] を** 3 回選択して変更を保存します。

12. [**Active Directory ユーザーとコンピューター**] を閉じます。

次に、APP1 で、パスワード書き戻し用の Azure AD Connect を構成します。

1. 必要に応じて、TESTLAB\User1 アカウントを使用して APP1 に接続します。

2. APP1 のデスクトップで、[**Azure AD Connect**] をダブルクリックします。

3. [ようこそ] **ページで、[** 構成] を **選択します**。

4. [追加タスク **] ページで** 、[同期オプションの **カスタマイズ] を選択し**、[次へ] を **選択します**。

5. [Azure **Connect] ページで** AD管理者アカウントの資格情報を入力し、[次へ] を選択 **します**。

6. [ディレクトリ] **Connect[****ドメイン/OU フィルター] ページで、[** 次へ] を **選択します**。

7. [オプション機能 **] ページで** 、[パスワードの書き **戻し] を選択し**、[次へ] を **選択します**。

8. [構成の **準備完了] ページで、[** 構成] **を選択し** 、プロセスが完了するのを待ちます。

9. 構成が完了したら、[終了] を **選択します**。

これで、シミュレートされたイントラネットの仮想ネットワークに接続されていないコンピューター上のユーザーのパスワード ライトバックをテストする準備ができました。

結果の構成は次のように表示されます。

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

この構成は、次の内容で成立します。

- TESTLAB Microsoft 365 E5試用版または有料サブスクリプションをDNS ドメインします。\<*your domain name*> が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。
- Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。
- パスワードの書き戻しが有効になっているため、ユーザーは簡略化されたイントラネットに接続せずに、Azure AD 経由でパスワードを変更できます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)