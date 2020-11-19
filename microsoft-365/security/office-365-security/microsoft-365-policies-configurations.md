---
title: Id とデバイスのアクセス構成-エンタープライズ向け Microsoft 365
description: セキュリティで保護された電子メール、ドキュメント、およびアプリのポリシーと構成を展開するための Microsoft の推奨事項と中心概念について説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/29/2020
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
ms.openlocfilehash: 993dd1ed66ca5bc6635c0eadf2dc7345ab84b57d
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356921"
---
# <a name="identity-and-device-access-configurations"></a>ID とデバイスのアクセス構成

組織の先進セキュリティ境界は、ネットワークを超えて拡張され、さまざまなデバイスを備えたあらゆる場所からクラウドベースのアプリにアクセスするユーザーが含まれるようになりました。 セキュリティインフラストラクチャで、特定のアクセス要求を許可するかどうか、およびその条件について判断する必要があります。

この判断は、サインインのユーザーアカウント、使用しているデバイス、アクセスのためにユーザーが使用しているアプリ、アクセス要求が行われた場所、および要求のリスクの評価に基づいて行う必要があります。 この機能により、承認されたユーザーとデバイスのみが重要なリソースにアクセスできるようになります。

このシリーズの記事では、id およびデバイスアクセスの前提条件となる構成のセット、および azure Active Directory (Azure AD) の条件付きアクセス、Microsoft Intune、および Azure AD Application Proxy で公開されているその他の SaaS サービス、およびオンプレミスアプリケーションに対する Microsoft 365 へのアクセスを保護するためのポリシーについて説明します。

Id とデバイスのアクセスの設定とポリシーは3層で推奨されます。ベースライン保護、機密保護、および厳しいデータを持つ環境の保護。 これらの層とそれに対応する構成は、データ、ID、およびデバイス全体で一貫したレベルの保護を提供します。

これらの機能と推奨事項:

- は、Microsoft 365 E3 および Microsoft 365 E5 でサポートされています。
- は、 [Microsoft セキュリティスコア](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) と [Azure AD の id スコア](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)に沿って配置されており、組織にとってこれらのスコアが増加します。
- は [、id インフラストラクチャをセキュリティで保護するための5つの手順を](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)実装するのに役立ちます。

組織に固有の環境要件や複雑さがある場合は、これらの推奨事項を出発点として使用します。 ただし、ほとんどの組織では、これらの推奨事項を定められたとおりに実装できます。

>[!Note]
>Microsoft は、Office 365 サブスクリプションの Enterprise Mobility + Security (EMS) ライセンスも販売しています。 EMS E3 および EMS E5 機能は、Microsoft 365 E3 および Microsoft 365 E5 の機能と同じです。 詳細については、「 [EMS プラン](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) 」を参照してください。
>

## <a name="intended-audience"></a>対象ユーザー

これらの推奨事項は、Microsoft 365 のクラウド生産性およびセキュリティサービス (Azure AD (identity)、Microsoft Intune (デバイス管理)、および Azure Information Protection (データ保護) を含む) に精通しているエンタープライズアーキテクトおよび IT 担当者を対象としています。

### <a name="customer-environment"></a>お客様の環境

推奨されるポリシーは、Microsoft クラウド内で完全に運用しているエンタープライズ組織と、ハイブリッド id インフラストラクチャを使用しているお客様 (オンプレミスの Active Directory ドメインサービス (AD DS) フォレストで、Azure AD テナントと同期されている) に適用されます。

提供されている推奨事項の多くは、Microsoft 365 E5、Microsoft 365 E3 (Identity & Threat Protection アドオン、EMS E5、または Azure Premium P2 ライセンス) でのみ利用可能なサービスに依存しています。

これらのライセンスを持っていない組織については、少なくとも Microsoft 365 プランに含まれている [セキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)を実装することをお勧めします。

### <a name="caveats"></a>べき

お客様の組織は、これらの推奨される構成から分岐するポリシーを適用する必要がある特定の推奨事項を含む、規制またはその他のコンプライアンス要件の対象となる場合があります。 これらの構成では、これまで利用できなかった使用状況コントロールが推奨されます。 これらのコントロールは、セキュリティと生産性のバランスがあると考えられるため、お勧めします。

さまざまな組織保護要件を考慮することをお勧めしますが、お客様の組織のすべての要件や固有の要素を考慮することはできません。

## <a name="three-tiers-of-protection"></a>3層の保護

ほとんどの組織は、セキュリティとデータ保護に関して固有の要件を用意しています。 そのような要件は業種によって、また、組織内の職務によって変わります。 たとえば、法務部門や管理者は、他の部署では必要とされないメール通信に関して、追加のセキュリティと情報保護を必要とする場合があります。

