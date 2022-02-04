---
title: ユーザーの ID インフラストラクチャを展開Microsoft 365
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: ユーザーの ID インフラストラクチャをMicrosoft 365。
---

# <a name="deploy-your-identity-infrastructure-for-microsoft-365"></a>ユーザーの ID インフラストラクチャを展開Microsoft 365

エンタープライズMicrosoft 365では、十分に計画され実行された ID インフラストラクチャによって、生産性ワークロードとデータへのアクセスを認証済みのユーザーとデバイスにのみ制限するなど、より強力なセキュリティへの道が開きます。 ID のセキュリティはゼロトラスト展開の重要な要素であり、オンプレミスとクラウドの両方のリソースにアクセスしようとするすべての試みは認証および承認されます。

エンタープライズ向け各 Microsoft 365 の ID 機能、Azure Active Directory (Azure AD)、オンプレミスおよびクラウドベースのコンポーネントの役割、および最も一般的な認証構成については、「[Identity Infrastructure ポスター](../downloads/m365e-identity-infra.pdf)」を参照してください。

[![Id インフラストラクチャのポスター。](../downloads/m365e-identity-infra.png)](../downloads/m365e-identity-infra.pdf)

この 2 ページのポスターを確認して、エンタープライズ向け ID の概念と構成をすばやくMicrosoft 365してください。

このポスター [はダウンロードして](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/m365e-identity-infra.pdf) 、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷できます。

## <a name="whats-in-this-solution"></a>このソリューションの機能

このソリューションでは、従業員にアクセスを提供し、id ベースの攻撃から保護するために、Microsoft 365 テナントの ID インフラストラクチャを展開する手順を説明します。

![ユーザーの ID インフラストラクチャを展開Microsoft 365](../media/deploy-identity-solution-overview/deploy-identity-solution-overview.png)

このソリューションの手順は次のとおりです。

1. [ID モデルを決定します。](deploy-identity-solution-identity-model.md)
2. [特権アカウントMicrosoft 365保護します。](protect-your-global-administrator-accounts.md)
3. [ユーザー アカウントMicrosoft 365保護します。](microsoft-365-secure-sign-in.md)
4. [ID モデルを展開します。](cloud-only-identities.md)

