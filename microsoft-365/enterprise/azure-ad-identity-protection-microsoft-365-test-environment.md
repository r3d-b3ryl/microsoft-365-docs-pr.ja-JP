---
title: Microsoft 365 Enterprise テスト環境の Azure AD id 保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection を構成し、Microsoft 365 Enterprise テスト環境で現在のアカウントを分析します。
ms.openlocfilehash: bdac512f7645bf78c0a9c6bc5f71b35916bc4812
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279096"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境の Azure AD id 保護

Azure AD id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動化された応答を構成し、インシデントを調査できます。 この記事では、Azure AD id 保護を有効にし、テスト環境アカウントの分析を表示する方法について説明します。

Microsoft 365 エンタープライズテスト環境で Azure AD id 保護をセットアップするには、次の2つのフェーズがあります。

1. Microsoft 365 Enterprise テスト環境を作成します。
2. Azure AD id 保護を有効にして使用します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する

最小限の要件で Azure AD Identity Protection を軽量な方法でテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> Azure AD Identity Protection のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 これは、Azure AD id 保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして提供されています。 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>フェーズ 2: Azure AD Identity Protection を有効にして使用する

1. ブラウザーのプライベートインスタンスを開き、Microsoft 365 Enterprise テスト環境のグローバル管理[https://portal.azure.com](https://portal.azure.com)者アカウントを使用して Azure portal にサインインします。
2. Azure portal で、[**すべてのサービス > Marketplace**] をクリックします。
3. 「 **Azure AD Identity Protection** 」と入力し、それをクリックします。
4. [スタート**** ] ブレードで、[**設定**] の下の [**オン**] をクリックし、[**ダッシュボードに Pin**] をクリックしてから、[**作成**] をクリックします。
5. azure portal で、ダッシュボードの [ **azure AD id 保護**] をクリックします。 

   **Azure AD Identity Protection-概要**ブレードとダッシュボードが表示されているはずです。 [**脆弱性**] で、多要素認証が登録されていないユーザーアカウントの数が決まっていることを確認します。 この数値は、以前に実行した Microsoft 365 Enterprise のテストラボガイドによって異なります。

6. **調査**のカテゴリをクリックして、検出されたユーザーまたはイベントがあるかどうかを確認します。

テストと実験の詳細については、「[リスクイベントをシミュレート](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)する」を参照してください。

Azure AD id 保護を運用環境に展開するための情報とリンクについては、id フェーズの「[資格情報が侵害](identity-multi-factor-authentication.md#identity-ident-prot)されないように保護する」の手順を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 展開](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
