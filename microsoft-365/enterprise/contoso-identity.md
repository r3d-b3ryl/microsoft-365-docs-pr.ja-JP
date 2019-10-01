---
title: Contoso 社の ID
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: f40be4ad7d93781ff2ac980228ae5271a8e844c4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982128"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso 社の ID

**概要:** Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。

Microsoftは、Azure Active Directory（Azure AD）を使用して、自社のクラウド製品にIDaaS (Identity as a Service)を提供します。 Microsoft 365 EnterpriseEnterprise導入のため、ContosoのIDaaSソリューションは、自社運用のIDプロバイダーを利用しながら、既存の信頼できるサードパーティのIDプロバイダーと連携した認証方法を一体化させる必要がありました。

## <a name="contosos-active-directory-domain-services-forest"></a>ContosoのActive Directoryドメイン　サービス フォレスト

Contosoは、contoso.comに1つのActive Directoryドメインサービス（AD DS）フォレストを使用し、7つのサブドメイン（世界中の各地域に1つ）を使用します。 本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。

図 1 では、地域ハブを含む世界各地の地域ドメインを持つ Contoso 社のフォレストを示しています。

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**図 1: Contoso 社の世界的なフォレストとドメイン**

Contosoは、contoso.comフォレストのアカウントとグループをMicrosoft 365の作業とサービスの認証・承認に使用したいと考えていました。

## <a name="contosos-federated-authentication-infrastructure"></a>Contoso 社のフェデレーション認証インフラストラクチャ

Contoso 社では次のことが可能です。

- 顧客は Microsoft、Facebook、または Google のメール アカウントを使用してパブリック Web サイトにサインインできます。
- ベンダーおよびパートナーは、LinkedIn、Salesforce、または Google のメール アカウントを使用してパートナー エクストラネットにサインインできます。

図 2 は、公開 Web サイト、パートナーのエクストラネット、および Active Directory フェデレーション サービス (AD FS) サーバーのセットを含む Contoso 社の DMZ を示しています。DMZ は、顧客、パートナー、およびインターネット サービスを含むインターネットに接続されています。

![](./media/contoso-identity/contoso-identity-fig2.png)

**図 2: Contoso 社の顧客とパートナーのフェデレーション認証のサポート**
 
DMZ の AD FS サーバーは、ID のプロバイダーが提供しパブリック Web サイトにアクセスするための顧客資格情報、およびパートナー エクストラネットにアクセスするためのパートナー資格情報の認証を容易にします。

Contoso 社は、このインフラストラクチャを維持し、顧客とパートナーの認証専用で使用することに決定しました。Contoso 社の ID 設計者は、このインフラストラクチャから Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) および [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査中です。

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID

Contosoは、自社運用のAD DSフォレストをMicrosoft 365クラウドリソースへの認証に活用したいと考えていました。 ここから、パスワードハッシュ同期（PHS）が誕生しました。

PHSは、自社運用のAD DSフォレストをMicrosoft 365 Enterpriseの登録のあるAzure ADテナントと同期し、ユーザーアカウントとグループアカウント、およびハッシュ化されたバージョンのユーザーアカウントパスワードをコピーします。 

継続的なディレクトリ同期を実行するために、ContosoはAzure AD 連携ツールをパリのデータセンター内のサーバーに展開しました。 図3は、Azure AD Connectを実行しているサーバーがContoso AD DSフォレストに変更をポーリングし、それらの変更をAzure ADテナントと同期することを示しています。

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**図3：ContosoのPHSディレクトリ同期インフラストラクチャ**


## <a name="conditional-access-policies-for-identity-and-device-access"></a>IDおよび機器のアクセスに対する条件付きアクセスポリシー

Contosoは、3つの保護レベルに対して、Azure ADとIntuneの[条件付きアクセスポリシー](identity-access-policies.md)を作成しました。

- **ベースライン**保護はすべてのユーザーアカウントに適用されます。
- **選定**保護が上級幹部および幹部職員に適用されます。
- **高規制**保護は、高度に規制されたデータにアクセスできる財務、法務、および研究部門の特定のユーザーに適用されます。

図4は、この結果得られるIDと機器の条件付きアクセスポリシーのセットを示しています。

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**図4：ContosoのIDと機器の条件付きアクセスポリシー**

## <a name="next-step"></a>次の手順

Contoso 社が System Center Configuration Manager インフラストラクチャを利用して、現在の Windows 10 Enterprise を組織全体に展開し、維持する方法について[説明](contoso-win10.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の ID](identity-infrastructure.md)

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
