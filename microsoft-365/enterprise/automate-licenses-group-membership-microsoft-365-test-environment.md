---
title: エンタープライズテスト環境の Microsoft 365 のライセンスとグループメンバーシップを自動化する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: エンタープライズテスト環境では、Microsoft 365 のグループベースのライセンスと動的なグループメンバーシップを構成します。
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685560"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズテスト環境の Microsoft 365 のライセンスとグループメンバーシップを自動化する

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

グループベースのライセンスは、グループメンバーシップに基づいてユーザーアカウントのライセンスを自動的に割り当てるか削除します。 動的グループメンバーシップは、ユーザーアカウントのプロパティ (部署、国など) に基づいてグループにメンバーを追加または削除します。 この記事では、Microsoft 365 for enterprise テスト環境の両方のデモを行います。

エンタープライズテスト環境の Microsoft 365 で自動ライセンスと動的グループメンバーシップをセットアップするには、次の2つのフェーズがあります。

1. エンタープライズテスト環境用の Microsoft 365 を作成します。
2. 動的なグループメンバーシップおよび自動ライセンスを構成してテストします。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で自動化されたライセンスとグループメンバーシップをテストする場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで自動ライセンスおよびグループメンバーシップをテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする

最初に、新しい Sales グループを作成し、そのグループメンバーシップのルールを追加して、Department を Sales に設定したユーザーアカウントが自動的に Sales グループに追加されるようにします。

1. インターネットブラウザーのプライベートインスタンスを使用して、microsoft 365 E5 テストラボサブスクリプションのグローバル管理者アカウントを使用して、 [microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。
2. ブラウザーの別のタブで、Azure portal に移動 [https://portal.azure.com](https://portal.azure.com) します。
3. Azure portal で、[検索] ボックスに「 **groups** 」と入力し、[ **グループ**] をクリックします。
4. [ **すべてのグループ** ] ウィンドウで、[ **新しいグループ**] をクリックします。
5. [ **グループの種類**] で、[ **Microsoft 365**] を選択します。
6. [ **グループ名**] に「 **Sales**」と入力します。
7. [ **メンバーシップの種類**] で、[ **動的ユーザー**] を選択します。
8. [ **動的ユーザーメンバー**] をクリックします。
9. [ **動的メンバーシップの規則** ] ウィンドウで、次のようにします。 
   - **Department**プロパティを選択します。
   - **Equals**演算子を選択します。
   - [ **売上** の **値**を入力します。
10. **[保存]** をクリックします。
11. **[作成]** をクリックします。

次に、メンバーに Microsoft 365 E5 ライセンスが自動的に割り当てられるように、Sales グループを構成します。

1. [ **Sales** ] グループをクリックし、[ **ライセンス**] をクリックします。
2. [ **ライセンスの割り当ての更新** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **保存**] をクリックします。
3. ブラウザーの [Azure Portal] タブを閉じます。

次に、ユーザー4アカウントの動的グループメンバーシップと自動ライセンスをテストします。 

1. ブラウザーの [ **Microsoft Office Home** ] タブで、[ **管理者**] をクリックします。
2. [ **Microsoft 365 管理センター** ] タブで、[ **アクティブなユーザー**] をクリックします。
3. [ **アクティブなユーザー** ] ページで、[ **User 4** ] アカウントをクリックします。
4. [ **User 4** ] ウィンドウで、[**製品ライセンス**] の [**編集**] をクリックします。
5. [ **製品ライセンス** ] ウィンドウで、 **Microsoft 365 E5** ライセンスを無効にしてから、[ **保存 > 閉じる**] をクリックします。
6. User 4 アカウントの [プロパティ] で、製品ライセンスが割り当てられておらず、グループメンバーシップもないことを確認します。
7. [**連絡先情報**] の [**編集**] をクリックします。
8. [ **連絡先情報の編集** ] ウィンドウで、[ **連絡先情報**] をクリックします。
9. [ **部署** ] フィールドに「 **Sales**」と入力し、[ **保存 > 閉じる**] をクリックします。
10. 数分待ってから、ユーザー4のアカウントウィンドウの右上にある [更新] アイコンを定期的にクリックします。 

時間内に、次のように表示されるはずです。

- **グループメンバーシップ** プロパティが **Sales** group で更新されました。
- **製品ライセンス** プロパティは、 **Microsoft 365 E5** ライセンスで更新されました。

動的グループメンバーシップと自動ライセンスを運用環境に展開するには、次の記事を参照してください。

- リンクの未定
- リンクの未定

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Identity ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
