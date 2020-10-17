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
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487578"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズテスト環境の Microsoft 365 のライセンスとグループメンバーシップを自動化する

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

グループベースのライセンスは、グループメンバーシップに基づいてユーザーアカウントのライセンスを自動的に割り当てるか削除します。 動的グループメンバーシップは、ユーザーアカウントのプロパティ ( **部署** 、 **国**など) に基づいてグループにメンバーを追加または削除します。 この記事では、Microsoft 365 for enterprise テスト環境におけるグループメンバーの追加と削除のデモンストレーションを行います。

Microsoft 365 for enterprise テスト環境での自動ライセンスと動的グループメンバーシップのセットアップには、次の2つのフェーズがあります。

- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で、自動ライセンスおよびグループメンバーシップのみをテストする場合は、「 [ライトウェイトの基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで自動ライセンスおよびグループメンバーシップをテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする

最初に、sales という名前の新しいグループを作成し、そのグループメンバーシップのルールを追加して、 **Department** を **sales** に設定したユーザーアカウントが自動的に sales グループに参加できるようにします。

1. インターネットブラウザーのプライベートインスタンスで、microsoft 365 E5 テストラボサブスクリプションの全体管理者アカウントを使用して、 [microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。
2. ブラウザーの別のタブで、Azure portal に移動 [https://portal.azure.com](https://portal.azure.com) します。
3. Azure portal で、[検索] ボックスに「 **groups** 」と入力し、[ **グループ**] を選択します。
4. [ **すべてのグループ** ] ウィンドウで、[ **新しいグループ**] を選択します。
5. [ **グループの種類**] で、[ **Microsoft 365**] を選択します。
6. [ **グループ名**] に、「 **Sales**」と入力します。
7. [ **メンバーシップの種類**] で、[ **動的ユーザー**] を選択します。
8. [ **動的ユーザーメンバー**] を選択します。
9. [ **動的メンバーシップの規則** ] ウィンドウで、次のようにします。 
   - **Department**プロパティを選択します。
   - **Equals**演算子を選択します。
   - [ **値** ] ボックスに「 **Sales**」と入力します。
10. [**保存**] を選択します。
11. **[作成]** を選択します。

次に、メンバーに Microsoft 365 E5 ライセンスが自動的に割り当てられるように、Sales グループを構成します。

1. [ **Sales** ] グループを選択し、[ **ライセンス**] を選択します。
2. [ **ライセンスの割り当ての更新** ] ウィンドウで、[ **Microsoft 365 E5**] を選択し、[ **保存**] を選択します。
3. ブラウザーで、[Azure portal] タブを閉じます。

次に、ユーザー4アカウントの動的グループメンバーシップと自動ライセンスをテストします。

1. ブラウザーの [ **Microsoft Office Home** ] タブで、[ **管理者**] を選択します。
2. [ **Microsoft 365 管理センター** ] タブで、[ **アクティブなユーザー**] を選択します。
3. [ **アクティブなユーザー** ] ページで、[ **User 4** ] アカウントを選択します。
4. [ **User 4** ] ウィンドウで、[**製品ライセンス**] の [**編集**] を選択します。
5. [**製品ライセンス**] ウィンドウで、 **Microsoft 365 E5**ライセンスを無効にしてから、[**保存**] [閉じる] を選択し  >  **Close**ます。
6. User 4 アカウントの [プロパティ] で、製品ライセンスが割り当てられておらず、グループメンバーシップもないことを確認します。
7. **連絡先情報**の場合は、[**編集**] を選択します。
8. [ **連絡先情報の編集** ] ウィンドウで、[ **連絡先情報**] を選択します。
9. [**部署**] ボックスに「 **Sales**」と入力し、[**保存**して閉じる] を選択し  >  **Close**ます。
10. 数分待ってから、ユーザー4のアカウントウィンドウの右上にある [ **更新** ] アイコンを定期的に選択します。

時間には、次のように表示されます。

- **グループメンバーシップ** プロパティが **Sales** group で更新されました。
- **製品ライセンス** プロパティは、 **Microsoft 365 E5** ライセンスで更新されました。

動的グループメンバーシップと自動ライセンスを運用環境に展開するには、次の記事を参照してください。

- [Azure Active Directory でのグループベースのライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory の動的グループ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[Identity ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
