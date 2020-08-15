---
title: Id とデバイスのアクセス構成-エンタープライズ向け Microsoft 365
description: セキュリティで保護された電子メール、ドキュメント、およびアプリのポリシーと構成を展開するための Microsoft の推奨事項と中心概念について説明します。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
ms.openlocfilehash: f39b5d72de630674ea6d58c30eadf211917de10d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686628"
---
# <a name="identity-and-device-access-configurations"></a>ID とデバイスのアクセス構成

この一連の記事では、条件付きアクセスポリシーと関連機能の規定セットを含む推奨される環境と構成を実装することにより、Enterprise Mobility + Security (EMS) 製品を使用してクラウドサービスへのセキュリティで保護されたアクセスを構成する方法について説明します。 EMS は、Microsoft 365 のコアコンポーネントです。 このガイダンスを使用して、azure Active Directory と統合されたすべてのサービスへのアクセスを保護できます。これには、Microsoft 365 サービス、その他の SaaS サービス、および Azure AD アプリケーションプロキシで公開されたオンプレミスアプリケーションが含まれます。 

これらの推奨事項は、Microsoft セキュリティスコアと [AZURE AD の id スコア](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)に沿っており、組織にとってこれらのスコアが増加します。 これらの推奨事項は [、id インフラストラクチャをセキュリティで保護するための5つの手順を](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)実装するのにも役立ちます。 

Microsoft は、組織によっては独自の環境要件や複雑さがあることを認識しています。 これらの組織のいずれかである場合は、これらの推奨事項を出発点として使用します。 ただし、ほとんどの組織では、これらの推奨事項を定められたとおりに実装できます。 

## <a name="intended-audience"></a>対象ユーザー

