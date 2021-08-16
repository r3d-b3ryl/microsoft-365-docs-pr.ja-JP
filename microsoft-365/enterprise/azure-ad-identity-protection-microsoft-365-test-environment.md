---
title: エンタープライズ AD環境向け Azure Microsoft 365 ID 保護
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
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
description: Azure AD Id Protection を構成し、エンタープライズ テスト環境用にMicrosoft 365アカウントを分析します。
ms.openlocfilehash: 68b77803b4a2955efe58f742e27cb4fa6cfbb58c
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356314"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ AD環境向け Azure Microsoft 365 ID 保護

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

Azure Active Directory (Azure AD) IDENTITY Protection を使用して、組織の ID に影響を与える潜在的な脆弱性を検出し、自動応答を構成し、インシデントを調査できます。 この記事では、Azure AD Id Protection を使用してテスト環境アカウントの分析を表示する方法について説明します。

エンタープライズ テスト環境ADで Azure id Protection をMicrosoft 365には、次の 2 つのフェーズがあります。

- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: Azure AD ID 保護を使用する](#phase-2-use-azure-ad-identity-protection)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小要件を使用して Azure AD Id Protection のみを軽量な方法でテストする場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで Azure AD ID 保護をテストする場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> Azure AD Identity Protection のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここではオプションとして提供され、Azure AD Id Protection をテストし、一般的な組織を表す環境でテストできます。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>フェーズ 2: Azure AD ID 保護を使用する

1. ブラウザーのプライベート インスタンスを開き、エンタープライズ テスト環境のグローバル管理者アカウントを使用して Azure portal [https://portal.azure.com](https://portal.azure.com) Microsoft 365サインインします。
2. Azure portal で、検索ボックスに **「ID 保護** 」と入力し、[Azure AD **Id Protection] を選択します**。
3. [Identity **Protection - Overview] ブレードで** 、各レポートを選択して、レポートの概要を確認します。
4. [通知 **] で**、[ **危険にさらされているユーザーが検出されたアラート] を選択します**。
5. [危険にさら **されているユーザーが検出された通知] ウィンドウで、[** 中] を **選択します**。
6. [**メールが次のユーザー** に送信される]で、[含める] を選択し、グローバル管理者アカウントが選択したメンバーの一覧に含まれているか確認します。
7. **[保存]** を選択します。

[ **保護] で**、さまざまなポリシーを選択して、それらを構成する方法を確認します。 ポリシーを作成してアクティブ化する場合は、すべてのユーザーのアクセスがブロックされていないか、サインインできない可能性があります。 これを防ぐには、グローバル管理者などの特定のユーザー アカウントを除外します。

テストと実験の詳細については、「リスク イベント [のシミュレート」を参照してください](/azure/active-directory/active-directory-identityprotection-playbook)。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)