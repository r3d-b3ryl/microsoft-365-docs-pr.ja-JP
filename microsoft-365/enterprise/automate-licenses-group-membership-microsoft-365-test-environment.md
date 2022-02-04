---
title: エンタープライズ テスト環境向けライセンスとグループ Microsoft 365を自動化する
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
  - TLG
  - Ent_TLGs
description: エンタープライズ テスト環境用に、グループ ベースのライセンスと動的Microsoft 365メンバーシップを構成します。
---

# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境向けライセンスとグループ Microsoft 365を自動化する

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

グループ ベースのライセンスでは、グループ メンバーシップに基づいて、ユーザー アカウントのライセンスが自動的に割り当てまたは削除されます。 動的グループ メンバーシップは、部署や国などのユーザー アカウントのプロパティに基づいて、グループにメンバー **を追加または** 削除 **します**。 この記事では、エンタープライズ テスト環境でグループ メンバーを追加および削除するMicrosoft 365手順を説明します。

エンタープライズ テスト環境用に自動ライセンスと動的グループ メンバーシップをMicrosoft 365には、次の 2 つのフェーズがあります。

- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 動的グループ メンバーシップと自動ライセンスの構成とテスト](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小限の要件で、自動ライセンスとグループ メンバーシップのみを軽量な方法でテストする場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで自動ライセンスとグループ メンバーシップをテストする場合は、「パススルー認証」 [の手順に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> ライセンスとグループ の自動メンバーシップをテストするには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここではオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>フェーズ 2: 動的グループ メンバーシップと自動ライセンスの構成とテスト

まず、Sales という名前の新しいグループを作成し、部署が Sales に設定されているユーザー アカウントが自動的に **Sales** グループに参加する動的グループ メンバーシップ ルールを追加します。

1. インターネット ブラウザーのプライベート インスタンスで、テスト ラボ [サブスクリプション](https://admin.microsoft.com)Microsoft 365 管理センター管理者アカウントを使用して、Microsoft 365 E5にサインインします。
2. ブラウザーの別のタブで、Azure portal に移動します [https://portal.azure.com](https://portal.azure.com)。
3. Azure portal で、検索ボックスに **グループ** を入力し、[グループ] を選択 **します**。
4. [すべてのグループ **] ウィンドウで** 、[新しいグループ] **を選択します**。
5. [**グループの種類] で**、[グループの種類 **] Microsoft 365**。
6. [ **グループ名] に「** Sales」と **入力します**。
7. [ **メンバーシップの種類] で**、[動的ユーザー **] を選択します**。
8. [動的 **ユーザー メンバー] を選択します**。
9. [動的メンバーシップ **ルール] ウィンドウで、次の操作を** 行います。 
   - 部門プロパティ **を選択** します。
   - [等号 **] 演算子を選択** します。
   - [値] **ボックスに** 「Sales」と **入力します**。
10. **[保存]** を選択します。
11. **[作成]** を選択します。

次に、メンバーにライセンスが自動的に割り当てMicrosoft 365 E5構成します。

1. [販売] **グループを選択** し、[ライセンス] を **選択します**。
2. [ライセンスの **割り当ての更新] ウィンドウ** で、[ライセンスの割 **り当Microsoft 365 E5** 選択し、[保存] を **選択します**。
3. ブラウザーで、[Azure ポータル] タブを閉じます。

次に、User 4 アカウントで動的グループ メンバーシップと自動ライセンスをテストします。

1. ブラウザーの **[Microsoft Office] タブ** で、[管理者] を選択 **します**。
2. [ユーザー] **タブMicrosoft 365 管理センター**[アクティブ ユーザー] **を選択します**。
3. [アクティブ な **ユーザー] ページ** で、[ **ユーザー 4] アカウントを選択** します。
4. [ユーザー **4] ウィンドウで** 、[製品ライセンス **の編集** ] **を選択します**。
5. [製品ライセンス **] ウィンドウ** で、**ライセンスを無効** Microsoft 365 E5し、[**SaveClose] を** > **選択します**。
6. User 4 アカウントのプロパティで、製品ライセンスが割り当てられていないか、グループ メンバーシップが割り当てられていないか確認します。
7. [ **連絡先情報] で、[** 編集] を **選択します**。
8. [連絡先情報 **の編集] ウィンドウで** 、[連絡先情報] **を選択します**。
9. [部署] **ボックスに**「**Sales」と入力** し、[**SaveClose**] **を** > 選択します。
10. 数分待ち、ユーザー 4 アカウント ウィンドウの右上にある  [更新] アイコンを定期的に選択します。

時間内に、次の情報が表示されます。

- **Sales グループで** 更新されたグループ メンバーシップ **プロパティ** 。
- **製品ライセンス** プロパティは、ライセンスライセンス **Microsoft 365 E5** 更新されます。

動的グループ メンバーシップと自動ライセンスを実稼働環境に展開するには、次の記事を参照してください。

- [グループ ベースのライセンス Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory の動的グループ](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID の展開](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)