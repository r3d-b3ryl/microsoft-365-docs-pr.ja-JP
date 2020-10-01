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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境の ID およびデバイス

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

[Id およびデバイスアクセスの構成](microsoft-365-policies-configurations.md) は、Azure Active Directory (azure AD) と統合されたすべてのサービスへのアクセスを保護する一連の機能と条件付きアクセスポリシーです。

共通の id とデバイスのアクセス構成を備えたテスト環境を作成するには、次のようにします。

1. ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。

  - [クラウドのみ](cloud-only-prereqs-m365-test-environment.md)
  - [パスワードハッシュの同期 (PHS)](phs-prereqs-m365-test-environment.md)
  - [パススルー認証 (PTA)](pta-prereqs-m365-test-environment.md)

2. [共通 id およびデバイスアクセスポリシー](identity-access-policies.md)を使用して、テスト環境用に構成された前提条件に基づいて構築されたポリシーを構成し、id とデバイスの保護を調べて確認します。

## <a name="see-also"></a>関連項目

[その他の ID のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md#identity)

[Identity ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
