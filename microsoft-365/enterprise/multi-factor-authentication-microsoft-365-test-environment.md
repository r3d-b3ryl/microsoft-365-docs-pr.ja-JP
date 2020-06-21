---
title: Microsoft 365 エンタープライズテスト環境多要素認証
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Microsoft 365 エンタープライズテスト環境でスマートフォンに送信されるテキストメッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: e26fb7470e01397266f5f424ee45941a79a2940c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819378"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境用の多要素認証

*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*

サブスクリプションに対して Azure AD テナントを使用する Microsoft 365 または任意のサービスまたはアプリケーションにサインインするための追加のセキュリティレベルについては、Azure 多要素認証を有効にすることができます。これには、アカウントを確認するために、ユーザー名とパスワードだけを必要とします。 

多要素認証を使用する場合、ユーザーは電話での通話を承認する必要があり、テキストメッセージで送信された検証コードを入力するか、またはパスワードを正しく入力した後にスマートフォンでアプリによる認証を確認する必要があります。 この第 2 の認証要素が満たされた後でのみ、ユーザーはサインインできます。 
  
この記事では、特定のユーザーアカウントに対してテキストメッセージベースの認証を有効にし、テストする方法について説明します。
  
Microsoft 365 エンタープライズテスト環境のアカウントに対して多要素認証をセットアップするには、次の2つのフェーズがあります。
  
1. Microsoft 365 Enterprise のテスト環境を作成します。
    
2. User 2 アカウントに対して、多要素認証を有効にしてテストします。

3. 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストします (オプション)。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 Enterprise のテストラボガイドスタックにあるすべての記事へのビジュアルマップの[テストラボガイドスタック](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)に移動します。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小要件での軽量な方法で多要素認証をテストする場合は、「[ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで多要素認証をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。
  
> [!NOTE]
> 多要素認証をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする

次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。
  
1. ブラウザーのプライベートインスタンスを個別に開き、Microsoft 365 管理センター () に移動して、 [https://portal.microsoft.com](https://portal.microsoft.com) 全体管理者アカウントでサインインします。
    
2. 左側のナビゲーションで、**[ユーザー] > [アクティブなユーザー]** をクリックします。
    
3. [アクティブなユーザー] ウィンドウで、[**多要素認証**] をクリックします。
    
4. リストで、 **User 2**アカウントを選択します。
    
5. **User 2** セクションで、**[クイック操作]** の **[有効にする]** をクリックします。
    
6. **[多要素認証を有効にする方法の概要]** ダイアログ ボックスで、**[Multi-Factor Auth を有効にする]** をクリックします。
    
7. [**更新が成功しまし**た] ダイアログボックスで、[**閉じる**] をクリックします。
    
8. [ **Microsoft 365 管理センター** ] タブで、右上の [ユーザーアカウント] アイコンをクリックし、[**サインアウト**] をクリックします。
    
9. ブラウザー インスタンスを閉じます。
   
次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。
  
1. ブラウザーの新しいプライベートインスタンスを開きます。
    
2. Office 365 ポータル () に移動 [https://portal.office.com](https://portal.office.com) し、User 2 のアカウント名とパスワードを使用してサインインします。
    
3. サインインした後、詳細についてはアカウントをセットアップするように求めるメッセージが表示されます。 **[次へ]** をクリックします。
    
4. **[追加のセキュリティ確認]** ページで、次の手順を実行します。 
    
   - 国または地域を選択します。
    
   - テキスト メッセージを受信するスマート フォンの電話番号を入力します。
    
   - [**メソッド**] の [**テキストメッセージでコードを送信する**] をクリックします。
    
5. **[次へ]** をクリックします。
    
6. スマート フォンで受信したテキスト メッセージに記載されている確認コードを入力して、**[確認]** をクリックします。
    
7. [**手順 3: 既存のアプリケーションを使用**したままにする] ページで、[**完了**] をクリックします。
    
8. If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.
    
    ブラウザーの [ **Microsoft Office Home** ] タブに、ユーザー2の office ポータルが表示されます。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>フェーズ 3: 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストする

*このフェーズは、Microsoft 365 エンタープライズテスト環境に対してのみ使用できます。*

このフェーズでは、グループと条件付きアクセスポリシーを使用して、User 3 アカウントに対して多要素認証を有効にします。

次に、MFAUsers という名前の新しいグループを作成し、そのグループに User 3 アカウントを追加します。

1. [ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションの [**グループ**] をクリックし、[**グループ**] をクリックします。
2. [**グループの追加] を**クリックします。
3. [**グループの種類を選択**してください] ウィンドウで、[**セキュリティ**] を選択し、[**次へ**] をクリックします。
4. [**基本の設定**] ウィンドウで、[**グループの作成**] をクリックし、[**閉じる**] をクリックします。
5. [**グループの追加の確認と完了**] ウィンドウで、「 **mfausers**」と入力し、[**次へ**] をクリックします。
6. グループの一覧で、[ **Mfausers** ] グループをクリックします。
7. [ **Mfausers** ] ウィンドウで、[**メンバー**] をクリックし、[**すべて表示**] をクリックして、[メンバーの管理] をクリックします。
8. [ **Mfausers** ] ウィンドウで、[**メンバーの追加**] をクリックし、 **User 3**のアカウントを選択してから、[保存] をクリック **> 閉じる > close**] をクリックします。

次に、MFAUsers グループのメンバーに対して多要素認証を必要とする条件付きアクセスポリシーを作成します。

1. ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。
2. [ **Azure Active Directory > セキュリティ > 条件付きアクセス**] をクリックします。
3. [**条件付きアクセス–ポリシー** ] ウィンドウで、[**新しいポリシー**] をクリックします。
4. **新しい**ウィンドウで、[**名前**] に**ユーザーアカウントの MFA**を入力します。
5. [**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。
6. [**ユーザーとグループ**] ウィンドウの [**含める**] タブで、[ユーザーとグループの > 選択] をクリックし **> 選択**] をクリックします。
7. [**選択**] ウィンドウで、[ **mfausers** ] グループをクリックし、[ **> の完了] を**クリックします。
8. **新しい**ウィンドウの [**アクセス制御**] セクションで、[**付与**] をクリックします。
9. [**付与**] ウィンドウで、[**多要素認証を必要とする**] をクリックし、[**選択**] をクリックします。
10. **新しい**ウィンドウで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。
11. **Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。

このポリシーをテストするには、サインアウトして、User 3 アカウントでサインインします。 MFA の構成を求めるメッセージが表示されます。 これは、MFAUsers ポリシーが適用されていることを示しています。

運用環境で多要素認証を展開するための情報とリンクについては、Id フェーズで[多要素認証](identity-secure-user-sign-ins.md#identity-mfa)手順を設定するを参照してください。
    
## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
