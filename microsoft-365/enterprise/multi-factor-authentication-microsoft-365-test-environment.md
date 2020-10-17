---
title: エンタープライズテスト環境の多要素認証のための Microsoft 365
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
description: エンタープライズテスト環境の Microsoft 365 で、スマートフォンに送信されるテキストメッセージを使用して、多要素認証を構成します。
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487142"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境での多要素認証

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

サブスクリプションに対して Azure AD テナントを使用する Microsoft 365 または任意のサービスまたはアプリケーションにサインインするための追加のセキュリティレベルについては、Azure 多要素認証を有効にすることができます。これには、アカウントを確認するために、ユーザー名とパスワードだけを必要とします。

多要素認証を使用する場合、ユーザーは電話での通話を承認する必要があり、テキストメッセージで送信された検証コードを入力するか、またはパスワードを正しく入力した後にスマートフォンでアプリによる認証を確認する必要があります。 この2番目の認証要因が満たされた後にのみ、サインインすることができます。
  
この記事では、特定のユーザーアカウントに対してテキストメッセージベースの認証を有効にし、テストする方法について説明します。
  
Microsoft 365 のアカウントに多要素認証を設定するエンタープライズテスト環境には、2つのフェーズと3番目のフェーズが含まれます。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [フェーズ 3: 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストする](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で多要素認証をテストする場合は、「 [ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで多要素認証をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従ってください。
  
> [!NOTE]
> 多要素認証をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする

次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。
  
1. ブラウザーのプライベートインスタンスを個別に開き、Microsoft 365 管理センター () に移動して、 [https://portal.microsoft.com](https://portal.microsoft.com) 全体管理者アカウントでサインインします。
    
2. 左側のナビゲーションで、[**ユーザー**  >  の**アクティブなユーザー**] を選択します。
    
3. [アクティブなユーザー] ウィンドウで、[ **多要素認証**] を選択します。
    
4. リストで、 **User 2** アカウントを選択します。
    
5. [ **User 2** ] セクションの [ **クイック操作**] で、[ **有効にする**] を選択します。
    
6. [ **多要素認証を有効に** する] ダイアログボックスで、[ **多要素認証を有効にする**] を選択します。
    
7. [ **更新が成功しまし** た] ダイアログボックスで、[ **閉じる**] を選択します。
    
8. [ **Microsoft 365 管理センター** ] タブで、右上の [ユーザーアカウント] アイコンを選択し、[ **サインアウト**] を選択します。
    
9. ブラウザー インスタンスを閉じます。
   
次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。
  
1. ブラウザーの新しいプライベートインスタンスを開きます。
    
2. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、User 2 のアカウント名とパスワードを使用してサインインします。
    
3. サインインした後、詳細についてはアカウントをセットアップするように求めるメッセージが表示されます。 [**次へ**] を選択します。
    
4. **[追加のセキュリティ確認]** ページで、次の手順を実行します。 
    
   - 国または地域を選択します。
    
   - テキストメッセージを受信するスマートフォンの電話番号を入力します。
    
   - [ **メソッド**] で、[ **テキストメッセージでコードを送信する**] を選択します。
    
5. [**次へ**] を選択します。
    
6. スマートフォンで受信したテキストメッセージの確認コードを入力して、[ **確認**] を選択します。
    
7. [ **手順 3: 既存のアプリケーションを使用** したままにする] ページで、[ **完了**] を選択します。
    
8. User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。 元のパスワードと新しいパスワードを2回入力し、[ **Update password**] を選び、[サインイン] を選択します。 新しいパスワードを安全な場所に記録します。
    
    ブラウザーの [ **Microsoft Office Home** ] タブに、ユーザー2の office ポータルが表示されます。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>フェーズ 3: 条件付きアクセスポリシーを使用して多要素認証を有効にしてテストする

*このフェーズは、Microsoft 365 for enterprise テスト環境に対してのみ使用できます。*

このフェーズでは、グループと条件付きアクセスポリシーを使用して、User 3 アカウントに対して多要素認証を有効にします。

次に、MFAUsers という名前の新しいグループを作成し、そのグループに User 3 アカウントを追加します。

1. [ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションで [ **グループ** ] を選択し、[ **グループ**] を選択します。
2. [ **グループの追加**] を選択します。
3. [ **グループの種類を選択** してください] ウィンドウで、[ **セキュリティ**] を選択し、[ **次へ**] を選択します。
4. [ **基本の設定** ] ウィンドウで、[ **グループの作成**] を選択し、[ **閉じる**] を選択します。
5. [ **グループの追加の確認と完了** ] ウィンドウで、[ **mfausers**] と入力し、[ **次へ**] を選択します。
6. グループの一覧で、[ **Mfausers** ] グループを選択します。
7. [ **Mfausers** ] ウィンドウで、[ **メンバー**] を選択し、[ **すべて表示**] を選択して、[メンバーの管理] をクリックします。
8. [ **Mfausers** ] ウィンドウで、[**メンバーの追加**] を選択し、 **User 3**のアカウントを選択してから、[**保存**して閉じる] を選択し  >  **Close**  >  **Close**ます。

次に、MFAUsers グループのメンバーに対して多要素認証を必要とする条件付きアクセスポリシーを作成します。

1. ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。
2. [ **Azure Active Directory**  >  **セキュリティ**  >  **条件付きアクセス**] を選択します。
3. [ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **新しいポリシー**] を選択します。
4. **新しい**ウィンドウで、[**名前**] ボックスに「**ユーザーアカウントの MFA** 」と入力します。
5. [ **割り当て** ] セクションで、[ **ユーザーとグループ**] を選択します。
6. [**ユーザーとグループ**] ウィンドウの [**包含**] タブで、[ユーザーとグループの**選択**] の [ユーザーとグループの選択] を選択し  >  **Users and groups**  >  **Select**ます。
7. **[選択**] ウィンドウで、[ **mfausers** ] グループを選択し、[完了 **]** を選択し  >  **Done**ます。
8. [**新規**] ウィンドウの [**アクセス制御**] セクションで、[**付与**] を選択します。
9. [ **付与** ] ウィンドウで、[ **多要素認証を必要とする**] を選択してから、[ **選択**] を選択します。
10. [**新規**] ウィンドウで、[**有効なポリシー**] の [オン] を選択し、[**作成**] を選択します。 **On**
11. **Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。

このポリシーをテストするには、サインアウトして、User 3 アカウントでサインインします。 MFA の構成を求めるメッセージが表示されます。 これは、MFAUsers ポリシーが適用されていることを示しています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Identity ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
