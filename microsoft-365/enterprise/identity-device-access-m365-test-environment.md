---
title: Microsoft 365 テスト環境の ID およびデバイス
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 9195f532222511fc9dce474617ed52916d8e382a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073597"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="63754-103">Microsoft 365 テスト環境の ID およびデバイス</span><span class="sxs-lookup"><span data-stu-id="63754-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="63754-104">[ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)は、機能と条件付きアクセス ポリシーのセットで、Office 365 および Microsoft 365 Enterprise の Enterprise Mobility + Security (EMS) などを含めた、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="63754-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="63754-105">これらのポリシーが正しく設定されたテスト環境を作成するには:</span><span class="sxs-lookup"><span data-stu-id="63754-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="63754-106">ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="63754-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="63754-107">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="63754-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="63754-108">パスワード ハッシュの同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="63754-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="63754-109">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="63754-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="63754-110">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、ID とデバイスの前提条件とテスト保護に構築するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="63754-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="63754-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="63754-111">See also</span></span>

[<span data-ttu-id="63754-112">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="63754-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="63754-113">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="63754-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="63754-114">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="63754-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="63754-115">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="63754-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="63754-116">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="63754-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
