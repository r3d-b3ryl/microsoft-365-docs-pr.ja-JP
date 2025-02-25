---
title: Microsoft 365 テスト環境のパスワードのリセット
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/13/2019
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
description: '概要: Microsoft 365 テスト環境のパスワードのリセットを構成してテストします。'
ms.openlocfilehash: 4e68372aee44887641d626c3e3667adbdedd5a1e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095622"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードのリセット

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

Azure Active Directory (Azure AD) のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。

この記事では、Microsoft 365テスト環境でパスワード リセットを構成してテストする方法について説明します。

SSPR の設定には、次の 3 つのフェーズがあります。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: パスワード ライトバックの有効化](#phase-2-enable-password-writeback)
- [フェーズ 3: パスワードのリセットを構成してテストする](#phase-3-configure-and-test-password-reset)
    
![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

まず、 [パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)の手順に従います。 

結果の構成は次のようになります。
  
![パスワード ハッシュ同期テスト環境を備えたシミュレートされたエンタープライズ。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織のイントラネット。
- Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。

## <a name="phase-2-enable-password-writeback"></a>フェーズ 2: パスワード ライトバックの有効化

[フェーズ 2 のパスワード ライトバックのテスト ラボ ガイド](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)の手順に従います。

パスワード リセットを使用するには、パスワード ライトバックを有効にしなければなりません。
  
## <a name="phase-3-configure-and-test-password-reset"></a>フェーズ 3: パスワードのリセットを構成してテストする

このフェーズでは、グループ メンバーシップを使用してAzure AD テナントでパスワード リセットを構成し、それが機能することを確認します。

最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。

1. ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。
2. Azure portalで、**Azure Active Directory** >  **GroupsNew グループを** > 選択します。
3. **[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定します。
4. **[メンバー]** を選択し、[**ユーザー 3**] を見つけて選択し、[**選択]** を選択して、[**作成**] を選択します。
5. **[グループ]** ウィンドウを閉じます。
6. Azure Active Directory ウィンドウで、左側のナビゲーションで [**パスワードのリセット**] を選択します。
7. **[パスワードのリセット - プロパティ]** ページの **[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。
8. [ **グループの選択] を** 選択し、 **PWReset** グループを選択して、 **SelectSave を選択** > **します**。
9. プライベート ブラウザー インスタンスを閉じます。

次に、ユーザー 3 アカウントのパスワード リセットをテストします。

1. 新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。
1. User 3 アカウントの資格情報でサインインします。
1. 必要 **な詳細情報** で、[ **次へ**] を選択します。 
1. **[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。
1. 両方が確認されたら、[ **見た目が良い**] を選択し、ブラウザーのプライベート インスタンスを閉じます。
1. 新しいプライベート ブラウザー インスタンスで、 [https://aka.ms/sspr](https://aka.ms/sspr).
1. ユーザー 3 アカウント名を入力し、CAPTCHA の文字を入力して、[ **次へ**] を選択します。
1. **確認手順 1** では、[**別のメールにメールを送信** する] を選択し、[**電子メール**] を選択します。 電子メールが届いたら、確認コードを入力し、[ **次へ**] を選択します。
1. **[アカウントに戻る] で**、ユーザー 3 アカウントの新しいパスワードを入力し、[完了] を選択 **します**。 変更された User 3 アカウントのパスワードをメモし、安全な場所に保管します。
1. 同じブラウザの別のタブで[https://admin.microsoft.com](https://admin.microsoft.com)に移動し、ユーザー 3 アカウント名およびその新しいパスワードでサインインします。 **[Microsoft Office Home]** ページが表示されます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)