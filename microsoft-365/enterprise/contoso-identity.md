---
title: Contoso 社の ID
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: fc53ae761f26776c4bd632704505d2eafe8daa88
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094440"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso 社の ID

Microsoft は、Azure Active Directory (Azure AD) を通じて、クラウド オファリング全体でサービスとしての ID (IDaaS) を提供しています。 エンタープライズにMicrosoft 365を導入するには、Contoso IDaaS ソリューションでオンプレミス ID プロバイダーを使用し、既存の信頼できるサード パーティ ID プロバイダーとのフェデレーション認証を含める必要がありました。

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory Domain Services フォレスト

Contoso は、7 つのサブドメインを持つ contosocom\. に 1 つのActive Directory Domain Services (AD DS) フォレストを使用します。1 つは、世界のリージョンごとに 1 つです。 本社、地域ハブ オフィス、サテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。

地域ハブを含む世界のさまざまな部分のリージョン ドメインを持つ Contoso フォレストを次に示します。

:::image type="content" alt-text="Contoso の世界中のフォレストとドメイン。" source="../media/contoso-identity/contoso-identity-fig1.png" lightbox="../media/contoso-identity/contoso-identity-fig1.png":::
 
Contoso は、contosocom\. フォレスト内のアカウントとグループを、そのMicrosoft 365ワークロードとサービスの認証と承認に使用することにしました。

## <a name="the-contoso-federated-authentication-infrastructure"></a>Contoso フェデレーション認証インフラストラクチャ

Contoso 社では次のことが可能です。

- お客様は、Microsoft、Facebook、または Google Mail アカウントを使用して、会社のパブリック Web サイトにサインインします。
- ベンダーとパートナーは、LinkedIn、Salesforce、または Google Mail アカウントを使用して、会社のパートナー エクストラネットにサインインします。

パブリック Web サイト、パートナー エクストラネット、および一連のActive Directory フェデレーション サービス (AD FS) (AD FS) サーバーを含む Contoso DMZ を次に示します。 DMZ は、顧客、パートナー、インターネット サービスを含むインターネットに接続されます。

![顧客とパートナーに対するフェデレーション認証の Contoso サポート。](../media/contoso-identity/contoso-identity-fig2.png)
 
DMZ 内の AD FS サーバーは、パブリック Web サイトにアクセスするための ID プロバイダーによる顧客資格情報の認証を容易にし、パートナー エクストラネットにアクセスするためのパートナー資格情報を提供します。

Contoso は、このインフラストラクチャを維持し、顧客とパートナーの認証に専念することにしました。 Contoso 社の ID アーキテクトは、このインフラストラクチャから Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) および [B2C](/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査しています。

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>クラウドベース認証のためのパスワードハッシュ同期によるハイブリッドID

Contoso は、クラウド リソースをMicrosoft 365する認証にオンプレミスの AD DS フォレストを使用したいと考えていました。 パスワード ハッシュ同期 (PHS) を使用することにしました。

PHS は、オンプレミスの AD DS フォレストを、エンタープライズ サブスクリプションのMicrosoft 365のAzure AD テナントと同期し、ユーザー アカウントとグループ アカウントとハッシュバージョンのユーザー アカウント パスワードをコピーします。

ディレクトリ同期を行うために、Contoso はAzure AD Connect ツールをパリのデータセンター内のサーバーにデプロイしました。

Contoso AD DS フォレストに変更をポーリングAzure AD Connect実行しているサーバーを次に示します。その後、それらの変更をAzure AD テナントと同期します。

![Contoso PHS ディレクトリ同期インフラストラクチャ。](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-zero-trust-identity-and-device-access"></a>ゼロ トラスト ID とデバイス アクセスの条件付きアクセス ポリシー

Contosoは、3 つの保護レベルに対して Azure AD と Intune の[条件付きアクセス ポリシー](../security/office-365-security/identity-access-policies.md)セットを作成しました。

- *開始点* の保護は、すべてのユーザー アカウントに適用されます。
- *Enterprise* 保護は、上級のリーダーシップとエグゼクティブ スタッフに適用されます。
- 高度に規制されたデータにアクセスできる財務、法務、および研究部門の特定のユーザーには、*特殊なセキュリティ* 保護が適用されます。

Contoso ID とデバイスの条件付きアクセス ポリシーの結果セットを次に示します。

:::image type="content" alt-text="Contoso の ID とデバイスの条件付きアクセス ポリシー。" source="../media/contoso-identity/contoso-identity-fig5.png" lightbox="../media/contoso-identity/contoso-identity-fig5.png":::
 
## <a name="next-step"></a>次の手順

Contoso がMicrosoft Endpoint Configuration Manager インフラストラクチャを使用して、組織全体に[最新のWindows 10 Enterpriseをデプロイして維持](contoso-win10.md)する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 ID の展開](deploy-identity-solution-overview.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)