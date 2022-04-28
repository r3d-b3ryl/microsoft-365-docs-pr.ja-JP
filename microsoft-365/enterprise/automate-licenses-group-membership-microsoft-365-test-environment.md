---
title: エンタープライズ テスト環境のMicrosoft 365のライセンスとグループ メンバーシップを自動化する
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: エンタープライズ テスト環境のMicrosoft 365でグループ ベースのライセンスと動的グループ メンバーシップを構成します。
ms.openlocfilehash: 1d471076ac07acb023cdf785233ea2222690b596
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097538"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365のライセンスとグループ メンバーシップを自動化する

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

グループ ベースのライセンスは、グループ メンバーシップに基づいて、ユーザー アカウントのライセンスを自動的に割り当てるか削除します。 動的グループ メンバーシップは、 **部門** や国などのユーザー アカウントのプロパティに基づいて、グループにメンバーを追加または削除 **します**。 この記事では、エンタープライズ テスト環境のMicrosoft 365でグループ メンバーを追加および削除するデモについて説明します。

エンタープライズ テスト環境のMicrosoft 365で自動ライセンスと動的グループ メンバーシップを設定するには、次の 2 つのフェーズが必要です。

- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 動的グループ メンバーシップと自動ライセンスを構成してテストする](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を満たす軽量な方法で自動ライセンスとグループ メンバーシップのみをテストする場合は、 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)の手順に従います。
  
シミュレートされたエンタープライズで自動ライセンスとグループ メンバーシップをテストする場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスとグループ メンバーシップのテストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 ここでは、自動化されたライセンスとグループ メンバーシップをテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>フェーズ 2: 動的グループ メンバーシップと自動ライセンスを構成してテストする

まず、Sales という名前の新しいグループを作成し、 **部門** が Sales に設定されているユーザー アカウントが **自動的に Sales** グループに参加するように、動的グループ メンバーシップ 規則を追加します。

1. インターネット ブラウザーのプライベート インスタンスで、[Microsoft 365 E5](https://admin.microsoft.com)テスト ラボ サブスクリプションのグローバル管理者アカウントを使用してMicrosoft 365 管理センターにサインインします。
2. ブラウザーの別のタブで、次のAzure portalに[https://portal.azure.com](https://portal.azure.com)移動します。
3. Azure portalで、検索ボックスに **グループ** を入力し、[**グループ**] を選択します。
4. **[すべてのグループ**] ウィンドウで、[**新しいグループ**] を選択します。
5. **[グループの種類**] で、[**Microsoft 365**] を選択します。
6. **グループ名** に「Sales」と入力 **します**。
7. **[メンバーシップの種類]** で、[**動的ユーザー**] を選択します。
8. **[動的ユーザー メンバー**] を選択します。
9. **[動的メンバーシップ規則**] ウィンドウで、次の操作を行います。 
   - **department** プロパティを選択します。
   - **Equals 演算子を** 選択します。
   - [ **値** ] ボックスに「 **Sales**」と入力します。
10. **[保存]** を選択します。
11. **[作成]** を選択します。

次に、Microsoft 365 E5 ライセンスがメンバーに自動的に割り当てられるように、Sales グループを構成します。

1. **[Sales**] グループを選択し、[**ライセンス**] を選択します。
2. [**ライセンスの割り当ての更新**] ウィンドウで **Microsoft 365 E5を選択** し、[保存] を選択 **します**。
3. ブラウザーで、[Azure portal] タブを閉じます。

次に、ユーザー 4 アカウントで動的グループ メンバーシップと自動ライセンスをテストします。

1. ブラウザーの **[Microsoft Office ホーム**] タブで、[管理者] を選択 **します**。
2. **[Microsoft 365 管理センター**] タブで、[**アクティブなユーザー**] を選択します。
3. [ **アクティブなユーザー** ] ページで、 **ユーザー 4** アカウントを選択します。
4. **[ユーザー 4**] ウィンドウで、[**製品ライセンス** の **編集]** を選択します。
5. [**製品ライセンス**] ウィンドウで、**Microsoft 365 E5** ライセンスを無効にし、[**SaveClose** > ] を選択 **します**。
6. ユーザー 4 アカウントのプロパティで、製品ライセンスが割り当てられていないか、グループ メンバーシップがないことを確認します。
7. 連絡先情報の場合 **は**、[ **編集**] を選択します。
8. [ **連絡先情報の編集]** ウィンドウで、[ **連絡先情報**] を選択します。
9. [**部署**] ボックスに「**Sales**」と入力し、**SaveClose** >  を選択します。
10. 数分待ってから、ユーザー 4 アカウント ウィンドウの右上にある **[更新** ] アイコンを定期的に選択します。

時間内に、次の情報が表示されます。

- **Sales** **グループで更新されたグループ メンバーシップ** プロパティ。
- **Microsoft 365 E5 ライセンス** で更新された製品ライセンス プロパティ。

運用環境で動的グループ メンバーシップと自動ライセンスをデプロイするには、次の記事を参照してください。

- [Azure Active Directoryでのグループ ベースのライセンス](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory の動的グループ](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID をデプロイする](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)