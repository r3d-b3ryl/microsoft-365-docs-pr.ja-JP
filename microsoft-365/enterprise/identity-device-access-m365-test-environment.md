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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: e43483afc9e17de9582b2998867b53cfff7d8492
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601004"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="98488-103">Microsoft 365 テスト環境の ID およびデバイス</span><span class="sxs-lookup"><span data-stu-id="98488-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="98488-104">*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="98488-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="98488-105">[ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)は、機能と条件付きアクセス ポリシーのセットで、Office 365 および Microsoft 365 Enterprise の Microsoft Intune などを含めた、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="98488-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="98488-106">これらのポリシーが正しく設定されたテスト環境を作成するには:</span><span class="sxs-lookup"><span data-stu-id="98488-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="98488-107">ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="98488-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="98488-108">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="98488-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="98488-109">パスワード ハッシュの同期 (PHS)</span><span class="sxs-lookup"><span data-stu-id="98488-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="98488-110">パススルー認証 (PTA)</span><span class="sxs-lookup"><span data-stu-id="98488-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="98488-111">[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、ID とデバイスの前提条件とテスト保護に構築するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="98488-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="98488-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="98488-112">See also</span></span>

[<span data-ttu-id="98488-113">その他の ID のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="98488-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="98488-114">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="98488-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="98488-115">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="98488-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="98488-116">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="98488-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="98488-117">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="98488-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
