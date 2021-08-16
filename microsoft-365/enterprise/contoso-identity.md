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
ms.openlocfilehash: 47a9492f0924f777da12361b2c161ef9b5b0770d24d720ac927b02b44f369bc8
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899752"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso 社の ID

Microsoft は、クラウド サービス全体でサービスとしての ID (IDaaS) を提供Azure Active Directory (Azure AD)。 エンタープライズ向Microsoft 365を採用するには、Contoso IDaaS ソリューションでオンプレミス ID プロバイダーを使用し、既存の信頼できるサード パーティ ID プロバイダーとのフェデレーション認証を含める必要がありました。

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory ドメイン サービス フォレスト

Contoso は、7 つのサブドメインを持つ contoso com の単一の Active Directory ドメイン サービス (DS) フォレスト (AD DS) を使用します。1 つは世界の各地域に \. 1 つです。 本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。

地域ハブを含む世界の各地域の地域ドメインを持つ Contoso フォレストを次に示します。

![Contoso 社の世界中のフォレストとドメイン](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso 社は、contoso com フォレスト内のアカウントとグループを、そのワークロードとサービスの認証と承認Microsoft 365 \. 決定しました。

## <a name="the-contoso-federated-authentication-infrastructure"></a>Contoso フェデレーション認証インフラストラクチャ

Contoso 社では次のことが可能です。

- お客様は、Microsoft、Facebook、または Google メール アカウントを使用して、会社のパブリック Web サイトにサインインします。
- ベンダーとパートナーは、LinkedIn、Salesforce、または Google メール アカウントを使用して、会社のパートナーエクストラネットにサインインします。

パブリック Web サイト、パートナー エクストラネット、および Active Directory フェデレーション サービス (FS) サーバーのセットを含む Contoso DMZ をADします。 DMZ は、顧客、パートナー、およびインターネット サービスを含むインターネットに接続されています。

![顧客とパートナーのフェデレーション認証に対する Contoso のサポート](../media/contoso-identity/contoso-identity-fig2.png)
 
AD FS サーバーを使用すると、パブリック Web サイトにアクセスするための ID プロバイダーによる顧客資格情報の認証と、パートナーエクストラネットへのアクセスのためのパートナー資格情報の認証が容易になります。

Contoso 社は、このインフラストラクチャを維持し、顧客とパートナー認証に使用することを決定しました。 Contoso 社の ID アーキテクトは、このインフラストラクチャから Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) および [B2C](/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査しています。

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID

Contoso 社は、オンプレミスの DS フォレストを使用ADクラウド リソースの認証にMicrosoft 365しました。 パスワード ハッシュ同期 (PHS) の使用を決定しました。

PHS は、オンプレミスの AD DS フォレストを、エンタープライズ サブスクリプションの Microsoft 365 の Azure AD テナントと同期し、ユーザー アカウントとグループ アカウント、およびハッシュ化されたバージョンのユーザー アカウント パスワードをコピーします。

ディレクトリ同期を実行するために、Contoso 社は Azure AD Connectツールをパリデータセンターのサーバーに展開しました。

Azure を実行しているサーバー AD Connect Contoso AD DS フォレストをポーリングし、それらの変更を Azure AD テナントと同期します。

![Contoso PHS ディレクトリ同期インフラストラクチャ](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>ID およびデバイス アクセスの条件付きアクセス ポリシー

Contosoは、3 つの保護レベルに対して Azure AD と Intune の[条件付きアクセス ポリシー](../security/office-365-security/identity-access-policies.md)セットを作成しました。

- *ベースライン* 保護は、すべてのユーザー アカウントに適用されます。
- *機密性の* 高い保護は、上級リーダーシップとエグゼクティブ スタッフに適用されます。
- *規制の厳* しい保護は、規制の厳しいデータにアクセスできる財務部門、法務部門、研究部門の特定のユーザーに適用されます。

Contoso ID ポリシーとデバイス条件付きアクセス ポリシーのセットを次に示します。

![Contoso 社の ID およびデバイスの条件付きアクセス ポリシー](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>次の手順

Contoso 社が組織全体にMicrosoft Endpoint Configuration Managerインフラストラクチャを使用して現在の[Windows 10 Enterpriseを維持](contoso-win10.md)する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 の ID ロードマップ](identity-roadmap-microsoft-365.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)