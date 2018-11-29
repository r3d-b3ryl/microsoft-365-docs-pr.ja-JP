---
title: Microsoft 365 Enterprise のテスト ラボ ガイド
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 以下のテスト ラボ ガイドを使用して、Microsoft 365 Enterprise のデモ、概念実証、開発/テスト環境を設定します。
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869499"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a>Microsoft 365 Enterprise のテスト ラボ ガイド

テスト ラボ ガイド (TLG) を活用すれば、Microsoft 製品の概要をいち早く把握することができます。テスト ラボ ガイドは、簡単ではあるものの代表的なテスト環境を構成する方法を説明しています。これらの環境は、試用期間または有料サブスクリプションの期間内に、デモ、カスタマイズ、概念の複合的な証拠の作成に使用できます。 

TLG はモジュラーとして機能するように設計されています。TLG は、テストしてみたい内容やそのテストに必要な要件にできるだけ一致するように、複数の構成を行える仕組みになっています。この実地体験型ガイドにより、新しい製品やシナリオの展開要件を理解し、運用環境でホストする計画を立てやすくなります。

また、TLG を使用すると、アプリケーションの開発およびテスト用の典型的な環境を作成することもできます。これは、開発/テスト環境とも呼ばれます。
  
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="base-configuration"></a>基本構成

最初に、Office 365 E5、Enterprise Mobility + Security (EMS) E5、Windows 10 Enterprise を含む [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) のテスト環境を作成します。基本構成は 2 種類作成できます:

- オンプレミスのコンポーネントを含まないクラウド専用の環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)を使用します。

- Windows Server Active Directory (AD) ドメインなどのオンプレミスのコンポーネントを使用するハイブリッド クラウド環境で、Microsoft 365 Enterprise の機能を構成しデモンストレーションする場合は、[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)を使用します。
    
## <a name="identity"></a>ID

ID に関連する機能や能力のデモンストレーションは、以下を参照してください:

- [パスワード ハッシュ同期](password-hash-sync-m365-ent-test-environment.md)
  
   Windows Server AD ドメイン コントローラーからのパスワード ハッシュによるディレクトリ同期を有効にしてテストします。

- [パススルー認証](pass-through-auth-m365-ent-test-environment.md)
  
   Windows Server AD ドメイン コントローラーへのパススルー認証を有効にしてテストします。

- [Azure AD シームレス シングル サインオン](single-sign-on-m365-ent-test-environment.md)
  
   Azure AD シームレス シングル サインオン (SSO) をWindows Server AD ドメイン コントローラーで有効にし、テストします。

- [多要素認証](multi-factor-authentication-microsoft-365-test-environment.md)
  
   特定のユーザー アカウントで、スマートフォンによる多要素認証を有効にしてテストします。

- [全体管理者アカウントを保護する](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Office 365 Cloud App Security と条件付きアクセス ポリシーを使用して、全体管理者アカウントをロックします。

- [パスワードのリセット](password-reset-m365-ent-test-environment.md)

   セルフサービスによるパスワードのリセット (SSPR) を使用して、パスワードをリセットします。

- [ライセンスとグループ メンバーシップの自動管理](automate-licenses-group-membership-microsoft-365-test-environment.md)

   自動ライセンス認証と動的なグループ メンバーシップを使用すると、新しいアカウントの管理をこれまでよりも簡単に行えます。

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   現在のユーザー アカウントの脆弱性を確認します。

## <a name="mobile-device-management"></a>モバイル デバイス管理

モバイル デバイス管理に関連する機能や能力のデモンストレーションは、以下を参照してください。

- [MAM ポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   iOS および Android デバイスのユーザー グループとモバイル アプリケーション管理 (MAM) のポリシーを作成します。
    
- [iOS および Android デバイスの登録](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   iOS または Android デバイスを登録し、それらをリモートで管理します。


## <a name="information-protection"></a>情報保護

情報保護に関連する機能や能力のデモンストレーションは、以下を参照してください。

- [Office 365 のセキュリティ強化](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   強化された Office 365 セキュリティの設定を構成し、組み込みのセキュリティ ツールを調査します。
  
- [データ分類](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Office 365 ラベルを構成し、SharePoint Online チーム サイトのドキュメントに適用します。
    
- [Microsoft 365 Enterprise テスト環境の特権アクセスの管理](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Office 365 組織の昇格されたタスクと特権タスクへの Just-In-Time アクセスを可能にするため、特権アクセス管理を構成します。

## <a name="see-also"></a>関連項目

[クラウド導入のテスト ラボ ガイドを使用して Microsoft Cloud を体験する](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[One Microsoft Cloud テスト ラボ ガイド一式](http://aka.ms/catlgstack)
