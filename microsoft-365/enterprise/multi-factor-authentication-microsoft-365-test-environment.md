---
title: Microsoft 365テスト環境の多要素認証の機能
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
description: エンタープライズ テスト環境でスマートフォンに送信されるテキスト メッセージを使用して多要素Microsoft 365構成します。
ms.openlocfilehash: 4f410b7e8a57a119ecce33626354639af89c0e65aea01b123d213908735dbb00
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53813020"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境向けMicrosoft 365要素認証

*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*

Microsoft 365 またはサブスクリプションに Azure AD テナントを使用するサービスまたはアプリケーションにサインインするセキュリティの追加レベルについては、アカウントを確認するためにユーザー名とパスワード以上の必要がある Azure AD 多要素認証を有効にできます。

多要素認証では、ユーザーは、パスワードを正しく入力した後、電話を確認したり、テキスト メッセージで送信された検証コードを入力したり、スマートフォンでアプリで認証を確認したりする必要があります。 この 2 番目の認証要素が満たされた後にのみサインインできます。
  
この記事では、特定のユーザー アカウントのテキスト メッセージ ベース認証を有効にしてテストする方法について説明します。
  
エンタープライズ テスト環境向け Microsoft 365アカウントの多要素認証のセットアップには、2 つのフェーズと 3 番目のオプション フェーズが含まれる。
- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [フェーズ 3: 条件付きアクセス ポリシーを使用して多要素認証を有効にしてテストする](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小要件で軽量な方法で多要素認証をテストする場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで多要素認証をテストする場合は、「パススルー認証」の [手順に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 多要素認証のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 この指示は、一般的な組織と類似した環境で多要素認証をテストしてお試しいただけるようオプションとしてここで提供しています。
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>フェーズ 2:User 2 アカウントに対して、多要素認証を有効にしてテストする

次の手順を実行して、User 2 アカウントに対して多要素認証を有効にしてテストします。
  
1. ブラウザーの別のプライベート インスタンスを開き、Microsoft 365 管理センター ( ) に移動し、グローバル管理者アカウント [https://portal.microsoft.com](https://portal.microsoft.com) でサインインします。
    
2. 左側のナビゲーションで、[ユーザーがアクティブな **ユーザー]**  >  **を選択します**。
    
3. [アクティブ ユーザー] ウィンドウで、[多要素認証] **を選択します**。
    
4. 一覧で、[ユーザー **2] アカウントを選択** します。
    
5. [ユーザー **2] セクションの** [クイック ステップ] **で**、[有効にする] を **選択します**。
    
6. [多 **要素認証の有効化について]** ダイアログ ボックスで、[多要素認証を有効 **にする] を選択します**。
    
7. [成功した **更新プログラム] ダイアログ ボックス** で、[閉じる] を **選択します**。
    
8. [ユーザー  Microsoft 365 管理センター] タブで、右上のユーザー アカウント アイコンを選択し、[サインアウト]**を選択します**。
    
9. ブラウザー インスタンスを閉じます。
   
次の手順を実行して、User 2 アカウントで確認のためにテキスト メッセージを使用するように構成を完了し、それをテストします。
  
1. ブラウザーの新しいプライベート インスタンスを開きます。
    
2. [[ユーザー]](https://admin.microsoft.com) Microsoft 365 管理センターに移動し、User 2 アカウント名とパスワードを使用してサインインします。
    
3. サインイン後、詳細については、アカウントのセットアップを求めるメッセージが表示されます。 **[次へ]** を選択します。
    
4. **[追加のセキュリティ確認]** ページで、次の手順を実行します。 
    
   - 国または地域を選択します。
    
   - テキスト メッセージを受信するスマートフォンの電話番号を入力します。
    
   - [ **メソッド] で**、[ **テキスト メッセージでコードを送信する] を選択します**。
    
5. **[次へ]** を選択します。
    
6. スマートフォンで受信したテキスト メッセージから確認コードを入力し、[確認] を **選択します**。
    
7. [手順 **3: 既存のアプリケーションを** 保持する] ページで、[完了] を **選択します**。
    
8. User 2 アカウントでサインインするのが今回で初めての場合、パスワードの変更を求められます。 元のパスワードと新しいパスワードを 2 回入力し、[パスワードの更新とサインイン **] を選択します**。 新しいパスワードを安全な場所に記録します。
    
    ブラウザーの [Officeホーム] タブにユーザー 2 Microsoft Office **ポータル** が表示されます。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>フェーズ 3: 条件付きアクセス ポリシーを使用して多要素認証を有効にしてテストする

*このフェーズは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

このフェーズでは、グループと条件付きアクセス ポリシーを使用して、User 3 アカウントの多要素認証を有効にします。

次に、MFAUsers という名前の新しいグループを作成し、ユーザー 3 アカウントを追加します。

1. [グループ] **Microsoft 365 管理センター** 左側のナビゲーションで [**グループ**] を選択し、[グループ] を **選択します**。
2. [グループ **の追加] を選択します**。
3. [グループの **種類の選択] ウィンドウで** 、[セキュリティ] **を選択** し、[次へ] を **選択します**。
4. [基本 **の設定] ウィンドウで、[グループの作成** ] を選択 **し**、[閉じる] を **選択します**。
5. [グループの **確認と追加の完了] ウィンドウで****、「MFAUsers」** と入力し、[次へ] を **選択します**。
6. グループの一覧で **、MFAUsers グループを選択** します。
7. **[MFAUsers] ウィンドウで[****メンバー]** を選択し、[すべて表示] を選択して **メンバーを管理します**。
8. **[MFAUsers] ウィンドウで、[** メンバーの追加]**を選択し**、[**ユーザー 3]** アカウントを選択し、[閉じる保存]  >  **を選択**  >  **します**。

次に、MFAUsers グループのメンバーに多要素認証を要求する条件付きアクセス ポリシーを作成します。

1. ブラウザーの新しいタブで、 に移動します [https://portal.azure.com](https://portal.azure.com) 。
2. [セキュリティ **Azure Active Directory**  >  **アクセス**  >  **] を選択します**。
3. [条件付き **アクセス - ポリシー] ウィンドウで、[** 新しいポリシー] **を選択します**。
4. [新しい **] ウィンドウ** で、[名前] **ボックスにユーザー アカウント** の MFA と **入力** します。
5. [割り **当て] セクションで** 、[ユーザーと **グループ] を選択します**。
6. [ユーザーと **グループ] ウィンドウ** の [含める]**タブ** で、[ユーザーとグループの選択] [ユーザーと **グループ**  >  **の選択] を**  >  **選択します**。
7. [選択 **] ウィンドウで****、[MFAUsers] グループを選択** し、[完了の選択]**を**  >  **選択します**。
8. [新しい **] ウィンドウの** [アクセス制御] セクション **で、[** 許可] を **選択します**。
9. [付与 **] ウィンドウで** 、[多 **要素認証を要求** する] を選択し、[選択] を **選択します**。
10. [新しい **] ウィンドウで**、[ポリシーの有効化 **] で [オン****] を** 選択し、[作成] を **選択します**。
11. Azure portal を **閉じ、** タブ **Microsoft 365 管理センター** します。

このポリシーをテストするには、サインアウトして User 3 アカウントでサインインします。 MFA の構成を求めるメッセージが表示されます。 これは、MFAUsers ポリシーが適用されているのを示しています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)