これらの推奨事項は、 [Office 365](https://docs.microsoft.com/microsoft-365/admin) と [microsoft Enterprise Mobility + Security](https://microsoft.com/ems)に精通している企業のアーキテクトおよび IT 担当者を対象としています。これには、azure Active Directory (Identity)、microsoft Intune (デバイス管理)、azure Information protection (データ保護) などが含まれます。

### <a name="customer-environment"></a>お客様の環境

推奨されるポリシーは、Microsoft クラウド内で完全に運用しているエンタープライズ組織と、ハイブリッドインフラストラクチャ (オンプレミスと Microsoft クラウドの両方) を使用しているお客様向けに適用されます。

提供されている推奨事項の多くは、Enterprise Mobility + Security (EMS) E5 ライセンスでのみ利用可能なサービスに依存しています。 推奨される推奨事項は、完全な EMS E5 ライセンス機能を前提としています。

Enterprise Mobility + Security E5 ライセンスを持っていない組織では、少なくともすべてのプランに含まれている Azure AD ベースの保護機能を実装することをお勧めします。 詳細については、記事「Azure AD ライブラリの [ベースライン保護](/azure/active-directory/active-directory-conditional-access-baseline-protection)について」を参照してください。

### <a name="caveats"></a>べき

お客様の組織は、これらの推奨される構成から分岐するポリシーを適用する必要がある特定の推奨事項を含む、規制またはその他のコンプライアンス要件の対象となる場合があります。 これらの構成では、これまで利用できなかった使用状況コントロールが推奨されます。 これらのコントロールは、セキュリティと生産性のバランスがあると考えられるため、お勧めします。  

さまざまな組織保護要件に対応できるようにしていますが、すべての要件を考慮することも、組織のすべての特有の要素を考慮することもできません。

## <a name="three-tiers-of-protection"></a>3層の保護

ほとんどの組織は、セキュリティとデータ保護に関して固有の要件を用意しています。 そのような要件は業種によって、また、組織内の職務によって変わります。 たとえば、法務部門や管理者は、他の部署のユーザーには必要のない、電子メールの通信に関してセキュリティと情報保護に関する追加の制御が必要になる場合があります。 

また、あらゆる業種が独自の特別な規制を用意しています。 考えられるすべてのセキュリティオプションの一覧、または各業種セグメントまたはジョブ機能に対する推奨事項の一覧を提供するのではなく、ニーズの粒度に基づいて適用可能な3つのセキュリティと保護の層について推奨事項が提供されています。

- **ベースライン保護**: データを保護するための最小限の標準と、データにアクセスする id およびデバイスを設定することをお勧めします。 これらのベースライン推奨事項に従って、多くの組織のニーズを満たす強力な既定の保護を提供することができます。
- **機密保護**: 一部のお客様は、より高いレベルで保護する必要があるデータのサブセットを持っているか、すべてのデータをより高いレベルで保護する必要がある場合があります。 Microsoft 365 環境のすべてまたは特定のデータセットに対して、強化された保護を適用することができます。 機密データにアクセスする ID とデバイスはそれに相応しいレベルのセキュリティで保護することを推奨します。  
- 厳しく**規制**されている組織の中には、非常に多くのデータがあり、取引の機密を構成したり、規制されたデータが含まれている場合があります。 Microsoft は、ID とデバイスの保護を追加するなど、組織がそのような要件を満たすための機能を提供しています。

![セキュリティコーン-特定のお客様 > 一部のお客様 >。 特定のアプリケーションに対する幅広いアプリケーション](../media/M365-idquality-threetiers.png)

このガイダンスでは、これらの各層の保護の id とデバイスの保護を実装する方法について説明します。 組織の出発点としてこのガイダンスを使用し、組織の特定の要件を満たすようにポリシーを調整します。

データ、ID、デバイス全体で一貫したレベルの保護を使用することが重要です。 たとえば、このガイダンスを実装する場合は、必ず同等のレベルでデータを保護してください。 これらのアーキテクチャモデルは、どの機能が同等であるかを示しています。

**Office 365 の ID とデバイス保護**<br/>
![ポスターのサムネイル「Office の Id とデバイスの保護365」](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)

**Office 365 のファイル保護ソリューション**<br/>
![ポスターのサムネイル「Office のファイル保護ソリューション」 (365)](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>セキュリティと生産性の折り合い

セキュリティ戦略を実装するには、セキュリティと生産性の間にトレードオフが必要です。 各決定が、セキュリティ、機能、および使いやすさのバランスにどのように影響するかを評価するのに役立ちます。

![セキュリティ、機能性、使いやすさのバランスを保つためのセキュリティの障害許容。](../media/policies-configurations/security-triad.png)

提供される推奨事項は、次の原則に基づいています。

- 対象ユーザーを認識し、セキュリティおよび機能要件に柔軟に対応します。
- セキュリティポリシーを時刻だけに適用し、意味のあるものにします。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Id とデバイスのアクセス保護のサービスと概念

Microsoft 365 for enterprise は大規模な組織向けに設計されており、Office 365 Enterprise、Windows 10 Enterprise、Enterprise Mobility + Security (EMS) を統合することにより、すべてのユーザーがクリエイティブに共同作業し、安全に共同作業を行うことができます。

このセクションでは、id とデバイスのアクセスにおいて重要な Microsoft 365 サービスと機能の概要について説明します。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD には、id 管理機能の完全なスイートが用意されています。 アクセスを保護するには、次の機能を使用することをお勧めします。

- **[セルフサービスによるパスワードのリセット (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: 管理者が制御できる複数の認証方法を確認することにより、ユーザーがパスワードを安全に再設定し、ヘルプデスクの介入を行わないようにします。

- **[多要素認証 (mfa)](/azure/active-directory/authentication/concept-mfa-howitworks)**: mfa では、ユーザーパスワード、Microsoft Authenticator アプリまたは電話からの通知など、2つの形式の認証を提供する必要があります。 MFA は、盗んだ id を使用して環境にアクセスできるリスクを大幅に削減します。

- **[条件付きアクセス](/azure/active-directory/conditional-access/overview)**: Azure AD は、ユーザーログインの条件を評価し、アクセスを許可するために作成した条件付きアクセスポリシーを使用します。 たとえば、このガイダンスでは、機密データへのアクセスにデバイスのコンプライアンスを必要とする条件付きアクセスポリシーを作成する方法を示します。 これにより、id が盗まれたハッカーが機密データにアクセスできるリスクが大幅に軽減されます。 また、デバイスは正常性とセキュリティの特定の要件を満たしているため、デバイス上の機密データも保護されます。

- **[AZURE ad グループ](/azure/active-directory/fundamentals/active-directory-manage-groups)**: 条件付きアクセスルール、Intune を使用したデバイス管理、および組織内のファイルおよびサイトへのアクセス許可については、ユーザーまたは Azure AD グループへの割り当てを利用します。 実装する保護のレベルに対応する Azure AD グループを作成することをお勧めします。 たとえば、役員スタッフの方が、ハッカーの価値が高いと考えられます。 そのため、これらの従業員を Azure AD グループに割り当て、より高いレベルのアクセスを適用する条件付きアクセスポリシーとその他のポリシーにこのグループを割り当てることをお勧めします。

- **[デバイスの登録](/azure/active-directory/devices/overview)**: デバイスに id を提供するために、デバイスを Azure AD に登録します。 この id は、ユーザーがサインインして、ドメインに参加しているか、準拠している Pc を必要とする条件付きアクセスルールを適用するときに、デバイスを認証するために使用されます。 このガイダンスでは、device registration を使用して、ドメインに参加している Windows コンピューターを自動的に登録します。 デバイス登録は、Intune を使用してデバイスを管理するための前提条件です。 

- **[AZURE Ad Identity protection](/azure/active-directory/identity-protection/overview)**: Azure Ad id 保護を使用すると、組織の id に影響を及ぼす可能性のある脆弱性を検出し、自動修復ポリシーを低、中、高のサインインリスクとユーザーのリスクに構成することができます。 このガイダンスは、このリスク評価に基づいて、多要素認証の条件付きアクセスポリシーを適用します。 このガイダンスには、アカウントに対して高リスクのアクティビティが検出された場合にユーザーにパスワードの変更を要求する条件付きアクセスポリシーも含まれています。

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) は、Microsoft のクラウドベースのモバイルデバイス管理サービスです。 このガイダンスでは、Intune を使用して Windows Pc のデバイスを管理することと、デバイスコンプライアンスポリシーの構成を推奨することをお勧めします。 Intune は、デバイスが準拠しているかどうかを判断し、条件付きアクセスポリシーを適用するときに使用するために、このデータを Azure AD に送信します。

#### <a name="intune-app-protection"></a>Intune アプリの保護

[Intune アプリ保護](https://docs.microsoft.com/intune/app-protection-policy) ポリシーを使用して、モバイルアプリで組織のデータを保護できます。または、デバイスを管理者に登録することができます。 Intune では、情報を保護して、従業員の生産性を維持し、データ損失を防ぐことができます。 アプリレベルのポリシーを実装することで、会社のリソースへのアクセスを制限し、データを IT 部門のコントロール内に保持することができます。

このガイダンスは、承認済みアプリの使用を強制するために推奨されるポリシーを作成する方法と、これらのアプリをビジネスデータで使用する方法を決定する方法を示しています。

### <a name="microsoft-365"></a>Microsoft 365

このガイダンスでは、Exchange Online、SharePoint Online、OneDrive for business などの Office 365 へのアクセスを保護する一連のポリシーを実装する方法について説明します。 これらのポリシーを実装するだけでなく、次のリソースを使用してテナントの保護レベルも上げることをお勧めします。

- [セキュリティ強化のためにテナントを構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/tenant-wide-setup-for-increased-security)します。これらの推奨事項は、テナントのベースラインセキュリティに適用されます。
- [Microsoft 365 セキュリティロードマップ: 最初の30日間、90日以降の優先順位](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap): これらの推奨事項には、ログ、データガバナンス、管理アクセス、および脅威保護があります。


### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 および Microsoft 365 Apps for enterprise

Pc に推奨されるクライアント環境として、Windows 10 と Microsoft 365 の enterprise 用アプリがあります。 Azure は、オンプレミスと Azure AD の両方に対して、最もスムーズな環境を提供するように設計されているため、Windows 10 をお勧めします。 Windows 10 には、Intune で管理できる高度なセキュリティ機能も含まれています。 Microsoft 365 enterprise 用アプリには、最新バージョンの Office アプリケーションが含まれています。 これらは先進認証を使用します。これは、より安全で、条件付きアクセスの要件です。 これらのアプリには、強化されたセキュリティおよびコンプライアンスツールも含まれています。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>3つの保護層の間にこれらの機能を適用する

次の表では、3つの保護層でこれらの機能を使用するための推奨事項を要約しています。

|保護メカニズム|基準|機密|厳しく規制|
|:-------------------|:-------|:--------|:---------------|
|**MFA の強制**|中程度以上のサインイン リスクで|低以上のサインイン リスクで|すべての新しいセッションで|
|**パスワードの変更を強制する**|リスクの高いユーザーの場合|リスクの高いユーザーの場合|リスクの高いユーザーの場合|
|**Intune アプリケーション保護を強制する**|はい|はい|はい|
|**Intune 登録の強制 (COD)**|PC に準拠しているか、ドメインに参加している必要がありますが、OD 電話/タブレットを許可する|準拠しているまたはドメインに参加しているデバイスを必要とする|準拠しているまたはドメインに参加しているデバイスを必要とする|

## <a name="device-ownership"></a>デバイスの所有権

上記の表には、企業が所有するデバイスを混在させてサポートするための多くの組織の傾向と、個人または社内のデバイス (BYODs) をサポートしています。これにより、従業員全体にわたるモバイルの生産性が向上します。 Intune アプリ保護ポリシーでは、企業所有のデバイスと BYODs の両方で、電子メールが Outlook mobile アプリおよびその他の Office モバイルアプリから exfiltrating から保護されていることを確認します。  

企業所有のデバイスを Intune またはドメインに参加させて管理し、追加の保護と制御を適用することをお勧めします。 データの機密性に応じて、特定のユーザー人口または特定のアプリに対しては、を使用しないようにすることもできます。

## <a name="next-steps"></a>次の手順

[Id およびデバイスアクセスポリシーを実装するための前提条件](identity-access-prerequisites.md)
