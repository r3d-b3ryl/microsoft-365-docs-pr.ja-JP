---
title: Microsoft 365 Enterprise テスト環境用の多要素認証
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 エンタープライズテスト環境でスマートフォンに送信されるテキストメッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: f209c3cebaefd8b4bddafb68471c35e5c37905be
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071576"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境用の多要素認証

Office 365 へのサインイン、または組織に対して Azure AD テナントを使用するサービスまたはアプリケーションに対して追加のセキュリティレベルを設定するには、Azure 多要素認証を有効にします。これには、ユーザー名とパスワードだけを使用して確認することができます。分割払. 多要素認証では、ユーザーは電話での通話を承認する必要があり、テキストメッセージで送信された検証コードを入力するか、またはパスワードを正しく入力した後にスマートフォンでアプリパスワードを指定する必要があります。 この第 2 の認証要素が満たされた後でのみ、ユーザーはサインインできます。 
  
この記事では、特定のアカウントに対してテキストメッセージベースの認証を有効にし、テストする方法について説明します。
  
Microsoft 365 エンタープライズテスト環境のアカウントに対して多要素認証をセットアップするには、次の2つのフェーズがあります。
  
1. Microsoft 365 Enterprise のテスト環境を作成します。
    
2. User 2 アカウントに対して、多要素認証を有効にしてテストします。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する

最小要件での軽量な方法で多要素認証をテストする場合は、「[ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで多要素認証をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。
  
> [!NOTE]
> 多要素認証をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする

次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。
  
1. ブラウザーのプライベートインスタンスを個別に開き、Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動して、全体管理者アカウントでサインインします。
    
2. 左側のナビゲーションで、 **[ユーザー] > [アクティブなユーザー]** をクリックします。
    
3. [アクティブなユーザー] ウィンドウで、[ **More > 多要素認証のセットアップ**] をクリックします。
    
4. リストで、 **User 2**アカウントを選択します。
    
5. **User 2** セクションで、**[クイック操作]** の **[有効にする]** をクリックします。
    
6. **[多要素認証を有効にする方法の概要]** ダイアログ ボックスで、**[Multi-Factor Auth を有効にする]** をクリックします。
    
7. [**更新が成功しまし**た] ダイアログボックスで、[**閉じる**] をクリックします。
    
8. [ **Microsoft 365 管理センター** ] タブで、右上の [ユーザーアカウント] アイコンをクリックし、[**サインアウト**] をクリックします。
    
9. ブラウザー インスタンスを閉じます。
   
次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。
  
1. ブラウザーの新しいプライベートインスタンスを開きます。
    
2. Office 365 ポータル ([https://portal.office.com](https://portal.office.com)) に移動し、User 2 のアカウント名とパスワードを使用してサインインします。
    
3. サインインした後、詳細についてはアカウントをセットアップするように求めるメッセージが表示されます。 **[次へ]** をクリックします。
    
4. **[追加のセキュリティ確認]** ページで、次の手順を実行します。 
    
   - 国または地域を選択します。
    
   - テキスト メッセージを受信するスマート フォンの電話番号を入力します。
    
   - [**メソッド**] の [**テキストメッセージでコードを送信する**] をクリックします。
    
5. **[次へ]** をクリックします。
    
6. スマート フォンで受信したテキスト メッセージに記載されている確認コードを入力して、**[確認]** をクリックします。
    
7. **[手順 3: 既存のアプリケーションを使用し続ける]** ページで、User 2 アカウント用に表示されているアプリ パスワードを安全な場所に記録してから、**[完了]** をクリックします。
    
8. User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。元のパスワードと、新しいパスワードを 2 回入力して、**[パスワードを更新してサインイン]** をクリックします。新しいパスワードを安全な場所に記録します。
    
    ブラウザーの [ **Microsoft Office Home** ] タブに、ユーザー2の office ポータルが表示されます。


運用環境で多要素認証を展開するための情報とリンクについては、Id フェーズで[多要素認証](identity-secure-user-sign-ins.md#identity-mfa)手順を設定するを参照してください。
    
## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
