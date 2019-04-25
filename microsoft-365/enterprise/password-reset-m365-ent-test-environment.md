---
title: Microsoft 365 テスト環境のパスワードのリセット
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
description: '概要: Microsoft 365 テスト環境のパスワードのリセットを構成してテストします。'
ms.openlocfilehash: f5fc8d68493464d6b4a6ffdcda64ed9a0d8c7cdd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289466"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードのリセット

Azure AD のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。 

この記事では、Microsoft 365 テスト環境でパスワードの構成およびリセットを行う方法を、次の 2 つのフェーズに分けて説明します。

1.  Microsoft 365 Enterprise のテスト環境を作成します。
2.  User 2 アカウントのパスワードのリセットを構成してテストする。
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-configure-password-hash-synchronization-and-password-writebback-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 のテスト環境の、パスワード ハッシュ同期とパスワード ライトバックを設定します

まず、「[パスワード ハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。 
  
- Office 365 E5 および EMS E5 の試用版サブスクリプションまたは有料サブスクリプション。
- インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。 
- Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Office 365 および EMS E5 サブスクリプションの Azure AD テナントに同期されます。

次に、テスト ラボ ガイドの「[パスワード ライトバックのフェーズ 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)」の手順に従います。

パスワード リセットを使用するには、パスワード ライトバックを有効にしなければなりません。
  
## <a name="phase-2-configure-and-test-password-reset"></a>フェーズ 2: パスワードのリセットを構成してテストする

このフェーズでは、グループ メンバーシップとして、Azure AD テナントでパスワードのリセットを構成し、それが機能することを確認します。

最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。

1. ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。
2. Azure portal で **[Azure Active Directory] > [グループ] > [新しいグループ]** の順にクリックします。
3. **[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定し、**[作成]** をクリックします。
5. リストの中から **[PWReset]** グループをクリックし、**[メンバー]** をクリックします。
6. **[メンバーの追加]** > **[User 2]** > **[選択** の順にクリックします。その後、**[PWReset]** ページおよび **[グループ]** ページを閉じます。
7. Azure Active Directory のページで、**[パスワードのリセット]** をクリックします。
8. **[プロパティ]** ページの、**[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。
9. **[グループの選択]** から **[PWReset]** をクリックし、**[保存]** をクリックします。
10. プライベート ブラウザー インスタンスを閉じます。

次に、User 2 アカウントのパスワードのリセットをテストします。

1. 新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。
2. User 2 アカウントの資格情報でサインインします。
3. **[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。
4. 認証用の電話とメールに問題がなければ、**[問題ありません]** をクリックして、ブラウザーのプライベート インスタンスを閉じます。
5. 新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/sspr](https://aka.ms/sspr) に移動します。
6. User 2 アカウントの資格情報でサインインして、CAPTCHA で示された文字を入力し、**[次へ]** をクリックします。
8. **[認証手順 1]** で、**[連絡用メール アドレスにメールする]** をクリックし、**[メール]** をクリックします。メールを受信したら、認証コードを入力し、**[次へ]** をクリックします。
9. **[アカウントに戻る]** で、User 2 アカウントの新しいパスワードを入力し、**[終了]** をクリックします。User 2 アカウントの変更したパスワードのメモを取り、安全な場所に保存します。
10. 同じブラウザーの別のタブで [https://office.com](https://office.com) に移動し、User 2 アカウント名と新しいパスワードでサインインすると、**Office Home** のページが表示されます。

実稼働環境でのパスワードのリセットの構成に関する情報およびリンクについては、ID フェーズの手順、「[パスワードのリセットを簡素化する](identity-password-reset.md#identity-pw-reset)」を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
