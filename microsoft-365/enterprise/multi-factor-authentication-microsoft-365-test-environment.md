---
title: Microsoft 365 エンタープライズの複数要素の認証はテスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 エンタープライズ テスト環境でスマート フォンに送信されるテキスト メッセージを使用して複数要素の認証を構成します。
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869001"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 エンタープライズの複数要素の認証はテスト環境

Office 365 または組織の Azure AD テナントを使用するアプリケーションやサービスへのサインインのセキュリティのレベル、だけで複数のユーザー名とパスワードを確認する必要がありますが、Azure の多要素認証を有効にできます、アカウントです。多要素認証は、ユーザーは、確認の電話、テキスト メッセージで送信された確認コードを入力、または自分のパスワードを正しく入力した後、スマート フォンのアプリのパスワードを指定する必要があります。この 2 番目の認証要素が満たされた後にのみ、サインインできます。 
  
この資料では、有効にして、特定のアカウントのテキスト メッセージ ベースの認証をテストする方法について説明します。
  
Microsoft 365 エンタープライズ テスト環境でアカウントを複数要素の認証を設定するのには 2 つのフェーズがあります。
  
1. Microsoft 365 エンタープライズ テスト環境を作成します。
    
2. User 2 アカウントに対して、多要素認証を有効にしてテストします。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で複数要素の認証をテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業内の複数要素の認証をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> 多要素認証のテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。提供されてここでは、オプション多要素認証をテストし、一般的な組織を表す環境で試すことができるようにします。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする

次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。
  
1. ブラウザーのインスタンスを個別に秘密を開き、Office のポータルに移動 ([https://office.com](https://office.com))、し、グローバル管理者アカウントでサインインします。
    
2. ポータルのメイン ページで、**[管理]** をクリックします。
    
3. 左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。
    
4. ユーザーのアクティブなウィンドウをクリックして**より > 多要素認証の設定**。
    
5. の一覧では、 **2 のユーザー**アカウントを選択します。
    
6. **User 2** セクションで、**[クイック操作]** の **[有効にする]** をクリックします。
    
7. **[多要素認証を有効にする方法の概要]** ダイアログ ボックスで、**[Multi-Factor Auth を有効にする]** をクリックします。
    
8. **正常な更新**] ダイアログ ボックスで [**閉じる**] をクリックします。
    
9. **[Microsoft Office Home]** タブで、右上部分にあるユーザー アカウントのアイコンをクリックし、**[サインアウト]** をクリックします。
    
10. ブラウザー インスタンスを閉じます。
   
次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。
  
1. お使いのブラウザーの新しい、プライベート インスタンスを開きます。
    
2. Office のポータルに移動 ([https://office.com](https://office.com)) と 2 のユーザー アカウントでサインイン (user2 @\<組織名 >. onmicrosoft.com) とパスワードです。
    
3. サインイン後、詳細については、アカウントを設定するように求められます。[**次へ**] をクリックします。
    
4. **[追加のセキュリティ確認]** ページで、次の手順を実行します。 
    
   - 国または地域を選択します。
    
   - テキスト メッセージを受信するスマート フォンの電話番号を入力します。
    
   - **メソッド**では、**コード、テキスト メッセージを送信してもらう**をクリックします。
    
5. [ **次へ**] をクリックします。
    
6. スマート フォンで受信したテキスト メッセージに記載されている確認コードを入力して、**[確認]** をクリックします。
    
7. **[手順 3: 既存のアプリケーションを使用し続ける]** ページで、User 2 アカウント用に表示されているアプリ パスワードを安全な場所に記録してから、**[完了]** をクリックします。
    
8. User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。元のパスワードと、新しいパスワードを 2 回入力して、**[パスワードを更新してサインイン]** をクリックします。新しいパスワードを安全な場所に記録します。
    
    お使いのブラウザーの [ **Microsoft Office のホーム**] タブで、Office のポータルのユーザー 2 のはずです。


情報と実稼働環境での複数要素の認証を展開するリンクの識別段階では、[多要素認証のセットアップ](identity-multi-factor-authentication.md)手順を参照してください。
    
## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 エンタープライズ展開](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