また、あらゆる業種が独自の特別な規制を用意しています。 考えられるすべてのセキュリティオプションの一覧、または各業種セグメントまたはジョブ機能に対する推奨事項の一覧を提供するのではなく、ニーズの粒度に基づいて適用可能な3つのセキュリティと保護の層について推奨事項が提供されています。

- **ベースライン保護**: データを保護するための最小限の標準と、データにアクセスする id およびデバイスを設定することをお勧めします。 これらのベースライン推奨事項に従って、多くの組織のニーズを満たす強力な既定の保護を提供することができます。
- **機密保護**: 一部のお客様は、より高いレベルで保護する必要があるデータのサブセットを持っているか、すべてのデータをより高いレベルで保護する必要がある場合があります。 Microsoft 365 環境のすべてまたは特定のデータセットに対して、強化された保護を適用することができます。 機密データにアクセスする ID とデバイスはそれに相応しいレベルのセキュリティで保護することを推奨します。
- 厳しく **規制** されている組織の中には、非常に多くのデータがあり、取引の機密を構成したり、規制されたデータが含まれている場合があります。 Microsoft は、ID とデバイスの保護を追加するなど、組織がそのような要件を満たすための機能を提供しています。

![セキュリティコーン-特定のお客様 > 一部のお客様 >。 特定のアプリケーションに対する幅広いアプリケーション](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

このガイダンスでは、これらの各層の保護の id とデバイスの保護を実装する方法について説明します。 組織の出発点としてこのガイダンスを使用し、組織の特定の要件を満たすようにポリシーを調整します。

データ、ID、デバイス全体で一貫したレベルの保護を使用することが重要です。 たとえば、このガイダンスを実装する場合は、必ず同等のレベルでデータを保護してください。

**Microsoft 365 アーキテクチャモデルの id およびデバイス保護** は、どの機能が同等であるかを示しています。

[![Microsoft 365 ポスターの Id およびデバイス保護のサムネイル画像](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [PDF として表示する](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [PDF としてダウンロードする](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf)  \| [Visio としてダウンロードする](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)

また、Microsoft 365 に保存されている情報を保護するために、「 [Deploy information protection for data privacy 規制](../../solutions/information-protection-deploy.md) ソリューション」を参照してください。

## <a name="security-and-productivity-trade-offs"></a>セキュリティと生産性の折り合い

セキュリティ戦略を実装するには、セキュリティと生産性の間にトレードオフが必要です。 各決定が、セキュリティ、機能、および使いやすさのバランスにどのように影響するかを評価するのに役立ちます。

![セキュリティ、機能性、使いやすさのバランスを保つためのセキュリティの障害許容。](../../media/microsoft-365-policies-configurations/security-triad.png)

提供される推奨事項は、次の原則に基づいています。

- ユーザーを理解し、セキュリティと機能の要件に柔軟に対応します。
- セキュリティポリシーを時刻だけに適用し、意味のあるものにします。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Id とデバイスのアクセス保護のサービスと概念

Microsoft 365 for enterprise は大規模な組織向けに設計されており、すべてのユーザーをクリエイティブにして安全に共同作業を行うことができます。

このセクションでは、id とデバイスのアクセスにおいて重要な Microsoft 365 サービスと機能の概要について説明します。

### <a name="azure-ad"></a>Azure AD

Azure AD には、id 管理機能の完全なスイートが用意されています。 Access をセキュリティで保護するには、これらの機能を使用することをお勧めします。

|機能|説明|ライセンス|
|---|---|---|
|[多要素認証 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA では、ユーザーのパスワード、Microsoft Authenticator アプリまたは電話からの通知など、2つの形式の認証を提供する必要があります。 MFA は、ユーザーの環境へのアクセスに使用できる資格情報を収集するリスクを大幅に軽減します。 Microsoft 365 は、MFA ベースのサインインに Azure 多要素認証サービスを使用します。|Microsoft 365 E3 または E5|
|[条件付きアクセス](/azure/active-directory/conditional-access/overview)|Azure AD は、ユーザーサインインの条件を評価し、条件付きアクセスポリシーを使用して許可されたアクセスを決定します。 たとえば、このガイダンスでは、機密データへのアクセスにデバイスのコンプライアンスを必要とする条件付きアクセスポリシーを作成する方法を示します。 これにより、自分のデバイスを持つハッカーが機密データにアクセスするリスクが大幅に軽減されます。 また、デバイスは正常性とセキュリティの特定の要件を満たす必要があるため、デバイス上の機密データを保護します。|Microsoft 365 E3 または E5|
|[Azure AD グループ](/azure/active-directory/fundamentals/active-directory-manage-groups)|条件付きアクセスポリシー、Intune を使用したデバイス管理、組織内のファイルおよびサイトへのアクセス許可は、ユーザーアカウントまたは Azure AD グループへの割り当てに依存しています。 実装する保護のレベルに対応する Azure AD グループを作成することをお勧めします。 たとえば、役員スタッフの方が、ハッカーの価値が高いと考えられます。 そのため、これらの従業員のユーザーアカウントを Azure AD グループに追加して、このグループを条件付きアクセスポリシーと、より高いレベルのアクセス保護を適用するその他のポリシーに割り当てることをお勧めします。|Microsoft 365 E3 または E5|
|[デバイスの登録](/azure/active-directory/devices/overview)|デバイスの id を作成するために、デバイスを Azure AD に登録します。 この id は、ユーザーがサインインして、ドメインに参加しているか、準拠している Pc を必要とする条件付きアクセスポリシーを適用するときに、デバイスを認証するために使用されます。 このガイダンスでは、device enrollment を使用して、ドメインに参加している Windows コンピューターを自動的に登録します。 デバイスの登録は、Intune を使用してデバイスを管理するための前提条件です。|Microsoft 365 E3 または E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動修復ポリシーを低、中、高のサインインリスクとユーザーのリスクに構成できます。 このガイダンスは、このリスク評価に基づいて、多要素認証の条件付きアクセスポリシーを適用します。 このガイダンスには、アカウントに対して高リスクのアクティビティが検出された場合にユーザーにパスワードの変更を要求する条件付きアクセスポリシーも含まれています。|Microsoft 365 E5、Microsoft 365 E3 with Identity & Threat Protection アドオン、EMS E5、または Azure Premium P2 ライセンス|
|[セルフサービスによるパスワードのリセット (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|管理者が制御できる複数の認証方法を確認することにより、ユーザーがパスワードを安全に、かつヘルプデスクの介入なしにリセットできるようにします。|Microsoft 365 E3 または E5|
|[Azure AD パスワード保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|既知の脆弱なパスワードとその亜種、および組織に固有のその他の弱い用語を検出およびブロックします。 既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。 カスタムの禁止パスワード リストに追加のエントリを定義できます。 ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。|Microsoft 365 E3 または E5|
|

ここでは、Intune および Azure AD オブジェクト、設定、および subservices を含む、id およびデバイスアクセスのコンポーネントを示します。

![Id とデバイスのアクセスのコンポーネント](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) は、Microsoft のクラウドベースのモバイルデバイス管理サービスです。 このガイダンスでは、Intune を使用して Windows Pc のデバイスを管理することと、デバイスコンプライアンスポリシーの構成を推奨することをお勧めします。 Intune は、デバイスが準拠しているかどうかを判断し、条件付きアクセスポリシーを適用するときに使用するために、このデータを Azure AD に送信します。

#### <a name="intune-app-protection"></a>Intune アプリの保護

[Intune アプリ保護](https://docs.microsoft.com/intune/app-protection-policy) ポリシーを使用して、モバイルアプリで組織のデータを保護できます。または、デバイスを管理者に登録することができます。 Intune では、情報を保護して、従業員の生産性を維持し、データ損失を防ぐことができます。 アプリレベルのポリシーを実装することで、会社のリソースへのアクセスを制限し、データを IT 部門のコントロール内に保持することができます。

このガイダンスは、承認済みアプリの使用を強制するために推奨されるポリシーを作成する方法と、これらのアプリをビジネスデータで使用する方法を決定する方法を示しています。

### <a name="microsoft-365"></a>Microsoft 365

このガイダンスは、microsoft Teams、Exchange Online、SharePoint Online、OneDrive for Business などの Microsoft 365 クラウドサービスへのアクセスを保護する一連のポリシーを実装する方法を示しています。 これらのポリシーを実装するだけでなく、次のリソースを使用してテナントの保護レベルも上げることをお勧めします。

- [セキュリティ強化のためにテナントを構成する](tenant-wide-setup-for-increased-security.md)

  テナントのベースラインセキュリティに適用される推奨事項。

- [セキュリティロードマップ: 最初の30日間、90日以降の優先度](security-roadmap.md)

  ログ、データガバナンス、管理アクセス、および脅威保護を含む推奨事項。

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 および Microsoft 365 Apps for enterprise

Windows 10 for Microsoft 365 enterprise for enterprise は、Pc に推奨されるクライアント環境です。 Azure は、オンプレミスと Azure AD の両方に対して、最もスムーズな環境を提供するように設計されているため、Windows 10 をお勧めします。 Windows 10 には、Intune で管理できる高度なセキュリティ機能も含まれています。 Microsoft 365 enterprise 用アプリには、最新バージョンの Office アプリケーションが含まれています。 これらは先進認証を使用します。これは、より安全で、条件付きアクセスの要件です。 これらのアプリには、強化されたセキュリティおよびコンプライアンスツールも含まれています。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>3つの保護層の間にこれらの機能を適用する

次の表では、3つの保護層でこれらの機能を使用するための推奨事項を要約しています。

|保護メカニズム|基準|機密|厳しく規制|
|---|---|---|---|
|**MFA の強制**|中程度以上のサインイン リスクで|低以上のサインイン リスクで|すべての新しいセッションで|
|**パスワードの変更を強制する**|リスクの高いユーザーの場合|リスクの高いユーザーの場合|リスクの高いユーザーの場合|
|**Intune アプリケーション保護を強制する**|はい|はい|はい|
|**組織が所有するデバイスの Intune 登録を強制する**|PC に準拠しているか、ドメインに参加している必要がありますが、独自のデバイス (BYOD) の電話とタブレットを許可します。|準拠しているまたはドメインに参加しているデバイスを必要とする|準拠しているまたはドメインに参加しているデバイスを必要とする|
|

## <a name="device-ownership"></a>デバイスの所有権

上記の表には、組織が所有するデバイスを混在させるための多くの組織の傾向と、従業員を超えたモバイル生産性を実現するための個人または BYODs の傾向が反映されています。 Intune アプリ保護ポリシーは、組織が所有するデバイスと BYODs の両方で、電子メールが Outlook mobile アプリおよびその他の Office モバイルアプリから exfiltrating から保護されるようにします。

組織所有のデバイスは、追加の保護と制御を適用するために、Intune またはドメインに参加して管理することをお勧めします。 データの機密性に応じて、特定のユーザー人口または特定のアプリに対しては、を使用しないようにすることもできます。

## <a name="deployment-and-your-apps"></a>展開とアプリ

Azure AD 統合アプリの id とデバイスのアクセス構成を構成してロールアウトする前に、次のことを行う必要があります。

- 保護する組織で使用されているアプリを決定します。
- このアプリの一覧を分析して、適切なレベルの保護を提供するポリシーのセットを決定します。

  アプリの管理が煩雑になる可能性があるため、アプリごとに個別のポリシーセットを作成しないでください。 Microsoft では、同じユーザーに対して同じ保護要件を持つアプリをグループ化することをお勧めします。

  たとえば、すべてのユーザーのベースライン保護用のすべての Microsoft 365 アプリと、人事や財務部門で使用されているすべての機密アプリケーションに対する2番目のポリシーセットを含むポリシーセットがあり、それらをそれらのグループに適用することができます。

セキュリティで保護するアプリケーションのポリシーセットを決定したら、そのポリシーをユーザーに段階的にロールアウトして、その問題に対処します。

たとえば、exchange Online 用のすべての Microsoft 365 アプリで使用されるポリシーを構成し、Exchange に追加の変更を加えます。 これらのポリシーをユーザーにロールアウトして、問題を解決します。 その後、追加の変更を加えて Teams を追加し、それをユーザーにロールアウトします。 その後、追加の変更を加えて、SharePoint を追加します。 これらのベースラインポリシーを確実に構成して、すべての Microsoft 365 アプリを含めることができるようになるまで、残りのアプリの追加を続行します。

同様に、機密性の高いアプリについては、ポリシーのセットを作成して、一度に1つのアプリを追加し、すべての問題を処理する必要があります。これらはすべて、機密のアプリケーションポリシーセットに含まれます。

Microsoft では、意図しない構成が発生する可能性があるため、すべてのアプリに適用されるポリシーセットを作成しないことをお勧めします。 たとえば、すべてのアプリをブロックするポリシーにより、Azure portal から管理者をロックアウトし、Microsoft Graph などの重要なエンドポイントに対して除外を構成することはできません。

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Id とデバイスのアクセスを構成するプロセスの手順

![Id とデバイスのアクセスを構成する手順。](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. 前提条件となる id 機能とその設定を構成します。
2. 共通 id を構成し、条件付きアクセスポリシーにアクセスします。
3. ゲストユーザーと外部ユーザーの条件付きアクセスポリシーを構成します。
4. Microsoft Teams、Exchange Online、SharePoint などの Microsoft 365 クラウドアプリの条件付きアクセスポリシーを構成します。

Id とデバイスのアクセスを構成した後は、「 [azure ad 機能展開ガイド](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) 」を参照して、考慮すべき追加機能の段階的チェックリストと、アクセスの保護、監視、および監査を行う [Azure ad identity ガバナンス](https://docs.microsoft.com/azure/active-directory/governance/) に関する説明を参照してください。

## <a name="next-step"></a>次の手順

[Id およびデバイスアクセスポリシーを実装するための前提条件](identity-access-prerequisites.md)
