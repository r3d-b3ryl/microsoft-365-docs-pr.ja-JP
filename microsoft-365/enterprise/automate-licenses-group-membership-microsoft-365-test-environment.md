---
title: Microsoft 365 Enterprise テスト環境のライセンスとグループメンバーシップを自動化する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 Enterprise テスト環境で、グループベースのライセンスと動的なグループメンバーシップを構成します。
ms.openlocfilehash: cb01e1a405e7cff1f9965e34751b3ce638dd8018
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071726"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境のライセンスとグループメンバーシップを自動化する

グループベースのライセンスは、グループメンバーシップに基づいてユーザーアカウントのライセンスを自動的に割り当てるか削除します。 動的グループメンバーシップは、ユーザーアカウントのプロパティ (部署、国など) に基づいてグループにメンバーを追加または削除します。 この記事では、Microsoft 365 エンタープライズテスト環境の両方のデモを行います。

Microsoft 365 Enterprise テスト環境で自動ライセンスと動的グループメンバーシップをセットアップするには、次の2つのフェーズがあります。

1. Microsoft 365 Enterprise のテスト環境を作成します。
2. 動的なグループメンバーシップおよび自動ライセンスを構成してテストします。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する

最小要件での軽量な方法で自動化されたライセンスとグループメンバーシップをテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで自動ライセンスおよびグループメンバーシップをテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>フェーズ 2: 動的なグループメンバーシップおよび自動ライセンスを構成してテストする

最初に、新しい Sales グループを作成し、そのグループメンバーシップのルールを追加して、Department を Sales に設定したユーザーアカウントが自動的に Sales グループに追加されるようにします。

1. インターネットブラウザーのプライベートインスタンスを使用して、office 365 のポータルに office 365 [https://portal.office.com](https://portal.office.com) E5 テストラボサブスクリプションの全体管理者アカウントでサインインします。
2. ブラウザーの別のタブで、Azure portal に移動[https://portal.azure.com](https://portal.azure.com)します。
3. Azure portal で **[Azure Active Directory] > [ユーザーとグループ] > [すべてのグループ]** の順にクリックします。
4. [**すべてのグループ**] ブレードで、[**新しいグループ**] をクリックします。
5. [**グループの種類**] で、[ **Office 365**] を選択します。
6. [**グループ名**] に「 **Sales**」と入力します。
7. [**メンバーシップの種類**] で、[**動的ユーザー** ] を選択します。
8. **[動的クエリの追加]** をクリックします。
9. **[ユーザーを追加する場所]** で、**[部署]** を選択します。
10. 次のフィールドで、**[等しい]** を選択します。
11. 次のフィールドで、「 **Sales**」と入力します。
12. **[クエリの追加]** をクリックしてから、**[作成]** をクリックします。
13. [グループと**グループ-すべて**のグループ **]** ブレードを閉じます。

次に、メンバーに Office 365 E5 および Enterprise Mobility + Security E5 ライセンスが自動的に割り当てられるように、Sales グループを構成します。

1. [Azure Active Directory の**概要**] ブレードで、[**すべての製品 > ライセンス**] をクリックします。
2. 一覧で、 **[Enterprise Mobility + Security E5]** と **[Office 365 Enterprise E5]** を選択し、 **[割り当て]** をクリックします。
3. [**ライセンスの割り当て**] ブレードで、[**ユーザーとグループ**] をクリックします。
4. グループの一覧で、[ **Sales** ] グループを選択します。
5. **[選択]** をクリックし、 **[割り当て]** をクリックします。
6. ブラウザーの [Azure Portal] タブを閉じます。

次に、ユーザー4アカウントの動的グループメンバーシップと自動ライセンスをテストします。 

1. ブラウザーの [ **Microsoft Office Home** ] タブで、[**管理者**] をクリックします。
2. [ **Microsoft 365 管理センター** ] タブで、[**アクティブなユーザー**] をクリックします。
3. [**アクティブなユーザー** ] ページで、[ **User 4** ] アカウントをクリックします。
4. [ **User 4** ] ウィンドウで、[**製品ライセンス**] の [**編集**] をクリックします。
5. [**製品ライセンス**] ウィンドウで、 **Enterprise Mobility + Security e5**および**Office 365 Enterprise e5**ライセンスをオフにして、[**保存 > 閉じる**] をクリックします。
6. User 4 アカウントの [プロパティ] で、製品ライセンスが割り当てられておらず、グループメンバーシップもないことを確認します。
7. [**連絡先情報**] の [**編集**] をクリックします。
8. [**連絡先情報の編集**] ウィンドウで、[**連絡先情報**] をクリックします。
9. [**部署**] フィールドに「 **Sales**」と入力し、[**保存 > 閉じる**] をクリックします。
10. 数分待ってから、ユーザー4のアカウントウィンドウの右上にある [更新] アイコンを定期的にクリックします。 

時間内に、次のように表示されるはずです。

- **グループメンバーシップ**プロパティが**Sales** group で更新されました。
- **Enterprise Mobility + Security e5**および**Office 365 enterprise e5**ライセンスで更新された**製品ライセンス**のプロパティ。

動的グループメンバーシップと自動ライセンスを運用環境に展開するための情報とリンクについては、Id フェーズの以下の手順を参照してください。

- [自動ライセンスをセットアップする](identity-use-group-management.md#identity-group-license)
- [動的グループ メンバーシップをセットアップする](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
