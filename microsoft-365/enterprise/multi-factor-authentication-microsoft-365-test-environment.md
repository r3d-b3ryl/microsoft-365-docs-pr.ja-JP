---
title: エンタープライズ テスト環境の多要素認証のMicrosoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
- admindeeplinkMAC
description: エンタープライズ テスト環境のMicrosoft 365でスマートフォンに送信されるテキスト メッセージを使用して多要素認証を構成します。
ms.openlocfilehash: aa72375342bdf60e1fe1bc504f14b1f51a48b701
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65078737"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365の多要素認証

*このテスト ラボ ガイドは、エンタープライズ環境とOffice 365 Enterpriseテスト環境の両方のMicrosoft 365に使用できます。*

Microsoft 365またはサブスクリプションのAzure AD テナントを使用するサービスまたはアプリケーションにサインインするための追加のレベルのセキュリティについては、アカウントを確認するためにユーザー名とパスワードを超える必要があるAzure AD多要素認証を有効にすることができます。

多要素認証では、ユーザーは電話を確認したり、テキスト メッセージに送信された確認コードを入力したり、パスワードを正しく入力した後にスマートフォン上のアプリで認証を確認したりする必要があります。 この 2 番目の認証要素が満たされた後にのみサインインできます。
  
この記事では、特定のユーザー アカウントに対してテキスト メッセージ ベースの認証を有効にしてテストする方法について説明します。
  
エンタープライズ テスト環境のMicrosoft 365でアカウントの多要素認証を設定するには、次の 2 つのフェーズと 3 番目のオプション フェーズが含まれます。
- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [フェーズ 3: 条件付きアクセス ポリシーを使用して多要素認証を有効にしてテストする](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を満たす軽量な方法で多要素認証をテストするだけの場合は、「 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従います。
  
シミュレートされたエンタープライズで多要素認証をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 多要素認証をテストする場合、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする

次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。
  
1. ブラウザーの別のプライベート インスタンスを開き、Microsoft 365 管理センター ([https://portal.microsoft.com](https://portal.microsoft.com)) に移動し、グローバル管理者アカウントでサインインします。
    
2. 左側のナビゲーションで、[**UsersActive** >  ユーザー] を選択 <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**します**</a>。
    
3. [アクティブ ユーザー] ウィンドウで、[ **多要素認証**] を選択します。
    
4. 一覧で、 **ユーザー 2** アカウントを選択します。
    
5. [ **ユーザー 2** ] セクションの [ **クイック ステップ**] で 、[ **有効]** を選択します。
    
6. [ **多要素認証の有効化について** ] ダイアログ ボックスで、[ **多要素認証を有効にする**] を選択します。
    
7. [ **更新の成功** ] ダイアログ ボックスで、[ **閉じる**] を選択します。
    
8. **[Microsoft 365 管理センター**] タブで、右上の [ユーザー アカウント] アイコンを選択し、[**サインアウト**] を選択します。
    
9. ブラウザー インスタンスを閉じます。
   
次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。
  
1. ブラウザーの新しいプライベート インスタンスを開きます。
    
2. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、ユーザー 2 アカウント名とパスワードでサインインします。
    
3. サインイン後、詳細については、アカウントの設定を求めるメッセージが表示されます。 **[次へ]** を選択します。
    
4. **[追加のセキュリティ確認]** ページで、次の手順を実行します。 
    
   - 国または地域を選択します。
    
   - テキスト メッセージを受信するスマートフォンの電話番号を入力します。
    
   - **[メソッド**] で、[**テキスト メッセージでコードを送信** する] を選択します。
    
5. **[次へ]** を選択します。
    
6. スマートフォンで受信したテキスト メッセージから確認コードを入力し、[ **確認**] を選択します。
    
7. [ **手順 3: 既存のアプリケーションを保持する** ] ページで、[ **完了**] を選択します。
    
8. User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。 元のパスワードと新しいパスワードを 2 回入力し、[パスワードの更新] を選択 **してサインイン** します。 新しいパスワードを安全な場所に記録します。
    
    ブラウザーの [Microsoft Office ホーム] タブに、ユーザー 2 の **Office** ポータルが表示されます。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>フェーズ 3: 条件付きアクセス ポリシーを使用して多要素認証を有効にしてテストする

*このフェーズは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

このフェーズでは、グループと条件付きアクセス ポリシーを使用して、ユーザー 3 アカウントの多要素認証を有効にします。

次に、MFAUsers という名前の新しいグループを作成し、ユーザー 3 アカウントを追加します。

1. **[Microsoft 365 管理センター**] タブで、左側のナビゲーションで [**グループ**] を選択し、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**グループ**</a>] を選択します。
2. [ **グループの追加] を選択します**。
3. [ **グループの種類の選択** ] ウィンドウで [ **セキュリティ**] を選択し、[ **次へ**] を選択します。
4. [ **基本のセットアップ** ] ウィンドウで、[グループの **作成**] を選択し、[ **閉じる**] を選択します。
5. [ **グループの追加の確認と完了** ] ウィンドウで、「 **MFAUsers」** と入力し、[ **次へ**] を選択します。
6. グループの一覧で、 **MFAUsers グループを** 選択します。
7. **[MFAUsers**] ウィンドウで [**メンバー**] を選択し、[**すべての表示とメンバーの管理**] を選択します。
8. **[MFAUsers**] ウィンドウで [**メンバーの追加**] を選択し、**ユーザー 3** アカウントを選択して、[**SaveCloseClose** >  > ] を選択 **します**。

次に、MFAUsers グループのメンバーに多要素認証を要求する条件付きアクセス ポリシーを作成します。

1. ブラウザーの新しいタブで、 [https://portal.azure.com](https://portal.azure.com).
2. **[Azure Active Directory** >  **SecurityConditional** >  Access] を選択します。
3. [ **条件付きアクセス – ポリシー** ] ウィンドウで、[ **新しいポリシー**] を選択します。
4. [**新規**] ウィンドウの [名前] ボックス **に「ユーザー アカウントの MFA」****と** 入力します。
5. [ **割り当て** ] セクションで、[ **ユーザーとグループ**] を選択します。
6. [**ユーザーとグループ**] ウィンドウの [**インクルード**] タブで、[**ユーザーとグループのユーザーとグループ** > の選択] **と [groupsSelect** > ] を選択 **します**。
7. **[選択**] ウィンドウで、**MFAUsers** グループを選択し、**SelectDone** >  を選択します。
8. [**新規**] ウィンドウの [**アクセス制御**] セクションで、[**許可**] を選択します。
9. **[許可**] ウィンドウで、[**多要素認証が必要]** を選択し、[選択] を **選択します**。
10. [**新規**] ウィンドウで、[ポリシーを **有効にする**] **で [オン**] を選択し、[**作成**] を選択します。
11. **Azure portal** タブと **Microsoft 365 管理センター** タブを閉じます。

このポリシーをテストするには、ユーザー 3 アカウントでサインアウトしてサインインします。 MFA の構成を求めるメッセージが表示されます。 これは、MFAUsers ポリシーが適用されていることを示しています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID をデプロイする](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)