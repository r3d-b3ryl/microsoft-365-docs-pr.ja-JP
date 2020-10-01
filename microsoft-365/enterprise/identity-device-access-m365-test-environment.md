---
title: Microsoft 365 テスト環境の ID およびデバイス
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327809"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6eb61-103">Microsoft 365 テスト環境の ID およびデバイス</span><span class="sxs-lookup"><span data-stu-id="6eb61-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6eb61-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="6eb61-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6eb61-105">[Id およびデバイスアクセスの構成](microsoft-365-policies-configurations.md) は、Azure Active Directory (azure AD) と統合されたすべてのサービスへのアクセスを保護する一連の機能と条件付きアクセスポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6eb61-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="6eb61-106">共通の id とデバイスのアクセス構成を備えたテスト環境を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6eb61-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="6eb61-107">ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="6eb61-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="6eb61-108">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="6eb61-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="6eb61-109">パスワードハッシュの同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="6eb61-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="6eb61-110">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="6eb61-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="6eb61-111">[共通 id およびデバイスアクセスポリシー](identity-access-policies.md)を使用して、テスト環境用に構成された前提条件に基づいて構築されたポリシーを構成し、id とデバイスの保護を調べて確認します。</span><span class="sxs-lookup"><span data-stu-id="6eb61-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="6eb61-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eb61-112">See also</span></span>

[<span data-ttu-id="6eb61-113">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="6eb61-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="6eb61-114">Identity ロードマップ</span><span class="sxs-lookup"><span data-stu-id="6eb61-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="6eb61-115">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="6eb61-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6eb61-116">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="6eb61-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6eb61-117">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6eb61-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
