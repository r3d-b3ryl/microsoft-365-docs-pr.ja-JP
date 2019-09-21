---
title: Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 次の手順を使用して、Microsoft 365 Enterprise テスト環境の全体管理者アカウントを保護します。
ms.openlocfilehash: 457ac33aa2242dc4b25cd662bf233bb1599a6fec
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071556"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護する

組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。 この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。

Microsoft 365 Enterprise テスト環境で全体管理者アカウントを保護するには、次の2つのフェーズがあります。

1.  Microsoft 365 Enterprise のテスト環境を作成します。
2.  専用のグローバル管理者アカウントを保護します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する

最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。

  
> [!NOTE]
> グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。 グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>フェーズ 2: 条件付きアクセスポリシーを構成する

最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。

1. 別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。
2. [**アクティブなユーザー**] で、[**ユーザーの追加**] をクリックします。
3. [**新しいユーザー** ] ページで、[**名前**]、[**表示名**]、および [**ユーザー名**] に**DedicatedAdmin**入力します。
4. [**パスワード**] をクリックし、[**パスワードの作成を許可**する] をクリックして、強力なパスワードを入力します。 この新しいアカウントのパスワードを安全な場所に記録します。
5. **[このユーザーが最初にサインインしたときにパスワードを変更するのをクリアする**。
6. [**ロール**] をクリックし、[**全体管理者**] をクリックします。
7. [**製品ライセンス**] をクリックし、 **Enterprise Mobility + Security e5**および**Office 365 enterprise e5 ライセンス**を有効にします。
8. **[追加]** をクリックします。
9. [**ユーザーが追加されました] ページ**で、[**電子メールでパスワードを送信**する] をオフにして、[**閉じる**] をクリックします。

次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。

1. **Microsoft 365 管理センター**のタブで、左側のナビゲーションの [グループ] アイコンをクリックし、[**グループ**] をクリックします。
2. [**グループの追加] を**クリックします。
3. [**新しいグループ**] ページで、「 **globaladmins**」と入力します。
4. [**所有者の選択**] をクリックし、全体管理者アカウントをクリックしてから、[**追加 > 閉じる**] をクリックします。
5. グループの一覧で、[ **Globaladmins** ] グループをクリックします。
6. [ **Globaladmins** ] ページで、[**メンバーの編集**] をクリックし、[**メンバーの追加**] をクリックします。
7. 一覧で、 **DedicatedAdmin**アカウントをクリックし、[保存] をクリックして **> 閉じる > > 管理センターを閉じ**ます。

次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが中または高の場合は認証を拒否します。

この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。

1. ブラウザーの新しいタブで、に[https://portal.azure.com](https://portal.azure.com)移動します。
2. [ **Azure Active Directory > 条件付きアクセス**] をクリックします。
3. [**条件付きアクセス–ポリシー** ] ブレードで、[**ベースラインポリシー: 管理者に MFA を必須とする (プレビュー)**] をクリックします。
4. [**基準ポリシー...** ブレードで、[**今すぐポリシーを使用 > 保存**] をクリックします。

この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。

1. [**条件付きアクセス–ポリシー** ] ブレードで、[**新しいポリシー**] をクリックします。
2. **新しい**ブレードで、[**名前**] に「 **Global administrators** 」と入力します。
3. [**割り当て**] セクションで、[**ユーザーとグループ**] をクリックします。
4. [**ユーザーとグループ**] ブレードの [**含める**] タブで、[ユーザーとグループの**選択 > ユーザーとグループの選択] > 選択**] をクリックします。
5. **[選択]** ブレードで、[ **globaladmins] > [> 完了] を選択**します。
6. [**割り当て**] セクションで、[**条件**] をクリックします。
7. [**条件**] ブレードで、 **[サインインリスク**] をクリックし、[**構成**] で [**はい**] をクリックして、[**高**と**中**] をクリックし、[**選択**して**完了**] をクリックします。
8. **新しい**ブレードの [**アクセス制御**] セクションで、[**付与**] をクリックします。
9. [**許可**] ブレードで、[**アクセスのブロック**] をクリックし、[**選択**] をクリックします。
10. **新しい**ブレードで、[**有効なポリシー**] の [**オン**] をクリックし、[**作成**] をクリックします。
11. **Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。

最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。 ユーザーアカウントで MFA を構成するように求めるメッセージが表示されます。 これは、最初のポリシーが適用されていることを示しています。

運用の全体管理者アカウントを保護するための情報とリンクについては、Id フェーズの[グローバル管理者アカウントの保護](identity-create-protect-global-admins.md#identity-global-admin)の手順を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
