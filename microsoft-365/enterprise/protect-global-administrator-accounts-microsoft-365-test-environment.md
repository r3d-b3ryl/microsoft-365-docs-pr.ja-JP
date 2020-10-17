---
title: エンタープライズテスト環境の Microsoft 365 で全体管理者アカウントを保護する
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
description: 次の手順を使用して、エンタープライズテスト環境の Microsoft 365 のグローバル管理者アカウントを保護します。
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487638"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズテスト環境の Microsoft 365 で全体管理者アカウントを保護する

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

組織でのデジタル攻撃を防止するには、管理者アカウントのセキュリティを可能な限り確保することができます。 

この記事では、Azure Active Directory (Azure AD) 条件付きアクセスポリシーを使用して全体管理者アカウントを保護する方法について説明します。

Microsoft 365 でのグローバル管理者アカウントの保護エンタープライズテスト環境では、次の2つのフェーズが必要になります。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 条件付きアクセスポリシーを構成する](#phase-2-configure-conditional-access-policies)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で全体管理者アカウント保護をテストする場合は、「軽量な [基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで全体管理者アカウントの保護をテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> グローバル管理者アカウント保護のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) のディレクトリ同期が含まれます。 グローバル管理者アカウントの保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして、ここに記載されています。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>フェーズ 2: 条件付きアクセスポリシーを構成する

最初に、専用のグローバル管理者として新しいユーザーアカウントを作成します。

1. 別のタブで、 [Microsoft 365 管理センター](https://admin.microsoft.com/)を開きます。
2. [**ユーザー**のアクティブなユーザー] を選択し、[  >  **Active users****ユーザーの追加**] を選択します。
3. [**ユーザーの追加**] ウィンドウで、[**名**]、[**表示名**]、および [ユーザー**名**] ボックスに「 **DedicatedAdmin** 」と入力します。
4. [ **パスワード**] を選択し、[ **パスワードの作成を許可**する] を選択し、強力なパスワードを入力します。 この新しいアカウントのパスワードを安全な場所に記録します。
5. [**次へ**] を選択します。
6. [ **製品ライセンスの割り当て** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **次へ**] を選択します。
7. [**オプションの設定**] ウィンドウで、[**ロール**  >  **管理センターアクセス**の  >  **グローバル管理者**] を選択し  >  **Next**ます。
8. [ **ほぼ完了** ] ウィンドウで、[ **追加の完了**] を選択し、[ **閉じる**] を選択します。

次に、GlobalAdmins という名前の新しいグループを作成し、そのグループに DedicatedAdmin アカウントを追加します。

1. [ **Microsoft 365 管理センター** ] タブで、左側のナビゲーションで [ **グループ** ] を選択し、[ **グループ**] を選択します。
2. [ **グループの追加**] を選択します。
3. [ **グループの種類を選択** してください] ウィンドウで、[ **セキュリティ**] を選択し、[ **次へ**] を選択します。
4. [ **基本の設定** ] ウィンドウで、[ **グループの作成**] を選択し、[ **閉じる**] を選択します。
5. [ **グループの追加の確認と完了** ] ウィンドウで、「 **globaladmins**」と入力してから、[ **次へ**] を選択します。
7. グループの一覧で、[ **Globaladmins** ] グループを選択します。
8. [ **Globaladmins** ] ウィンドウで、[ **メンバー**] を選択し、[ **すべて表示**] を選択して、[メンバーの管理] をクリックします。
9. [ **Globaladmins** ] ウィンドウで、[**メンバーの追加**] を選択し、 **DedicatedAdmin**アカウントとグローバル管理者アカウントを選択してから、[**保存**して閉じる] を選択し  >  **Close**  >  **Close**ます。

次に、グローバル管理者アカウントに対して多要素認証を必要とする条件付きアクセスポリシーを作成し、サインインリスクが [中] または [高] の場合は認証を拒否します。

この最初のポリシーでは、すべてのグローバル管理者アカウントで MFA を使用する必要があります。

1. ブラウザーの新しいタブで、に移動 [https://portal.azure.com](https://portal.azure.com) します。
2. [ **Azure Active Directory**  >  **セキュリティ**] [  >  **条件付きアクセス**] をクリックします。
3. [ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **ベースラインポリシー: 管理者に MFA を必須にする (プレビュー)**] を選択します。
4. [ **基準ポリシー** ] ウィンドウで、[ **直ちにポリシーを使用 > 保存**] を選択します。

この2番目のポリシーは、サインインリスクが中または高の場合に、全体管理者アカウントの認証へのアクセスをブロックします。

1. [ **条件付きアクセス–ポリシー** ] ウィンドウで、[ **新しいポリシー**] を選択します。
2. **新しい**ウィンドウで、[**名前**] に**全体管理者**を入力します。
3. [ **割り当て** ] セクションで、[ **ユーザーとグループ**] を選択します。
4. [**ユーザーとグループ**] ウィンドウの [**包含**] タブで、[ユーザーとグループの**選択**] の [ユーザーとグループの選択] を選択し  >  **Users and groups**  >  **Select**ます。
5. **[選択**] ウィンドウで、[ **globaladmins** ] グループを選択してから、[完了 **]** を選択し  >  **Done**ます。
6. [ **割り当て** ] セクションで、[ **条件**] を選択します。
7. [**条件**] ウィンドウで、 **[サインインリスク**] を選択し、[**構成**] で [**はい**] を選択し、[**高**と**中**] を選択して、[**選択**して**完了**] を選択します。
8. [**新規**] ウィンドウの [**アクセス制御**] セクションで、[**付与**] を選択します。
9. [ **付与** ] ウィンドウで、[ **アクセスのブロック**] を選択し、[ **選択**] を選択します。
10. [**新規**] ウィンドウで、[**有効なポリシー**] の [オン] を選択し、[**作成**] を選択します。 **On**
11. **Azure portal**および**Microsoft 365 管理センター**のタブを閉じます。

最初のポリシーをテストするには、DedicatedAdmin アカウントでサインアウトし、サインインします。 MFA の構成を求めるメッセージが表示されます。 これは、最初のポリシーが適用されていることを示しています。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Identity ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
