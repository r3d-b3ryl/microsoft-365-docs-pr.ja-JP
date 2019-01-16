---
title: Microsoft 365 エンタープライズ向けの azure の AD のアイデンティティ保護環境をテストします。
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
description: Azure AD Id 保護を構成し、Microsoft 365 エンタープライズ テスト環境の現在のアカウントを分析します。
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869083"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 エンタープライズ向けの azure の AD のアイデンティティ保護環境をテストします。

Azure AD の識別情報の保護を使用すると、潜在的な脆弱性の影響、組織の識別情報を与えることを検出しへの自動応答を構成し、インシデントを調査できます。この資料では、Azure AD Id 保護を有効にして、テスト環境のアカウントの分析を表示する方法について説明します。

Microsoft 365 エンタープライズ テスト環境での Azure AD の Id の保護を設定するのには 2 つのフェーズがあります。

1. Microsoft 365 エンタープライズ テスト環境を作成します。
2. 有効にして、Azure AD Id 保護を使用します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

Azure AD Id 保護を最低限の要件を持つ軽量な方法でテストする場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業で Azure AD Id 保護をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> Azure AD Id 保護をテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。Azure AD Id 保護をテストし、通常の組織を表す環境で実験するためのオプションとしてここで。 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>フェーズ 2: を有効にして、Azure AD Id 保護を使用して、

1. お使いのブラウザーのプライベート インスタンスを開くし、Azure ポータルにサインイン[https://portal.azure.com](https://portal.azure.com)Microsoft 365 エンタープライズ テスト環境のグローバル管理者アカウントを使用します。
2. Azure のポータルをクリックして**のすべてのサービス > 市場**です。
3. **Azure AD Id 保護**を入力し、[] をクリックします。
4. **はじめ**のブレードで**Onboard**を [**設定**] をクリックして**をダッシュ ボードには、暗証番号 (pin)**、し、[**作成**] をクリックします。
5. Azure のポータルでは、ダッシュ ボードの**Azure AD Id 保護**をクリックします。 

   ダッシュ ボードで、 **Azure AD アイデンティティ保護概要**ブレードを参照してくださいする必要があります。の下**の脆弱性**、多要素認証登録なしのユーザー アカウントの数を決定するを確認します。この番号は、以前 Microsoft 365 エンタープライズ テスト ラボ ガイドを行うことにより異なります。

6. あるかどうか、ユーザーまたは検出されたイベントを表示するのには**調査**のカテゴリをクリックします。

さらにテストと実験を行うには、[リスク イベントのシミュレーション](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)を参照してください。

情報と実稼働環境での Azure AD のアイデンティティの保護の展開へのリンクの識別段階では、[侵害の資格情報を保護する](identity-azure-ad-identity-protection.md)手順を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 エンタープライズ展開](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
