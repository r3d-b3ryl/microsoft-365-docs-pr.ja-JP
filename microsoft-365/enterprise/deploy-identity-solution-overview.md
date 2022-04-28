---
title: Microsoft 365用の ID インフラストラクチャをデプロイする
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
- m365initiative-coredeploy
- m365solution-m365-identity
- m365solution-scenario
- m365solution-overview
ms.custom:
- intro-overview
description: Microsoft 365用の ID インフラストラクチャをデプロイします。
ms.openlocfilehash: 6128daa59bfece9403953e041f258d87ef6a7413
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092957"
---
# <a name="deploy-your-identity-infrastructure-for-microsoft-365"></a>Microsoft 365用の ID インフラストラクチャをデプロイする

エンタープライズ向けのMicrosoft 365では、十分に計画され実行された ID インフラストラクチャにより、生産性ワークロードとそのデータへのアクセスを認証されたユーザーとデバイスのみに制限するなど、セキュリティの強化が実現します。 ID のセキュリティは、オンプレミスとクラウドの両方でリソースにアクセスしようとするすべての試行が認証され、承認される、ゼロ トラストデプロイの重要な要素です。

エンタープライズ向けの各Microsoft 365の ID 機能、Azure Active Directory (Azure AD)、オンプレミスおよびクラウドベースのコンポーネントの役割、および最も一般的な認証構成については、[Identity Infrastructure ポスター](../downloads/m365e-identity-infra.pdf)を参照してください。

[![ID インフラストラクチャのポスター。](../downloads/m365e-identity-infra.png)](../downloads/m365e-identity-infra.pdf)

この 2 ページのポスターを確認して、企業向けのMicrosoft 365の ID の概念と構成をすぐに確認してください。

[このポスターはダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/m365e-identity-infra.pdf)でき、レター形式、法的形式、または Tabloid 形式 (11 x 17) 形式で印刷できます。

このソリューションは、Microsoft 365 ゼロ トラストデプロイ スタックを構築するための最初の手順です。

![Microsoft 365 ゼロ トラストデプロイ スタック](../media/deploy-identity-solution-overview/zero-trust-deployment-stack.png)

詳細については、[Microsoft 365 ゼロ トラストデプロイ 計画](/microsoft-365/security/microsoft-365-zero-trust)を参照してください。

## <a name="whats-in-this-solution"></a>このソリューションの機能

このソリューションでは、Microsoft 365 テナント用の ID インフラストラクチャをデプロイして、従業員にアクセスし、ID ベースの攻撃から保護する手順を説明します。

![Microsoft 365用の ID インフラストラクチャをデプロイする](../media/deploy-identity-solution-overview/deploy-identity-solution-overview.png)

このソリューションの手順は次のとおりです。

1. [ID モデルを決定します。](deploy-identity-solution-identity-model.md)
2. [Microsoft 365特権アカウントを保護します。](protect-your-global-administrator-accounts.md)
3. [Microsoft 365ユーザー アカウントを保護します。](microsoft-365-secure-sign-in.md)
4. [ID モデルをデプロイします。](cloud-only-identities.md)

