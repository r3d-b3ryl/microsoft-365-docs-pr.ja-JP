---
title: Contoso 社の ID
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869468"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso 社の ID

**概要:** Contoso 社で、IDaaS (Identity as a Service) を活用して、従業員向けのクラウド ベース認証や、パートナーと顧客向けのフェデレーション認証を提供している方法を説明します。

Microsoft は、Azure Active Directory (AD) により、クラウド製品全体に IDaaS (Identity as a Service) を提供します。Microsoft 365 Enterprise を採用するため、Contoso 社の IDaaS ソリューションでは、オンプレミスの ID プロバイダーを活用しつつ、信頼できる既存のサードパーティ ID プロバイダーを使用したフェデレーション認証も含める必要がありました。

## <a name="contosos-windows-server-ad-forest"></a>Contoso 社の Windows Server AD フォレスト

Contoso 社では contoso.com に対して、7 つのサブドメイン (世界の地域ごとに 1 つのサブドメイン) を持つ単一の Windows Server Active Directory (AD) フォレストを使用します。本社、地域ハブ オフィス、およびサテライト オフィスには、ローカルの認証と承認のためのドメイン コントローラーが含まれています。

図 1 では、地域ハブを含む世界各地の地域ドメインを持つ Contoso 社のフォレストを示しています。

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**図 1: Contoso 社の世界的なフォレストとドメイン**

Contoso 社では、クラウドベースのアプリおよびワークロードの認証と承認のために、contoso.com フォレストのアカウントとグループを使用することを望んでいます。

## <a name="contosos-federated-authentication-infrastructure"></a>Contoso 社のフェデレーション認証インフラストラクチャ

Contoso 社では次のことが可能です。

- 顧客は Microsoft、Facebook、または Google のメール アカウントを使用してパブリック Web サイトにサインインできます。
- ベンダーおよびパートナーは、LinkedIn、Salesforce、または Google のメール アカウントを使用してパートナー エクストラネットにサインインできます。

図 2 は、公開 Web サイト、パートナーのエクストラネット、および Active Directory フェデレーション サービス (AD FS) サーバーのセットを含む Contoso 社の DMZ を示しています。DMZ は、顧客、パートナー、およびインターネット サービスを含むインターネットに接続されています。

![](./media/contoso-identity/contoso-identity-fig2.png)

**図 2: Contoso 社の顧客とパートナーのフェデレーション認証のサポート**
 
DMZ の AD FS サーバーは、パブリック Web サイトにアクセスするための顧客資格情報、およびパートナー エクストラネットにアクセスするためのパートナー資格情報を認証します。

Contoso 社は、このインフラストラクチャを維持し、顧客とパートナーの認証専用で使用することに決定しました。Contoso 社の ID エンジニアは、このインフラストラクチャから Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) および [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) ソリューションへの変換を調査中です。

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a>クラウドベース認証にパススルー認証を使用したハイブリッド ID

Contoso 社は、Microsoft 365 のクラウド リソースへの認証にオンプレミスの Windows Server AD フォレストを活用したいと考えており、パスワード ハッシュ同期 (PHS) によるパススルー認証 (PTA) を採用することに決定しました。

### <a name="pta-authentication"></a>PTA 認証

ユーザー資格情報の認証については、Contoso 社は PTA を使用しています。Contoso 社のユーザーがクラウドベースのリソースにアクセスすると、送信された資格情報は Azure AD によって Contoso 社の本社データ センターでの認証エージェントを実行するサーバーに渡されます。これらの認証エージェント サーバーの 1 つが、Azure AD に代わってユーザー資格情報を検証します。

図 3 は、Contoso 社の本社で認証エージェントを実行するサーバー群を図示したもので、Azure AD から渡される認証要求をこれらが処理します。 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
**図 3: Contoso 社のパススルー認証インフラストラクチャ**

Contoso 社では、認証のためのすべての試行が、ユーザー アカウント状態、パスワード ポリシー、サインイン時間に関して、オンプレミスの Windows Server AD フォレストに加えられた直近の変更に照らして評価されることがセキュリティ要件となっており、これを満たす目的で PTA を選択しました。

### <a name="phs"></a>PHS

PHS は、ユーザー アカウントとグループ アカウント、およびハッシュされたバージョンのユーザー アカウント パスワードをコピーして、オンプレミスの Windows Server AD フォレストを Microsoft 365 Enterprise サブスクリプションの Azure AD テナントと同期します。Contoso 社は、PTA が使用できない場合に Azure AD テナントを使った認証の代替手段を直接提供できるように、PHS を採用することに決定しました。

ディレクトリ同期を継続的に実行するため、Contoso 社は、パリにある自社のデータ センターのサーバー上に Azure AD Connect ツールを展開しました。図 4 は、変更に関して Contoso 社の Windows Server AD フォレストをポーリングし、それらの変更を Azure AD テナントと同期する、Azure AD Connect を実行中のサーバーを図示したものです。

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**図 4: Contoso 社の PHH ディレクトリ同期インフラストラクチャ**

## <a name="conditional-access-policies-for-identity"></a>ID 用の条件付きアクセスポリシー

Contoso 社では、ある認証要求に関連して Azure AD がサインイン リスクがあると判断した場合に、多要素認証とパスワード変更が確実に適用されるようにするために、一連の Azure AD [条件付きアクセス ポリシー](identity-access-policies.md)を作成しています。

図 5 は、ID 用の条件付きアクセスポリシーの結果セットを図示したものです。

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**図 5: Contoso 社の ID ベース条件付きアクセスポリシー**

## <a name="next-step"></a>次の手順

Contoso 社が System Center Configuration Manager インフラストラクチャを利用して、現在の Windows 10 Enterprise を組織全体に展開し、維持する方法について[説明](contoso-win10.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の ID](identity-infrastructure.md)

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
