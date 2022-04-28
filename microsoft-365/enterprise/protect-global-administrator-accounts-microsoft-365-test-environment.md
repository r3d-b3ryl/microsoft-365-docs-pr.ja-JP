---
title: エンタープライズ テスト環境用にMicrosoft 365のグローバル管理者アカウントを保護する
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
description: エンタープライズ テスト環境のMicrosoft 365内のグローバル管理者アカウントを保護するには、次の手順に従います。
ms.openlocfilehash: bf053b9767aea4a290c5357d6309c57677a36cad
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098276"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境用にMicrosoft 365のグローバル管理者アカウントを保護する

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

管理者アカウントができるだけ安全であることを確認することで、組織に対するデジタル攻撃を防ぐことができます。 

この記事では、Azure Active Directory (Azure AD) 条件付きアクセス ポリシーを使用してグローバル管理者アカウントを保護する方法について説明します。

エンタープライズ テスト環境用にMicrosoft 365のグローバル管理者アカウントを保護するには、次の 2 つのフェーズが必要です。
- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 条件付きアクセス ポリシーを構成する](#phase-2-configure-conditional-access-policies)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を持つ軽量な方法でグローバル管理者アカウント保護をテストする場合は、 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)の手順に従います。
  
シミュレートされたエンタープライズでグローバル管理者アカウント保護をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) のディレクトリ同期が含まれます。 ここでは、グローバル管理者アカウント保護をテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>フェーズ 2: 条件付きアクセス ポリシーを構成する

まず、専用のグローバル管理者として新しいユーザー アカウントを作成します。

1. 別のタブで、Microsoft 365 管理センターを開[きます](https://admin.microsoft.com/)。
2. **[UsersActive** >  **ユーザー**] を選択し、[**ユーザーの追加]** を選択します。
3. [**ユーザーの追加]** ウィンドウで、[**名**]、[**表示名**]、および **[ユーザー名**] ボックスに **「DedicatedAdmin**」と入力します。
4. **[パスワード**] を選択し、[**パスワードを作成する]** を選択して、強力なパスワードを入力します。 この新しいアカウントのパスワードを安全な場所に記録します。
5. **[次へ]** を選択します。
6. [**製品ライセンスの割り当て**] ウィンドウで **[Microsoft 365 E5**]、[**次へ**] の順に選択します。
7. **[オプションの設定]** ウィンドウで、[**RolesAdmin** >  **center** **accessGlobal** >  **adminNext** > ] を選択します。
8. [ **ほぼ完了]** ウィンドウで、[ **追加の完了**] を選択し、[ **閉じる**] を選択します。

次に、GlobalAdmins という名前の新しいグループを作成し、DedicatedAdmin アカウントを追加します。

1. **[Microsoft 365 管理センター**] タブで、左側のナビゲーションで [**グループ**] を選択し、[**グループ**] を選択します。
2. [ **グループの追加] を選択します**。
3. [ **グループの種類の選択** ] ウィンドウで [ **セキュリティ**] を選択し、[ **次へ**] を選択します。
4. [ **基本のセットアップ** ] ウィンドウで、[グループの **作成**] を選択し、[ **閉じる**] を選択します。
5. [ **グループの追加の確認と完了** ] ウィンドウで、「 **GlobalAdmins**」と入力し、[ **次へ**] を選択します。
7. グループの一覧で、 **GlobalAdmins グループを** 選択します。
8. **[GlobalAdmins**] ウィンドウで [**メンバー**] を選択し、[**すべての表示とメンバーの管理**] を選択します。
9. **[GlobalAdmins**] ウィンドウで [**メンバーの追加**] を選択し、**DedicatedAdmin** アカウントとグローバル管理者アカウントを選択し、**SaveCloseClose** >  >  を選択 **します**。

次に、条件付きアクセス ポリシーを作成して、グローバル管理者アカウントに多要素認証を要求し、サインイン リスクが中程度または高い場合に認証を拒否します。

この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。

1. ブラウザーの新しいタブで、 [https://portal.azure.com](https://portal.azure.com).
2. **[Azure Active Directory** >  **SecurityConditional** >  Access] をクリックします。
3. [ **条件付きアクセス – ポリシー** ] ウィンドウで、[ **ベースライン ポリシー: 管理者に MFA を要求する (プレビュー)]** を選択します。
4. [ **ベースライン ポリシー** ] ウィンドウで、[ **ポリシーをすぐに使用する] > [保存]** を選択します。

この 2 番目のポリシーは、サインイン リスクが中程度または高い場合に、グローバル管理者アカウント認証へのアクセスをブロックします。

1. [ **条件付きアクセス – ポリシー** ] ウィンドウで、[ **新しいポリシー**] を選択します。
2. [ **新規** ] ウィンドウで、「名前」に **「グローバル管理者** 」 **と入力します**。
3. [ **割り当て** ] セクションで、[ **ユーザーとグループ**] を選択します。
4. [**ユーザーとグループ**] ウィンドウの [**インクルード**] タブで、[**ユーザーとグループのユーザーとグループ** > の選択] **と [groupsSelect** > ] を選択 **します**。
5. **[選択**] ウィンドウで **GlobalAdmins** グループを選択し、**SelectDone** >  を選択します。
6. [ **割り当て** ] セクションで、[条件] を選択 **します**。
7. **[条件**] ウィンドウ **で、[サインイン リスク**] を選択し、[**構成**] **で [はい**] を選択し、[**高****] と [中**] を選択して、[選択して完了 **] を選択****します**。
8. [**新規**] ウィンドウの [**アクセス制御**] セクションで、[**許可**] を選択します。
9. **[許可**] ウィンドウで [**アクセスのブロック**] を選択し、[選択] を **選択します**。
10. [**新規**] ウィンドウで、[ポリシーを **有効にする**] **で [オン**] を選択し、[**作成**] を選択します。
11. **Azure portal** タブと **Microsoft 365 管理センター** タブを閉じます。

最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトしてサインインします。 MFA の構成を求めるメッセージが表示されます。 これは、最初のポリシーが適用されていることを示しています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID をデプロイする](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)