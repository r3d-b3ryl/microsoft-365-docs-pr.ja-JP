---
title: ゼロ トラスト ID とデバイス アクセスの構成 - Microsoft 365 for enterprise
description: セキュリティで保護された電子メール、ドキュメント、アプリのポリシーと構成をゼロ トラストに展開するための Microsoft の推奨事項とコア概念について説明します。
ms.author: dansimp
author: dansimp
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
- m365solution-zero-trust
- zerotrust-solution
- highpri
ms.technology: mdo
ms.openlocfilehash: 7480fdcf3d394e152ff3b1de738d48f5723d7b75
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481198"
---
# <a name="zero-trust-identity-and-device-access-configurations"></a>ゼロ トラスト ID とデバイスのアクセス構成

ネットワーク ファイアウォールと仮想プライベート ネットワーク (VPN) に依存して組織のテクノロジ リソースとサービスへのアクセスを分離および制限するセキュリティ アーキテクチャは、従来の企業ネットワークの境界を超えて存在するアプリケーションやリソースへのアクセスを定期的に必要とする従業員にとっては十分ではなくなりました。

この新しいコンピューティングの世界に対処するために、Microsoft は、次の原則に基づくゼロ トラストセキュリティ モデルを高くお勧めします。

- 明確に確認する

  使用可能なすべてのデータ ポイントに基づいて、常に認証と承認を行います。 ここで、サインインと継続的な検証を行うには、ゼロ トラスト ID ポリシーとデバイス アクセス ポリシーが重要です。

- 最小限の特権アクセスを使用する

  Just-In-Time と Just-Enough-Access (JIT/JEA)、リスク ベースのアダプティブ ポリシー、データ保護を使用してユーザー アクセスを制限します。

- 侵害を想定する

  爆発半径とセグメント アクセスを最小限に抑えます。 エンドツーエンドの暗号化を確認し、分析を使用して可視性を高め、脅威検出を推進し、防御を強化します。

ゼロ トラストの全体的なアーキテクチャを次に示します。

:::image type="content" source="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png" alt-text="Microsoft ゼロ トラスト アーキテクチャ" lightbox="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png":::

ゼロ トラスト ID ポリシーとデバイス アクセス ポリシーは、次の場合 **の検証の明示的な** ガイド原則に対処します。

- ID

  ID がリソースへのアクセスを試みる場合は、強力な認証を使用してその ID を確認し、要求されたアクセスが準拠していて一般的であることを確認します。

- デバイス (エンドポイントとも呼ばれます)

  デバイスの正常性とコンプライアンスの要件を監視し、セキュリティで保護されたアクセスを適用します。

- アプリケーション

  コントロールとテクノロジを適用してシャドウ IT を検出し、アプリ内の適切なアクセス許可を確保し、リアルタイム分析に基づいてアクセスをゲートし、異常な動作を監視し、ユーザーアクションを制御し、セキュリティで保護された構成オプションを検証します。

この一連の記事では、一連の ID およびデバイス アクセスの前提条件構成と、Azure Active Directory (Azure AD) 条件付きアクセス、Microsoft Intune、およびエンタープライズ クラウド アプリとサービス、その他の SaaS サービス、Azure AD アプリケーション プロキシで公開されるオンプレミス アプリケーションに対する Microsoft 365 へのゼロ トラスト アクセスに関するその他のポリシーについて説明します。

ゼロ トラスト ID とデバイスのアクセス設定とポリシーは、開始点、エンタープライズ、および高度に規制されたデータまたは分類されたデータを持つ環境に対する特殊なセキュリティという 3 つの層で推奨されます。 これらの層とそれに対応する構成により、データ、ID、デバイス全体で一貫したレベルのゼロ トラスト保護が提供されます。

これらの機能とその推奨事項:

- Microsoft 365 E3とMicrosoft 365 E5でサポートされています。
- [Azure AD](/azure/active-directory/fundamentals/identity-secure-score) の Id スコアと同様に [Microsoft Secure Score](../defender/microsoft-secure-score.md) と一致し、組織のこれらのスコアを増やします。
- [ID インフラストラクチャをセキュリティで保護するための 5 つの手順を](/azure/security/azure-ad-secure-steps)実装するのに役立ちます。

組織に固有の環境要件や複雑さがある場合は、これらの推奨事項を出発点として使用します。 ただし、ほとんどの組織では、これらの推奨事項を規定どおりに実装できます。

