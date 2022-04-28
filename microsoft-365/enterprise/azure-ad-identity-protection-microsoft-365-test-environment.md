---
title: エンタープライズ テスト環境のMicrosoft 365に対する id Protection のAzure AD
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection を構成し、エンタープライズ テスト環境のMicrosoft 365の現在のアカウントを分析します。
ms.openlocfilehash: 1f947f9b74b1909aa1e6451ec835a2ad78964f75
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65078759"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365に対する id Protection のAzure AD

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

Azure Active Directory (Azure AD) Identity Protection を使用して、組織の ID に影響を与える潜在的な脆弱性を検出し、自動応答を構成し、インシデントを調査できます。 この記事では、Azure AD Identity Protection を使用して、テスト環境アカウントの分析を表示する方法について説明します。

エンタープライズ テスト環境のMicrosoft 365で Azure AD Identity Protection を設定するには、次の 2 つのフェーズがあります。

- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: Azure AD Identity Protection を使用する](#phase-2-use-azure-ad-identity-protection)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を満たす軽量な方法で Azure AD Identity Protection のみをテストする場合は、[ライトウェイト 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)の手順に従います。
  
シミュレートされたエンタープライズで Azure AD Identity Protection をテストする場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> Identity Protection Azure ADテストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 ここでは、Identity Protection Azure ADテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>フェーズ 2: Azure AD Identity Protection を使用する

1. ブラウザーのプライベート インスタンスを開き、エンタープライズ テスト環境のMicrosoft 365[https://portal.azure.com](https://portal.azure.com)のグローバル管理者アカウントでAzure portalにサインインします。
2. Azure portalで、検索ボックスに **「ID 保護」** と入力し、**Azure AD Identity Protection** を選択します。
3. [ **Identity Protection - 概要** ] ブレードで、各レポートを選択して、レポートの内容を確認します。
4. [ **通知]** **で、[危険にさらされているユーザーが検出されたアラート**] を選択します。
5. [ **危険にさらされているユーザーが検出されたアラート** ] ウィンドウで、[ **中**] を選択します。
6. **次のユーザーに電子メールが送信される場合は**、[**含める**] を選択し、選択したメンバーの一覧にグローバル管理者アカウントが含まれていることを確認します。
7. **[保存]** を選択します。

[ **保護**] で、さまざまなポリシーを選択して、それらを構成する方法を確認します。 ポリシーを作成してアクティブ化する場合は、ポリシーがすべてのユーザーのアクセスをブロックしていないことを確認するか、サインインできない可能性があります。 これを防ぐには、グローバル管理者などの特定のユーザー アカウントを除外します。

その他のテストと実験については、「 [リスク イベントのシミュレート](/azure/active-directory/active-directory-identityprotection-playbook)」を参照してください。

## <a name="next-step"></a>次の手順

テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。

## <a name="see-also"></a>関連項目

[ID をデプロイする](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)