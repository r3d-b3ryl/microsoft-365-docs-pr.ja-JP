---
title: Azure ADテスト環境向け id Protection Microsoft 365 Id Protection
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
  - TLG
  - Ent_TLGs
description: Id Protection Azure AD構成し、エンタープライズ テスト環境に合Microsoft 365アカウントを分析します。
---

# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure ADテスト環境向け id Protection Microsoft 365 Id Protection

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

Azure Active Directory (Azure AD) ID 保護を使用して、組織の ID に影響を与える潜在的な脆弱性を検出し、自動応答を構成し、インシデントを調査できます。 この記事では、Id Protection を使用してAzure AD環境アカウントの分析を表示する方法について説明します。

エンタープライズ テスト環境Azure AD ID 保護をMicrosoft 365には、次の 2 つのフェーズがあります。

- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: ID 保護Azure AD使用する](#phase-2-use-azure-ad-identity-protection)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小要件を使用してAzure AD Id Protection のみをテストする場合は、「Lightweight 基本構成」の手順[に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで id Protection Azure ADする場合は、「パススルー認証」[の手順に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> Id Protection Azure ADテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここでは、一般的な組織を表す環境で id Protection をテストし、Azure ADを試みるオプションとして提供されています。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>フェーズ 2: ID 保護Azure AD使用する

1. ブラウザーのプライベート インスタンスを開き、エンタープライズ テスト環境のグローバル管理者アカウントを使用して Azure portal [https://portal.azure.com](https://portal.azure.com) Microsoft 365サインインします。
2. Azure portal で、検索ボックスに **「ID 保護**」と入力し、[id Protection] Azure AD **選択します**。
3. [Identity **Protection - Overview] ブレードで** 、各レポートを選択して、レポートの概要を確認します。
4. [ **通知] で**、[ **危険にさらされているユーザーが検出されたアラート] を選択します**。
5. [危険にさら **されているユーザーが検出された通知] ウィンドウで、[** 中] を **選択します**。
6. [ **メールが次のユーザー** に送信される] で、[含める] **を選択し** 、グローバル管理者アカウントが選択したメンバーの一覧に含まれているか確認します。
7. **[保存]** を選択します。

[ **保護] で**、さまざまなポリシーを選択して、それらを構成する方法を確認します。 ポリシーを作成してアクティブ化する場合は、すべてのユーザーのアクセスがブロックされていないか、サインインできない可能性があります。 これを防ぐには、グローバル管理者などの特定のユーザー アカウントを除外します。

テストと実験の詳細については、「 [リスク イベントのシミュレート」を参照してください](/azure/active-directory/active-directory-identityprotection-playbook)。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID の展開](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)