このソリューションは、[ゼロ トラスト](https://www.microsoft.com/security/business/zero-trust/)の主な原則をサポートしています。

- **明示的に確認する:** 使用可能なすべてのデータ ポイントに基づいて、常に認証と承認を行います。
- **最低限の特権アクセスを使用する:** Just-In-Time および Just-Enough-Access (JIT/JEA)、リスクベースのアダプティブ ポリシー、データ保護を使用してユーザー アクセスを制限します。
- **違反を想定する:** 影響範囲とセグメント アクセスを最小限に抑えます。 エンドツーエンドの暗号化を確認し、分析を使用して可視性を高め、脅威検出を推進し、防御を強化します。

組織のファイアウォールの背後にあるすべてを信頼する従来のイントラネット アクセスとは異なり、ゼロ トラストは、組織のファイアウォールの背後またはインターネット上の各サインインとアクセスを、管理されていないネットワークからのもののように処理します。ゼロ トラストでは、ネットワーク、インフラストラクチャ、ID、エンドポイント、アプリ、データを保護する必要があります。

## <a name="microsoft-365-capabilities-and-features"></a>Microsoft 365 の機能と機能

Azure ADは、Microsoft 365 テナントの ID 管理機能とセキュリティ機能の完全なスイートを提供します。

|機能|説明|ライセンス|
|---|---|---|
|[多要素認証 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA では、ユーザーが 2 つの形式の検証 (ユーザー パスワードと、Microsoft Authenticator アプリからの通知や電話など) を提供する必要があります。 MFA を使用すると、盗難された資格情報を使用して環境にアクセスできるリスクが大幅に軽減されます。 Microsoft 365は、MFA ベースのサインインにAzure AD多要素認証サービスを使用します。|Microsoft 365 E3 または E5|
|[条件付きアクセス](/azure/active-directory/conditional-access/overview)|Azure ADユーザー サインインの条件を評価し、条件付きアクセス ポリシーを使用して許可されたアクセスを決定します。 たとえば、このガイダンスでは、機密データへのアクセスにデバイスコンプライアンスを要求する条件付きアクセス ポリシーを作成する方法について説明します。 これにより、自分のデバイスと盗難された資格情報を持つハッカーが機密データにアクセスできるリスクが大幅に軽減されます。 また、デバイスは正常性とセキュリティに関する特定の要件を満たす必要があるため、デバイス上の機密データも保護します。|Microsoft 365 E3 または E5|
|[Azure AD グループ](/azure/active-directory/fundamentals/active-directory-manage-groups)|条件付きアクセス ポリシー、Intuneを使用したデバイス管理、さらには組織内のファイルやサイトへのアクセス許可は、ユーザー アカウントまたはAzure AD グループへの割り当てに依存します。 実装している保護レベルに対応するAzure AD グループを作成することをお勧めします。 たとえば、エグゼクティブ スタッフはハッカーの価値ターゲットが高い可能性があります。 したがって、これらの従業員のユーザー アカウントをAzure AD グループに追加し、このグループを条件付きアクセス ポリシーやその他のポリシーに割り当てて、より高いレベルのアクセス保護を適用すると便利です。|Microsoft 365 E3 または E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|組織の ID に影響を与える潜在的な脆弱性を検出し、自動修復ポリシーを低、中、高のサインイン リスクとユーザー リスクに構成できるようにします。 このガイダンスでは、このリスク評価に基づいて、多要素認証に条件付きアクセス ポリシーを適用します。 このガイダンスには、リスクの高いアクティビティがアカウントで検出された場合にユーザーがパスワードを変更する必要がある条件付きアクセス ポリシーも含まれています。|MICROSOFT 365 E5、E5 セキュリティ アドオン、EMS E5、またはAzure AD Premium P2 ライセンスを使用したMicrosoft 365 E3|
|[セルフサービス パスワード リセット (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|管理者が制御できる複数の認証方法の検証を提供することで、ユーザーがヘルプ デスクの介入なしで安全にパスワードをリセットできるようにします。|Microsoft 365 E3 または E5|
|[Azure ADパスワード保護](/azure/active-directory/authentication/concept-password-ban-bad)|既知の脆弱なパスワードとそのバリアント、および組織に固有の追加の脆弱な用語を検出してブロックします。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。|Microsoft 365 E3 または E5|
|

## <a name="next-steps"></a>次の手順

Microsoft 365 テナントの ID モデルと認証インフラストラクチャをデプロイするには、次の手順に従います。

1. [クラウド ID モデルを決定します。](deploy-identity-solution-identity-model.md)
2. [Microsoft 365特権アカウントを保護します。](protect-your-global-administrator-accounts.md)
3. [Microsoft 365ユーザー アカウントを保護します。](microsoft-365-secure-sign-in.md)
4. クラウド ID モデル ( [クラウド専用](cloud-only-identities.md) または [ハイブリッド](prepare-for-directory-synchronization.md)) をデプロイします。

[![Microsoft 365 テナントに使用する ID モデルを決定する](../media/deploy-identity-solution-overview/identity-solution-identity-model.png)](deploy-identity-solution-identity-model.md)
  
## <a name="additional-microsoft-cloud-identity-resources"></a>その他の Microsoft クラウド ID リソース

### <a name="manage"></a>管理

Microsoft クラウド ID のデプロイを管理するには、次を参照してください。

- [ユーザー アカウント](manage-microsoft-365-accounts.md)
- [ライセンス](assign-licenses-to-user-accounts.md)
- [パスワード](manage-microsoft-365-passwords.md)
- [グループ](manage-microsoft-365-groups.md)
- [ガバナンス](manage-microsoft-365-identity-governance.md)
- [ディレクトリ同期](view-directory-synchronization-status.md)

### <a name="how-microsoft-does-identity-for-microsoft-365"></a>Microsoft がMicrosoft 365の ID を行う方法

Microsoft の IT エキスパートが [ID を管理し、アクセスをセキュリティで保護](https://www.microsoft.com/en-us/itshowcase/managing-user-identities-and-secure-access-at-microsoft)する方法について説明します。

>[!Note]
>この IT ショーケース リソースは英語でのみ使用できます。
>

### <a name="how-contoso-did-identity-for-microsoft-365"></a>Contoso がMicrosoft 365の ID を行った方法

架空の代表的な多国籍組織が、Microsoft 365 クラウド サービス用のハイブリッド ID インフラストラクチャをデプロイした方法の例については、「[Contoso Corporation の ID」を](contoso-identity.md)参照してください。

<!--

## Plan

To plan for your identity implementation:

- [Understand the different identity models](about-microsoft-365-identity.md)
- [Plan for hybrid identity and directory synchronization](plan-for-directory-synchronization.md)

## Deploy

To deploy your identity implementation:

- [Protect your global administrator accounts](protect-your-global-administrator-accounts.md)
- [Configure and use cloud-only identities](cloud-only-identities.md)
- [Configure and use hybrid identities](prepare-for-directory-synchronization.md)
- [Set up directory synchronization](set-up-directory-synchronization.md)
- If needed, deploy [hybrid identity scenarios](hybrid-solutions.md)

### Identity and device access recommendations

To help ensure a secure and productive workforce, Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md). For identity, use the recommendations and settings in these articles:

- [Prerequisites](../security/office-365-security/identity-access-prerequisites.md)
- [Common identity and device access policies](../security/office-365-security/identity-access-policies.md)

--> 
