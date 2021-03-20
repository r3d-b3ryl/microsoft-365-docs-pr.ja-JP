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
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907470"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境の ID およびデバイス

*このテスト ラボ ガイドは、エンタープライズ テスト環境の Microsoft 365 でのみ使用できます。*

[ID およびデバイス アクセス](../security/office-365-security/microsoft-365-policies-configurations.md) 構成は、Azure Active Directory (Azure Active Directory ) と統合されているすべてのサービスへのアクセスを保護するための一連の推奨構成と条件付きアクセス ポリシー AD。

共通の ID とデバイス アクセス構成が設定されたテスト環境を作成するには、次の方法を実行します。

1. ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。

  - [クラウドのみ](cloud-only-prereqs-m365-test-environment.md)
  - [パスワード ハッシュ同期 (PHS)](phs-prereqs-m365-test-environment.md)
  - [パススルー認証 (PTA)](pta-prereqs-m365-test-environment.md)

2. 共通 [ID およびデバイス アクセス](../security/office-365-security/identity-access-policies.md) ポリシーを使用して、テスト環境用に構成された前提条件に基いて構築されるポリシーを構成し、ID とデバイスの保護を確認して検証します。

## <a name="see-also"></a>関連項目

[その他の ID のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md#identity)

[ID ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)