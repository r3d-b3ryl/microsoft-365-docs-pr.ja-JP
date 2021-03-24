---
title: Microsoft 365 テスト環境の ID およびデバイス
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: e90c27edbf4ad5a78c337bf2488956ce82a1ec3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051320"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c39a1-103">Microsoft 365 テスト環境の ID およびデバイス</span><span class="sxs-lookup"><span data-stu-id="c39a1-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c39a1-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境の Microsoft 365 でのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="c39a1-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c39a1-105">[ID およびデバイス アクセス](../security/defender-365-security/microsoft-365-policies-configurations.md) 構成は、Azure Active Directory (Azure Active Directory ) と統合されているすべてのサービスへのアクセスを保護するための一連の推奨構成と条件付きアクセス ポリシー AD。</span><span class="sxs-lookup"><span data-stu-id="c39a1-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="c39a1-106">共通の ID とデバイス アクセス構成が設定されたテスト環境を作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c39a1-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="c39a1-107">ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="c39a1-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="c39a1-108">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="c39a1-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="c39a1-109">パスワード ハッシュ同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="c39a1-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="c39a1-110">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="c39a1-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="c39a1-111">共通 [ID およびデバイス アクセス](../security/defender-365-security/identity-access-policies.md) ポリシーを使用して、テスト環境用に構成された前提条件に基いて構築されるポリシーを構成し、ID とデバイスの保護を確認して検証します。</span><span class="sxs-lookup"><span data-stu-id="c39a1-111">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c39a1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c39a1-112">See also</span></span>

[<span data-ttu-id="c39a1-113">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="c39a1-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="c39a1-114">ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="c39a1-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c39a1-115">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="c39a1-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c39a1-116">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="c39a1-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c39a1-117">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="c39a1-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
