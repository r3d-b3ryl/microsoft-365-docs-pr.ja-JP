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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境の ID およびデバイス

[ID とデバイスのアクセス構成](microsoft-365-policies-configurations.md)は、機能と条件付きアクセス ポリシーのセットで、Office 365 および Microsoft 365 Enterprise の Enterprise Mobility + Security (EMS) などを含めた、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護します。

これらのポリシーが正しく設定されたテスト環境を作成するには:

1. ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。

  - [クラウドのみ](cloud-only-prereqs-m365-test-environment.md)
  - [パスワード ハッシュの同期 (PHS)](phs-prereqs-m365-test-environment.md)
  - [パススルー認証 (PTA)](pta-prereqs-m365-test-environment.md)

2. [共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)を使用して、ID とデバイスの前提条件とテスト保護に構築するポリシーを構成します。

## <a name="see-also"></a>関連項目

[その他の ID のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md#identity)

[フェーズ 2: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
