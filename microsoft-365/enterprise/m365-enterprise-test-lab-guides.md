---
title: Microsoft 365 Enterprise のテスト ラボ ガイド
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 以下のテスト ラボ ガイドを使用して、Microsoft 365 Enterprise 向けのデモ、概念実証、または開発/テスト環境を設定します。
ms.openlocfilehash: 582068e84d82bfa681d1e1e64234698544ce3b9d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631599"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Microsoft 365 Enterprise のテスト ラボ ガイド

*これは、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。 

TLG はモジュラーとして機能するように設計されています。TLG は、テストしてみたい内容やそのテストに必要な要件にできるだけ一致するように、複数の構成を行える仕組みになっています。この実地体験型ガイドにより、新しい製品やシナリオの展開要件を理解し、運用環境でホストする計画を立てやすくなります。

また、TLG を使用すると、アプリケーションの開発およびテスト用の典型的な環境を作成することもできます。これは、開発/テスト環境とも呼ばれます。
  
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。

[![The Microsoft 365 Enterprise のテスト ラボ ガイド スタック](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>基本構成

最初に、Office 365 E5、Enterprise Mobility + Security (EMS) E5、および Windows 10 Enterprise を含む [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) のテスト環境を作成します。2 種類の基本構成を作成できます:

- オンプレミスのコンポーネントを含まないクラウド専用の環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合には、[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)を使用します。

- Active Directory Domain Services (AD DS) ドメインなどのオンプレミスのコンポーネントを使用するハイブリッド クラウド環境で Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合には、[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)を使用します。

試用版または運用テスト環境に Microsoft 365 E5 ライセンスを追加することなく、Office 365 E5 のテスト環境を作成することもできます。
    
## <a name="identity"></a>ID

ID に関連する機能や能力のデモンストレーションは、以下を参照してください:

- [パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)
  
   AD DS ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。

- [パススルー認証](pass-through-auth-m365-ent-test-environment.md)
  
   AD DS ドメイン コントローラーへのパススルー認証を有効にしてテストします。

- [フェデレーション認証](federated-identity-for-your-office-365-dev-test-environment.md)
  
   AD DS ドメイン コントローラーへのフェデレーション認証を有効にしてテストします。

- [Azure AD シームレス シングル サインオン](single-sign-on-m365-ent-test-environment.md)
  
   Azure AD シームレス シングル サインオン (SSO) を AD DS ドメイン コントローラーで有効にしてテストします。

- [多要素認証](multi-factor-authentication-microsoft-365-test-environment.md)
  
   特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。

- [全体管理者アカウントを保護する](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   条件付きアクセス ポリシーを使用してグローバル管理者アカウントをロックする。

- [パスワード ライトバック](password-writeback-m365-ent-test-environment.md)

   パスワードの書き戻しは、Azure AD から AD DS ユーザー アカウントのパスワードを変更する場合に使用します。

- [パスワードのリセット](password-reset-m365-ent-test-environment.md)

   セルフサービスによるパスワードのリセット (SSPR) を使用して、パスワードをリセットします。

- [ライセンスとグループ メンバーシップの自動管理](automate-licenses-group-membership-microsoft-365-test-environment.md)

   自動ライセンス認証と動的なグループ メンバーシップを使用すると、新しいアカウントの管理をこれまでよりも簡単に行えます。

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   現在のユーザー アカウントの脆弱性を確認します。

- [ID と デバイス アクセス](identity-device-access-m365-test-environment.md)

   お勧めする ID、デバイス アクセスの構成、および条件付きアクセス ポリシーをテストするための環境を作成します。


## <a name="mobile-device-management"></a>モバイル デバイス管理

モバイル デバイス管理に関連する機能や能力のデモンストレーションは、以下を参照してください。

- [デバイス コンプライアンス ポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Windows 10 デバイスのユーザー グループおよびデバイス コンプライアンス ポリシーを作成します。
    
- [iOS および Android デバイスの登録](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   iOS または Android デバイスを登録し、それらをリモートで管理します。


## <a name="information-protection"></a>情報保護

情報保護に関連する機能や能力のデモンストレーションは、以下を参照してください。

- [強化された Microsoft 365 のセキュリティ](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   強化された Microsoft 365 セキュリティの設定を構成し、組み込みのセキュリティ ツールを調査します。
  
- [データ分類](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   ラベルを構成し、SharePoint Online チーム サイトのドキュメントに適用します。
    
- [特権アクセスの管理](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   組織の昇格されたタスクと特権タスクへの Just-In-Time アクセスを可能にするため、特権アクセス管理を構成します。


