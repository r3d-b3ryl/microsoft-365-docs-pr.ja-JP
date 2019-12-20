---
title: Microsoft 365 Enterprise テスト環境の Azure AD Id 保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection を構成し、Microsoft 365 Enterprise テスト環境で現在のアカウントを分析します。
ms.openlocfilehash: c0d364eaef9cfd37531d9f9e1803db66739a7984
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802102"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境の Azure AD Id 保護

*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*

Azure Active Directory (Azure AD) Id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動化された応答を構成し、インシデントを調査できます。 この記事では、Azure AD Identity Protection を使用して、テスト環境アカウントの分析を表示する方法について説明します。

Microsoft 365 エンタープライズテスト環境で Azure AD Id 保護をセットアップするには、次の2つのフェーズがあります。

1. Microsoft 365 Enterprise のテスト環境を作成します。
2. Azure AD Identity Protection を使用します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小限の要件で Azure AD Identity Protection を軽量な方法でテストする場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順を実行します。
  
> [!NOTE]
> Azure AD Identity Protection のテストでは、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 これは、Azure AD Id 保護をテストして、一般的な組織を表す環境で試してみることができるようにするためのオプションとして提供されています。 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>フェーズ 2: Azure AD Identity Protection を使用する

1. ブラウザーのプライベートインスタンスを開き、Microsoft 365 Enterprise テスト環境のグローバル管理[https://portal.azure.com](https://portal.azure.com)者アカウントを使用して Azure portal にサインインします。
2. Azure portal で、検索ボックスに「 **id 保護**」と入力し、[ **Azure AD id 保護**] をクリックします。
3. [ **Identity Protection-概要**] ブレードで、各レポートをクリックして、報告されているものを確認します。
4. [**通知**] の下で、[**リスクが検出された通知のユーザー**] をクリックします。
5. [**リスクが検出されたユーザーのアラート**] ウィンドウで、[**中**] を選択します。
6. **メールが次のユーザーに送信さ**れる場合は、[**含める**] をクリックして、グローバル管理者アカウントが選択されているメンバーの一覧に含まれていることを確認します。
7. [**保存**] をクリックします。

[**保護**] の下にあるさまざまなポリシーをクリックして、それらを構成する方法を確認します。 ポリシーを作成してアクティブにした場合は、アクセスがブロックされている範囲を超えていないか、またはグローバル管理者であってもサインインできないことを確認してください。

テストと実験の詳細については、「[リスクイベントをシミュレート](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)する」を参照してください。

Azure AD Id 保護を運用環境に展開するための情報とリンクについては、Id フェーズの「[資格情報が侵害](identity-secure-user-sign-ins.md#identity-ident-prot)されないように保護する」の手順を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
