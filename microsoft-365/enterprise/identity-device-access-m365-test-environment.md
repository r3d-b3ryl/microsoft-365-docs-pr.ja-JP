---
title: Microsoft 365 テスト環境の ID およびデバイス
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID とデバイスのアクセスをテストするための Microsoft 365 環境を作成します。
ms.openlocfilehash: 09c7bf9ecb6aaadc89cedfd881e66a5fd19f28d7
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091217"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境の ID およびデバイス

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

[ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md)は、Azure Active Directory (Azure AD) と統合されているすべてのサービスへのアクセスを保護するための推奨される構成と条件付きアクセス ポリシーのセットです。

共通の ID とデバイス アクセスの構成が配置されているテスト環境を作成するには、次の手順を実行します。

1. ユーザーが選択した ID モデルおよび認証方法を基に、前提条件となる ID およびセキュリティ機能を備えたテスト環境を構成します。

  - [クラウドのみ](cloud-only-prereqs-m365-test-environment.md)
  - [パスワード ハッシュ同期 (PHS)](phs-prereqs-m365-test-environment.md)
  - [パススルー認証 (PTA)](pta-prereqs-m365-test-environment.md)

2. [共通 ID ポリシーとデバイス アクセス ポリシー](../security/office-365-security/identity-access-policies.md)を使用して、テスト環境用に構成された前提条件に基づいて構築されるポリシーを構成し、ID とデバイスの保護を調べて検証します。

## <a name="see-also"></a>関連項目

[その他の ID のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md#identity)

[ID をデプロイする](deploy-identity-solution-overview.md)

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
