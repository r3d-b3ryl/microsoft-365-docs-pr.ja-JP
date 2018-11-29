---
title: Microsoft 365 エンタープライズ テスト環境のライセンスとグループのメンバーシップを自動化します。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 エンタープライズ テスト環境では、グループ ベースのライセンスと動的グループのメンバーシップを構成します。
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869387"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 エンタープライズ テスト環境のライセンスとグループのメンバーシップを自動化します。

グループ ベース ライセンスを自動的に割り当てるか、グループ メンバーシップに基づいてユーザー アカウントのライセンスを削除します。動的グループのメンバーシップを追加または部門や国などのユーザー アカウントのプロパティに基づいて、グループにメンバーを削除します。この資料は、Microsoft 365 エンタープライズ テスト環境の両方のデモンストレーションする手順を示します。

Microsoft 365 エンタープライズ テスト環境での自動ライセンスおよび動的グループのメンバーシップを設定するのには 2 つのフェーズがあります。

1. Microsoft 365 エンタープライズ テスト環境を作成します。
2. 構成し、動的グループのメンバーシップおよび自動ライセンスをテストします。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で自動化されたライセンスとグループのメンバーシップをテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業で自動化されたライセンスとグループのメンバーシップをテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>フェーズ 2: を構成して、動的グループのメンバーシップおよびライセンスの自動テスト

最初に、新しいセールス ・ グループを作成し、部門の売り上げ高に設定を持つユーザー アカウントを Sales グループに自動的に追加できるように、動的グループのメンバーシップの規則を追加します。

1. Office 365 ポータルにサインインして、インターネット ブラウザーのプライベート インスタンスを使用すると、 [https://portal.office.com](https://portal.office.com) 、Office 365 の E5 の試用版サブスクリプションのグローバル管理者アカウントを使用しています。
2. Azure ポータルには、ブラウザーの別のタブ、[ [https://portal.azure.com](https://portal.azure.com)。
3. Azure portal で **[Azure Active Directory] > [ユーザーとグループ] > [すべてのグループ]** の順にクリックします。
4. **グループのすべて**のブレードでは、**新しいグループ**をクリックします。
5. **グループの種類**では、 **Office 365**を選択します。
6. **グループ名**、**売り上げ高**を入力します。
7. **メンバーシップの種類**] では、**動的なユーザー**を選択します。
8. **[動的クエリの追加]** をクリックします。
9. **[ユーザーを追加する場所]** で、**[部署]** を選択します。
10. 次のフィールドで、**[等しい]** を選択します。
11. 次のフィールドでは、**売り上げ高**を入力します。
12. **[クエリの追加]** をクリックしてから、**[作成]** をクリックします。
13. **グループ**と**グループのすべてのグループ**のブレードを閉じます。

次に、Office 365 の E5 とエンタープライズ モビリティとセキュリティ E5 ライセンスのメンバーが自動的に割り当てられるように、セールス ・ グループを構成します。

1. Azure Active Directory の**概要**のブレードでをクリックして**ライセンス > すべての製品**。
2. 一覧で、 **[Enterprise Mobility + Security E5]** と **[Office 365 Enterprise E5]** を選択し、 **[割り当て]** をクリックします。
3. **ライセンスの割り当て**のブレードでは、**ユーザーとグループ**をクリックします。
4. グループの一覧では、 **Sales**グループを選択します。
5. **[選択]** をクリックし、 **[割り当て]** をクリックします。
6. ブラウザーの [Azure Portal] タブを閉じます。

次に、動的グループのメンバーシップと 4 のユーザー アカウントの自動ライセンスの取得をテストします。 

1. **Microsoft Office ホーム**] タブからお使いのブラウザーで、[**管理**] をクリックします。
2. **Office 管理者センター** ] タブで、**アクティブなユーザー**をクリックします。
3. [**アクティブ ユーザ**] ページでは、 **4 のユーザー**アカウントをクリックします。
4. **ユーザー 4**ウィンドウで、**製品のライセンス**の [**編集**] をクリックします。
5. **製品ライセンス**] ウィンドウで、[**エンタープライズ モビリティ + E5 のセキュリティ**を有効にするクリックし、 **Office 365 エンタープライズ E5**ライセンス オフ、**を保存 > 閉じる**。
6. 4 のユーザー アカウントのプロパティ] では、製品のライセンスが割り当てられていないと、グループ メンバーシップがないことを確認します。
7. **連絡先情報**の**編集**] をクリックします。
8. **については連絡先の編集**ウィンドウで、**連絡先情報**をクリックします。
9. [**部門**] フィールドで、**販売**を入力し] をクリックし、**を保存 > 閉じる**。
10. 、数分待ってから、定期的に 4 のユーザー アカウント] ウィンドウの右上の更新アイコンをクリックします. 

時刻が表示します。

- **グループ メンバーシップ**プロパティが、**セールス**・ グループを使用して更新します。
- **エンタープライズ モビリティおよびセキュリティ E5**と**Office 365 のエンタープライズ E5**のライセンスを更新する**製品のライセンス**プロパティです。

情報と動的グループのメンバーシップと実稼働環境での自動ライセンス展開へのリンクの識別段階では、次の手順を参照してください。

- [自動ライセンスをセットアップする](identity-group-based-licensing.md)
- [動的グループ メンバーシップをセットアップする](identity-automatic-group-membership.md)

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 エンタープライズ展開](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
