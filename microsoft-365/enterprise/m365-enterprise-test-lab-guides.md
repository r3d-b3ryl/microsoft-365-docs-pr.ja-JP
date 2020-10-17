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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 以下のテスト ラボ ガイドを使用して、Microsoft 365 Enterprise 向けのデモ、概念実証、または開発/テスト環境を設定します。
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487472"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Microsoft 365 Enterprise のテスト ラボ ガイド

*これは、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。

TLGs はモジュール化するように設計されています。互いに連携して、学習またはテスト構成のニーズにより近い複数の構成を作成します。「自分で作成したものと it が正常に機能する」という実践的な体験により、運用環境へのホスティングをより適切に計画できるようになります。

また、TLGs を使用して、開発/テストアプリケーション (開発/テスト環境とも呼ばれる) を開発およびテストするための典型的な環境を作成することもできます。
  
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、次の図を展開するか、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」にアクセスしてください。

[![The Microsoft 365 Enterprise のテスト ラボ ガイド スタック](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>基本構成

最初に、 [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)のテスト環境を作成します。2つの異なる種類の基本構成を作成できます。

- [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md) -エンタープライズの機能に対して、オンプレミスのコンポーネントを含まないクラウドのみの環境で、Microsoft 365 を構成してデモを行う場合に使用します。

- シミュレートされた[エンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)-エンタープライズ機能に対して Microsoft 365 を構成してデモンストレーションする場合は、Active Directory ドメインサービス (AD DS) ドメインなどのオンプレミスのコンポーネントを使用するハイブリッドクラウド環境で、これを使用します。

試用版または運用テスト環境に Microsoft 365 E5 ライセンスを追加することなく、Office 365 E5 のテスト環境を作成することもできます。
    
## <a name="identity"></a>ID

ID に関連する機能や能力のデモンストレーションは、以下を参照してください:

- [パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)
  
   AD DS ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。

- [パススルー認証](pass-through-auth-m365-ent-test-environment.md)
  
   AD DS ドメイン コントローラーへのパススルー認証を有効にしてテストします。

- [フェデレーション認証](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   AD DS ドメイン コントローラーへのフェデレーション認証を有効にしてテストします。

- [Azure AD シームレス シングル サインオン](single-sign-on-m365-ent-test-environment.md)
  
   AD DS ドメインコントローラーを使用して Azure AD のシームレスなシングルサインオン (シームレスな SSO) を有効にしてテストします。

- [多要素認証](multi-factor-authentication-microsoft-365-test-environment.md)
  
   特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。

- [全体管理者アカウントを保護する](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   条件付きアクセス ポリシーを使用してグローバル管理者アカウントをロックする。

- [パスワード ライトバック](password-writeback-m365-ent-test-environment.md)

   パスワードの書き戻しは、Azure AD から AD DS ユーザー アカウントのパスワードを変更する場合に使用します。

- [パスワードのリセット](password-reset-m365-ent-test-environment.md)

   セルフサービスによるパスワードのリセットを使用して、パスワードをリセットします。

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