エンタープライズ向け Microsoft 365 の ID とデバイス アクセスの構成の概要については、このビデオをご覧ください。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft は、Office 365 サブスクリプションのEnterprise Mobility + Security (EMS) ライセンスも販売しています。 EMS E3 および EMS E5 機能は、Microsoft 365 E3およびMicrosoft 365 E5の機能と同じです。 詳細については [、EMS プラン](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) を参照してください。

## <a name="intended-audience"></a>対象ユーザー

これらの推奨事項は、Azure AD (ID)、Microsoft Intune (デバイス管理)、Microsoft Purview 情報保護 (データ保護) を含む Microsoft 365 クラウドの生産性とセキュリティ サービスに精通しているエンタープライズ アーキテクトと IT プロフェッショナルを対象としています。

### <a name="customer-environment"></a>顧客環境

推奨されるポリシーは、Microsoft クラウド内で完全に運用されているエンタープライズ組織と、Azure AD テナントと同期される オンプレミスの Active Directory Domain Services (AD DS) フォレストであるハイブリッド ID インフラストラクチャを使用する顧客に適用されます。

提供される推奨事項の多くは、Microsoft 365 E5、E5 セキュリティ アドオン、EMS E5、またはAzure AD Premium P2 ライセンスを使用したMicrosoft 365 E3でのみ利用できるサービスに依存しています。

これらのライセンスを持っていない組織の場合は、少なくとも [セキュリティの既定値](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)を実装することをお勧めします。これは、すべての Microsoft 365 プランに含まれています。

### <a name="caveats"></a>警告

組織には、規制やその他のコンプライアンス要件が適用される場合があります。これには、これらの推奨される構成とは異なるポリシーを適用する必要がある特定の推奨事項が含まれます。 これらの構成では、これまで使用できなかった使用制御をお勧めします。 これらのコントロールは、セキュリティと生産性のバランスを表していると考えられるため、これらのコントロールをお勧めします。

さまざまな組織保護要件を考慮するために最善を尽くしてきましたが、すべての可能な要件または組織の固有の側面をすべて考慮することはできません。

## <a name="three-tiers-of-protection"></a>保護の 3 つの層

ほとんどの組織は、セキュリティとデータ保護に関して固有の要件を用意しています。 そのような要件は業種によって、また、組織内の職務によって変わります。 たとえば、法務部門と管理者は、他の部署では必要ない電子メール通信に関する追加のセキュリティと情報保護の制御を必要とする場合があります。

また、あらゆる業種が独自の特別な規制を用意しています。 すべての可能なセキュリティ オプションの一覧や、業界セグメントまたはジョブ機能ごとの推奨事項を提供するのではなく、ニーズの粒度に基づいて適用できる 3 つの異なるレベルのセキュリティと保護に関する推奨事項が提供されています。

- **開始点**: すべてのお客様が、データにアクセスする ID とデバイスだけでなく、データを保護するための最小標準を確立して使用することをお勧めします。 これらの推奨事項に従って、すべての組織の開始点として強力な既定の保護を提供できます。
- **エンタープライズ**: 一部の顧客は、より高いレベルで保護する必要があるデータのサブセットを持っているか、すべてのデータを上位レベルで保護する必要がある場合があります。 Microsoft 365 環境内のすべてのデータ セットまたは特定のデータ セットに対して、強化された保護を適用できます。 機密データにアクセスする ID とデバイスはそれに相応しいレベルのセキュリティで保護することを推奨します。
- **特殊なセキュリティ**: 必要に応じて、少数の顧客が、高度に分類された、営業秘密を構成する、または規制されている少量のデータを持っています。 Microsoft は、これらのお客様がこれらの要件を満たすのに役立つ機能を提供しています。これには、ID とデバイスの保護が追加されています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png" alt-text="セキュリティ コーン" lightbox="../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png":::

このガイダンスでは、これらの保護レベルごとに ID とデバイスのゼロ トラスト保護を実装する方法について説明します。 このガイダンスは、組織の最小要件として使用し、組織の特定の要件を満たすようにポリシーを調整します。

ID、デバイス、データ全体で一貫したレベルの保護を使用することが重要です。 たとえば、経営幹部、リーダー、マネージャーなどの優先アカウント&mdash;を持つユーザーの保護には、ID、デバイス、アクセス&mdash;するデータに対して同じレベルの保護を含める必要があります。 
<!--

