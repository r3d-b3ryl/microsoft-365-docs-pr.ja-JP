---
title: Contoso 社の ID
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754643"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso 社の ID

Microsoft は、Azure Active Directory (Azure AD) を通じて、クラウド製品全体で Id (IDaaS) をサービスとして提供します。 企業向けの Microsoft 365 を採用するために、Contoso IDaaS ソリューションは社内 id プロバイダーを使用し、信頼できる既存のサードパーティ id プロバイダーとのフェデレーション認証を含める必要がありました。

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory ドメインサービスフォレスト

Contoso 社では \. 、世界の地域ごとに1つずつ、7つのサブドメインを持つ contoso com に対して1つの Active Directory ドメインサービス (AD DS) フォレストを使用しています。 本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。

地域ハブを含む世界のさまざまな部分については、地域ドメインを含む Contoso フォレストを参照してください。

![Contoso 社の世界中のフォレストとドメイン](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso 社は、 \. Microsoft 365 のワークロードおよびサービスの認証と承認のために、contoso com フォレスト内のアカウントとグループを使用することを決定しました。

## <a name="the-contoso-federated-authentication-infrastructure"></a>Contoso 社のフェデレーション認証インフラストラクチャ

Contoso 社では次のことが可能です。

- お客様は、Microsoft、Facebook、または Google のメールアカウントを使用して、会社のパブリック web サイトにサインインします。
- ベンダーおよびパートナーは、自分の LinkedIn、Salesforce、または Google のメールアカウントを使用して、会社のパートナーエクストラネットにサインインします。

ここでは、パブリック web サイト、パートナーエクストラネット、および Active Directory フェデレーションサービス (AD FS) サーバーのセットを含む Contoso DMZ を示します。DMZ は、顧客、パートナー、インターネットサービスを含むインターネットに接続されています。

![顧客とパートナーのフェデレーション認証の Contoso サポート](../media/contoso-identity/contoso-identity-fig2.png)
 
DMZ の AD FS サーバーは、パブリック web サイトにアクセスし、パートナーエクストラネットにアクセスするためのパートナー資格情報を提供するために、id プロバイダーによる顧客資格情報の認証を容易にします。

Contoso 社は、このインフラストラクチャを維持し、顧客とパートナーの認証に専念することを決定しました。Contoso 社の id 設計者は、このインフラストラクチャから Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) および [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) ソリューションへの変換について調査しています。

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID

Contoso 社は、オンプレミスの AD DS フォレストを使用して、Microsoft 365 cloud resources への認証を希望しています。 パスワードハッシュ同期 (PHS) の使用を決定しました。

PHS は、オンプレミスの AD DS フォレストを、Microsoft 365 for enterprise サブスクリプションの Azure AD テナントと同期し、ユーザーアカウントとグループアカウント、およびハッシュされたバージョンのユーザーアカウントパスワードをコピーします。

ディレクトリ同期を実行するために、Contoso 社では、パリデータセンター内のサーバーに Azure AD Connect ツールを展開しました。

Azure ad Connect を実行しているサーバーは、変更については Contoso AD DS フォレストをポーリングしてから、それらの変更を Azure AD テナントと同期します。

![Contoso PHS ディレクトリ同期インフラストラクチャ](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>ID およびデバイス アクセスの条件付きアクセス ポリシー

Contosoは、3 つの保護レベルに対して Azure AD と Intune の[条件付きアクセス ポリシー](identity-access-policies.md)セットを作成しました。

- *ベースライン* の保護は、すべてのユーザーアカウントに適用されます。
- *重要* な保護は、シニアリーダーシップおよび経営スタッフに適用されます。
- *高度* な規制による保護は、厳しく規制されたデータにアクセスできる財務、法律、研究部門の特定のユーザーに適用されます。

Contoso identity とデバイスの条件付きアクセスポリシーの結果セットを次に示します。

![Contoso 社の ID およびデバイスの条件付きアクセス ポリシー](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>次の手順

Contoso 社が Microsoft エンドポイント構成マネージャーインフラストラクチャを使用して、組織全体に [現在の Windows 10 Enterprise を展開し、維持](contoso-win10.md) する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 の ID ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