このソリューションは、ゼロトラストの主な原則 [をサポートしています](https://www.microsoft.com/security/business/zero-trust/)。

- **明示的に確認する:** 使用可能なすべてのデータ ポイントに基づいて、常に認証と承認を行います。
- **最低限の特権アクセスを使用する:** Just-In-Time および Just-Enough-Access (JIT/JEA)、リスクベースのアダプティブ ポリシー、データ保護を使用してユーザー アクセスを制限します。
- **違反を想定する:** 影響範囲とセグメント アクセスを最小限に抑えます。 エンドツーエンドの暗号化を確認し、分析を使用して可視性を高め、脅威検出を推進し、防御を強化します。

組織のファイアウォールの背後にあるすべてを信頼する従来のイントラネット アクセスとは異なり、ゼロ トラストは、組織のファイアウォールの背後またはインターネット上の各サインインとアクセスを、管理されていないネットワークからのもののように処理します。 ゼロ トラストでは、ネットワーク、インフラストラクチャ、ID、エンドポイント、アプリ、データを保護する必要があります。

## <a name="microsoft-365-capabilities-and-features"></a>Microsoft 365 の機能と機能

Azure ADテナントの ID 管理とセキュリティ機能の完全なスイートをMicrosoft 365します。

|機能|説明|ライセンス|
|---|---|---|
|[多要素認証 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA では、ユーザーパスワードとアプリまたは電話からの通知など、2 つの形式Microsoft Authenticatorを提供する必要があります。 MFA は、盗まれた資格情報を使用して環境にアクセスするリスクを大幅に軽減します。 Microsoft 365 MFA ベースのサインインAzure AD多要素認証サービスを使用します。|Microsoft 365 E3 または E5|
|[条件付きアクセス](/azure/active-directory/conditional-access/overview)|Azure ADサインインの条件を評価し、条件付きアクセス ポリシーを使用して許可されたアクセスを決定します。 たとえば、このガイダンスでは、機密データへのアクセスにデバイスコンプライアンスを要求する条件付きアクセス ポリシーを作成する方法について説明します。 これにより、自分のデバイスと盗まれた資格情報を持つハッカーが機密データにアクセスするリスクが大幅に軽減されます。 また、デバイスは正常性とセキュリティに関する特定の要件を満たす必要があるため、デバイス上の機密データも保護します。|Microsoft 365 E3 または E5|
|[Azure ADグループ](/azure/active-directory/fundamentals/active-directory-manage-groups)|条件付きアクセス ポリシー、Intune を使用したデバイス管理、組織内のファイルやサイトに対するアクセス許可でさえ、ユーザー アカウントまたはユーザー グループへの割り当Azure ADします。 実装する保護Azure AD対応するグループを作成することをお勧めします。 たとえば、エグゼクティブ スタッフは、ハッカーの価値の高いターゲットである可能性が高くなります。 したがって、これらの従業員のユーザー アカウントを Azure AD グループに追加し、このグループを条件付きアクセス ポリシーおよびアクセスに対してより高いレベルの保護を適用する他のポリシーに割り当てるのが理にかなっています。|Microsoft 365 E3 または E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|組織の ID に影響を与える潜在的な脆弱性を検出し、自動修復ポリシーを低、中、高のサインイン リスクとユーザー リスクに構成できます。 このガイダンスは、多要素認証に条件付きアクセス ポリシーを適用するために、このリスク評価に依存します。 このガイダンスには、アカウントのリスクの高いアクティビティが検出された場合に、ユーザーがパスワードを変更する必要がある条件付きアクセス ポリシーも含まれています。|Microsoft 365 E5、Microsoft 365 E3 E5 セキュリティ アドオン、EMS E5、またはライセンスを使用Azure AD Premium P2する|
|[セルフサービス パスワードのリセット (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|管理者が制御できる複数の認証方法の検証を提供することで、ユーザーがヘルプ デスクの介入なしに安全にパスワードをリセットできます。|Microsoft 365 E3 または E5|
|[Azure ADパスワード保護](/azure/active-directory/authentication/concept-password-ban-bad)|既知の脆弱なパスワードとそのバリアント、および組織に固有の追加の弱い用語を検出してブロックします。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。|Microsoft 365 E3 または E5|
|

## <a name="next-steps"></a>次の手順

次の手順を使用して、ID モデルと認証インフラストラクチャをテナントにMicrosoft 365します。

1. [クラウド ID モデルを決定します。](deploy-identity-solution-identity-model.md)
2. [特権アカウントMicrosoft 365保護します。](protect-your-global-administrator-accounts.md)
3. [ユーザー アカウントMicrosoft 365保護します。](microsoft-365-secure-sign-in.md)
4. クラウド ID モデル (クラウド専用またはハイブリッド [)](cloud-only-identities.md) を [展開します](prepare-for-directory-synchronization.md)。

[![テナントに使用する ID モデルをMicrosoft 365する](../media/deploy-identity-solution-overview/identity-solution-identity-model.png)](deploy-identity-solution-identity-model.md)
  
## <a name="additional-microsoft-cloud-identity-resources"></a>その他の Microsoft クラウド ID リソース

### <a name="manage"></a>管理

Microsoft クラウド ID の展開を管理するには、以下を参照してください。

- [ユーザー アカウント](manage-microsoft-365-accounts.md)
- [ライセンス](assign-licenses-to-user-accounts.md)
- [パスワード](manage-microsoft-365-passwords.md)
- [グループ](manage-microsoft-365-groups.md)
- [ガバナンス](manage-microsoft-365-identity-governance.md)
- [ディレクトリ同期](view-directory-synchronization-status.md)

### <a name="how-microsoft-does-identity-for-microsoft-365"></a>Microsoft がユーザーの ID をMicrosoft 365

Microsoft の IT エキスパートが [ID を管理し、アクセスをセキュリティで保護](https://www.microsoft.com/en-us/itshowcase/managing-user-identities-and-secure-access-at-microsoft)する方法について説明します。

>[!Note]
>この IT ショーケース リソースは英語でのみ使用できます。
>

### <a name="how-contoso-did-identity-for-microsoft-365"></a>Contoso 社がユーザーの ID をMicrosoft 365

架空の代表的な多国籍組織が、Microsoft 365 クラウド サービス用のハイブリッド ID インフラストラクチャを展開した方法の例については、「[Identity for the Contoso Corporation」を参照してください](contoso-identity.md)。

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
