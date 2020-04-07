---
title: Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する
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
description: 次の手順を使用して、Microsoft 365 Enterprise テスト環境の全体管理者アカウントを保護します。
ms.openlocfilehash: e6b93e3888873b6d78fec1802d179ed9624ffa63
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153870"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する

*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*

組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。 この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。

Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護するには、次の2つのフェーズがあります。

1.  Microsoft 365 Enterprise のテスト環境を作成します。
2.  専用のグローバル管理者アカウントを保護します。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。 グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>フェーズ 2: 条件付きアクセスポリシーを構成する

最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。

1. 別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。
2. [**ユーザー > アクティブユーザー**] をクリックし、[**ユーザーの追加**] をクリックします。
3. [**ユーザーの追加**] ウィンドウで、[**名前**]、[**表示名**]、および [ユーザー**名**] に**DedicatedAdmin**入力します。
4. [**パスワード**] をクリックし、[**パスワードの作成を許可**する] をクリックして、強力なパスワードを入力します。 この新しいアカウントのパスワードを安全な場所に記録します。
5. [ **次へ**] をクリックします。
6. [**製品ライセンスの割り当て**] ウィンドウで、[ **Microsoft 365 e5** ] または [ **Office 365 E5**] を選択し、[**次へ**] をクリックします。
7. [**オプションの設定**] ウィンドウで、[**役割**] をクリックし、[**管理センター** ] [アクセス] および [**グローバル管理者**] を選択します。[**次へ**] をクリックします。
8. [**ほぼ完了**] ウィンドウで、[**追加の完了**] をクリックし、[**閉じる**] をクリックします。

次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。

1. [ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションの [**グループ**] をクリックし、[**グループ**] をクリックします。
2. [**グループの追加] を**クリックします。
3. [**グループの種類を選択**してください] ウィンドウで、[**セキュリティ**] を選択し、[**次へ**] をクリックします。
4. [**基本の設定**] ウィンドウで、[**グループの作成**] をクリックし、[**閉じる**] をクリックします。
5. [**グループの追加の確認と完了**] ウィンドウで、「 **globaladmins**」と入力し、[**次へ**] をクリックします。
7. グループの一覧で、[ **Globaladmins** ] グループをクリックします。
8. [ **Globaladmins** ] ウィンドウで、[**メンバー**] をクリックし、[**すべて表示**] をクリックして、[メンバーの管理] をクリックします。
9. [ **Globaladmins** ] ウィンドウで、[**メンバーの追加**] をクリックし、 **DedicatedAdmin**アカウントとグローバル管理者アカウントを選択して、[保存] をクリックし **> 閉じる**] を > します。

次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが中または高の場合は認証を拒否します。

この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。

1. ブラウザーの新しいタブで、に[https://portal.azure.com](https://portal.azure.com)移動します。
2. [ **Azure Active Directory > セキュリティ > 条件付きアクセス**] をクリックします。
3. [**条件付きアクセス–ポリシー** ] ウィンドウで、[**ベースラインポリシー: 管理者に MFA を必須にする (プレビュー)**] をクリックします。
4. [**基準ポリシー** ] ウィンドウで、[**直ちにポリシーを使用 > 保存**] をクリックします。

この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。

1. [**条件付きアクセス–ポリシー** ] ウィンドウで、[**新しいポリシー**] をクリックします。
2. **新しい**ウィンドウで、[**名前**] に「**グローバル管理者**」と入力します。
3. [**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。
4. [**ユーザーとグループ**] ウィンドウの [**含める**] タブで、[ユーザーとグループの > 選択] をクリックし **> 選択**] をクリックします。
5. [**選択**] ウィンドウで、[ **globaladmins** ] グループをクリックし、[ **> の完了] を**クリックします。
6. [**割り当て**] セクションで、[**条件**] をクリックします。
7. [**条件**] ウィンドウで、 **[サインインリスク**] をクリックし、[**構成**] で [**はい**] をクリックして、[**高**と**中**] をクリックし、[**選択**して**完了**] をクリックします。
8. **新しい**ウィンドウの [**アクセス制御**] セクションで、[**付与**] をクリックします。
9. [**付与**] ウィンドウで、[**アクセスをブロック**] をクリックし、[**選択**] をクリックします。
10. **新しい**ウィンドウで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。
11. **Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。

最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。 MFA の構成を求めるメッセージが表示されます。 これは、最初のポリシーが適用されていることを示しています。

運用の全体管理者アカウントを保護するための情報とリンクについては、Id フェーズの[グローバル管理者アカウントの保護](identity-create-protect-global-admins.md#identity-global-admin)の手順を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