The **Zero Trust identity and device protection for Microsoft 365** architecture model shows you which capabilities are comparable.

[![Thumb image for Zero Trust Identity and device protection for Microsoft 365 poster.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-thumbnail.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [View as a PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf)  \| [Download as a Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)

--> 

さらに、Microsoft 365 に格納されている [情報を保護するためのデータ プライバシー規制の](../../solutions/information-protection-deploy.md) 情報保護の展開ソリューションに関するページを参照してください。

## <a name="security-and-productivity-trade-offs"></a>セキュリティと生産性の折り合い

セキュリティ戦略を実装するには、セキュリティと生産性のトレードオフが必要です。 各決定がセキュリティ、機能、使いやすさのバランスにどのような影響を与えるかを評価すると便利です。

:::image type="content" source="../../media/microsoft-365-policies-configurations/security-triad.png" alt-text="セキュリティ、機能、使いやすさのバランスを取るセキュリティ トライアド" lightbox="../../media/microsoft-365-policies-configurations/security-triad.png":::

推奨事項は、次の原則に基づいています。

- ユーザーを把握し、セキュリティと機能の要件に柔軟に対応します。
- セキュリティ ポリシーを適切なタイミングで適用し、意味があることを確認します。

## <a name="services-and-concepts-for-zero-trust-identity-and-device-access-protection"></a>ゼロ トラスト ID とデバイス アクセス保護のサービスと概念

Microsoft 365 for Enterprise は、大規模な組織が全員がクリエイティブになり、安全に共同作業できるように設計されています。

このセクションでは、ゼロ トラスト ID とデバイス アクセスに重要な Microsoft 365 サービスと機能の概要について説明します。

### <a name="azure-ad"></a>Azure AD

Azure AD には、ID 管理機能の完全なスイートが用意されています。 これらの機能を使用してアクセスをセキュリティで保護することをお勧めします。

|機能|説明|ライセンス|
|---|---|---|
|[多要素認証 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA では、ユーザーが 2 つの形式の検証 (ユーザー パスワードと Microsoft Authenticator アプリからの通知や電話など) を提供する必要があります。 MFA を使用すると、盗難された資格情報を使用して環境にアクセスできるリスクが大幅に軽減されます。 Microsoft 365 では、MFA ベースのサインインに Azure AD Multi-Factor Authentication サービスを使用します。|Microsoft 365 E3 または E5|
|[条件付きアクセス](/azure/active-directory/conditional-access/overview)|Azure AD は、ユーザー サインインの条件を評価し、条件付きアクセス ポリシーを使用して許可されるアクセスを決定します。 たとえば、このガイダンスでは、機密データへのアクセスにデバイスコンプライアンスを要求する条件付きアクセス ポリシーを作成する方法について説明します。 これにより、自分のデバイスと盗難された資格情報を持つハッカーが機密データにアクセスできるリスクが大幅に軽減されます。 また、デバイスは正常性とセキュリティに関する特定の要件を満たす必要があるため、デバイス上の機密データも保護します。|Microsoft 365 E3 または E5|
|[Azure AD グループ](/azure/active-directory/fundamentals/active-directory-manage-groups)|条件付きアクセス ポリシー、Intuneを使用したデバイス管理、さらには組織内のファイルやサイトへのアクセス許可は、ユーザー アカウントまたは Azure AD グループへの割り当てに依存します。 実装している保護レベルに対応する Azure AD グループを作成することをお勧めします。 たとえば、エグゼクティブ スタッフはハッカーの価値ターゲットが高い可能性があります。 そのため、これらの従業員のユーザー アカウントを Azure AD グループに追加し、このグループを条件付きアクセス ポリシーや、アクセスに対してより高いレベルの保護を適用するその他のポリシーに割り当てることは理にかなっています。|Microsoft 365 E3 または E5|
|[デバイスの登録](/azure/active-directory/devices/overview)|デバイスを Azure AD に登録して、デバイスの ID を作成します。 この ID は、ユーザーがサインインしたときにデバイスを認証し、ドメイン参加または準拠している PC を必要とする条件付きアクセス ポリシーを適用するために使用されます。 このガイダンスでは、デバイス登録を使用して、ドメインに参加している Windows コンピューターを自動的に登録します。 デバイスの登録は、Intuneを使用してデバイスを管理するための前提条件です。|Microsoft 365 E3 または E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|組織の ID に影響を与える潜在的な脆弱性を検出し、自動修復ポリシーを低、中、高のサインイン リスクとユーザー リスクに構成できるようにします。 このガイダンスでは、このリスク評価に基づいて、多要素認証に条件付きアクセス ポリシーを適用します。 このガイダンスには、リスクの高いアクティビティがアカウントで検出された場合にユーザーがパスワードを変更する必要がある条件付きアクセス ポリシーも含まれています。|MICROSOFT 365 E5、E5 セキュリティ アドオン、EMS E5、またはAzure AD Premium P2 ライセンスを使用したMicrosoft 365 E3|
|[セルフサービス パスワード リセット (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|管理者が制御できる複数の認証方法の検証を提供することで、ユーザーがヘルプ デスクの介入なしで安全にパスワードをリセットできるようにします。|Microsoft 365 E3 または E5|
|[Azure AD パスワード保護](/azure/active-directory/authentication/concept-password-ban-bad)|既知の脆弱なパスワードとそのバリアント、および組織に固有の追加の脆弱な用語を検出してブロックします。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。|Microsoft 365 E3 または E5|

Intuneと Azure AD オブジェクト、設定、サブサービスなど、ゼロ トラスト ID とデバイス アクセスのコンポーネントを次に示します。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-components.png" alt-text="ゼロ トラスト ID とデバイス アクセスのコンポーネント" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-components.png":::

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune)は、Microsoft のクラウドベースのモバイル デバイス管理サービスです。 このガイダンスでは、Intuneを使用した Windows PC のデバイス管理を推奨し、デバイス コンプライアンス ポリシーの構成を推奨します。 Intuneは、デバイスが準拠しているかどうかを判断し、条件付きアクセス ポリシーを適用するときに使用するためにこのデータを Azure AD に送信します。

#### <a name="intune-app-protection"></a>Intune アプリ保護

[Intuneアプリ保護](/intune/app-protection-policy)ポリシーは、デバイスを管理に登録するかどうかにかかわらず、モバイル アプリ内の組織のデータを保護するために使用できます。 Intuneは、情報を保護し、従業員が生産性を維持できるようにし、データ損失を防ぐのに役立ちます。 アプリ レベルのポリシーを実装することで、会社のリソースへのアクセスを制限し、IT 部門の制御内にデータを保持できます。

このガイダンスでは、承認済みアプリの使用を強制し、ビジネス データでこれらのアプリを使用する方法を決定するための推奨ポリシーを作成する方法について説明します。

### <a name="microsoft-365"></a>Microsoft 365

このガイダンスでは、Microsoft Teams、Exchange、SharePoint、OneDrive など、Microsoft 365 クラウド サービスへのアクセスを保護するための一連のポリシーを実装する方法について説明します。 これらのポリシーの実装に加えて、次のリソースを使用してテナントの保護レベルを上げることをお勧めします。

- [セキュリティ強化のためにテナントを構成する](tenant-wide-setup-for-increased-security.md)

  テナントの開始点のセキュリティに適用される推奨事項。

- [セキュリティ ロードマップ: 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)

  ログ記録、データ ガバナンス、管理者アクセス、脅威保護を含む推奨事項。

### <a name="windows-11-or-windows-10-with-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterpriseを使用したWindows 11またはWindows 10

Microsoft 365 Apps for enterpriseのWindows 11またはWindows 10は、PC に推奨されるクライアント環境です。 Windows 11またはWindows 10をお勧めします。Azure は、オンプレミスと Azure AD の両方で可能な限りスムーズなエクスペリエンスを提供するように設計されているためです。 Windows 11またはWindows 10には、Intuneで管理できる高度なセキュリティ機能も含まれています。 Microsoft 365 Apps for enterpriseには、最新バージョンの Office アプリケーションが含まれています。 これらは、より安全で条件付きアクセスの要件である先進認証を使用します。 これらのアプリには、強化されたコンプライアンスツールとセキュリティ ツールも含まれています。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>これらの機能を保護の 3 つの層に適用する

次の表は、3 つの保護レベルでこれらの機能を使用するための推奨事項をまとめたものです。

|保護メカニズム|開始点|Enterprise|特殊なセキュリティ|
|---|---|---|---|
|**MFA の強制**|中程度以上のサインイン リスクで|低以上のサインイン リスクで|すべての新しいセッションで|
|**パスワード変更を適用する**|リスクの高いユーザーの場合|リスクの高いユーザーの場合|リスクの高いユーザーの場合|
|**アプリケーション保護Intune適用する**|はい|はい|はい|
|**組織所有のデバイスのIntune登録を強制する**|準拠またはドメインに参加している PC を必要とするが、持ち込み専用デバイス (BYOD) のスマートフォンとタブレットを許可する|準拠デバイスまたはドメイン参加済みデバイスを要求する|準拠デバイスまたはドメイン参加済みデバイスを要求する|

## <a name="device-ownership"></a>デバイスの所有権

上の表は、多くの組織が組織所有のデバイスと個人または BYOD の組み合わせをサポートして、従業員全体のモバイル生産性を実現する傾向を反映しています。 Intuneアプリ保護ポリシーを使用すると、組織所有のデバイスと BYOD の両方で、メールが Outlook モバイル アプリやその他の Office モバイル アプリから流出しないように保護されます。

組織所有のデバイスは、追加の保護と制御を適用するために、Intuneまたはドメイン参加によって管理することをお勧めします。 データの機密性によっては、組織では、特定のユーザー集団または特定のアプリに対して BYOD を許可しない場合があります。

## <a name="deployment-and-your-apps"></a>デプロイとアプリ

Azure AD 統合アプリの id とデバイス アクセスの構成ゼロ トラスト構成してロールアウトする前に、次のことを行う必要があります。

- 保護する組織で使用するアプリを決定します。
- このアプリの一覧を分析して、適切なレベルの保護を提供するポリシーのセットを決定します。

  ポリシーの管理が煩雑になる可能性があるため、アプリごとに個別のポリシー セットを作成しないでください。 Microsoft では、同じユーザーに対して同じ保護要件を持つアプリをグループ化することをお勧めします。

  たとえば、すべてのユーザーが開始点を保護するためにすべての Microsoft 365 アプリを含む 1 セットのポリシーと、人事部門や財務部門によって使用されるアプリなど、すべての機密アプリに対する 2 番目のポリシー セットを含め、それらのグループに適用できます。

セキュリティで保護するアプリの一連のポリシーを決定したら、ポリシーを段階的にユーザーにロールアウトし、その過程で問題に対処します。

たとえば、Exchange に対する追加の変更を加えて、すべての Microsoft 365 アプリに対して Exchange 用に使用されるポリシーを構成します。 これらのポリシーをユーザーにロールアウトし、問題を解決します。 次に、追加の変更を加えて Teams を追加し、これをユーザーにロールアウトします。 次に、追加の変更を加えて SharePoint を追加します。 すべての Microsoft 365 アプリを含めるために、これらの開始点ポリシーを自信を持って構成できるまで、残りのアプリを追加し続けます。

同様に、機密性の高いアプリの場合は、ポリシーのセットを作成し、一度に 1 つのアプリを追加し、それらがすべて機密アプリ ポリシー セットに含まれるまで問題を解決します。

すべてのアプリに適用されるポリシー セットは、意図しない構成になる可能性があるため、作成しないことをお勧めします。 たとえば、すべてのアプリをブロックするポリシーは管理者をAzure portalからロックアウトする可能性があり、Microsoft Graph などの重要なエンドポイントに対して除外を構成することはできません。

## <a name="steps-to-configure-zero-trust-identity-and-device-access"></a>ゼロ トラスト ID とデバイス アクセスを構成する手順

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps.png" alt-text="ゼロ トラスト ID とデバイス アクセスを構成する手順" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps.png":::

1. 前提条件の ID 機能とその設定を構成します。
2. 共通 ID とアクセス条件付きアクセス ポリシーを構成します。
3. ゲストユーザーと外部ユーザーの条件付きアクセス ポリシーを構成します。
4. Microsoft Teams、Exchange、SharePoint&mdash;、Microsoft Defender for Cloud Apps ポリシーなどの Microsoft 365 クラウド アプリ&mdash;の条件付きアクセス ポリシーを構成します。

id とデバイス アクセスゼロ トラスト構成したら、考慮すべき追加機能の段階的なチェックリストと、アクセスを保護、監視、監査するための [Azure AD Identity Governance については、Azure AD](/azure/active-directory/governance/) [機能デプロイ ガイド](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2)を参照してください。

## <a name="next-step"></a>次のステップ

[ゼロ トラスト ID ポリシーとデバイス アクセス ポリシーを実装するための前提条件](identity-access-prerequisites.md)
