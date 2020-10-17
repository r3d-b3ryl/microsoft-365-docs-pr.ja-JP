---
title: Microsoft 365 テスト環境のパスワードのリセット
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
description: '概要: Microsoft 365 テスト環境のパスワードのリセットを構成してテストします。'
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487426"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のパスワードのリセット

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

Azure Active Directory (Azure AD) のセルフサービスによるパスワードのリセット (SSPR) によって、ユーザーは自分のパスワードまたはアカウントをリセットまたはロック解除することができます。

この記事では、Microsoft 365 テスト環境でパスワードのリセットを構成およびテストする方法について説明します。

SSPR のセットアップには、3つのフェーズが含まれます。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: パスワード ライトバックの有効化](#phase-2-enable-password-writeback)
- [フェーズ 3: パスワードのリセットを構成してテストする](#phase-3-configure-and-test-password-reset)
    
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

最初に、「 [パスワードハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の指示に従います。 

結果の構成は次のようになります。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。
- Azure AD Connect が APP1 上で実行され、TESTLAB Active Directory Domain Services (AD DS) ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。

## <a name="phase-2-enable-password-writeback"></a>フェーズ 2: パスワード ライトバックの有効化

[フェーズ 2 のパスワード ライトバックのテスト ラボ ガイド](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)の手順に従います。

パスワード リセットを使用するには、パスワード ライトバックを有効にしなければなりません。
  
## <a name="phase-3-configure-and-test-password-reset"></a>フェーズ 3: パスワードのリセットを構成してテストする

このフェーズでは、グループメンバーシップを使用して Azure AD テナントのパスワードのリセットを構成し、正常に動作することを確認します。

最初に、特定の Azure AD グループ内のアカウントのパスワードのリセットを有効にします。

1. ブラウザーのプライベート インスタンスから [https://portal.azure.com](https://portal.azure.com) を開き、全体管理者アカウントの資格情報でサインインします。
2. Azure portal で、[ **azure Active Directory**  >  **グループ**の  >  **新規グループ**] を選択します。
3. **[グループの種類]** を **[セキュリティ]**、**[グループ名]** を **[PWReset]**、**[メンバーシップの種類]** を **[割り当て済み]** に設定します。
4. [ **メンバー**] を選択し、[ **ユーザー 3**] を見つけて選択し、[ **選択**] を選択して、[ **作成**] を選択します。
5. **[グループ]** ウィンドウを閉じます。
6. [Azure Active Directory] ウィンドウで、左側のナビゲーションの [ **パスワードのリセット** ] を選択します。
7. **[パスワードのリセット - プロパティ]** ページの **[セルフサービスによるパスワードのリセットの有効化]** オプションで **[選択済み]** を選択します。
8. [**グループの選択**] を選択し、 **PWReset**グループを選択して、[保存 **]** を選択し  >  **Save**ます。
9. プライベート ブラウザー インスタンスを閉じます。

次に、ユーザー3アカウントのパスワードのリセットをテストします。

1. 新しいプライベート ブラウザー インスタンスを開き、[https://aka.ms/ssprsetup](https://aka.ms/ssprsetup) を参照します。
1. User 3 アカウントの資格情報でサインインします。
1. [ **詳細情報の入力**] で、[ **次へ**] を選択します。 
1. **[アカウントにアクセスできるようにする]** の認証用電話を携帯電話番号に設定し、認証用メールを仕事用や個人用メール アカウントに設定します。
1. 両方が確認されたら、[ **良好**] を選択し、ブラウザーのプライベートインスタンスを閉じます。
1. 新しいプライベートブラウザーインスタンスで、に移動し [https://aka.ms/sspr](https://aka.ms/sspr) ます。
1. User 3 のアカウント名を入力し、CAPTCHA の文字を入力して、[ **次へ**] を選択します。
1. **確認手順 1**の場合は、[連絡用メールを**送信**する] を選択し、[**電子メール**] を選択します。 電子メールを受信したら、確認コードを入力して、[ **次へ**] を選択します。
1. [ **アカウントに戻る**] で、User 3 アカウントの新しいパスワードを入力して、[ **完了**] を選択します。 変更された User 3 アカウントのパスワードをメモし、安全な場所に保管します。
1. 同じブラウザの別のタブで[https://portal.office.com](https://portal.office.com)に移動し、ユーザー 3 アカウント名およびその新しいパスワードでサインインします。 **[Microsoft Office Home]** ページが表示されます。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
