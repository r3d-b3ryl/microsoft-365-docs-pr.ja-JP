---
title: エンタープライズ テスト環境用に、Microsoft 365管理者アカウントを保護する
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
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
description: 次の手順を使用して、エンタープライズ テスト環境用にMicrosoft 365管理者アカウントを保護します。
ms.openlocfilehash: d9de3cb42a7473167c5e8c6dda5489aca2241909
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573705"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境用に、Microsoft 365管理者アカウントを保護する

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

管理者アカウントを可能な限り安全に管理することで、組織に対するデジタル攻撃を防止できます。 

この記事では、グローバル管理者アカウントを保護Azure Active Directory (Azure AD) 条件付きアクセス ポリシーを使用する方法について説明します。

エンタープライズ テスト環境用にMicrosoft 365管理者アカウントを保護するには、次の 2 つのフェーズがあります。
- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 条件付きアクセス ポリシーを構成する](#phase-2-configure-conditional-access-policies)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小要件でグローバル管理者アカウント保護を軽量な方法でテストする場合は、「Lightweight base [configuration」の手順に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズでグローバル管理者アカウント保護をテストする場合は、「パススルー認証」の [手順に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> グローバル管理者アカウント保護のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) のディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここでは、グローバル管理者アカウント保護をテストし、一般的な組織を表す環境でテストを行うオプションとして提供されています。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>フェーズ 2: 条件付きアクセス ポリシーを構成する

最初に、専用のグローバル管理者として新しいユーザー アカウントを作成します。

1. 別のタブで、タブを[開](https://admin.microsoft.com/)Microsoft 365 管理センター。
2. [ユーザー **の**  >  **アクティブなユーザー]** を選択し、[ユーザー **の追加] を選択します**。
3. [ユーザーの **追加] ウィンドウ** で、[名]、[表示名]、および [ユーザー名] ボックスに **「DedicatedAdmin」****と** 入力します。
4. [ **パスワード] を** 選択 **し、[パスワードを作成する**] を選択し、強力なパスワードを入力します。 この新しいアカウントのパスワードを安全な場所に記録します。
5. **[次へ]** を選択します。
6. [製品ライセンス **の割り当て**] ウィンドウで、[ライセンスの割 **り当て] Microsoft 365 E5** し、[次へ] を **選択します**。
7. [オプションの **設定] ウィンドウで**、[役割管理センター **アクセス**  >  **グローバル** 管理者  >  **次へ] を**  >  **選択します**。
8. [ほぼ **完了] ウィンドウで、[** 追加の完了] を選択し、[閉じる] を **選択します**。

次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。

1. [グループ] **Microsoft 365 管理センター** 左側のナビゲーションで [**グループ**] を選択し、[グループ] を **選択します**。
2. [グループ **の追加] を選択します**。
3. [グループの **種類の選択] ウィンドウで** 、[セキュリティ] **を選択** し、[次へ] を **選択します**。
4. [基本 **の設定] ウィンドウで、[グループの作成** ] を選択 **し**、[閉じる] を **選択します**。
5. [グループの **確認と追加の完了] ウィンドウで****、「GlobalAdmins」と入力** し、[次へ] を **選択します**。
7. グループの一覧で **、GlobalAdmins グループを選択** します。
8. **[GlobalAdmins]** ウィンドウで [**メンバー]** を選択し、[すべて表示] を選択 **してメンバーを管理します**。
9. **[GlobalAdmins]** ウィンドウで、[メンバーの追加] を選択し **、DedicatedAdmin** アカウントとグローバル管理者アカウントを選択し、[閉じる保存]  >  **を選択**  >  **します**。

次に、グローバル管理者アカウントに多要素認証を必要とする条件付きアクセス ポリシーを作成し、サインイン リスクが中程度または高い場合は認証を拒否します。

この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。

1. ブラウザーの新しいタブで、 に移動します [https://portal.azure.com](https://portal.azure.com) 。
2. [セキュリティ **Azure Active Directory**  >  **アクセス]**  >  **をクリックします**。
3. [条件付き **アクセス - ポリシー] ウィンドウで、[** 基準計画ポリシー: 管理者に MFA を **要求する (プレビュー) ] を選択します**。
4. [基準計画 **ポリシー] ウィンドウで** 、[ポリシーを **すぐに使用する] を選択>保存します**。

この 2 つ目のポリシーは、サインイン リスクが中程度または高の場合に、グローバル管理者アカウント認証へのアクセスをブロックします。

1. [条件付き **アクセス - ポリシー] ウィンドウで、[** 新しいポリシー] **を選択します**。
2. [新しい **] ウィンドウで**、[名前]**に「グローバル管理者」と****入力します**。
3. [割り **当て] セクションで** 、[ユーザーと **グループ] を選択します**。
4. [ユーザーと **グループ] ウィンドウ** の [含める]**タブ** で、[ユーザーとグループの選択] [ユーザーと **グループ**  >  **の選択] を**  >  **選択します**。
5. [選択 **] ウィンドウで****[GlobalAdmins] グループを選択** し、[完了] を **選択**  >  **します**。
6. [割り **当て] セクションで** 、[条件] を **選択します**。
7. [条件 **] ウィンドウで**、[サインイン **リスク]** を選択し、[構成]で **[** はい] を選択し、[高] と [中] を選択し、[選択] と [完了]**を選択****します**。 
8. [新しい **] ウィンドウの** [アクセス制御] セクション **で、[** 許可] を **選択します**。
9. [アクセス許可 **] ウィンドウで** 、[アクセス **をブロック** する] を選択し、[選択] を **選択します**。
10. [新しい **] ウィンドウで**、[ポリシーの有効化 **] で [オン****] を** 選択し、[作成] を **選択します**。
11. Azure portal を **閉じ、** タブ **Microsoft 365 管理センター** します。

最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトしてサインインします。 MFA の構成を求めるメッセージが表示されます。 これは、最初のポリシーが適用されているのを示しています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)